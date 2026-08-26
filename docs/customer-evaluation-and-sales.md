# Customer Evaluation and Sales

The other pages cover the architecture and how it got built. This page covers the part that happened before any of that mattered: getting a retailer to actually believe semantic search was worth switching for, and proving it fast enough to matter.

## What customers were actually evaluating

Nearly every prospect came in already running Algolia or Elastic and was deciding whether a semantic layer was worth the switch. The evaluation almost always came down to the same three questions: could it understand a query the way a shopper actually meant it, not just match keywords; would it hold up at their real catalog size and query volume; and could it drop in without months of reimplementation. Those three questions are what the architecture on the other pages was built to answer, and answering them for a skeptical technical buyer was a different job than answering them for an engineering team that already trusted the platform.

## What that looked like with real prospects

- Louis Vuitton's data science and machine learning team needed their catalog understood stylistically, not just matched on exact terms, and needed the long tail of vague queries handled without falling back to nothing. I built the custom demo that got them there, and it moved from that demo into a formal technical evaluation aimed at their in-store associate search tools.
- One of the largest retailers in the world ran us against the biggest incumbent search vendor in the category in a paid, side by side evaluation before deciding anything commercially.
- Early design partners like Cooklist and Bookopolis needed the same semantic and similarity search layer applied to catalogs nothing like retail apparel, recipes in one case, books in the other, which mattered because it proved the platform generalized instead of only working for one kind of catalog.

## My role in the sales motion

I ran the technical side of these conversations end to end. A prospect's complaint was almost never phrased as an architecture requirement, it was something like "our search does not understand what our customers actually want." My job was translating that into a working demo against their real catalog, then into a scoped technical evaluation with a specific bar to clear, then handing it to the commercial conversation with a working system behind it instead of a deck. Quantified across the customers I worked with directly, that side of the job, understanding a prospect's catalog and pain points and proving the platform against them, was the majority of where my time actually went, more than the architecture work itself.

A good chunk of that time was spent presenting directly to the people who would eventually decide, not through an intermediary. A data science or machine learning lead does not want a summary of what an evaluation found, they want to see the actual results, ask why a specific query returned what it did, and push on a tradeoff until they are satisfied with the answer. Being able to sit in that conversation and answer for the system myself, in plain terms, without falling back to "let me check with engineering," was what kept a technical evaluation moving instead of stalling on a follow up email.

## A structured path from POC to production

Not every deal moved on a demo alone. With Kueski, a consumer lending platform using our search to help people find and complete loan applications, the ask was different: prove the effect on conversion and application volume, not just relevance. That meant running an actual proof of concept with a defined shape instead of an open ended trial.

I set the structure up the same way each time it mattered: agree on the exact objectives before touching their data, take in their real catalog, run a bounded trial period with a fixed start and end date, and check progress against a short list of deliverables rather than a vague sense of how it was going. Partway through the Kueski trial the honest status was mixed, some pieces done, some still in progress, and I said so rather than smoothing it over, because a buyer deciding whether to go to production needs the real picture, not a good story. The trial ended in a joint review of the results against the original objectives, followed immediately by the conversation that actually gets a deal signed: budget, procurement, and security, the parts that have nothing to do with the technology working and everything to do with whether an organization can actually buy it.

That last step is the one people skip when they are excited about a good demo. I treated it as part of the sale, not an afterthought after the sale, because a technical win that stalls in procurement is not a win.

## What "it works" meant across verticals

The three evaluation questions above played out differently depending on who was asking. A fashion retailer's buyers rarely cared about the underlying architecture at all, they cared about conversion rate, average order value, and cost of acquisition, and wanted evidence the search and recommendation surfaces moved those numbers rather than just returning more relevant looking results. Building the sales materials and demos for that audience meant leading with the metrics a merchandising team actually tracked, not with how the retrieval worked underneath. A lending platform's buyers cared about application completion and approval volume instead. Same underlying platform, same three core evaluation questions, but a different translation of what "it works" meant depending on the business the prospect was actually running.

## Land and expand, by design

The product itself was built around a land and expand motion: search as the initial replacement that was easy to justify and quick to prove, discovery and personalization as the expansion once a customer trusted the platform with their core search traffic. That two stage structure shaped the architecture directly. The [ingestion, embedding, indexing, and serving design](../README.md) had to work for a narrow search replacement on day one and still have room underneath it for recommendations, similarity search, and personalization without a rebuild once a customer wanted to expand.
