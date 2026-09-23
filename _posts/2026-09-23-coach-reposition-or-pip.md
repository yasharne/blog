---
layout: post
title: "Managing Underperforming Engineers: Coach, Reposition, or PIP?"
date: 2026-09-23
permalink: /coach-reposition-or-pip.html
description: "Managing underperforming engineers: when to coach, find a better role, or use a performance improvement plan, while protecting team health and fairness."
excerpt: "Patience needs evidence of progress. Before moving to a PIP, understand whether the problem is performance, role fit, or team fit—and who is absorbing the cost."
categories: [engineering, leadership]
tags:
  - engineering management
  - performance management
  - coaching
  - role fit
  - team health
  - performance improvement plan
image: /assets/images/coaching-1.png
---

I was once told by a team member that I was too tolerant of low performers.

That feedback was uncomfortable because there may have been some truth in it.

My instinct has generally been to make expectations clear, give direct feedback, and allow someone a reasonable opportunity to improve. If they are still struggling, I want to understand whether different work or another team could help them contribute more effectively.

I still believe in that approach. But managing underperforming engineers also requires asking a question I can too easily overlook: what is happening to everyone else while I wait?

There is a difference between giving someone a fair chance and avoiding a difficult decision. From the manager's chair, those two things can look surprisingly similar.

![Engineering manager considering signposted paths for coaching, repositioning an employee, and a performance improvement plan]({{ site.baseurl }}/assets/images/coaching-1.png)

## Managing Underperforming Engineers Starts With Understanding the Gap

A missed deadline tells me something went wrong. It does not, by itself, tell me why.

Perhaps the engineer lacks a skill. Perhaps the assignment depends on cross-team coordination they have never learned to handle. Perhaps priorities changed three times, and I am treating a planning failure as an individual one.

Before deciding what to do about someone's performance, I need to understand what I am actually looking at.

> Before deciding someone is a performance problem, figure out whether you have a performance problem, a role-fit problem, or a team-fit problem.

A **skill or performance gap** means the person is not yet meeting an expectation of the role. They may need to improve debugging, execution, communication, or follow-through. The question is whether they can close that gap with clear feedback and appropriate support.

A **role-fit problem** means the shape of the work does not match their strengths. Imagine an engineer who is effective at deep technical investigation but repeatedly struggles to drive ambiguous projects across several teams. Their technical ability is real. So is the gap between that ability and what their current role requires.

A **team-fit problem** can involve how work is organized. Someone who does well with sustained focus may struggle on a team dominated by operational interruptions. Someone used to independent execution may need help working in a highly collaborative environment.

These are working explanations, not permanent labels. They can overlap. And "team fit" should describe concrete working requirements, not whether someone shares my personality or agrees with me.

I also need to check my own contribution. Did I explain the expectations? Are they appropriate for the person's level? Do they have access, context, and realistic priorities? If several people struggle with the same expectation, I should examine the environment before treating each person as a separate problem.

## Coaching Should Make the Next Attempt Different

"You need to show more ownership" may describe my frustration. It does very little to help someone act differently.

More useful feedback sounds like this:

> In the last three cases, I had to follow up several times before the task moved forward. For the next project, I expect you to identify blockers and follow up without waiting for me.

Now we have something observable to discuss. I can ask what prevented follow-through, clarify when to escalate, and agree on what the engineer will do next time.

Support should match the gap. If someone does not understand a system, pairing and documentation may help. If they struggle with coordination, another technical course probably will not. We might instead walk through how to identify dependencies, approach another team, and escalate a stalled decision.

I would agree on a checkpoint tied to actual work, then review what happened. That gives the person a chance to practice and gives both of us evidence.

Feedback does more than correct behavior. It produces information.

Does the engineer understand the expectation? Can they apply it? Do they ask for help earlier? Does improvement carry into the next assignment, or disappear as soon as I stop reminding them?

I made a similar point when writing about [specific feedback in promotion conversations]({% post_url 2026-06-24-promotion-readiness-why-good-engineers-dont-always-get-promoted %}). People need observable expectations. Here, though, the standard is the current role, not readiness for the next one. I should not confuse missing a promotion bar with underperformance.

## Patience Needs Evidence of Progress

I do not expect someone to become perfect after one conversation.

An engineer learning to manage dependencies may still miss one. But if they now identify most dependencies before implementation, raise blockers earlier, and need fewer reminders, something meaningful has changed.

That trajectory matters.

**Patience needs evidence of progress.** An apology, a positive conversation, or a promise to try harder is not the same as changed behavior.

The evidence should relate to the original gap. If the problem is follow-through, completing more small tickets does not necessarily address it. If the problem is work quality, faster delivery may simply move more repair work onto reviewers.

There is no universal number of weeks that makes patience reasonable. Learning an unfamiliar service and learning to lead a complex project require different opportunities to demonstrate progress. The seriousness of the gap and the cost to the team also matter.

But the review point should be explicit. We should know what we are looking for and when we will discuss it again. Repeatedly moving that point because the next project might finally be different is a warning sign for me as a manager.

## Coach → Reposition → PIP

This is the sequence I generally work through:

**Coach → Reposition → PIP**

It is a way to organize my judgment, not a requirement to transfer everyone before taking formal action. Successful coaching can end the process. Repositioning only makes sense when there is credible evidence of a better fit.

### Coach Against Clear Expectations

Start with the work the person is expected to do today. Explain the gap, provide relevant support, and give them a reasonable opportunity to demonstrate improvement.

The goal is sustainable performance. If the engineer succeeds only because I quietly take over the difficult parts, I have not yet learned whether the coaching is working.

### Reposition Where There Is a Real Fit

If the person has useful strengths that the current work rarely uses, I want to consider another assignment or a real opening elsewhere in the organization.

For example, an engineer who struggles with broad project coordination might have demonstrated strong results on focused tooling work. An existing developer-tools role could be worth exploring, provided its actual expectations match that evidence. Another team is not automatically easier; it has its own demands.

The question I need to ask is:

> Is there a real role this person can succeed in, or am I designing a role around everything they cannot do?

There is a difference between adjusting responsibilities sensibly and leaving someone with a collection of tasks nobody needs enough to justify a role.

A move also needs the employee's interest and an informed conversation with the receiving manager. I should be honest about strengths, gaps, and what we have tried. Passing an unresolved problem to someone else is not successful repositioning.

Nor should the search become an indefinite waiting room. If no realistic opportunity exists, I still have a decision to make about the current role.

### Use a PIP When Informal Support Has Not Been Enough

A performance improvement plan (PIP) makes the remaining gap, required outcomes, support, and review timeline formal and explicit.

It becomes appropriate when core expectations remain unmet despite clear feedback, relevant support, and reasonable time. It should provide a genuine opportunity to improve, with an honest explanation of what happens if the required improvement does not occur.

![Coach, reposition, or PIP framework showing feedback and support, a search for a better role, and a formal improvement process]({{ site.baseurl }}/assets/images/coaching-2.png)

*A fair chance to improve needs clear expectations, a realistic fit, and attention to the whole team.*

## Who Is Paying for Your Patience?

Giving someone several months to improve may be reasonable. But the calendar does not tell me who is absorbing the cost.

If I spend more time coaching, the engineer is doing the work, and progress is visible, that may be a healthy investment. Some planned pairing and review from teammates can be part of that investment too.

The equation changes when four other engineers repeatedly carry the workload.

Imagine the same pattern across several delivery cycles: a teammate finishes an incomplete change, a senior engineer repairs avoidable mistakes, and someone else takes the harder on-call work because we still cannot rely on this person to handle it.

Each intervention might look manageable on its own. Together, they reduce everyone else's capacity and make delivery less predictable. The senior engineer who is constantly supervising routine work cannot spend that time improving the system or helping others grow.

> Patience is healthy only as long as the rest of the team isn't paying the price for it.

That does not mean learning must have zero cost. Teams should help people develop. The boundary is sustained, repeated compensation for the same gaps without enough progress to reduce that burden.

I need to look beyond whether the project shipped. Who actually finished it? How much rescue work happened? Whose planned work disappeared? Are harder rotations repeatedly landing on the same people?

As I wrote about [key-engineer dependency and shared ownership]({% post_url 2026-08-12-key-engineer-single-point-of-failure %}), a team becomes fragile when it depends on the same people to keep functioning. Repeatedly using strong engineers to cover unresolved performance gaps creates another version of that dependency.

What feels like compassion toward one employee can feel like unfairness to everyone else.

High performers notice when reliability earns them more rescue work while consistently missed expectations appear to have no consequences. They do not need access to private performance conversations to experience the imbalance.

I should protect that privacy while still addressing workload, setting limits on support, and taking responsibility for the decision. "Please keep helping" is not an adequate long-term answer.

## When Patience Becomes Avoidance

This is where the feedback about being too tolerant becomes useful.

I can explain my intentions very well. I want to be fair. I want to recognize strengths. I do not want to give up on someone too early.

But intentions do not answer whether the arrangement is still working.

If I keep describing potential while the team keeps describing the same unfinished work, I need to pay attention. If every review ends with another extension but no new evidence, I may be delaying the discomfort rather than helping the employee.

Before extending the timeline, I should be able to name what has improved, what remains missing, and why more time is likely to change the outcome. I should also be able to explain how the team can sustain that time.

If I cannot, continuing is a decision too. It assigns the cost of my hesitation to other people.

## When a Performance Improvement Plan Becomes Appropriate

For me, the case for a PIP becomes clear when expectations have been understood, feedback has been specific, support and resources have been available, and reasonable time has passed—but progress is still insufficient on the core requirements of the role.

An unavailable transfer does not have to delay that decision. Neither does a small improvement automatically justify another extension if the remaining gap is substantial and the team's burden is growing.

> If a PIP comes as a complete surprise to the employee, something probably went wrong before the PIP.

The formal process should make an existing conversation more explicit. It should not reveal months of concerns that I kept to myself.

A useful plan connects expectations to observable work, sets achievable outcomes within the person's control, explains the support available, and defines when progress will be reviewed. "Be more proactive" is no more useful in a formal document than in a one-on-one.

I do not see this as punishment. I see it as the point where informal coaching has not produced sufficient improvement and continuing requires a clear, documented process. That process needs honesty about both the opportunity and the consequences.

## A Fair Chance Has Boundaries

I still want coaching to be my first response. I still want to recognize strengths and look for a better fit when one realistically exists.

But I also need to recognize when patience has stopped helping.

My responsibility includes clear expectations, honest feedback, and meaningful support. It also includes the engineers whose own work and growth suffer when I leave a performance problem unresolved.

The feedback I received is a useful reminder to evaluate both sides of that responsibility. Caring about the person in front of me cannot make the rest of the team disappear from the decision.

A manager's job is not to make every person succeed in every team. It is to create a fair environment where people have a real chance to succeed—and to recognize when that chance has been exhausted.

{% include utterances.html %}
