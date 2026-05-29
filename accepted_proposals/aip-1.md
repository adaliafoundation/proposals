# Adalia Improvement Proposal #2

## Introduction

We propose using github and the adaliafoundation/proposals repository as the place of record for DAO related proposals and decisions.

## Details

A proposal is only considered valid if it has successfully been voted on using the current voting mechanism (snapshot) and merged into the main branch.

Discussions should begin over chat and when a concrete proposal has matured, it is opened as a pull request (PR) against this repo.

Comments on the PR are welcome, and when discussions have subsided the proposal is voted on. Once the vote has been finalized:
 - If rejected by vote, the PR is closed or significantly modified.
 - IF accepted by vote, a link to the vote result page is added, and a sequence number is /added to the AIP's header. Then it can be merged into main.

Once a proposal is linked to a vote and merged it is considered decided and part of the rule book.

Proposals should be written in simple text or markdown format. We should try to keep the coding in the respective repos of the game.

Proposals should include a single file as summary of the proposal, but can also include changes to other files (such as updates to previous proposals). These should be mentioned in the main file of the proposal.

To view all proposed changes and make comments, please see the "changed files" section of the github PR page.

We should also try to figure out a few folders to organize proposals by theme. We suggest the following short list of themes (this list is TBD but just as an example):

 - governance (how we vote, tokens, etc)
 - content (new things in the game)
 - outreach (efforts to attract new players)
 - more ideas are welcome.

We advocate keeping this list short, and not using sub-folders for now.

## Additional minutia

Details that are not central to the proposal, particularly numeric values and technical details, can be voted on separately. We should use a TBD placeholder in such cases, with the understanding that a proposal can be accepted generally, and a further vote would be required to pin down the exact value.

As an example: Once a PR is published with a new proposal, the proposer can instigate the beginning of voting, which lasts TBD days until the vote is concluded.

It is evident that we can all agree on the present proposal even if we still have to argue about the exact value of the number of days per vote.

Later, when a separate proposal is submitted for a specific value, that PR would include a replacement of TBD in this file, with the chosen value.

## Formatting rules

At this stage we do not enforce any formatting rules. Please keep it short and simple.

## Advantages

This proposal has several advantages:
 - Github is stable and can provide a place of record for many years to come.
 - It is free, and allows anyone to post comments.
 - It encourages building proposals using incremental changes and modifying old proposals when the need arises, and as built-in tools to monitor the changes and updates by all users.
 - Using git allows tracing history (and blame!) and reverting unwanted changes if needed.

## Disadvantages

There can be disadvantages to using this method:
 - It requires players to open github accounts in order to comment or open pull requests.
 - Opening PRs is not trivial for non-coders.

 Since we are naturally going to have some coders around, please feel free to send a proposal file to any of us to upload it for you.



