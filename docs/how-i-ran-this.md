# How I Ran This

The README covers the architecture itself. This page covers how that architecture actually got scoped and built, and who owned which part of it.

## The pattern

1. Sit with the people who would actually run a catalog through the platform and find out what a retailer needed to ask of their own data, and what a wrong answer cost them.
2. Turn that into a build sequence with an explicit bar to clear at each stage, not one big release.
3. Run the working sessions where the tradeoffs get made, then write the decision down so it stays made.
4. Watch what breaks or gets slow as real usage grows, and let that tell you what the next architecture change has to be.

## Discovery

Retail catalogs do not fail the same way twice. A merchandiser's actual complaint was rarely "search is broken," it was something specific: a query for a type of product returning items in the wrong category, or a shopper's intent not mapping to anything in the catalog at all. Getting to a reference architecture meant translating complaints like that into requirements a platform could actually be built against: what needed to happen at ingestion time versus query time, what could be approximate and what could not, and where latency mattered enough to change the design.

## Scoping the build

The build sequence in the README, demo path, first production path, continuous path, was not three unrelated features. Each stage had a bar it had to clear before the next one started.

- The demo path had to prove semantic relevance actually beat keyword matching on a real catalog, with nothing else riding on it.
- The first production path had to hold up under real query volume without the manual notebook step in the loop.
- The continuous path had to keep single record ingestion behaviorally identical to the batch path, so nothing downstream had to know which one produced a given document.

That staging is what let the business start selling and onboarding customers before the ideal end state existed, instead of waiting on a single big release.

## Who owned what

- I owned the product definition, the reference architecture, the cost and latency tradeoffs, the working sessions where those decisions got made, and the artifacts that came out of them.
- Engineering leads owned implementation against that architecture and flagged where a design assumption did not hold once it hit real code.
- The provider abstraction at the embedding layer and the cadence based index versioning were both decisions I pushed for before the first production customer, specifically so a later model or vendor change would not force a rewrite.

## Where it expanded

The provider router and the multi mode ingestion path were both designed in early, before either one was strictly necessary. That decision paid off as adoption grew: catalog sizes and update patterns varied more than the first customers suggested they would, and the platform absorbed that variation without a rewrite because the room for it was already there. The lesson I took from it: build the seam before you need it, not after.
