# Purpose
This document is a draft and collaboration on how to incorporate code review and GitHub into our development process.

# Overview of the process
An idealized process would look something like this:

1. Requester makes a request
2. Management reviews the request, gathers additional data, and assigns a priority
3. Manager and programmer review the request and break it out into cards
4. When work is to begin programmers are assigned and discuss the issue to come up with an approach on both the backend and frontend.
5. Programmers create individual branches and develop their change set.
6. Push branch and open a pull request.  Pull request should contain:
    * A summary of what is being done
    * A reference to any related cards
    * Any deployment notes (such as MySQL commands that'll need to be ran)
7. Add link to pull request to the related card(s).
8. Another programmer, one familiar with the issue is preferred, does a code review.
    * Revisions are made to the pull request until the programmers are satisfied with the change set.
    * After revisions are made and it needs to be reviewed again make sure to leave a comment to let reviewers know that there are changes.
9. Once code review is completed the change set is deployed to a test environment for programmer QA.
10. Once programmer QA is completed the requester is notified to perform user acceptance testing (UAT)
11. Once UAT is completed the pull request is merged and deployed.
12. Delete the branches after they've been merged.

# What to look for in a code review
When doing a code review look for the following:
* Syntax errors
* Logic errors
* Code formatting and style
* Overall structure
* Maintainability
* Anything that makes you go "what the hell?"
* Ability to follow the code and logic
* Algorithm inefficiency (e.g. using bubble sort)
* Dangerous code (e.g. using eval)
* Security concerns

When doing a code review be nit-picky, ask questions, make suggestions, and check your ego (hard for some of us).

# User acceptance testing not user QA
Since we can't rely on the requester to perform an adequate QA we'll need to start bring it into the development process beginning with automating testing and code review.  For users we should be seeking an acceptance testing which is what most are performing anyways.  In this it is mainly just the user testing it in a few normal business cases and making sure it performs how they wanted.

# Tracking pull request state
Tracking the state of a pull request can be done by either adding comments to the PR and/or by using labels.

Example comments:
* @soandso please review
* looks good (review completed)
* QA done, sending to soandso for UAT
* UAT completed
* Deployed (with details)

A slightly more formal process uses issue labels on PRs in addition to comments.  Some possible labels (used as states) we could use:
* (No label): In development before code review
* Code review: Needs a code review
* Development: After a code review if additional changes are needed
* QA: Code review completed and in QA
* UAT: QA completed and pending UAT
* Ready for release: UAT completed
* Released

Additional labels that aren't state based:
* Hold: Something is going on and we don't want to go any further with this PR until it is resolved.  It would be something as simple as the PR depending on another PR before it can be merged or it could be that we might cancel the project.

# Use small change sets
Code reviews work best with small change sets where you can easily keep the changes in your head and understand the changes as a whole.  Large change sets are doable just annoying and are often delayed.

# Large projects (or change sets)
For a large project you can make use of an integration branch to house the sum of the changes.  You then make smaller feature branches off of the integration branch and use PRs back to the integration branch.  Once all the features are completed then you can merge the integration branch into master.

# Hmmm..
