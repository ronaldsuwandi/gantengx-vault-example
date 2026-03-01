An [article](https://www.linkedin.com/feed/update/urn:li:activity:7338580823962435585/) found on LinkedIn by Steven Huynh. He can pick things up quickly even in the area outside of his expertise. He basically categorise information into 4 buckets

1. Facts: this is the **what**, the basic building blocks
2. Procedural: this is process, the **how**, the steps (all about sequence of actions) like deploying code, SOP
3. Conceptual: this is the **ideas** and how the ideas connected to each other
4. Questions: this is important because it highlights what you already know and what you don't

When creating a note, categorise the information into the 4 buckets: facts, procedural, conceptual, questions

Whether in a meeting, reading document, training don't just jot down blindly. **Pause** and categorise the info into the buckets. If you are **unsure**, dump it into questions

Simply structuring the information this way it'll drastically improve onboarding and learning

From discussion with [[ChatGPT]], [[Claude AI]] and [[Perplexity]] basically this system is best for
- capturing inbox
- meeting notes
- training/workshops (depends on the scope and size)
- permanent notes (smallest scope)

For these types of notes
- Larger permanent note/in depth technical notes or MOC notes (e.g. Kafka, Rust)
- Workflow based notes (e.g. 7 questions to ask to find chess positions)
- Code examples

The 4 bucket system doesn't work well. Either split it into much smaller scope (but can still be unnatural) or just stick to old school way: break it down by sections

> **The real issue:** The 4-bucket system optimizes for _categorization_ when technical learning needs _narrative flow_ and _connected understanding_.

The 4 bucket systems works well for project updates (hub-and-spoke model) where the main note with 4 bucket captures the **latest state** and any in depth detailed notes can go to a separate note linked from the main note. We can also optionally have logs section where we capture the logs/decisions for references

## Training/Course
From other discussion with [[Claude AI]] it also highlights for course/training it may not be the best. If it's a short course (treat it as extended meeting)

If it can fit within 1 note, then 4 bucket system works, otherwise split it by module (either 4 bucket or just standard note)

## Blurred lines between sections
One of the most problematic part of this system is the lines between the bucket often blurred. Let's pick example between Facts/Conceptual.

### Facts/Conceptual
In the case of Kafka for example
- Facts
	- Kafka uses pub-sub model
	- Topic is named stream of records
- Conceptual
	- Why Kafka is durable: uses replication and disk-based logs
	- Kafka decouples producers and consumers to allow scalability

Now all the points in conceptual section are in fact "facts". Let's pick up the first example. "Whay Kafka is durable: uses replication and disk-based logs". It's conceptual because we are **explaining a property** using multiple facts. Think of it this way:
- Kafka uses replication (facts)
- Kafka writes to disk (facts)
- Kafka is durable because of replication + disk (conceptual)

### Facts/Procedural
With meeting notes discussing bugs/fixes. Originally this falls under facts (but it's actually combination of facts and procedural)
"Order ID rendering is broken. Convert it into HEX and take out the last 8 digit and append colon".

These can be approached 2 ways

Option 1 - split
- Fact: Order ID rendering is broken
- Procedural: To fix order id rendering, convert to HEX and take out the last 8 digit and append colon
- This gives clarity but adds overhead and might be redundant

Option 2 - compact
- Keep it as is and put it in fact
- Treat it as: "what's wrong, and how to fix it"
- This is pragmatic and gives the procedural very closely tied to facts and easier on the context

### Rule of thumb
- Facts = bricks
- Concepts = how those bricks fit together and what they build
	- If it **explains tradeoffs, design principles, behaviours**  = conceptual
- For working notes, facts/procedural opt for option 2. This is perfect for sync-up meeting
- Facts/procedural option 1 (split) is more applicable for
	- Turning notes into documentation or onboarding material
	- Fix **multiple steps with edge cases** - the fix is complex, spans multiple components, etc
	- Maintaining checklist for SOP
