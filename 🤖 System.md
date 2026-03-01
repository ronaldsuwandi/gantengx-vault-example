> [!info] Personal reference
> This is my personal system reference — written for myself, not for publication. The published version is [[Post - The PKM Setup I Settled On After Many Iterations]].

This is the system that is used to manage all my notes and references (mainly in Obsidian). The idea is derived from combination of [PARA](https://fortelabs.com/blog/para/) and [[#Evergreen Notes]] (also LYT some extend) after discussing with [[ChatGPT]] and [[Claude AI]]. This is for notes and desktop workflow system is described in [[💻 Desktop Workflow System]]

I previously considered of using Zettelkasten but after experimenting with it I felt that it's only good in theory. Having to follow so many links is just not sustainable and ended up adding too much overhead

The main idea of the system is that notes are generally grouped to seven types:
* Project: anything **time-bound** related notes
* Area/Resource (merged): any ongoing focus/interest area or reference materials
* Archive: completed/inactive/outdated items (this is simply any note with #archived tag on it)
* MOC: serve as high level overview for the notes. Project and Area *can* be an MOC
* Evergreen notes: the default note. Knowledge meant to last and be referenced again. Ranges from atomic single-concept notes to topic reference notes
* Log: any log based (requires date) note that’s used to capture things. Some can be ephemeral and migrated to evergreen notes as the knowledge is settled. Generally avoid creating separate log note (embed into the main context) and only extract it as needed (log gets too large)
* Scratchpad: this is store in daily note. Meant to be processed and should be empty

Now then from [[#Evergreen Notes]] perspective, the notes must be enduring, interconnected and worth revisiting.

In the original PARA approach, Area and Resources are different, the idea is that Area is something ongoing focus/interest and the notes that I capture myself whereas Resource is mainly for any reference articles. Personally I do not see any benefit separating them - it just adds more clutter so I feel that it's fine to merge them. After all the system should work to my style, not the other way around

Use [[#MOC (Maps of Content)]] to provide relationship/birds eye view of the relevant notes and have the main MOC like [[🏡 Home]] as the starting point

[[#Inbox]] is used to capture note/plan to read materials quickly and important that the inbox must be drained. Any old items that will be read sometime in the future should be discarded after a while.

For the [[#File storage organization]], use system similar to Johnny.Decimals but without the decimal prefix

As for the file naming, follow [[#Note file naming]]

Keep note as simple as possible (very minimal [[#Note template]]), no ceremonies like metadata about date or topics (exception of status tag in [[#Note status]]). If I need to add topics just add it under "See also" sections. The only note that has metadata will be project note. Health log has a specific style but that's about it

I previously have "topics" header (it's just an alternative to tags) but I realised after a while the association is quite pointless. I have hundreds of notes related with [[Kafka]] for example and if I do go to Kafka page, there is no way I will be able to go through over 100 notes without losing interest. See [[#Note associations]] for more details

Note capturing methodology is to use the [[4 buckets note capturing system]]. This format is ideal for capturing the inbox, meeting notes, training/workshops and evergreen notes (but only the smallest scope). 

Larger/in depth notes/workflow based notes like Kafka or Rust should be treated like MOC and split into smaller notes. Do **not shoehorn** it into 4 bucket system if it doesn't fit

> [!tip] For training/course
> Same concept as above, while 4 bucket works with training/course, it might be too big to squeeze the whole course into a single 4 bucket note. Either split it into smaller 4 bucket notes or just standard modular notes
> 
> In general, if everything can be squeezed in 1 note without much issue, 4 bucket will be a good approach

One final important point is that I should be writing notes **for myself** and not for publishable material first. That will reduce the friction and blockage. If the note is important enough to be published then re-write the version into publishable form. So from now on notes are generally in first person view format because these notes are meant for me and not others

## Evergreen Notes
Evergreen notes are enduring, interconnected and meant to be revisited. The goal is longevity and reusability. Notes should evolve as understanding deepens.

The evergreen note should be atomic, containing 1 concept (not to the level of Zettelkasten). Note can have few related ideas but the core concept is still only one

Note title can be a sentence to make concept precise (if note contains why, how or an insight e.g. `Count number of lines in a file`) but it's also okay to use descriptive topic title if sentence would feel forced (e.g. `Ownership concept`, `Chess psychology`). Title should be precise enough to be unambiguous

## Combining PARA and Evergreen Notes
One of the issue that I thought is that some completed project still have useful information that can be referenced. Example is Apache Kafka Certification. Even when completed, the knowledge that I obtained is still useful to refer from time to time. If we were to strictly follow PARA, this can be tricky. Hence combining it with Evergreen Notes works well

The main idea is that utilise Evergreen notes for capturing the core knowledge and Projects is just essentially a [[#MOC (Maps of Content)]] for the knowledge

So in the case of Kafka certification example, we have a Project called "Kafka Certifications" and it has the start, goals, due date and then the content itself will be a reference to Evergreen notes about Kafka

## File storage organization
Decided to stick with **flat file structure** on Obsidian. Use naming convention that provides context. There are only 3 directories within Obsidian: templates, attachments and daily notes (empty files). More details see [[#Note taxonomy]]  

Outside Obsidian, I will follow Johnny.Decimals' style where I only have up to 2 nested directories max and 10 groups each level. The only difference is that there **is no decimal/number prefix for ids** because I personally hated that number. I decided to make an exception for the area and categories. Root categories and areas do have two digit decimals

Similar to Johnny.Decimals, use an [[🗂 Index]] file to keep track of the file locations. Instead of a single index, I decided to split into link for each categories. This way in the index I only have up to 100 items in the row and it's still readable. Another option that can be considered is to use [Airtable template](https://airtable.com/app2QDvkeHs28xIgm/shr5vvlmaCV98G6z7/tbljpxMFbkn84Wkvo/viwC4h4adAkrPpk8g?blocks=hide)

## Inbox
Another core principal in Evergreen notes is to have an inbox note. The most important part of this is that the inbox **must be drained**. This is not a read me later list. If it's not drained, then it will just pile up and you will lose interest in keeping it clean

So it's very critical to be able to discard the items that is not going to be read after a while

The inbox will serve as centralised place to capture quick ideas, thoughts and links that I came across throughout the day. I settled with using daily note as my draft/scratching pad. I created [[📥 Inbox]] page to keep track of daily notes that have size more than 0 (since daily notes should be empty). This makes capturing idea on the go is pretty low friction, but the unprocessed daily notes will simply show the file name (date) without much context

## MOC (Maps of Content)
MOC is also a core concept in Evergreen notes. This is basically how you structure the notes and connect them together. Important tips to structure MOC
1. Have a main MOC to act as central hub for specific topic, project, area of interest
2. Sub-topic/area notes: create separate notes for each subtopic or subarea within main MOC. It should contain detailed information, insights and links related to the specific subtopic
3. Use heading and formatting to structure the content
4. **Summaries and highlights** will be very useful to have key highlights at the beginning of each subtopic/area notes. This provides quick overview of the content and helps in identifying key points or takeaways

Some examples of MOC types

### Project MOC
Example if I work on a software development project. I can have a project MOC that serves as central hub for relevant notes to the project. It could be project goals, requirements, design, implementations, etc. This will provide a birds eye view of the project and allow me to navigate between different stages/area of focus

### Topic MOC
For broad area of topic of interest, example "Artificial Intelligence". I can create MOC that capture various subtopics within AI. The MOC can link to machine learning, nlp, computer vision, etc

Person can be also considered MOC and then I can also link the logs into the Person MOC like 1-1 or catch ups (have the latest snapshot of info for 1-1 or person)

### Learning MOC
For self-directed learning, create Learning MOC to track progress and organise the study materials. The MOC can include links to notes on books, online courses, articles, tutorials, etc

### Reference MOC
Used for reference materials like research papers, then you can create this as central index. Can also use this to maintain bunch of manuals (similar to Index file)

### Main MOC
Main MOC can be considered the main/home page. You can think of it as atlas or a guide on where do you want to go. This is implemented in [[🏡 Home]]

## Note associations
Prior to this I tried tags and linked related topics in the note but then quickly realised as I go deeper into a specific topic, the amount of reference pointing back to them is so huge (example: Kafka or Kafka Streams) and visiting that page and looking at the 100 over files backlinks to them is quite pointless as I won't be able to keep up with so many files

I then read up more on Andy Matuschak's note about [tags are an ineffective association structure](https://notes.andymatuschak.org/Tags_are_an_ineffective_association_structure) and I learned quickly more about this. Namely:
- One should [prefer fine-grained associations](https://notes.andymatuschak.org/zS27HJzP3uD366crN7PYDQU). Having associations can be fine-grained or coarse-grained. Fine-grained is something like having link in the middle of the sentence whereas coarse-grained is something akin to "See also" header. I found that coarse-grained associations is more relevant than topics/tags
- [Prefer labeled associations](https://notes.andymatuschak.org/zRaJxQBJgbD5wgRYLoqTpa3). This is basically the same as fine-grained associations. Instead of saying "topic X is related to topic Y", have a link saying that "topic X goes into more detail about topic Y". It has a clearer associations and easier to understand
- [Prefer explicit associations to inferred associations](https://notes.andymatuschak.org/z8Ubad66AWp7ZLShUmRu3vu?). This forces you to think carefully the associations between notes instead of simply blindly associate notes without much context/relevance. By doing this it is also ensure that the association is high quality because it's done explicitly with more thoughts. Another reason doing this is that your terminology changes over time as you grow older and gain more knowledge

With this in mind, I basically remove "Topics" and "Tags" from my notes and only have an optional coarse-grained associations ("See also"). All the notes must be linked together somehow and this makes having [[#MOC (Maps of Content)]] even more critical

## Note template
Previously I added some metadata like date and topics in the template but I also feel like this doesn't really add much value and creates more friction. After reading the forum post on [metadata minimalism](https://forum.obsidian.md/t/principles-for-metadata-minimalism/11379/5) it really resonates with me

So what I decide is that I have the following note template
- standard note: no template at all. note status is in tag and I can just dump the tag anywhere in the note - perhaps at the footer or header
- project note template: this will have metadata like start date, end date, and goals
- log based note: no template except that all dates are stored in header 2 and good to have short single line summary of the day on the same headers this way all headers can be collapsed and still have a glimpse on what’s the takeaway daily
- health log template: this used to keep track of kids health log as before

Actual template design is described in details at [[Note Templates]] page

> [!question] What about Obsidian properties
> Properties is also a good option for the structured notes like for project/course but I still find it adds too much ceremony and not much value with the current flow

## Note status
As defined in [[Tags]] I only have 3 officially recognised tags
- Any incomplete notes should have `#todo` tag attached to the note. It can be anywhere, but usually better to be in the first line
- Completed/cancelled/archived note should have `#archived` tagged to the first line of the note
- Some notes may have an `#ongoing` tag if it's still not yet completed (e.g. ongoing sickness)

## Note taxonomy
Inspired from Andy Matuschak's approach, I further split my note into multiple types and this includes the three note types from [PARA](https://fortelabs.com/blog/para/)
- Ephemeral scratching in daily log where it's stored in `yyyy-mm-dd` file. By right all of this files should be empty and stored in `Daily Notes` directory and any unprocessed is captured in [[📥 Inbox]]
- [[#Evergreen Notes]] for the main knowledge notes. File name should be descriptive, think of an API
- Log based notes for things like meeting notes, health log, 1-1's, etc
- [[#MOC (Maps of Content)]] files for things like project notes, areas/resources

## Note file naming
Consistent file naming is crucial to keep things consistent and easily searchable. See [[Note file naming]] for more details

## Logs
### [[2026-02-25]]
- Updated evergreen notes to relax the requirement on the content as well as the note title
- Removed MOC examples and PARA section as those are not needed

## References
- [Johnny.Decimal](http://johnnydecimal.com)
- [PARA](https://fortelabs.com/blog/para/)
- [Evergreen Notes](https://notes.andymatuschak.org/About_these_notes?stackedNotes=z4SDCZQeRo4xFEQ8H4qrSqd68ucpgE6LU155C)
- [Taxonomy of note types](https://notes.andymatuschak.org/About_these_notes?stackedNotes=z4SDCZQeRo4xFEQ8H4qrSqd68ucpgE6LU155C&stackedNotes=z5aJUJcSbxuQxzHr2YvaY4cX5TuvLQT7r27Dz&stackedNotes=z6f6xgGG4NKjkA5NA1kDd46whJh2Gt5rAmfX)
- [LYT Kit (Linking Your Thinking)](https://notes.linkingyourthinking.com/Cards/%2B+Start+Here)