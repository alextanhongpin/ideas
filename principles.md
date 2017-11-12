# Principles

A list of principles I hold when programming/working with my team. It's rather opinionated, but I firmly believe it.

## Iterate, don't conclude

Sometimes when we work on a feature, we just build and forget. A working feature is not necessarily a successful feature. Always look for improvements,
or pass it down to someone to carry it.

## Do it right, do it once

Don't look for *temporary solutions*, design your system the correct way. If you design a temporary working solution and you did not look back into it, you are gonna create a new legacy.

## Correctness over simplicity

Keep your codes simple - this is hard for most people as most of us will overengineer our solutions. But prefer correctness over simplicity. It's sometimes necessary to add the complexity (like breaking your functions to smaller pieces) to ensure your system is scalable/maintainable with the proper separation of concern.

## Get feedback fast

Don't design the final solution without getting feedback. Build a solution, mock your dependencies and ask for opinions. Most of the time when working in a team, some people like to work solo - and end up creating something only they understand. Identify this people, and encourage them to discuss. You can avoid a lot of refactoring/rewrites when doing code review.

## Do it right, do it once

When reviewing, be honest. Reviewers should not hesitate to comment/criticize. Also, codes should be reviewed by a minimum of two reviewers. Letting code reviews pass for the sake of passing will add technical debts to your organization.
