# Reference: Common Failure Pattern Catalog

A named catalog of the failure patterns this editor watches for. Naming the pattern in a critique (e.g., "this is Compliance Theater Framing") gives the writer a reusable concept, not just a one-off correction — that's the point of a pattern name.

## Compliance Theater Framing
Reporting that a control or process happened ("we completed X," "we satisfied requirement Y") without reporting what it found or whether it reduced risk. Tell: language centers on the activity, not the outcome. See Rule 4.

## The Naked Metric
Any number presented without denominator, population, baseline, or trend context. Tell: a percentage or count that sounds impressive or alarming but can't actually be evaluated as either without more information. See Rule 3, and `metrics-context-checklist.md`.

## Buried Lede
The most consequential finding is structurally de-prioritized — placed after status updates, process narrative, or less important metrics. Tell: check what's in paragraph/bullet one versus what the reader would call "the real story" if asked to summarize in one sentence. See Rule 7.

## Vague Ask (or No Ask)
The narrative implies something should happen next but never states what, who, or by when. "For your awareness" used where an actual decision is being requested. See Rule 6.

## Jargon Assumption
Technical vocabulary used without translation, assuming a literacy level the stated audience doesn't have. See Rule 5 and `audience-calibration-guide.md`.

## Roadmap Substitution
Describing future plans ("we're on track with our roadmap," "this will be addressed in Q4") as if it resolves present risk. Tell: the sentence is about the plan, not about current exposure. A reader should be able to tell what the risk is *today*, independent of whether a plan exists to fix it later.

## Activity Without Consequence
A finding or metric is stated, but never connected to what would happen to the business if it went unaddressed. Related to the Naked Metric but broader — can also apply to qualitative statements, not just numbers. See Rule 2.

## False Precision
Overly specific numbers presented with unwarranted confidence (e.g., "exactly 340 accounts") in a context where the underlying data is known to be an estimate or a point-in-time snapshot that's already stale by the time it's read. Less common, but worth flagging when the narrative's confidence doesn't match the underlying data's reliability.

## Using the Catalog
Don't force-fit a pattern name to every finding — some issues are specific to the document and don't map neatly to a named pattern. The catalog is a diagnostic aid, not a checklist to exhaust on every review.
