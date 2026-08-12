---
layout: post
title: "Your Key Engineer Shouldn't Be a Single Point of Failure"
date: 2026-08-12
description: "Engineering teams remove infrastructure single points of failure but often create them around people. See how shared ownership and succession planning build resilience."
excerpt: "Engineering teams remove infrastructure single points of failure but often create them around people. See how shared ownership and succession planning build resilience."
categories: [engineering, sre, leadership]
tags:
  - engineering management
  - key-person dependency
  - bus factor
  - engineering team resilience
  - shared ownership
  - knowledge sharing
  - succession planning
  - internal mobility
  - technical leadership
image: /assets/images/key-engineer-single-point-of-failure-hero.png
---

![Key engineer as a single point of failure in an otherwise redundant production architecture]({{ site.baseurl }}/assets/images/key-engineer-single-point-of-failure-hero.png)

Recently, I watched a key engineer move out of a team.

It wasn't my team, but it made me think about mine.

What if tomorrow one of my key engineers tells me they're leaving?

Not six months from now. Not after we've had enough time to prepare a replacement. Tomorrow.

What stops working?

Which projects suddenly slow down? Which systems become harder to operate? Which architectural decisions can nobody fully explain anymore? Which incidents become much more difficult to handle?

As someone coming from SRE, the irony was hard to miss.

We spend a significant amount of time removing single points of failure from infrastructure.

We replicate databases. We run multiple application instances. We design failover mechanisms. We write disaster recovery plans.

And then we build engineering teams where one person knows how half the critical systems work.

That key engineer has become a human single point of failure.

## The Problem Isn't Having Key Engineers

Every strong engineering team has people who become particularly important.

They accumulate context.

They understand why architectural decisions were made.

They know the ugly edge cases that never made it into documentation.

They have relationships across teams.

And when something breaks, they often know where to look before everyone else does.

That's valuable.

Trying to make engineers completely interchangeable would be unrealistic and undesirable.

The problem starts when expertise becomes dependency.

There is a significant difference between:

> This engineer knows the system better than anyone else.

and:

> This system cannot be safely operated without this engineer.

The first is expertise.

The second is a reliability problem.

This is often described as the team's **bus factor**: how many people could become unavailable before essential work can no longer continue. The phrase is uncomfortable, but the question behind it is useful. A low bus factor exposes key-person dependency and weakens engineering team resilience.

## Shared Ownership Shouldn't Mean Exclusivity

Clear ownership is important.

Someone should feel responsible for moving a project forward, maintaining its quality, understanding its problems, and making sure it doesn't quietly rot.

But ownership shouldn't mean being the only person capable of operating or changing the system.

A healthy project can have one clear owner while several engineers understand its architecture, have reviewed important changes, participated in incidents, and know enough to step in when necessary.

The owner can be unique.

The knowledge shouldn't be.

This kind of shared ownership is also a behavior I look for when evaluating [engineering judgment and collaboration]({% post_url 2026-05-31-after-the-technical-interview %}). It does not dilute accountability. It makes that accountability sustainable.

## Build Team Redundancy Before You Need It

Infrastructure redundancy built during an outage is usually too late.

Team redundancy works the same way.

The worst possible time to discover that nobody else understands a critical system is during the handover period after its owner has resigned.

By then, you're racing against the clock.

Engineering knowledge sharing needs to happen while everything is normal.

This doesn't require everyone to know everything.

It also doesn't require massive documentation projects.

Useful practices include:

- Periodically rotating ownership of selected systems or projects
- Having engineers shadow each other on critical systems
- Involving multiple engineers in architecture and code reviews
- Ensuring important incidents are not repeatedly handled by the same expert
- Documenting how systems are deployed, debugged, recovered, and operated
- Recording important architectural decisions and known failure modes
- Deliberately giving engineers opportunities to operate systems they did not originally build

![Engineers sharing knowledge and ownership of a production system to reduce key-person dependency]({{ site.baseurl }}/assets/images/shared-engineering-ownership.png)

These practices are easier to protect when teams treat them as reliability work, not optional cleanup. Like other [important but not urgent engineering investments]({% post_url 2026-06-20-important-but-not-urgent-where-future-incidents-usually-start %}), knowledge distribution creates value through failures that never become crises.

The goal isn't to eliminate specialization.

It's to eliminate helplessness.

## Succession Planning Isn't Just for Managers

When people hear the phrase "succession planning," they often imagine executives deciding who could replace a manager.

Engineering teams need a smaller version of the same exercise.

Pick any critical engineer on your team and ask:

> If this person left the team tomorrow, who could take over their responsibilities?

Maybe nobody could replace them immediately.

That's completely reasonable.

The more useful question is:

> Who could become capable of taking over within the next three months?

If there's a reasonable answer, the risk is probably manageable.

If the answer is "nobody," you've discovered a key-person dependency worth fixing.

And if you ask the same question for several engineers and keep getting the same answer, you probably don't have an individual performance problem.

You have a team design problem.

Succession planning for engineers is not about quietly choosing replacements. It is about creating enough knowledge, access, confidence, and opportunity for other people to grow into critical responsibilities.

## Don't Turn Key-Person Dependency Into a Career Trap

There is another, less obvious consequence of allowing an engineer to become a single point of failure.

Eventually, their importance to the team can start working against their own career growth.

![Engineer held back by critical system dependencies while looking toward new career opportunities]({{ site.baseurl }}/assets/images/key-engineer-career-trap.png)

An engineer may reach a point where their current role no longer gives them enough room to grow.

They may want to:

- Work on a different type of problem
- Move closer to product development
- Explore another technical domain
- Move into leadership
- Join another part of the organization
- Simply try something new

At that point, a manager faces a difficult trade-off.

Losing the engineer hurts.

The team may lose context, expertise, velocity, relationships, and years of accumulated knowledge.

The short-term reaction can easily become:

> I can't afford to lose this person.

But that's exactly where dependency becomes dangerous.

If the main reason an engineer cannot move is that the team would struggle without them, we've turned their competence into a penalty.

The more valuable they became, the harder we made it for them to leave.

That isn't a healthy retention strategy.

Managers should absolutely try to retain great engineers.

We should understand what motivates them, create growth opportunities, expand their responsibilities, recognize their impact, and compensate them appropriately.

But sometimes the next step that person needs simply doesn't exist inside our team.

When that happens, helping them move may be better management than convincing them to stay.

From an organizational perspective, internal mobility isn't necessarily losing an engineer.

The organization keeps their experience, institutional knowledge, and relationships while the engineer gets a new growth path.

Trying too hard to optimize for one team's short-term stability can produce the opposite result.

You might prevent someone from moving to another team today, only to watch them leave the organization entirely tomorrow.

A resilient team gives its best engineers the freedom to leave.

Not because losing them doesn't hurt.

But because their departure shouldn't destroy what they helped build.

## Run a Key-Person Failure Scenario

There is a simple exercise engineering managers and SRE leaders can run periodically.

Pick one of your most critical engineers and imagine they tell you tomorrow that they're leaving the team.

No judgment.

No assumptions about whether they're happy or likely to leave.

Treat it like a reliability failure scenario.

Ask:

- What stops working?
- What slows down?
- Which projects lose their effective owner?
- Which systems become difficult to operate?
- Which architectural knowledge disappears?
- Which relationships depend primarily on this person?
- Who would step in during the first week?
- What would the first 30 days look like?
- Who could realistically take over within 90 days?

The uncomfortable answers are useful.

They reveal organizational dependencies while there is still time to address them.

In reliability engineering, we don't wait for a database node to die before asking whether failover works.

Maybe we shouldn't wait for a resignation letter before asking the same question about our engineering teams.

Your strongest engineers should make the team significantly better.

But they shouldn't be the reason it continues to function.

If your most critical engineer resigned tomorrow, what would stop working?

Whatever your answer is, that's probably what you should work on today.

{% include utterances.html %}
