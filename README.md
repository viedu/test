test
====

Test repo for playing with and learning how to use GitHub


# Instructions

1. Sign up for a GitHub account
  * If you already have a GitHub account you can reuse it.  Just add your VIE email address and set it to receive notifications from this organization.
2. Let @mikemill or @bholladay know your user name via VIE email or chat.  We'll then invite you to the organization.  You'll have to accept the invite before being added to the organization.
3. Read [this page on generating and adding your SSH key to GitHub](https://help.github.com/articles/generating-ssh-keys)
4. Clone this repository: `git clone git@github.com:viedu/test.git`
  * *Note:* If you are using the OSX client you may need to use the https version of the repo: `https://github.com/viedu/test.git`
5. Create branches, make some changes, create pull requests, comment on PRs, merge PRs, etc etc etc.  Get to know the interface and flow.
6. Haha I'm making a conflict.

# Commit statuses

GitHub has an API for modifying the status of commits.  I will be writing a dumb bot shortly to look for commits and update the status so you can see how it affects pull requests.  It will be parsing the commit message looking for one of the following key words (case sensative):
* PENDING
* SUCCESS
* ERROR
* FAILURE

Commits will be set to the corresponding state..  The bot will run every few minutes and look for new heads (latest commit) in the open PRs.  This starts to model the behavior we'd see with a system like Jenkins.
