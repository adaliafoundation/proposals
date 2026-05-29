# Adalia Improvement Proposals

This repository is the place of record for Adalia DAO proposals and decisions.

Adalia Improvement Proposals, or AIPs, are used to propose, discuss, vote on, and record changes related to the Adalia DAO, the Influence ecosystem, governance processes, community initiatives, and related project decisions.

## Purpose

The purpose of this repository is to provide a stable, transparent, and long-lived record of DAO decisions.

A proposal is only considered valid and binding once it has:

1. Been successfully voted on using the current DAO voting mechanism.
2. Been linked to the relevant vote result.
3. Been merged into the `main` branch of this repository.

Once those steps are complete, the proposal is considered decided and becomes part of the Adalia rule book.

## Proposal Process

Discussions should usually begin informally in chat or another community discussion venue.

Once an idea has matured into a concrete proposal, it should be opened as a pull request against this repository.

Community members may then review the pull request, leave comments, suggest changes, and discuss the proposal. To view the full set of proposed changes, use the **Changed files** section of the GitHub pull request page.

When discussion has subsided, the proposal may be put to a DAO vote using the current voting mechanism.

After the vote has concluded:

- If the proposal is rejected, the pull request should be closed or significantly modified before being reconsidered.
- If the proposal is accepted, a link to the vote result should be added to the proposal, and the pull request may be merged into `main`.

## AIP Numbering

Going forward, AIP numbers should match the GitHub pull request number.

For example, if a proposal is submitted as pull request `#12`, then the proposal should be titled:

```md
# Adalia Improvement Proposal #12
```

This keeps numbering simple, avoids the need for a separate sequence assignment process, and makes it easy to trace each accepted proposal back to the original pull request discussion.

## Repository Structure

The repository should contain folders for proposals based on their final status:

```txt
accepted_proposals/
rejected_proposals/
```

Accepted proposals should be placed in the `accepted_proposals` folder once they have passed a DAO vote and been merged.

Rejected proposals should be placed in the `rejected_proposals` folder if they are kept for historical reference after failing a DAO vote or being formally withdrawn.

The repository may also include a small number of theme-based folders if useful. Examples of possible themes include:

- `governance` — voting rules, DAO processes, tokens, and related governance matters.
- `content` — new game content, mechanics, or ecosystem additions.
- `outreach` — initiatives to attract, retain, or support players.

The list of themes should remain short. Subfolders should be avoided unless there is a clear need for them.

## Proposal Format

Proposals should be written in plain text or Markdown.

Each proposal should include a single main file that summarizes the proposal. A proposal may also include changes to other files, such as updates to previous proposals, but those changes should be mentioned in the main proposal file.

Code changes should generally be kept in the relevant game or application repositories rather than in this proposal repository.

At this stage, there are no strict formatting requirements. Proposals should be kept short, clear, and simple.

## Handling Undecided Details

Some details may not be central to a proposal, especially numeric values or technical parameters.

When a proposal can be accepted in principle without finalizing every detail, the proposal may use a `TBD` placeholder. In those cases, the proposal should make clear that a later vote or proposal will be required to decide the exact value.

For example, a proposal may establish that voting should last for a fixed number of days while leaving the exact number as `TBD`.

A later proposal can then replace the `TBD` value with a specific value approved by vote.

## Advantages of This Process

Using GitHub as the place of record has several advantages:

- GitHub is stable and can serve as a long-term public record.
- It is free to use.
- It allows community members to comment on proposals.
- It supports incremental changes to proposals.
- It provides built-in tools for reviewing, discussing, and tracking changes.
- Git history makes it possible to trace decisions, review past changes, assign responsibility, and revert unwanted changes if necessary.

## Disadvantages of This Process

This process also has some disadvantages:

- Community members need GitHub accounts to comment on proposals or open pull requests.
- Opening pull requests may be difficult for non-coders or people unfamiliar with GitHub.

Community members who are not comfortable using GitHub may ask others to upload proposal files on their behalf.

## Status of This Repository

This repository is intended to be the canonical record of DAO proposal history.

A proposal is not final merely because it appears in a pull request. It becomes final only after it has passed a DAO vote, includes a link to the vote result, and has been merged into `main`.