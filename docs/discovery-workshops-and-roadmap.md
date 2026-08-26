# Running Discovery With a Customer

The other pages cover the architecture and the sales motion around it. This page is about the part in between: the actual working sessions with a prospect or customer where a vague complaint turned into a scoped plan, and how that plan turned into a roadmap instead of a one-off project.

## Getting in early, before the demo

I did not wait for a signed deal to get involved. On the opportunities that mattered, I was in the room with the account side from early on, before any custom demo got built, to figure out whether a prospect's pain was real and specific enough to justify the effort a full technical evaluation takes. That meant a short conversation with whoever owned search or catalog on their side, enough to tell the difference between a prospect who was mildly curious and one who had an actual, quantifiable problem with their current search vendor. Getting that read right mattered, because a custom demo built against a real catalog is expensive to build well, and building one for a prospect who was never going to move was a wasted cycle for everyone.

The other half of getting in early was building credibility with the people who would eventually have to say yes on the technical side. With a data science or machine learning team evaluating whether to replace their search vendor, showing up with an opinion and a working system against their own catalog carried more weight than showing up with a deck. That credibility is what turned a first conversation into a real evaluation instead of a polite pass.

## Mapping the process, not just the ask

Once a prospect was worth the time, the next step was never straight to building. It was a structured session, sometimes more than one, to map out what was actually happening before proposing anything new.

- **Current state pain points.** What their existing setup actually got wrong: queries returning nothing because the shopper phrased it in their own words instead of the exact product term, results that matched keywords but missed intent entirely, and a long tail of searches that just failed. This is where a complaint like "our search doesn't understand what people want" got broken down into specific, reproducible failure cases against their own catalog.
- **Stakeholder needs.** The same project looked different depending on who was in the room. A merchandising stakeholder cared about conversion and average order value. A data science or engineering stakeholder cared about relevance quality and how much reimplementation a switch would cost them. Whoever owned the vendor relationship cared about migration risk and what could go wrong during a cutover. Mapping all three out explicitly meant the eventual plan had to satisfy all of them, not just whichever one was easiest to convince.
- **Decision flow.** How a search result actually reached a shopper today: what system fired first, what reranked or filtered after that, and where in that flow a semantic layer would sit versus replace something outright. Getting this wrong meant proposing an integration that looked good on a slide and did not fit how their stack actually worked.
- **Data and technical constraints.** What their catalog data actually looked like: how complete the product attributes were, how often the catalog updated, whether there was a real-time ingestion requirement or a nightly batch was fine, and what their current infrastructure could and could not support during a transition.
- **Target state.** What the end state actually had to do, described concretely enough that everyone in the room agreed on it: handle natural language and keyword queries in the same box, understand style and intent instead of just exact terms, and do it at their real catalog size without a latency regression.
- **The wish list.** What came up that was not in scope for a first phase but that the customer wanted eventually, personalization, recommendations, a conversational assistant. Writing that down mattered as much as the in-scope list, because it became the input to the roadmap conversation.

## Choosing the landing use case and sequencing what comes next

Every one of those workshops produced a decision: what to land first, and what to promise for later. Search replacement was almost always the landing use case, because it was the easiest thing to justify against an existing, budgeted line item and the fastest thing to prove with a real before-and-after. Discovery and personalization became the second and third phases once a customer had already trusted the platform with their core search traffic, which is the same land-and-expand sequencing described in the [architecture write-up](../README.md).

Turning that into an actual roadmap meant being explicit with the customer about the order and the reason for the order, not just handing them a list of features. A customer who had just sat through a workshop where they told me their personalization ambitions in detail needed to hear, clearly, why phase one was search only and what had to be true before phase two started.

## Setting success criteria and a rough ROI frame before starting

Nothing moved into real delivery without agreeing, explicitly and in writing, on what success looked like and roughly what it was worth. That meant sitting down with whoever on the customer side owned the business outcome, not just the technical evaluation, and getting alignment across their technical, business, and (for a regulated business like a lender) risk stakeholders on the same page before any real work started. The [proof of concept structure covered on the customer evaluation page](customer-evaluation-and-sales.md) is what that agreement turned into in practice: a defined trial period, a short list of deliverables, and criteria for what counted as a pass.

## Turning it into something reusable

The workshop format itself did not stay a one-off exercise I repeated from scratch every time. The pain point categories, the stakeholder mapping, and especially the vertical-specific framing of what "it works" meant, conversion and average order value for a retailer, application completion for a lender, became a template other people on the team could pick up and run themselves instead of reinventing the approach on every new account. Writing that structure down once, instead of carrying it only in my own head, was as much a part of the job as running any single workshop.
