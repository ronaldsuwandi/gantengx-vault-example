Date: [[2026-02-25]]
Published: [[2026-02-26]]
Subtitle: My PKM setup using Obsidian, built from merging PARA, Evergreen Notes, and the 4 Buckets System.
SEO Description: My note-taking system built from PARA, Evergreen Notes, flat file structure, and more. Distilled into something simple and usable in daily practice
Tags: pkm, productivity, obsidian, knowledge management, notetaking

---

The system I use for note-taking today is a combination of [PARA](https://fortelabs.com/blog/para/), [Evergreen Notes](https://notes.andymatuschak.org/About_these_notes) and [4 Buckets System](https://www.linkedin.com/feed/update/urn:li:activity:7338580823962435585/) that I ended up merging after a lot of iterations. This post is part 1 of a 3-part series on my PKM setup using [Obsidian](https://obsidian.md), how I got there and how it's used daily.

Fair warning: none of this is groundbreaking. It's just a mix-and-match of various frameworks that eventually clicked. If you've ever spent more time setting up your system rather than actually using it, this might resonate.

## TL;DR

The main idea of the system is that notes are generally grouped to seven types:
* Project: anything **time-bound** related notes
* Area/Resource (merged): any ongoing focus/interest area or reference materials
* Archive: completed/inactive/outdated items (this is simply any note with #archived tag on it)
* MOC (Map of Content): serve as high level overview for the notes. Project and Area *can* be an MOC
* Evergreen notes: the default note. Knowledge meant to last and be referenced again. Ranges from atomic single-concept notes to topic reference notes
* Log: any log based (requires date) note that’s used to capture things. Some can be ephemeral and migrated to evergreen notes as the knowledge is settled. Generally avoid creating separate log note (embed into the main context) and only extract it as needed (log gets too large)
* Scratchpad: stored in daily note. Meant to be processed and should be empty

Notes must be enduring, interconnected and worth revisiting.

In the original PARA approach, Area and Resources are different, the idea is that Area is something ongoing focus/interest and the notes that I capture myself whereas Resource is mainly for any reference articles. Personally I do not see any benefit separating them - it just adds more clutter so I feel that it's fine to merge them. After all the system should work to my style, not the other way around.

## Zettelkasten

I started with Zettelkasten. The pitch is appealing: atomic notes, each capturing one core idea, all interconnected in a way that compounds over time. For researchers or writers it probably makes sense but for me personally it feels like this introduces a lot of overhead. Having to follow so many links is not sustainable and maintaining the system became a hassle.

## Evergreen Notes

Evergreen notes are enduring, interconnected and meant to be revisited. The goal is longevity and reusability. Notes should evolve as understanding deepens.

The evergreen note should be atomic, containing 1 concept (not to the level of Zettelkasten). A note can have a few related ideas but the core concept is still only one.

Note title can be a sentence to make concept precise (if note contains why, how or an insight e.g. `Count number of lines in a file`) but it's also okay to use descriptive topic title if sentence would feel forced (e.g. `Ownership concept`, `Chess psychology`). Title should be precise enough to be unambiguous.

## Combining PARA and Evergreen Notes

The gap I found in PARA is that once a project closes, the knowledge inside gets archived with it. When I finished my Apache Kafka Certification, the knowledge was still worth referencing. Evergreen Notes solves this as the underlying notes outlast the project. The project is just a container for goals and tracking.

## Note associations (tags, backlinks)

Prior to this I tried using tags and linking related topics in the note but quickly realised that as I go deeper the amount of references pointing back to them is huge (example: Kafka or Kafka Streams) and visiting the Kafka page looking at 100+ backlinks is pointless.

Andy Matuschak has a piece on why [tags are an ineffective association structure](https://notes.andymatuschak.org/Tags_are_an_ineffective_association_structure). Fine-grained associations ("topic X goes into more detail about topic Y") are more useful than coarse ones ("topic X is related to topic Y"). I removed topic headers and tags afterwards.

## Note metadata

At some point I was adding metadata to a bunch of my notes (creation date, updated date, topics, status) and realised shortly after that it doesn't really add much value and creates more friction.

I landed on a principle from this [forum post on metadata minimalism](https://forum.obsidian.md/t/principles-for-metadata-minimalism/11379/5): only add metadata if you actually use it for navigation or querying. 

With that I ended up with 3 status tags: #todo, #archived, #ongoing and date field on project notes.

## Flat file structure

Everything in Obsidian lives flat with only three directories: daily notes (empty files), attachments, and templates. Everything else sits at root level. This was inspired when I used to use [Roam Research](https://roamresearch.com).

Going flat frees up my brain from worrying about categorisation at the point of capture. I use file naming conventions to provide context instead.

## File storage outside Obsidian

For everything outside Obsidian, I follow a structure loosely based on [Johnny.Decimal](http://johnnydecimal.com). The core idea: no more than two levels of nesting, up to ten groups per level.

One thing I didn't adopt is the number prefix as I personally dislike having decimal IDs in file names. Root categories and areas are an exception and do have 2-digit decimals.

I maintain an index file to keep track where things live. Rather than 1 massive index, I split it by category so each category index stays small and actually readable.

## Note file naming

I want the file naming to be consistent so I set up some rules:
- Main root index uses emoji prefix to keep it pretty (e.g. `🏡 Home`, `📚 Topics`, etc)
- No prefix for MOC and project notes
- Log-based notes use `Log - <type>` prefix. Some logs are ephemeral and used to capture progress that can be converted into an evergreen note
	- `Log - 1-1 - <name>` to capture 1-1s with colleagues. This can grow pretty large and can be broken into yearly logs if needed
	- `Log - Health - <yyyy-mm-dd> - <name> - <illness>` specifically to keep track of my kids' illnesses
	- `Log - People - <name>` for catch-ups
	- `Log - <Project name>` for any side project logs
- Generally keep log embedded (be it for project, idea, engagements, etc) as much as possible and only extract when there is a need (log gets too large)
- Some notes have prefixes:
	- `Course - <course name>` for learnings
	- `Idea - <idea>`
	- `<Company name> - <note title>` for any notes related to a specific company. I use 2-4 character codes to map company names (e.g. `CFLT → Confluent, EYE → Eyeota, IND → Indeed`)
	- `Prompt - <prompt title>` for keeping track of LLM prompts

## Inbox

Inbox serves as a centralised place to capture quick ideas and I settled with using daily notes as a scratchpad. It's low friction — dump anything throughout the day and process it later. My rule is daily notes should be empty by default; a non-empty daily note means there's unprocessed stuff.

Inbox then simply show list of files containing #todo tag, or daily notes that are not empty.

## Write for yourself, rewrite to publish

The thing that made the most practical difference: I write notes for myself, not for an imagined reader. My notes are written in first person view format and if it's important enough to be published then I will rewrite the note to a publishable form.

---

*This is part 1 of a 3-part series. [[Post - How I Capture Notes Using the 4 Bucket System|Part 2]] covered how I capture notes. [[Post - The Obsidian setup behind the system|Part 3]] covered the Obsidian setup.*
