---
layout: post
title: "Important but Not Urgent: Where Future Incidents Usually Start"
date: 2026-06-20
categories: [engineering, sre, leadership]
tags: [sre, reliability, incident-management, technical-debt, planning]
excerpt: "Many incidents don't begin with catastrophic failures. They begin as small bugs that sit in the backlog long enough to become urgent."
---

Most incidents don't start with a catastrophic failure.

They start with a small bug.

A strange edge case. A warning that occasionally appears in logs. A timeout that happens once in a while. A task gets created, acknowledged, prioritized somewhere in the backlog, and then quietly forgotten.

Months later, that same issue becomes an incident.

## The "Important but Not Urgent" Trap

One of the most useful frameworks for thinking about prioritization is the Eisenhower Matrix. It separates work into four categories based on urgency and importance.

![Eisenhower Matrix for Engineering Teams]({{ site.baseurl }}/assets/image/eisenhower-matrix.png)

Many operational risks live in the **Important but Not Urgent** quadrant.

These are the tasks that everyone agrees should be addressed:

- Reliability improvements
- Technical debt
- Missing monitoring and alerting
- Capacity planning
- Architecture improvements
- Low-frequency bugs
- Test coverage gaps

Nobody argues against them. The problem is that they are competing with work that is both important and urgent.

In fast-moving organizations, there is never a shortage of urgent work:

- New product requirements
- Customer escalations
- Production incidents
- Revenue-impacting requests
- Strategic initiatives

As a result, the backlog of important-but-not-urgent work grows continuously.

The dangerous assumption is that these items can safely wait forever.

They can't.

What makes this category particularly dangerous is that many teams mistake a lack of urgency for a lack of risk. The issue is visible. The task exists. Everyone agrees it should eventually be fixed.

But risk doesn't stay constant.

Every week that passes, dependencies change, traffic grows, systems become more interconnected, and operational complexity increases. The cost of fixing the issue rises while its probability of causing an incident quietly increases in the background.

## How Incidents Are Born

A pattern I've observed repeatedly is that many incident postmortems contain a familiar sentence:

> We had already identified the issue.

Or:

> There was already a task created for this.

The incident wasn't caused by a lack of awareness.

It was caused by a lack of execution.

The system had already given us signals. We simply had more urgent things to work on.

Over time, the unresolved issue accumulates risk. Maybe another service becomes dependent on it. Maybe traffic increases. Maybe operational complexity grows.

Then one day the same issue crosses a threshold and suddenly becomes urgent.

What was once an *Important but Not Urgent* task has now been promoted into a production incident.

The interesting part is that, after the incident, the priority often looks obvious in hindsight. Everyone agrees the issue should have been fixed earlier.

But the decision wasn't made with hindsight. It was made in the middle of dozens of competing priorities, deadlines, incidents, and business requests.

That's why this is fundamentally a planning problem rather than a technical one.

## Planning Is Risk Management

The lesson is not that every bug should be fixed immediately.

That would be unrealistic.

The lesson is that planning is not only about delivering new capabilities. It is also about consciously reducing future risk.

In environments like Snapp, new urgent priorities emerge every day. Product opportunities appear, operational issues surface, customers escalate problems, and business demands evolve.

If teams allocate 100% of their capacity to today's urgent work, tomorrow's incidents are already being created.

The challenge is not identifying technical debt or reliability risks. Most teams are actually very good at identifying them.

The challenge is protecting enough engineering capacity to address them before they become urgent.

Some teams do this through reliability initiatives. Others reserve explicit engineering capacity for maintenance work, platform improvements, or technical debt reduction. Others use error budgets to force conversations about reliability investments.

The mechanism matters less than the outcome.

What matters is creating space for work whose value comes from incidents that never happen.

## Before They Become Someone's Pager Alert

The most expensive reliability issues are rarely surprises.

They are often known problems that remained in the backlog long enough to become emergencies.

Good planning is not about predicting every incident.

It is about ensuring that important work does not need to become urgent before it receives attention.

Because eventually, every ignored risk creates its own priority.

And when it does, it usually arrives as an incident.

{% include utterances.html %}
