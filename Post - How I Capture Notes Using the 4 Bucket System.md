Date: [[2026-02-26]]
Published: [[2026-02-28]]
Subtitle: Context-dependent capture, the 4 bucket system, and where it breaks down
SEO Description: How I approach note capture depending on context, built around the 4 bucket system. Includes where it works well, where it breaks down, and blurred lines
Tags: pkm, productivity, notetaking

---

The way I capture notes depends on what I'm doing.

If I'm just jotting something down quickly (e.g. random thoughts, recruiter calls, something to follow up) it goes straight to Daily Note in point form, to process later.

If I know what I'm walking into (e.g. meeting, customer call, course, project update) I default to the 4 bucket system. This is what the post is about, and it's part 2 of a 3-part series on my PKM setup.

For everything else (e.g. deep technical notes, workflows, reference material) I just write in sections and let the structure come from the content.

The 4 bucket system comes from [Steve Huynh on LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7338580823962435585/). Essentially when capturing information, categorise everything into four buckets:

1. Facts: this is the **what**, the basic building blocks
2. Procedural: this is process, the **how**, the steps (all about sequence of actions) like deploying code, SOP
3. Conceptual: this is the **ideas** and how the ideas connected to each other
4. Questions: this is important because it highlights what you already know and what you don't. If anything you're unsure about or doesn't fit, put it here

![[Example of 4 bucket system note.png]]

## The pause is the point

When capturing, don't just write down everything you hear. Categorising forces you to ask: is this a fact, or does it explain something? That moment of judgment is where the actual thinking happens.

The result is notes that are already partially processed. When you come back to them, you're not re-reading a raw transcript. You're reading organised understanding.

## Where it works well

- **Meeting and sync-up notes**: especially project updates where you're capturing status, decisions, and open questions at the same time
- **Inbox capture**: quick notes that need processing later. The structure makes processing faster because you've already categorised what matters
- **Training and workshops**: if the scope fits in a single note. Short course? Treat it like an extended meeting and apply four buckets throughout
- **Small evergreen notes**: when the concept is self-contained enough that all four buckets fit naturally

For project updates specifically, I use a hub-and-spoke pattern: the main note captures the **latest state** with four buckets, and any in-depth detail lives in a separate linked note. I also have an embedded logs section where I capture logs/decisions for reference.

## Where it breaks down

Personally I feel the four bucket system doesn't work on these types of notes:
- Large permanent/deep technical notes or MOC notes (e.g. deep dive into Kafka, deep dive into Polish openings in chess, etc)
- Longer training/course
- Workflow based notes (e.g. SOPs, 7 questions to ask to find chess positions)
- Code examples

The 4-bucket system optimises for categorisation whereas technical learning needs narrative flow and connected understanding.

## The blurred lines between sections

One of the most problematic parts is that bucket boundaries aren't always clear. Two cases come up regularly.

### Facts vs Conceptual

In the case of Kafka, for example:
- Facts
	- Kafka uses pub-sub model
	- Topic is named stream of records
- Conceptual
	- Why Kafka is durable: uses replication and disk-based logs
	- Kafka decouples producers and consumers to allow scalability

Now all the points in the conceptual section are in fact "facts". Take the first example. "Why Kafka is durable: uses replication and disk-based logs". It's conceptual because it **explains a property** using multiple facts. Think of it this way:
- Kafka uses replication (facts)
- Kafka writes to disk (facts)
- Kafka is durable because of replication + disk (conceptual)

Rule of thumb: Facts = individual bricks. Conceptual = how those bricks fit together and what they build. If it **explains tradeoffs, design principles, behaviours**, it's conceptual.

### Facts vs Procedural

The following example is a note I captured during a meeting: "Order ID rendering is broken. Convert it into HEX and take out the last 8 digits and append colon".

These can be approached 2 ways:

Option 1 - split
- Fact: Order ID rendering is broken
- Procedural: To fix order ID rendering, convert to HEX and take out the last 8 digits and append colon
- This gives clarity but adds overhead and might be redundant

Option 2 - compact (just keep it in fact)
- Treat it as: "what's wrong, and how to fix it"
- This is pragmatic and keeps the procedural closely tied to the fact

For working notes, option 2 is almost always the right call. Option 1 is worth it when the fix is complex (spans multiple components), you're turning notes into documentation or onboarding material, or maintaining a checklist for an SOP.


---

*This is part 2 of a 3-part series. [[Post - The PKM Setup I Settled On After Many Iterations|Part 1]] covered the overall system for organising notes. Part 3 will cover the Obsidian setup.*
