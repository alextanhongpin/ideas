# Principles

A list of principles I hold when programming/working with my team. It's rather opinionated, but I firmly believe it.

## If you want to move fast, walk alone. If you want to move far, walk together.

Success is a journey that you have to carry others on. Period. 

Make sure you walk that path with the people you trust.

## Iterate, don't conclude

Sometimes when we work on a feature, we just build and forget. A working feature is not necessarily a successful feature. Always look for improvements, or pass it down to someone to improve it.

## Do it right, do it once

- Don't look for **temporary solutions**, design your system the correct way. If you design a temporary working solution and you did not look back into it, you are gonna create a new legacy. If you do not know the correct way, spend some time researching/asking others.
- When reviewing, be honest. Reviewers should not hesitate to comment/criticize. Also, codes should be reviewed by a minimum of two reviewers. Letting code reviews pass for the sake of passing will add technical debts to your organization.
- Most of the time, we will have idea on what is the right thing to do - but often there are times that test our decision - are you gonna stick to the right thing, or are you just gonna let it slip for once?

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

## Say no to invisible work

Invisible work is works that gets done that no one knows is happening or happens in the background.


## Cargo Cult

A.k.a copy-paste programming. A style of software development where you ignore how a piece of code works and its relationship with the code around it.


## Deciding on Technology Stack

It's not about using the latest technology - it's about using what makes sense. In order to achieve that, you need to develop a good intuition on what technology will stand the test of time. Take for example, blockchain. During the time it was release, do you have the correct intuition on where it will be in the next 5 years?

## Business before Technology

It's important not to value technology and abandon business. There has to be a sweet spot of focus for both, since they should co-exist together. Value tech and business (and people too).

## Full Stack Myth

A lot of people call themselves a full stack developer - overestimating their capabilities. I prefer the title `developer` - it's plain and humble. If I ask someone how many bugs they have created and how they value themselves after that, most of them would be embarrased to admit they are a full stack anymore. People make mistakes. Stay humble.

## Cheesy Developer Lines

- may the source be with you
- the code must go on
- change must come from within

## Problem Exist Between Chair and Keyboard
https://en.wiktionary.org/wiki/PEBCAK


## Read a book a day

Try not to juggle between many books at the same time. Currently juggling 8 books at a time. Reduce it to 3 books (treat them as follow up), but finish one book at a time.

## Pareto Principle

[Pareto's principle](https://en.wikipedia.org/wiki/Pareto_principle) can be applied in many different areas - even when designing your own principle! You do not need to be overly attached to a principle, you can always set some budget. Say, for every 10 times you promise yourself not to do something, you can do it twice. 

## Dilbert Principle
https://en.wikipedia.org/wiki/Dilbert_principle


## Don't rewrite

If you have to spend 2 days rewriting a functional piece of work after 2 months worth of time figuring out why things wouldn't work - work it backwards. Spend 2 days writing something that works and only do the alternative when you have time.

## UI matters, but...

I've seen many companies doing a complete overhaul of the design (a totally new contrasting design from the previous one, rather than making small, measurable changes) and the results, while pretty, are not that praiseworthy from the end-user side. It's better to make small measurable changes to the design.
