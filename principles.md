# Principles

A list of principles I hold when programming/working with my team. It's rather opinionated, but I firmly believe it.

## If you want to move fast, walk alone. If you want to move far, walk together.

Also, you need to want to walk the same path. If our destination differs, split.

## Iterate, don't conclude

Sometimes when we work on a feature, we just build and forget. A working feature is not necessarily a successful feature. Always look for improvements, or pass it down to someone to improve it.

## Do it right, do it once

- Don't look for **temporary solutions**, design your system the correct way. If you design a temporary working solution and you did not look back into it, you are gonna create a new legacy. If you do not know the correct way, spend some time researching/asking others.
- When reviewing, be honest. Reviewers should not hesitate to comment/criticize. Also, codes should be reviewed by a minimum of two reviewers. Letting code reviews pass for the sake of passing will add technical debts to your organization.


## Correctness over simplicity

Keep your codes simple - this is hard for most people as most of us will overengineer our solutions. But prefer correctness over simplicity. It's sometimes necessary to add the complexity (like breaking your functions to smaller pieces) to ensure your system is scalable/maintainable with the proper separation of concern.

## Get feedback fast

Don't design the final solution without getting feedback. Build a solution, mock your dependencies and ask for opinions. Most of the time when working in a team, some people like to work solo - and end up creating something only they understand. Identify this people, and encourage them to discuss. You can avoid a lot of refactoring/rewrites when doing code review.


## Don't push proto-production

Working on new technologies and would like to try it out in production? Not untill you write 10 similar development prototype. Pushing new technology for the sake of pushing it will only add debts.

## What's more important than deploying is knowing how to destroy it

It's easy to push stuff to production, bringing them down without breaking other dependencies is hard. Always plan on how to bring down the things you want to deploy.

Done working on a feature and ready for production? Don't go there straight away. Take 30 minutes of your team's time, and start battle-testing your system. Try all weird inputs, try to break your system. Once you are confident, release it.

## Learn as much as you can

When time is scarce, learn what you need. When time is abundant, learn as much as you can. Do not worry about not _specializing_ in one field - it is an anti-pattern too, since specializing in only one thing narrows your thinking. A lot of skills are interchangable across domains. So, keep building t-shape skills.

## Know what you do not know

It is important not just to know about this, but also to do something about it. If you are lacking in some areas, always seek to improve and not necessarily by yourself - you can get help from others.


## Good decisions come from experience, and experience comes from bad decisions

## Pushing new technology is simple

__ (Replace this with the technology in mind) __ is not our core business, we should delegate it so that we can prioritize on what is important for us.
