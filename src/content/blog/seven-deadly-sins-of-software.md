---
title: "The Seven Deadly Sins of Software Development"
description: "Pride, Sloth, Greed — turns out medieval theologians were describing your codebase all along."
pubDate: 2026-03-25
tags: ["Engineering", "Career", "Satire"]
tldr: "Pride = overconfidence in your own code. Greed = over-engineering for imaginary scale. Lust = chasing shiny frameworks. Envy = grass-is-greener syndrome across tech stacks. Gluttony = dependency hoarding and bloat. Wrath = git blame as a weapon. Sloth = shipping without caring about the downstream. All seven are virtues pushed past their limit."
---

# The Seven Deadly Sins of Software Development

<details style="margin: 1.5rem 0;">
<summary style="cursor: pointer; padding: 0.5rem 0;"><strong>TL;DR</strong> — the short version for the slothful</summary>
<div style="margin-top: 1rem;">

| Sin | Dev manifestation | Antidote |
|---|---|---|
| **Pride** | "I don't need tests, I know what this does" | Humility is a technical skill |
| **Greed** | Building microservices for 12 users | Ship working things today, not perfect things in Q3 |
| **Lust** | Rewriting in Rust after one conference talk | Boring stacks ship |
| **Envy** | "Their architecture is so clean, ours is a disaster" | Every blog post hides three years of outages |
| **Gluttony** | 47 npm dependencies, one of which checks if a number is even | Every line is something you'll have to maintain |
| **Wrath** | `git blame` as condemnation, not understanding | Context doesn't excuse bad code, but it helps you fix it calmly |
| **Sloth** | "It works on my machine. Ship it." | Care is a professional skill |

</div>
</details>

Somewhere around the 4th century, a monk named **Evagrius Ponticus** catalogued eight spiritual vices that corrupt the soul. They were later condensed to seven by **Pope Gregory I**. Neither of them worked in software, yet they described it perfectly.

What follows is a **theological audit of your career**. Read it with the door closed.

---

## I. Pride — *Superbia*

> "I don't need tests. I know what this code does."

Pride is the **first sin, the root of all others**. In software, it manifests as the engineer who writes code so **clever** that even they can't debug it six months later.

Pride is the senior dev who dismisses **PR reviews** as "just formalities." It's the architect who designs a **distributed system** for a CRUD app serving 12 users. It's the README that says "**self-documenting code**" with no further explanation.

The theological view is that pride is a refusal to **acknowledge one's limitations**. The engineering view is exactly the same.

**The uncomfortable truth:** Humility is a technical skill. The best engineers I've worked with are the first to say **"I don't know"** and the fastest to reach for the documentation.

---

## II. Greed — *Avaritia*

> "We'll need this abstraction layer eventually. Might as well build it now."

Greed in software is the insatiable accumulation of **architecture *just in case***. It's **YAGNI** violations dressed up as foresight. It's building a **microservices mesh** for a feature nobody has requested yet.

The greedy engineer hoards **abstractions, layers, and premature generalizations**. Every function becomes a strategy pattern. Every config becomes a DSL. Every data fetch becomes an **event-driven pipeline** that "could scale to millions."

This sin is particularly dangerous because it **feels virtuous**. You're *planning ahead*. You're *future-proofing*. In reality, you're building a monument to your own anxiety about being caught unprepared.

**The uncomfortable truth:** Most of what you're hoarding will be **deleted in the next refactor**. Shipping a working thing today beats a perfect thing in Q3.

---

## III. Lust — *Luxuria*

> "Have you heard of Bun? We should rewrite the backend in Bun."

Lust is **desire without discernment**. In technology, it's called **framework chasing**.

The lustful engineer is perpetually aroused by the **latest release**. They watched a 20-minute conference talk and are now *absolutely certain* that **Rust + WASM** is the solution to the ticket they've been avoiding for three weeks. Their `package.json` has 47 dependencies, six of which are **experimental**.

This sin is seductive because **curiosity is genuinely good**. Learning new tools matters. But lust mistakes **arousal for judgment**. The new framework is always sexier than your current one because you haven't had to **maintain** it yet.

**The uncomfortable truth:** Boring stacks ship. **PostgreSQL** has been the correct answer to most problems since before you were born.

---

## IV. Envy — *Invidia*

> "Their architecture is so clean. Ours is a disaster."

Envy is the grief we feel at another's good. In engineering, it's the **grass-is-greener fallacy** applied to codebases, teams, and tech stacks.

You've read the **Netflix blog post** about their microservices. You've seen the **Shopify piece** on their monolith. You have concluded, based on approximately 1200 words, that their infrastructure is superior to yours and that your current employer is **uniquely broken**.

What the blog post doesn't show: the **three-year migration**, the seventeen outages, the engineers who quit, the Monday morning the database went **read-only** for four hours.

Envy also appears at the **individual level** — the engineer who can't engage with a colleague's good idea without immediately proposing their own alternative. The one who rewrites your code not because it was **wrong**, but because it wasn't **theirs**.

**The uncomfortable truth:** Every impressive codebase looks better from the outside. Every architecture made sense when it was designed. The question isn't "why can't we be like them?" — it's **"what constraint were they solving that we don't have?"**

---

## V. Gluttony — *Gula*

> "Let me add one more dependency for this."

Gluttony is **excess without need**. In software, it has a precise unit of measurement: `node_modules`.

The gluttonous engineer reaches for a **library** before reaching for their keyboard. They `npm install` their way through problems. Their `package.json` contains a package that formats phone numbers, a package that checks if a number is even, and **three date libraries**, two of which are deprecated.

But gluttony isn't only about dependencies. It's also **over-engineering at every scale** — the 400-line component that could be 80 lines, the meeting with 12 stakeholders when two would do, the PR with 23 files changed that should have been **three separate PRs**.

The body processes what it can and stores the rest as fat. **Codebases do the same.**

**The uncomfortable truth:** Every dependency is a **liability**. Every line of code is something you'll have to maintain, explain, and eventually delete. **Restraint is a feature.**

---

## VI. Wrath — *Ira*

> `git blame`

Wrath is the **disordered response to a perceived injustice**. In software, it is invoked the moment you open a file someone else wrote.

The wrathful engineer leaves comments that are **technically accurate and humanly devastating**. They write `// WHY` in code reviews without further elaboration. They use `git blame` not to understand, but to **condemn**. They describe architectural decisions as "criminal" in the company Slack, **publicly, at 11pm**.

Wrath also manifests as **heroic burning** — the engineer so frustrated with process, with slowness, with *everyone else's incompetence* that they rewrite the **auth system** over a long weekend without telling anyone. They feel righteous. The on-call engineer feels something else entirely on Monday morning.

**Anger** at poor code is natural. **Acting on it without discipline** is a sin.

**The uncomfortable truth:** The code you're furious about was written by someone **under pressure**, with **incomplete information**, probably shipping a deadline that came from above. Understanding context doesn't excuse bad code — but it might help you fix it without **burning the team down**.

---

## VII. Sloth — *Acedia*

> "It works on my machine. Ship it."

Sloth is **not laziness**. This is a common misunderstanding. Acedia is **spiritual apathy** — the refusal to care about the things that matter.

The slothful engineer isn't idle. They are often **extremely busy**. But they skip the tests because "it's obvious it works." They don't write the **migration plan** because "we'll figure it out." They **copy-paste** the Stack Overflow answer without reading it. They merge the PR without running it locally.

The sin isn't in moving fast. It's in **not caring about the consequences** for the people downstream — the users who hit the bug, the colleagues who inherit the **debt**, the on-call engineer at **3am**.

Sloth is perhaps the most dangerous sin because it **compounds silently**. No single instance looks catastrophic. But acedia is not one bad commit — it's a **culture**.

**The uncomfortable truth:** Care is a professional skill. Writing a **clear commit message**, keeping the README updated, leaving the campsite cleaner than you found it — these are not "nice to haves." They are the difference between a codebase that **ages well** and one that collapses under its own neglect.

---

## Absolution

The good news — and there is good news — is that software development is one of the few fields where you get to **commit your sins**, observe the consequences **in production**, and fix them in the **next sprint**.

The seven sins described above are not character flaws. They are **failure modes**. They emerge from real virtues pushed to excess or applied without wisdom: **confidence** becomes pride, **planning** becomes greed, **curiosity** becomes lust.

The path isn't suppression of the vice — it's cultivation of the **opposite virtue**. Humility over pride. Sufficiency over greed. Discernment over lust. Solidarity over envy. Restraint over gluttony. Patience over wrath. Care over sloth.

None of which requires a theology degree. Just a **good code review culture** and the willingness to be wrong.

---

*Write code as though the person who maintains it is a stranger who knows where you live. They might.*
