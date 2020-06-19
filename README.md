# Project Tips

## Contents <!-- omit in toc -->

- [Overall Work Structure](#Overall-Work-Structure)
- [Alignment Game](#Alignment-Game)
- [Screen and Routes](#Screen-and-Routes)
- [Wireframes, etc](#Wireframes-etc)
- [Designing Database Schema](#Designing-Database-Schema)
- [What To Do When Stuck](#What-To-Do-When-Stuck)
- [Choosing Libraries / Modules](#Choosing-Libraries--Modules)

## Overall Work Structure

1. Start with a group brainstorming and design session. Do not touch any code. NO CODE ZONE. 🚨🚨🚨
1. Organize the work based on features.
1. Sequence the work based on which features are *most necessary* for the MVP.

   Imagine it's the day before presentations and you only have 50% of the features ready to go. Structure your work so you can triage while minimizing the impact on the MVP. THIS WILL HAPPEN. IT HAPPENS TO EVERYONE, NOT JUST STUDENTS.
1. Sync regularly to revise the plan. At least once per day is *required*, we strongly recommend once in the morning and once in the late mid-day (9AM and 3PM, say).
1. When starting a feature, first...
   - Make wireframes of all the relevant screens a user sees
   - If you're using a back-end, design a database schema
   - If you're using an interactive front-end, outline the main pieces of data, what they look like, and what they represent in your code
1. Every feature involves some combination of changes to the screens a user sees, the way the underlying information is organized + stored, and how those two interact with each other.
1. Don't **overplan**. Plans change. Spending 1 day coming up with a super-detailed plan around something that's likely to change before the end of the week is a bad use of time. The detail in your plans should be proportional to the likelihood that they will change.

For example, before starting a feature I'd...

- [ ] Make a list of all the *screens* involved in a feature
- [ ] Make a diagram of how a user moves from one screen to another and under what circumstance (the site "flow")
- [ ] For each screen, make multiple wireframes using pen+paper, Balsamiq, etc. Keep these in source control (git).
- [ ] If in a group, play the [alignment game](#Alignment-Game) to improve quality and reduce chance of misalignment.

## Alignment Game

Use the following alignment trick regularly:

- Get together as a group to talk about X, where X is "design a feature", "make a
- Put aside 3-5 minutes where everyone describes their idea of X (via picture, words, anything) but *on their own*
- After 3-5 minutes, everyone shares their individual pictures/descriptions

Any serious misalignment will be much clearer and you'll get a broader range of better, more interesting ideas. It's good for brainstorming, designing, or even just verifying everyone is on the same page about something.

**At a minimum**, you should do the above once for every major feature where you all spend ~5 minutes independently creating wireframes and then coming together to compare.

You can do the same with a database schema design, though. Or ideas for the presentation. Or...

<!--
## Screen and Routes

Someone using a website sees a series of screens, each at a different URL. For example, a user might:

1. Visit the homepage. They click the login button and then...
1. See the login page. They fill in the information and log in, then...
1. See their profile page, feed, etc. depending on the functionality of the site

The user sees **three** screens here, but there are **four** routes at work:

1. `GET /` - Visit homepage
1. `GET /login` — Visit login page
1. `POST /login` — Process login form submission
1. `GET /profile` — See their profile (or whatever page they redirect to after logging in, it could be `GET /` again)

The user thinks in screens, while the developer tends to think more in routes. It's important to think in both depending on the situation.
-->

## Wireframes, etc

Wireframes aren't a contract, they're a communication tool. They're the visual equivalent of putting your thoughts into words. Once they're outside yourself they're easier for you to refine and get feedback on.

They help you and your team get and stay on the same page more quickly. This allows people to work independently without deviating too far from the intended work.

Your final design can differ significantly from your wireframes.

<!--
## Designing Database Schema

This only applies if you're using a back-end. Use a tool like [DBDesigner](https://www.dbdesigner.net/) to design your database schema. All tiers are free for Davidson students if you sign up for an academic account. Here's an example: <https://dbdesigner.page.link/HuDLQ6FRjjd1qfgr6>.
-->

## What To Do When Stuck

> The most effective debugging tool is still careful thought, coupled with judiciously placed print statements.
>
> — [Brian Kernighan][wiki-kernighan], "Unix for Beginners" (1979)

First, under **no** circumstances ask the following unless you're at a genuine loss: "I'm getting X error, what is broken?" Nobody is psychic. They're just going to ask you to undertake the same process and you might as well undertake it yourself.

1. Understand the error message
1. Understand what a stack trace is telling you
1. If your program is crashing there is some line of code in your program that is either throwing an error itself or calls code that throws the error. The stack trace tells you where this is
1. Google the error message
1. Pay attention to the dates of everything you're reading. A 5-year-old answer or solution might

If your program isn't working as expect then it means something, somewhere in your code isn't doing what you expect or doesn't have the value you expect. That means...

- Using the scientific method to isolate the part of the code
- Use `console.log` to verify things are what you expect
- Double-check that your HTML/CSS are valid using the [W3's HTML Validator][url-validator]
- Use your browser's Inspector + Developer Console to get visibility into how the browser is rendering the page (and why it looks different from what you expect).


## Save Time Before Asking For Help

If you come to a teacher for help, they are going to point at every variable/value in the relevant section of code and ask you to `console.log` it. Do that preemptively so you don't get blocked waiting for help!

Are you _sure_ it's not a typo? Believing it's not a typo isn't enough. Being 99% confident it's not a typo isn't enough. Your brain fills in gaps and convinces you it didn't. You should...

- Isolate the parts that aren't working as you expect (scientific method) and compare to a known-working example
- Place a known-working snippet of code right next to the not-working snippet of code so that typos are more obvious. For example, if you think two lines of code are identical, put them on two separate lines in a new file. You'll see right away if their length is different, which tells you they're not the same.

## Choosing Libraries / Modules

No matter what module you choose, you're going to get stuck at some point. The module can't do what you want or if it can, you don't know how to make it do what you want.

You need to pick modules that are actively maintained and have a large [mind share][wiki-mind-share]. The more people using a module the more likely people are asking/answering questions about it, the more likely people have invested in good documentation/tutorials, the more likely that someone you ask for help will know about it, etc.

For modules on `npm`, always look up:

1. How long ago was the last version published?
1. How many people are downloading the module each week?

A module that hasn't been updated in over a year and has few weekly downloads is probably abandoned. A very stable module not got get updated regularly, but it should have many, many downloads.

For example, [Express][npm-express] hasn't been updated in over a year but it has ~13 million weekly downloads. This is because Express is intended to be minimal, stable, and extensible.

READ THE MENU BEFORE ORDERING.

[wiki-kernighan]: https://en.wikipedia.org/wiki/Brian_Kernighan
[wiki-mind-share]: https://en.wikipedia.org/wiki/Mind_share
[npm-express]: https://www.npmjs.com/package/express
[url-validator]: https://validator.w3.org/
