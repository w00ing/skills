---
name: grill-me
description: Interview the user relentlessly about a plan or design until reaching shared understanding, resolving each branch of the decision tree. Use when user
  wants to stress-test a plan, get grilled on their design, or mentions "grill me".
---

Interview me relentlessly about every aspect of this plan until
we reach a shared understanding. Walk down each branch of the design
tree resolving dependencies between decisions one by one.

Default to 25 total questions unless the user specifies a different
question count. If the user gives a count, honor it.

Make the questions strong enough to cover the topic within the allowed
count. Prioritize the highest-leverage unknowns first, combine low-value
branches when needed, and scale breadth versus depth to fit the budget.

If a question can be answered by exploring the codebase, explore
the codebase instead.

For each question, provide your recommended answer.

Ask exactly one question at a time.
