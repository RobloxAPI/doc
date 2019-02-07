[DRAFT]

# Guidelines
This document provides guidelines for writing documentation for the
[Roblox][roblox] Lua application programming interface (API).

[roblox]: https://corp.roblox.com/

## Prerequisites

- Writers should be fluent in the language in which they are writing, and should
  have at least an intuitive understanding of the language.
- Writers should be at least moderately familiar with a text editor (opposed to
  a word processor).
- API documentation is written primarily in [Markdown][markdown], of which
  writers should have at least moderate knowledge.
- Writers will benefit from having an unreasonable desire for correctness.

[markdown]: https://daringfireball.net/projects/markdown/

## Languages
Currently, documentation is available in English only, and other languages are
explicitly not provided. This restriction may be relaxed once a majority of
existing documentation can be considered "complete", as this provides a
sufficient reference. Consider the English version a "baseline implementation".

## Terminology
This section defines several terms, which are used throughout this document, but
not necessarily throughout the API documentation.

- An **entity** is a unit or piece of the API. For example, class, property,
  enum, or data type.
- A **primary** entity is defined in relation to no other entities.
- A **secondary** entity belongs to a primary entity; it can only be referred to
  in relation to that entity.
- The entity **type** indicates the kind of entity. This is used to disambiguate
  the names of primary entities.

Primary entities include:

- Classes, type "class"
- Enums, type "enum"
- Data Types, type "type"

Secondary entities include:

- Properties (of class)
- Functions (of class)
- Events (of class)
- Callbacks (of class)
- Enum items (of enum)

Within this document, an element of the form `$VAR` indicates a variable value
within literal content. For example, `class:$CLASS` refers to the literal string
"class:" with a class name appended to it (it could be substituted with
"class:Workspace" or "class:Model", for example).

## Formatting
This section describes requirements and recommendations for formatting the plain
text of documents.

A text editor that supports Markdown is recommended.

A monospace font is recommended.

In general, the plain text itself should be readable and presentable, as though
it were a final rendering of the document. For this reason, writers should
strive for simple text and formatting.

Documents are formatted primarily with Markdown. In cases where multiple styles
are available, the following styles are preferred:

- `*text*` for italic text.
- `**text**` for bold text.
- `## Name` for headings. In particular, the multiline heading style should be
  avoided.
- `-` for unordered lists.
- `1.` for ordered lists.
- `----` for horizontal rules.
- `` ``` `` for code blocks. Directly after the first set of backticks, a
  language may be specified, for syntax highlighting (e.g. `` ```lua``).

Simple tables may be created with the following format:

```markdown
column 1 | column 2 | column 3
---------|----------|---------
cell 1   | cell 2   | cell 3
cell 4   | cell 5   | cell 6
```

column 1 | column 2 | column 3
---------|----------|---------
cell 1   | cell 2   | cell 3
cell 4   | cell 5   | cell 6

Markdown should be used when possible, but HTML elements may be used directly,
if needed.

Generally, text should be wrapped to 80 characters. Exceptions include HTML
elements, or lines containing inline links with long URLs (in this case, it may
be better to use a reference-style link).

Tabs must be used for indentation. There is no required tab length (although 4
is recommended), so text alignment involving tabs must be avoided.

Trailing whitespace (whitespace at the end of lines) must not be present within
documents.

Newlines must be in UNIX format (`\n` rather than `\r\n`).

A document must have one trailing newline at the end of the file.

### Links
In order to decouple documents from a particular rendering, several URL schemes
are defined for referring to other documents or resources.

- `res:$PATH`: Refers to a file located in the resource directory.
	- `$PATH` is a relative file path (e.g. `image.png`).
- `class:$CLASS`: Refers to a class document.
	- `$CLASS` is the name of a class entity.
- `class:$CLASS/$MEMBER`: Refers to a member within a class document.
	- `$CLASS` is the name of a class entity.
	- `$MEMBER` is the name of a member entity within the class.
- `enum:$ENUM`: Refers to an enum document.
	- `$ENUM` is the name of an enum entity.
- `enum:$ENUM/$MEMBER`: Refers to a member (enum item) within an enum document.
	- `$ENUM` is the name of an enum entity.
	- `$MEMBER` is the name of an enum item entity within the enum.
- `type:$TYPE`: Refers to a data type document.
	- `$TYPE` is the name of a type entity.
- `member:$MEMBER`: Refers to a member within the current document.
	- `$MEMBER` is the name of a secondary entity within the primary entity of
	  the current document.

The usual `http` URL scheme can be used to refer to external references (note
that `https` is preferred, when available).

## File structure
All documents and related files are located under the `src/` directory.

- `src/`: The root of the document file tree.
- `src/res/`: Resources; embedded images, etc. May contain subdirectories.
- `src/doc/`: Root location of document files.
- `src/doc/$LANG/$TYPE/$PRIMARY.$EXT`
	- `$LANG` is an IETF language tag, indicating the language of the contained
	  documents. For example, `en` represents English.
	- `$TYPE` is the API entity type. There are currently three types:
		- `class`: API class entities. e.g. Instance, Workspace, Model, Part.
		- `enum`: API enum entities. e.g. NormalId, KeyCode, SurfaceType.
		- `type`: API data type entities. e.g. bool, int, Vector3, BrickColor.
	- `$PRIMARY` is the name of a primary API entity.
	- `$EXT` is the file extension. Currently, `.md` for markdown is supported.

Here are some examples:

- `src/doc/en/class/Workspace.md`: Document for the Workspace class in English.
- `src/doc/es/enum/NormalId.md`: Document for the NormalId enum in Spanish.
- `src/doc/de/type/Vector3.md`: Document for the Vector3 type in German.

The combination of `$PRIMARY.$EXT` indicates a file that documents the referred
API entity. For example, `class/Workspace.md` is a markdown file documenting the
Workspace class.

### Sections
Regardless of file type, all documents have their own structure. In general, a
document consists of "sections", which in turn may contain their own
sub-sections. For Markdown, headings are used.

Every entity document should strive to have the following pieces of information:

#### Summary
The Summary section contains a short description of the entity. The very first
sentence should provide an adequate summary on its own, as it may be extracted
and displayed in isolation.

The summary may contain more than one sentence, or even multiple paragraphs, but
it should only provide a quick overview of the entity.

The Summary header may be omitted; when a section named "Summary" cannot be
found, the "orphan" section is used instead. An orphan section is the content
located after the start of the section, and before the start of the first
subsection. For example:

```markdown
# Entity
This content is treated as the summary.

## Details
This content is treated as the details.
```

This is equivalent to:

```markdown
# Entity

## Summary
This content is treated as the summary.

## Details
This content is treated as the details.
```

**Omitting the summary header is preferred.**

#### Details
The Details section provides absolutely all information about the entity.

Information should never be removed. If the entity changes, the change should be
documented. The main body should contain the current behavior, while previous
behavior is documented elsewhere.

Subsections may include:

- **Quirks**: Notable "gotchas", unexpected or unintuitive behaviors that the
  user should be aware of. Not necessarily bugs.
- **Bugs**: Definite problems with the entity, to the degree that they are
  likely to be fixed in the future.
- **Changes**: Changes to the entity. Previous behavior, along with the date of
  change.

#### Examples
The Examples section contains usable examples of the entity, usually in the form
of code snippets.

An example should strive to be useful; it should be tailored specifically to the
entity, demonstrating its capabilities. Ideally, it should not be possible to
just swap out the entity with another.

#### Members
Depending on the type, a primary entity may have a fourth section, called
"Members". This contains documentation for each secondary entity belonging to
the primary entity.

The name of a direct subsection of Members is the name of the secondary entity.
Subsections of this section are the usual Summary, Details, and Examples, as
described above.

Direct subsections of the Members section should be ordered by name.

## Content
This section describes how documentation should be written.

### Grammar

Avoid personal language. Do not speak to the reader ("you") or about the writer
("I").

When writing, consider the difference between *declaring* what an entity must do
and *explaining* what it does. Explanations should be used in regards to API
entities, and declarations should be reserved for user-controlled elements, such
as callback functions.

Avoid declaring what an entity must do:

> GetChildren must return an array of the object's children.

Instead, explain what the entity does:

> GetChildren returns an array of the object's children.

In particular, the first sentence of a summary should be written with the
subject omitted, as the subject is usually already nearby.

> Returns an array of the object's children.

Now consider a callback, which receives API-controlled arguments, and returns
user-controlled values. Observe how the speech changes when referring to each of
these subjects:

> The callback receives two numbers. The callback must return true or false.

### Acronyms
The first occurrence of an acronym should be its full form followed by its
abbreviation.

> The Roblox application programming interface (API)

### Stubs
Avoid empty documents or sections. For example, if a class member does not yet
have documentation, then its name should be omitted from the Members section. If
an entire class has no documentation, then it should have no document file.

### Images
Avoid images containing text. If an image requires explanation, write it near
the image.

### Common terminology
Several terms are defined for use across the entire API documentation body.

- **Object**: An instance of the current class. That is, instead of saying "an
  instance of this class", just say "object". Avoid using "instance".
- **User**: A user of the current entity. Only use specific terms like
  "developer" when describing something that applies only to that type of user.
- **Game**:
- **Place**:
- **Universe**: A game, comprising a set of places.
- **Player**: A person playing a game on Roblox.
- **Character**: A player's in-game avatar.
- **Peer**: A program that runs Roblox, or the device on which such a program
  runs.
- **Client**: A peer that runs on the player's device.
- **Server**: A peer that serves clients.
- **Instance**: An active copy of a place running on a peer. (TODO: find a
  better word for this)
- **Game tree**: the Instance hierarchy that makes up a game.
- **DataModel**: The root of a game tree. Specifically, "workspace" must not be
  used for this.
- **Developer**: A person who develops games on Roblox.
- **Engineer**: A person who develops Roblox.
- **Remote**: Referring to both RemoteFunctions and RemoteEvents.
- **Bindable**: Referring to both BindableFunctions and BindableEvents.
