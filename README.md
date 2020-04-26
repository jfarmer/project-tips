# Project Tips

## Contents <!-- omit in toc -->

- [Overall Work Structure](#Overall-Work-Structure)
- [Alignment Game](#Alignment-Game)
- [Screen and Routes](#Screen-and-Routes)
- [Wireframes, etc](#Wireframes-etc)
- [Designing Database Schema](#Designing-Database-Schema)

## Overall Work Structure

1. Start with a group brainstorming and design session. Do not touch any code. NO CODE ZONE. 🚨🚨🚨
1. Organize the work based on features.
1. Sequence the work based on which features are *most necessary* for the MVP.

   Imagine it's the day before presentations and you only have 50% of the features ready to go. Structure your work so you can triage while minimizing the impact on the MVP. THIS WILL HAPPEN. IT HAPPENS TO EVERYONE, NOT JUST STUDENTS.
1. Sync regularly to revise the plan. At least once per day is *required*, we strongly recommend once in the morning and once in the late mid-day (9AM and 3PM, say).
1. When starting a feature, first...
   - Make wireframes of all the relevant screens a user sees
   - Design a database schema
1. Every feature involves some combination of changes to the screens a user sees and to the database (making new components, changing or removing old ones, etc.).
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

## Wireframes, etc

Wireframes aren't a contract, they're a communication tool. They're the visual equivalent of putting your thoughts into words. Once they're outside yourself they're easier for you to refine and get feedback on.

They help you and your team get and stay on the same page more quickly. This allows people to work independently without deviating too far from the intended work.

Your final design can differ significantly from your wireframes.

## Designing Database Schema

Use a tool like [DBDesigner](https://www.dbdesigner.net/) to design your database schema. All tiers are free for Davidson students if you sign up for an academic account. Here's an example: <https://dbdesigner.page.link/HuDLQ6FRjjd1qfgr6>.
