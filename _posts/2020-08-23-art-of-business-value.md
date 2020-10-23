---
title: "Summary of The Art of Business Value"
categories: lean agile business management
layout: post
---

Big Idea: Business value is a hypothesis, held by leadership, about the values and behaviors that will best accomplish the organization's goals. Leaders create the context and incentives for teams to discover value through experimentation and adaptation. Combining experimentation with a variety of metrics, we incrementally clarify our understanding of business value and how to deliver it.


[The Art of Business Value by Mark Schwartz](https://itrevolution.com/book/the-art-of-business-value/) is a meditation--the author would say investigation--on the meaning, discovery and pursuit of business value. Schwart contends that if producing business value is the goal of Agile practices, then we ought to know what it is and how to achieve it.

Schwart is an experienced, engaging, insightful observer and apparently a student of Greek philosophy.

I read the book because I struggle to prioritize my Ops team's backlog in a way that defensibly maximizes business value. Each stakeholder who looks at our backlog has a different perspective on the relative priority of stories. Compliance thinks risk stories should be done first. Ops chooses automation, maintenance and bug fixes. Management says "strategic initiatives" trump all else. I tried to make various scorecards to help with this, but none of them felt right. I hoped this book would give me answers. It didn't give me a simple formula to calculate value. Instead, it gave me a new mental model and a language for talking about business value with the team and with stakeholders. It challenged my thinking of "IT as service provider." It encouraged me to challenge the toxic "contractor control" dynamic and embrace IT's role in the joint discovery of value and ownership of outcomes. 


## Key Points

### Chapter 1: The Problem


>A good understanding of business value is critical to Agile practice...To say that we want to deliver business value is to say nothing much except that we want to do the right thing, do lots of it, and do it quickly. But this does not help us understand how to select and prioritize features.

Business value, customer value and user value are used interchangeably, but they are distinct.

Traditional financial measures, such as Return on Investment (ROI) are of little use to prioritize user stories.

ROI does not consider the timing of profits, risk of expected returns, or accounting of profits. It is not impossible to calculate, but it is of little use for prioritizing features. 

Some aspects of business value are impossible to quantify. How do you measure the value of reducing technical debt, compliance requirements, learning, and knowledge?

### Chapter 2: The Meaning

Other financial measures, such as Market Value Added (MVA) or Shareholder Value Added (SVA) or Net Present Value (NPV) are again very difficult to use as a prioritization method for stories. MVA and SVA don't apply to private organizations, whose owners define their values.

These financial measures are at best proxies of business value, and they are of little use to product owners or Agile teams. They also ignore how stories fit into a coherent business strategy. 

Business value is complex and impossible to distill in a single measure. To understand business value, Schwart says we must:

> Consider the goals of the particular organization, the interests of at least some of its stakeholders, and a variety of indicators of value, some of which may be quantifiable, and some of which may not.

### Chapter 3: The Culture

Schwartz defines Culture as is the values, behaviors and assumptions that the organization learned over time in the pursuit of its mission.

If business value is complicated, must be discovered and interpreted, then it is not fair to expect "the business" or "the product owner" to have all the information required to prioritize stories effectively. Instead, the team must own value discovery and interpretation, and delivery.  


The team discovers value through scientific experimentation, through "provoke and observe." Deliver something that we believe to be valuable, then observe the results, and adjust accordingly.

> For the Agile team to use culture as a guide to what is valued by the business, it must excavate, deduce, hypothesize, test.... Corporate culture is not an impediment to Agile adoption; it is a valuable clue to defining the success of Agile adoption.

We should take an Agile approach to Agile adoption through incremental change, instead of pining that the organization's culture and rules must change to accomodate Agile.

### Chapter 4: The Rules

> Bureacracy delivers business value. Just sometimes not enough.

Bureacracy is the most efficient way to run an organization fairly, free of emotion and caprice. Rules are good, so long as they are allowed to change. When rules become petrified, they can stifle growth. 

Rules lead to compliance requirements. These are not waste if they add business value. They express deeper business needs.

"Rules are a form of institutional memory." Therefore, we should use these rules to further discover what the business values.

### Chapter 5: The CIO

The traditional view of the business-IT relationship considers IT to be the service provider, instead of a part of the business. This leads to "requirements" and "business needs" foisted upon IT, who dutifully delivers, but fails to achieve the real business need. This perpetuates a negative feedback cycle of distrust and control that opposes Agile practice. The underlying false assumption is that the business knows what it needs.

IT helps identify business value, define business needs, and own the delivery of outcomes, not just technical requirements. 

### Chapter 6: The Clue

The Waterfall project management model develops a long-term plan based on little information up front. The Agile approach adapts as experiments provide more information.

In a decentralized environment, the criteria for decision making must be diffused to the teams making decisions.

Our understanding of business value changes as we learn. Assigning value to stories must consider the timing of value harvesting. Approaches such as ROI and NPV do not account for this dynamic nature of value. They ignore the economic value of "latent assets" like learning, information, and the Enterprise Architecture. They pretent to be objective, but they are the result of individual work, incorporating biases and politics.

Organizations are complex adaptive systems (CAS). The role of the leader is to influence and incentivize the system towards the desired outcomes.

Leaders must interpret the organization's goals into values that teams can internalize and use for decision-making.

Cost of Delay, Options Thinking and Scenario Planning incorporate the time dimension of business value.

### Chapter 7: The Delivery

Schwartz offers some experiments to try.

  1. Shorten feedback loops through a continuous delivery pipeline.
  2. Assemble cross-functional teams.
  3. Move towards small batches.
  4. Extend the delivery pipeline with a variety of metrics that capture business intelligence that helps assess delivery of value.
  5. Examine bureacracy, compliance and accounting with a critical eye to eliminate waste.
  6. Negotiate administrative nad compliance overhead.
  7. Use Impact Mapping to find things that affect value but are not features.
  8. Involve compliance teams early, and get them to offer solutions.
  9. Use Scenario Planning to picture future states.
  10. Build in flexibility through simple design.
  11. Consider Cost of Delay when prioritizing.
  12. Allow the team to consider stories optional, as a way to practice Options Thinking. [Gabe: This is why our team maintains an Idea list apart from the Backlog.]
  13. Recognize the economic value of the Enterprise Architecture.
  14. Focus on the IT asset rather than specific project returns. The value of new features include how they will improve the overall IT asset.
  15. Consider the value of information.
  16. Invest in outcomes, rather than programs.
  17. Incentivize teams to fail productively.
  18. Shorten the investment review cycle through continuous transparency.
  19. Move Beyond Budgeting.

#### New ways to think of the CIO

  - Guides the CAS by setting context of business value, incentives and success criteria.
  - The architect or conductor.
  - Owns the enterprise architecture, which represents business capability.
  - Impediment remover, servant leader and optimizer of black box development.
  - Develops and cultivates high-performing teams.
  - Guardian of IT rules, ensures they don't petrify.
