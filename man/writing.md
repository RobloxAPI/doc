# Writing documents
This page provides a guideline for writing and formatting documents.

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

## Formatting
For writing and editing documents, a text editor that supports Markdown is
recommended. A monospace font is recommended.

In general, the plain text itself should be readable and presentable, as though
it were a final rendering of the document. For this reason, simple text and
formatting should be strived for.

### Syntax
Documents are formatted with [Markdown][markdown]. In cases where multiple
styles are available, the following styles are preferred:

- `*text*` for italic text.
- `**text**` for bold text.
- `## Name` for headings (ATX-style). In particular, setext-style headings
  should be avoided.
- `-` for unordered lists.
- `1.` for ordered lists.
- `----` for horizontal rules.

Several extensions to regular Markdown are allowed:

- `` ``` `` for fenced code blocks. Directly after the first set of backticks, a
  language may be specified for syntax highlighting (e.g. `` ```lua``).
- Simple tables may be created with the following format:

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

- The `## Heading {#heading-id}` syntax may be used to specify heading
  identifiers explicitly. Generally, this syntax should be avoided, but may be
  necessary for certain unusual formats. The [Headings](#user-content-headings)
  section describes how identifers are generated automatically.
- Markdown should be used when possible, but HTML elements may be used directly,
  if needed.
- Generally, text should be wrapped to 80 characters. Exceptions include HTML
  elements, or lines containing inline links with long URLs (in this case, it
  may be better to use a reference-style link).
- Tabs must be used for indentation. There is no required tab length (although 4
  is recommended), so text alignment involving tabs must be avoided.
- Trailing whitespace (whitespace at the end of lines) must not be present
  within documents.
- Newlines must be in UNIX format (`\n` rather than `\r\n`).
- A document must have one trailing newline at the end of the file.

Review your text editor settings or extensions for options to enforce these
rules.

### Links
In order to decouple documents from a particular rendering, several URI schemes
are defined for referring to other documents or resources. The non-scheme
portion of the URI is a path that should be URL-escaped if needed. A URI may
also have a fragment (starting after `#`) that indicates an identifier with the
section pointed to by the path.

<dl>

<dt><code>res:$PATH</code></dt>
<dd>

Refers to a file located in the resource directory. `$PATH` is a relative file
path (e.g. `image.png`).

</dd>

<dt><code>class:$CLASS</code></dt>
<dd>

Refers to a class document. `$CLASS` is the name of a class entity.

</dd>

<dt><code>class:$CLASS/$MEMBER</code></dt>
<dd>

Refers to a member within a class document. `$CLASS` is the name of a class
entity. `$MEMBER` is the name of a member entity within the class.

</dd>

<dt><code>enum:$ENUM</code></dt>
<dd>

Refers to an enum document. `$ENUM` is the name of an enum entity.

</dd>

<dt><code>enum:$ENUM/$MEMBER</code></dt>
<dd>

Refers to a member (enum item) within an enum document. `$ENUM` is the name of
an enum entity. `$MEMBER` is the name of an enum item entity within the enum.

</dd>

<dt><code>type:$TYPE</code></dt>
<dd>

Refers to a data type document. `$TYPE` is the name of a type entity.

</dd>

<dt><code>member:$MEMBER</code></dt>
<dd>

Refers to a member within the current document. `$MEMBER` is the name of a
secondary entity within the primary entity of the current document.

</dd>

<dt><code>article:$NAME</code></dt>
<dd>

Refers to an article document. `$NAME` is the name of the article.

</dd>

</dl>

The usual `http` URL scheme is allowed for external references (note that
`https` is preferred, when available).

If an entity name is too unwieldy for linking to within a document, then
reference links may be used. The reference should be placed at the top of the
section of the referred entity.

For example:
```markdown
## Changed
A link to [GetPropertyChangedSignal][GPCS].

## GetPropertyChangedSignal
[GPCS]: member:GetPropertyChangedSignal

Description of GetPropertyChangedSignal...
```

More generally, a local reference (within the same document) should be placed at
the top of the referred section.

External references are placed based on where they're used. If such a reference
is used throughout the entire document, then it should be placed at the bottom
of the document. If it is used only within a single section, then it may be
placed at the bottom of that section.

Excessive linking should be avoided. If an entity is referred to multiple times,
then only first reference needs to be linked. On the other hand, sparse linking
should also be avoided.

To decide whether a reference should be linked, consider how the reader will
view the content. That is, if a reader can jump directly to a particular
section, then the first occurrence of the reference, in relation to that
section, should be linked. This is because the reader will have skipped over any
previous content, and so will have missed a previous link of that reference.

For example:

```markdown
## ChildAdded
This section refers to [Parent](member:Parent). A second reference to Parent is
made, but it is not linked.

## ChildRemoving
This section also refers to [Parent](member:Parent). It is also linked despite
being the third reference in this document, because a reader is able to jump
directly to this section.
```

Generally, treat *only* the following sections as if they can be jumped to
directly:

- The Summary section of a primary entity.
- The Details section of a primary entity.
- The Examples section of a primary entity.
- The section of a secondary entity.

This rule is not absolute. It may be worth linking a reference if the section is
long and detailed enough to have subsections, or if the subject has changed and
the reference hasn't appeared recently.

### Headings
Headings generated by a document can be linked to. The identifier is derived
from the heading name as follows:
- Characters that aren't a letter or digit are converted to dashes (`-`).
- Dashes are collapsed.
- ID is converted to lowercase.
- ID is prefixed with `doc-`. Includes identifiers defined explicitly.
- Multiple occurrences of an ID are suffixed with `-N`, where in `N` is a number
  indicating the Nth occurrence of the ID (the first ID does not have the
  suffix).

For example, to link to the first "Foo Bar" heading:

	[Foo Bar](#doc-foo-bar)

The second "Foo Bar" heading:

	[Foo Bar](#doc-foo-bar-2)

When creating new headings, other occurrences of headings with the same name in
the document should be considered, as well as links to those headings; the
heading number within a link may have to be adjusted.

### Member parameters
Any time a member parameter is referred to, *italics* must be used. To avoid
confusion, italics should be used *only* for parameters. The capitalization of
the parameter must be as given by the API, even at the start of sentences.

```markdown
## FindFirstChild
*name* matches the Name of the child to be found. *recursive* expands the search
to all descendants.
```

Within a member section, a parameter given by name refers to a parameter of the
current member. If a parameter on another member needs to be referred to, use
language that links it to the referred member. e.g. rather than just "*name*",
use "the *name* argument of FindFirstChild".

## Sections
Regardless of file type, all documents have their own structure. In general, a
document consists of **sections**, which in turn may contain their own
subsections. A **top-level** section is at the root of a document, and has no
parent section.

For Markdown, headings are used to delimit sections.

Every entity document should strive to have the following sections, in order:

- Summary
- Details
- Examples

### Summary
The Summary top-level section contains a short description of the entity. The
very first sentence should provide an adequate summary on its own, as it may be
extracted and displayed in isolation.

The summary may contain more than one sentence, or even multiple paragraphs, but
it should only provide a quick overview of the entity.

The Summary heading may be omitted; when a section named "Summary" cannot be
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

For the top-level summary, retaining the summary heading is preferred. For
subsection summaries, the heading should be omitted.

### Details
The Details top-level section provides absolutely all information about the
entity.

Information should never be removed. If the entity changes, the change should be
documented. The main body should contain the current behavior, while previous
behavior is documented elsewhere.

Common subsection may include:

- **Bugs**: Definite problems with the entity, to the degree that they are
  likely to be fixed in the future.
- **Changes**: Changes to the entity. Previous behavior, along with the date or
  version of change.

### Examples
The Examples top-level section contains usable examples of the entity, usually
in the form of code snippets.

An example should strive to be useful; it should be tailored specifically to the
entity, demonstrating its capabilities. Ideally, it should not be possible to
just swap out the entity with another.

An example should be stand-alone; it should be possible to copy the example and
run it in the Studio's command bar, or within a script. For complex examples
were this isn't possible, prerequisites, instructions, or attachments should be
provided.

### Members
Depending on the type, a primary entity may have a fourth top-level section,
called "Members". This contains documentation for each secondary entity
belonging to the primary entity.

Each direct subsection of Members corresponds to a secondary entity. The name of
the section is the name of the entity. Subsections of this section are the usual
Summary, Details, and Examples, as described above.

Direct subsections of the Members section should be ordered by name.

```markdown
# Members
## ChildAdded
Summary of ChildAdded.

### Details
Details of ChildAdded.

## ChildRemoved
Summary of ChildRemoved.

### Details
Details of ChildRemoved.
```

### Struct data types
Data types like `Vector3` and `CFrame` are **struct** types. Documents
describing struct types have several additional sections. Every such document
should strive to have the following sections, in order:

- Summary
- Details
- **Constructors**
- **Fields**
- **Methods**
- **Operators**
- Examples

Each additional section lists the components of the data type. Subsections
describe a single component, and have a particular format. The heading name is a
**type declaration**. The [Type declarations](typedec.md) page describes how
type declarations are formatted.

```markdown
## `Lerp(goal: CFrame, alpha: number): CFrame`
```

Because of the unusual naming scheme, such headings are parsed in a particular
way to generate consistent identifiers. For an identifier to be properly
generated, the syntax of the heading must be correct, and the heading must be
under the proper section.

Subsections of a component section are the usual Summary, Details, and Examples,
as described previously.

#### Constructors
The Constructors top-level section lists the type's constructor functions.

Each function name must be described with the name of the type. That is,
`CFrame.new()` instead of just `new()`.

If a constructor returns a value of the current type, then the return type may
be omitted in the declaration (`CFrame.new()` instead of `CFrame.new():
CFrame`).

The identifier of a heading begins with `ctor-` followed by the case-sensitive
name of the constructor. When a constructor has multiple definitions, the names
of each argument are also appended.

```markdown
# Constructors
## `CFrame.new()`
## `CFrame.new(position: Vector3)`
## `CFrame.new(position: Vector3, lookAt: Vector3)`
## `CFrame.new(x: number, y: number, z: number)`
## `CFrame.Angles(rx: number, ry: number, rz: number)`
```

In a final rendering, these would produce the following identifiers:
- `doc-constructors`
- `doc-ctor-new`
- `doc-ctor-new-position`
- `doc-ctor-new-position-lookAt`
- `doc-ctor-new-x-y-z`
- `doc-ctor-new-rx-ry-rz`
- `doc-ctor-Angles`

#### Fields
The Fields top-level section lists the fields of the type.

The identifier of a heading begins with `field-` followed by the case-sensitive
name of the field.

```markdown
# Fields
## `X: number`
## `Y: number`
## `Z: number`
## `Position: Vector3`
## `LookVector: Vector3`
```

In a final rendering, these would produce the following identifiers:
- `doc-fields`
- `doc-field-X`
- `doc-field-Y`
- `doc-field-Z`
- `doc-field-Position`
- `doc-field-LookVector`

#### Methods
The Methods top-level section lists the methods of the type.

The identifier of a heading begins with `method-` followed by the case-sensitive
name of the method.

```markdown
# Methods
## `Inverse(): CFrame`
## `Lerp(goal: CFrame, alpha: number): CFrame`
## `ToWorldSpace(cf: CFrame): CFrame`
## `ToObjectSpace(cf: CFrame): CFrame`
```

In a final rendering, these would produce the following identifiers:
- `doc-methods`
- `doc-method-Inverse`
- `doc-method-Lerp`
- `doc-method-ToWorldSpace`
- `doc-method-ToObjectSpace`

#### Operators
The Operators top-level section lists the operators of the type.

Each operator has its own syntax. Generally, the name of the type is used with
the operator, along with any other operands, if applicable, followed by the type
of the resulting value. In particular, the syntax of the `call` operator is the
same as the method syntax.

The identifier of a heading begins with `op-` followed by the metamethod name,
then the other operand, if applicable.

```markdown
Identifiers on binary operators use the second operand.
## `Type + Operand : Result`  <!-- ID: doc-op-add-Operand -->
## `Type - Operand : Result`  <!-- ID: doc-op-sub-Operand -->
## `Type * Operand : Result`  <!-- ID: doc-op-mul-Operand -->
## `Type / Operand : Result`  <!-- ID: doc-op-div-Operand -->
## `Type % Operand : Result`  <!-- ID: doc-op-mod-Operand -->
## `Type ^ Operand : Result`  <!-- ID: doc-op-pow-Operand -->
## `Type .. Operand : Result` <!-- ID: doc-op-concat-Operand -->
## `Type == Operand`          <!-- ID: doc-op-eq-Operand -->
## `Type < Operand`           <!-- ID: doc-op-lt-Operand -->
## `Type <= Operand`          <!-- ID: doc-op-le-Operand -->

Identifiers on other operators have no extra information.
## `-Type : Result`            <!-- doc-op-unm -->
## `#Type : Result`            <!-- doc-op-len -->
## `Type[Operand] : Result`    <!-- doc-op-index -->
## `Type[OperandA] = OperandB` <!-- doc-op-newindex -->
## `Type(Parameters) : Result` <!-- doc-op-call -->
```

Real example:
```markdown
# Operators
## `CFrame * CFrame : CFrame`
## `CFrame * Vector3 : Vector3`
## `CFrame + Vector3 : CFrame`
## `CFrame - Vector3 : CFrame`
```

In a final rendering, these would produce the following identifiers:
- `doc-operators`
- `doc-op-mul-CFrame`
- `doc-op-mul-Vector3`
- `doc-op-add-Vector3`
- `doc-op-sub-Vector3`

## Grammar
Avoid personal language. Do not speak to the reader ("you") or about the writer
("I").

When writing, consider the difference between *declaring* what an entity must do
and *explaining* what it does. Explanations should be used in regards to API
entities, and declarations should be reserved for user-controlled elements, such
as callback functions.

*Avoid declaring what an entity must do:*

> GetChildren must return an array of the object's children.

*Instead, explain what the entity does:*

> GetChildren returns an array of the object's children.

In particular, the first sentence of a summary should be written with the
subject omitted, as the subject is usually already nearby.

> Returns an array of the object's children.

### Acronyms
Within a document, the first occurrence of an acronym should include its full
form.

> The Roblox application programming interface (API)

Or,

> The Roblox API (application programming interface)

### Event chronology
A Roblox event (RBXScriptSignal) fires in response to some action. The event
should always be described as firing either before or after the action.

For example, PlayerAdded fires *after* a player is added to the game. When a
listener receives the affected Player object, it will already have its parent
set. On the other hand, PlayingRemoving fires *before* the player is removed
from the game. That is, it will also still have a parent when received by a
listener.

### Output messages
Errors, warnings, and other such messages are merely "emitted", rather than
having a specific result such as being "displayed in output". Errors in
particular are usually "thrown", and can be "caught" by `pcall` or coroutines.

## Common terminology
Several terms are defined for use across the entire API documentation body.

<dl>

<dt>object</dt>
<dd>An instance of the current class. For example, a member is described in the
context of a class, so an instance of that class is referred to as "the object".
"The current object" may be used when differentiating between the object and
others. In particular, avoid using "instance", as this already has a specific
definition in the context of the API.</dd>

<dt>member</dt>
<dd>A secondary entity belonging to a class. Distinct from "child", which
involves a hierarchical relationship with another object.</dd>

<dt>user</dt>
<dd>A user of the current entity. Only use specific terms like "developer" when
describing something that applies only to that type of user.</dd>

<dt>game</dt>
<dd>A collection of place files, assets, data stores, settings, stats, active
servers, etc.</dd>

<dt>universe</dt>
<dd>Equivalent to "game". Used where "game" would be ambiguous.</dd>

<dt>place</dt>
<dd>A file containing a single game tree. May also refer to an actively running
job of such.</dd>

<dt>job</dt>
<dd>An active copy of a place running on a peer. Avoid using "instance".</dd>

<dt>player</dt>
<dd>A person playing a game on Roblox.</dd>

<dt>character</dt>
<dd>A player's in-game avatar.</dd>

<dt>peer</dt>
<dd>A program that runs Roblox, or the device on which such a program runs.</dd>

<dt>client</dt>
<dd>A peer that runs on the player's device.</dd>

<dt>server</dt>
<dd>A peer that serves clients.</dd>

<dt>game tree</dt>
<dd>A complete object hierarchy with a DataModel as its root.</dd>

<dt>DataModel</dt>
<dd>The root object of a game tree. Literally of the <code>DataModel</code>
class. "Workspace", which sometimes occurs in the wild, must not be used for
this.</dd>

<dt>developer</dt>
<dd>A person who develops games on Roblox.</dd>

<dt>engineer</dt>
<dd>A person who develops Roblox.</dd>

<dt>Remote</dt>
<dd>Referring to both RemoteFunctions and RemoteEvents. Should be
capitalized.</dd>

<dt>Bindable</dt>
<dd>Referring to both BindableFunctions and BindableEvents. Should be
capitalized.</dd>

<dt>save</dt>
<dd>To store a place, model, or other asset locally on the user's device.</dd>

<dt>publish</dt>
<dd>To upload a place, model, or other asset to Roblox.</dd>

</dl>
