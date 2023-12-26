---
smip: 'XXXX'
title: Title of SMIP
authors:
  - (fill in with names of authors)
category: Standard/Meta
type: Core/Networking/Interface/Meta
status: Draft
created: (fill in with today's date, YYYY-MM-DD)
feature: (fill in with feature tracking issues once accepted)
supersedes: (optional - fill this in if the SMIP supersedes a previous SMIP)
extends: (optional - fill this in if the SMIP extends the design of a previous SMIP)
---

<!--
  READ SMIP-1 (https://github.com/smfoundation/smips/blob/main/proposals/smip-0001.md) BEFORE USING THIS TEMPLATE!

  This is the suggested template for new SMIPs. After you have filled in the requisite fields, please delete these comments.

  Note that a SMIP number will be assigned by an editor. When opening a pull request to submit your SMIP, please use an abbreviated title in the filename, `smip-draft_title_abbrev.md`.

  The title should be 44 characters or less. It should not repeat the SMIP number in title, irrespective of the category.

  TODO: Remove this comment before submitting
-->

## Abstract

A brief summary of the proposed feature or change.

## Scope

The scope lists components of the technical stack, processes, or designs that will be impacted by the proposed change. It should include all significant dependencies and interactions upon other components and processes. How will the implemented proposal impact dapp developers, miners, core contributors and other stakeholders?

## Stakeholders and Reviewers *(Optional)*

This section is optional.

Optionally specify individuals, organizations, or authors/maintainers of other technical components that should be involved in the review process of the proposal.

## Motivation *(Optional)*

This section is optional.

The motivation section should include a description of any nontrivial problems the proposal solves. It should not describe how the SMIP solves those problems, unless it is not immediately obvious. It should not describe why the SMIP should be made into a standard, unless it is not immediately obvious.

## Alternatives Considered *(Optional)*

This section is optional.

What alternative designs were considered and what pros/cons does this feature
have relative to them?

## New Terminology *(Optional)*

This section is optional.

Is there any new terminology introduced with this proposal?

## Specification

The Specification section should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Spacemesh platforms.

It is recommended to follow RFC 2119 and RFC 8170. Do not remove the keyword definitions if RFC 2119 and RFC 8170 are followed.

Explain the feature as if it was already implemented and you're explaining it to another Spacemesh core contributor. The generally means:

- Explain the proposed change and how it works
- Where the feature fits in to the runtime, core, or relevant sub-system
- How this feature was/could be implemented
- Interaction with other features
- Edge cases

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in [RFC
2119](https://www.ietf.org/rfc/rfc2119.txt) and [RFC
8174](https://www.ietf.org/rfc/rfc8174.txt).

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

Discuss potential performance implications/considerations relevant to the proposed change

## Security Considerations

What security implications/considerations come with implementing this feature?
Are there any implementation-specific guidance or pitfalls?

All SMIPs must contain a section that discusses the security implications/considerations relevant to the proposed change. Include information that might be important for security discussions, surfaces risks and can be used throughout the lifecycle of the proposal. For example, include security-relevant design decisions, concerns, important discussions, implementation-specific guidance and pitfalls, an outline of threats and risks and how they are being addressed. SMIP submissions missing the "Security Considerations" section will be rejected.

## Drawbacks *(Optional)*

What are some reasons we might not want to do this?

## Copyright

Copyright and related rights waived via [CC0](../LICENSE.md).
