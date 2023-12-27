---
smip: '0002'
title: Remove Vault Vesting Cliff
authors:
  - Lane Rettig <lane@spacemesh.io>
category: Standard
type: Core
status: Draft
created: 2023-12-26
---

## Abstract

This SMIP removes the 25% vesting cliff one year post-genesis from the coins in the genesis vesting vaults with a slight change to the interpretation of the vault account parameters. After this change, the coins in these vaults vest linearly over a three-year period, from one year post-genesis to four years post-genesis.

## Scope

This proposal requires a slight change to the precompile/genesis VM code in go-spacemesh. One parameter in the economics library (https://github.com/spacemeshos/economics/) will also need to change.

It has no additional impact on and requires no support from dapp developers, miners, etc.

## Stakeholders and Reviewers *(Optional)*

- Spacemesh core contributors (who have already reviewed and approved this proposed change)
- Spacemesh development company investors (who have already reviewed and approved this proposed change)
- all Spacemesh miners, hodlers, and community members (since there is a short-term economic impact years 1-4) are given the chance to review this proposal and comment on it here, in the community Discord, and in the upcoming town hall (details TBA)

## Motivation

See https://spacemesh.io/blog/smoothing-spacemesh-economics/.

## Alternatives Considered

The only alternative considered was not making this change and maintaining the current vesting schedule.

## Specification

The `InitialUnlockAmount` parameter passed to the `Vault` template when a vault account is instantiated (see [this code snippet](https://github.com/spacemeshos/go-spacemesh/blob/eb55894737514b456bbd4af4a41178639a6bda15/genvm/templates/vault/vault.go#L26-L34) must be ignored when calculating the available balance in such an account.

For clarity, the old algorithm was:

`AVAILABLE_BALANCE := INITIAL_UNLOCK_AMOUNT + (TOTAL_AMOUNT - INITIAL_UNLOCK_AMOUNT) * (LAYER - VESTING_START) / (VESTING_END - VESTING_START)`

This proposal changes the algorithm to:

`AVAILABLE_BALANCE := TOTAL_AMOUNT * (LAYER - VESTING_START) / (VESTING_END - VESTING_START)`

## Rationale

This is the simplest possible change to effect the desired result. It doesn't change the state of any existing accounts, and the address of the existing accounts also does not change.

## Backwards Compatibility

This proposal changes the interpretation of the arguments passed to the genesis vault accounts. As long as this change is implemented well before vesting begins (one year post genesis), no special backwards-compatibility handling is required. Additionally, no new genesis vault accounts will ever be created on mainnet, so no backwards-compatibility handling is required for this account type.

If this proposal is implemented, in general, developers need to be aware that the `InitialUnlockAmount` vault argument is ignored and should be ignored in all Spacemesh infrastructure and applications.

This is especially important for developers creating other networks based on the Spacemesh protocol, which in future may contain new genesis vault accounts.

## Test Cases

Included in reference implementation, see https://github.com/spacemeshos/go-spacemesh/compare/develop...smip-0002-remove-vault-vesting-cliff#diff-0bfccdca15d6dbcc197bfb848d43168c815a9d1dfe1dc359bfbafb72101e90f1

## Reference Implementation

See https://github.com/spacemeshos/go-spacemesh/tree/smip-0002-remove-vault-vesting-cliff and https://github.com/spacemeshos/economics/tree/smip-0002-remove-vault-vesting-cliff

## Performance Considerations

There are no known performance considerations.

## Security Considerations

It's essential that all network infrastructure, applications, and stakeholders agree at all times on the actual, vested, accessible balance of every account. If there's disagreement this can lead to a chain split or worse. It's therefore critical that all running Spacemesh nodes and all infrastructure upgrade to support this change well before the first anniversary of genesis (mid July 2024).

Assuming that happens, the only other known potential security consideration is a bug in the implementation such as a rounding error or an integer overflow. Every possible effort has been made to prevent such errors in the provided sample implementations, and every possible effort should be made to prevent such errors through, e.g., a thorough code review process and thorough unit and system tests.

## Drawbacks

The best argument against this change is the argument that no aspect of Spacemesh economics should be altered under any circumstances. The author is of the opinion that this change should be made because it is beneficial for the short-term health of the Spacemesh protocol and community and because there is zero impact on long-term economics. Note that the only economic impact of this change is to slow down the increase in the circulating coin supply between years 1-4 and that it does not transfer the ownership of any existing coins or alter any existing account state.

## Copyright

Copyright and related rights waived via [CC0](../LICENSE.md).
