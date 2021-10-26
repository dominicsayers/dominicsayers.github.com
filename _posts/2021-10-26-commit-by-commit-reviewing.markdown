---
layout: post
title: Code reviews commit-by-commit
date: 2021-10-26 08:00:00 +0100
image: diff_comment.jpg
thumbnail: diff_comment.jpg
tags:
  - featured
---
Here's how I approach a code review for a merge request (or pull request if you're using GitHub). It's a general approach, not language-specific. I'd really like to improve my process so if you have any thoughts or tips please let me know.

This is a rough draft and needs tightening up and refactoring. I hope it makes some sort of sense as it is.

## Bibliography

On reviewing:

- [Guidelines on code review](https://github.com/thoughtbot/guides/tree/main/code-review) - Thoughtbot
- [Derek Prior video](https://www.youtube.com/watch?v=PJjmw9TRB7s) - worth 30 mins of your time

We're looking for merge requests that use git sensibly to present a change in a way that helps us understand it. I've found these articles helpful to know what good looks like in this respect:

- [Telling stories through your commits](https://blog.mocoso.co.uk/talks/2015/01/12/telling-stories-through-your-commits/) - Joel Chippindale
- [A Note About Git Commit Messages](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html) - Tim Pope
- [My favourite Git commit](https://dhwthompson.com/2019/my-favourite-git-commit) - Dave Thompson
- [A Branch in Time (a story about revision histories)](https://tekin.co.uk/2019/02/a-talk-about-revision-histories) - Tekin Suleyman

## Not included

I'm assuming the build process includes

- automated checks for code quality
- running the test suite
- checking for known security issues like vulnerabilities in 3rd party components

If not then you should put these in place. It's not a good use of human time to do these things manually.

## Getting started

### 1. Read the merge request overview

- Do you understand the overall change that is being made, and the approach taken?
- Why was the change necessary?

### 2. Review each commit individually (see below for how I do this)

- Click the Commits tab, then ⌘-click each commit description.
- This will open a new browser tab for each commit (which I find useful).
- Review the commit in isolation.
- If you're 💯 sure the commit is fine, close the tab.

### 4. Go back and re-review any commits you didn't fully understand on the first pass

- Maybe now you've been through the whole code change they might make more sense.

### 5. Add any final comments and questions on the code

- Click _Submit review_ in any of the open tabs and add your summary thoughts

## Reviewing a commit

### 1. Read the commit message

- Do you understand the change that is being made?
- Do you understand the reason for the change and the approach taken?

### 2. Ask yourself these questions

- Has the submitter taken steps to make the review process easy for you?
- Is the commit the embodiment of a single intention?
- Is it comprised of the minimum code change necessary to implement that intention?
- If the submitter is making you work harder than you need to then say so. Cognitive overhead is a big drain on team time.

### 3. Are there any code changes in the commit that are not necessary for what is described in the commit message?

- Maybe they should be in a separate commit (e.g. whitespace changes, code reformatting, etc.)

### 4. Would the specs pass after this commit?

- This is not a hard-and-fast rule, but ideally each commit would take a step forward without breaking any specs.
- Any necessary spec changes should be in that same commit.

### 5. If you don't fully understand the change then it's useful to ask a question in the merge request

- Others will certainly have the same question so ask it where everybody can see it.
- If you think it's a naïve question that's OK - stupid questions should be encouraged in your team. If they aren't then you're working in a poisonous environment and you should get out!

### 6. Answers to questions should go in a commit message

- The submitter will be tempted to answer your question in the merge request web page because that's easier
- Make sure any useful information is added to the commit message then it's in the git log for posterity.
- The merge request is ephemeral, the git log is permanent.
- Others in the future will undoubtedly have the same question.

### 7. For legacy codebases, consider this

- You may have a list of known exceptions to the static code quality checks because the legacy code is rubbish
- For example, in Ruby using Rubocop this would be in `.rubocop_todo.yml`
- Check that none of these exceptions have been fixed by this merge request, otherwise your legacy list will get out of date and be utterly useless.

### 8. Credit where it's due

- If you see something doubleplusgood, say so.

## Should I approve the merge request?

Yes, unless there is a reason not to.
