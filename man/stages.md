# Stages
Due to the vast size of the Roblox Lua API, work is divided into a number of
**stages**. Stages apply to each document individually. For a document to move
on to the next stage, each entity within the document must satisfy the
**conditions** of the current stage. A document containing entities that do not
yet satisfy conditions of the document's current stage is referred to as a
**partial** document. See the [branches](branches.md) document for information
about how partial documents are managed.

Each stage also has a **life cycle**, which describes generally how content
should be produced and submitted.

Stages also apply to the entire project itself, which gives it focus overall.
Once a particular document satisfies the conditions of the project's current
stage, rather than moving on to the next stage for the document, the writer
should begin focusing on other documents. When most or all documents satisfy the
current stage, the project can move on to the next stage.

*The project is currently in **Stage 1: Words***

## Stage 1: Words
The purpose of this stage is to provide the meat of the reference. Entities must
be described. Lots of words must be written. Descriptions of behaviors must be
verified for accuracy.

Occasionally, media works better than words. If it takes significantly more
effort to write a description than it does to take a screenshot, it's okay to
just take a screenshot.

**Conditions**: All entities within a document must have a summary and a
detailed description. Behaviors must be verified and described accurately.

**Life cycle**:
1. Make. Write words. Describe the behavior of entities. Verify the correctness
   of these descriptions.
2. Refine. Submit the content for review. Allow others to verify correctness,
   improve wording, and so on. Refine the content until it is pristine.
3. Merge. Deploy the content to the website.

## Stage 2: Garnish
The purpose of this stage is to enhance descriptions with images, video, audio,
and so on, as needed. Most entities will not require media, and a lot of media
will end up being more appropriate as examples, so this stage should be a lot
shorter than others.

**Conditions**: All entities within a document must be evaluated for the
inclusion of media. For entities deemed appropriate, media is produced and
included in the document.

**Life cycle**:
1. Deliberate. For large media, submit a description of the content before
   producing it. Allow others to share their input. (i.e. Don't spend hours
   producing a video only to have it rejected.)
2. Produce. Create the content. Take a screenshot. Shoot a video. Record audio.
3. Refine. Submit a rough cut for review. Allow others to make suggestions on
   details. Refine until pristine. Render the final cut.
4. Merge. Deploy the content to the website.

## Stage 3: Examples
The purpose of this stage is to fill in the final section of each item:
Examples.

**Conditions**: All entities with a document must have at least one example
which satisfies the requirements defined in the [guidelines](GUIDELINES.md).

**Life cycle**:
1. Make. Write code. Take screenshots. Create attachments. For large media,
   follow the Stage 2 life cycle.
2. Refine. Submit the content for review. Allow others to verify correctness,
   improve wording, and so on. Refine the content until it is pristine.
3. Merge. Deploy the content to the website.

## Future Stages: Expansion
*The other aspects of documentation*

This stage addresses the fact that a reference is only one aspect of a complete
documentation suite:

- Reference: information-oriented
- **Tutorials**: learning-oriented
- **Guides**: problem-oriented
- **Discussions**: understanding-oriented

The planning of this stage is currently incomplete.
