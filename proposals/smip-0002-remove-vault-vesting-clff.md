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

TBD

## Rationale

The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages.

## Backwards Compatibility *(Optional)*

Does the feature introduce any breaking changes? All incompatibilities and
consequences should be listed.

## Test Cases *(Optional)*

This section is optional for non-Core SMIPs.

The Test Cases section should include expected input/output pairs, but may include a succinct set of executable tests. It should not include project build files. No new requirements may be be introduced here (meaning an implementation following only the Specification section should pass all tests here.)
If the test suite is too large to reasonably be included inline, then consider adding it as one or more files in `../assets/smip-####/`. External links will not be allowed.

## Reference Implementation *(Optional)*

This section is optional.

The Reference Implementation section should include a minimal implementation that assists in understanding or implementing this specification. It should not include project build files. The reference implementation is not a replacement for the Specification section, and the proposal should still be understandable without it.
If the reference implementation is too large to reasonably be included inline, then consider adding it as one or more files in `../assets/smip-####/`. External links will not be allowed.

## Performance Considerations

There are no known performance considerations.

## Security Considerations

What security implications/considerations come with implementing this feature?
Are there any implementation-specific guidance or pitfalls?

All SMIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the lifecycle of the proposal. For example, include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. SMIP submissions missing the "Security Considerations" section will be rejected.

## Drawbacks *(Optional)*

The best argument against this change is the argument that no aspect of Spacemesh economics should be altered under any circumstances. The author is of the opinion that this change should be made because it is beneficial for the short-term health of the Spacemesh protocol and community and because there is zero impact on long-term economics. Note that the only economic impact of this change is to slow down the increase in the circulating coin supply between years 1-4 and that it does not transfer the ownership of any existing coins or alter any existing account state.

## Copyright

Copyright and related rights waived via [CC0](../LICENSE.md).
