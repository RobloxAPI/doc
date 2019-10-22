# Manual of Style
This project aims to provide documentation for the [Roblox][roblox] Lua
application programming interface (API). This directory contains the **manual**,
or documentation for the project itself. It introduces concepts, values, and
goals for the project, and provides guidelines and workflow for writing API
documents.

[roblox]: https://corp.roblox.com/

## Contents
- [File structure](files.md): How project files are structured.
- [Stages](stages.md): How work on documentation is motivated.
- [States](states.md): Classification of document and entity progress.
- [Branches](branches.md): How branches are used in this repository.
- [Writing](writing.md): Guidelines for writing documents.
- [Resources](resources.md): How to handle resource files.
- [Type declarations](typedec.md): Format of type declarations in documents.
- [Contributing](/CONTRIBUTING.md): Information about contributing to the
  project.

## Terminology
This section defines several terms, which are used throughout the manual (but
not necessarily throughout the API documentation).

- An **entity** is a unit or piece of the API. For example, class, property,
  enum, or data type.
- A **primary entity** is defined in relation to no other entities.
- A **secondary entity** belongs to a primary entity; it can only be referred to
  in relation to that entity.
- The **entity type** indicates the kind of entity. This is used to disambiguate
  the names of primary entities. For example, the API has a Platform *class*, as
  well as a Platform *enum*.

	Primary entities:

	Entity     | Type  | Examples
	-----------|-------|---------
	Classes    | class | `Instance`, `Workspace`, `Model`, `BasePart`
	Enums      | enum  | `NormalId`, `Material`, `KeyCode`
	Data Types | type  | `int`, `string`, `Vector3`, `CFrame`

	Secondary entities:

	Entity     | Primary type | Examples
	-----------|--------------|---------
	Properties | class        | `Instance.Name`, `BasePart.Position`
	Functions  | class        | `Humanoid.MoveTo`, `GuiObject.TweenPosition`
	Events     | class        | `Sound.Played`, `AnimationTrack.KeyframeReached`
	Callbacks  | class        | `BindableFunction.OnInvoke`, `MarketplaceService.ProcessReceipt`
	Enum items | enum         | `NormalId.Front`, `Material.Water`.

- A **document** is a file that describes entities. A single document describes
  a single primary entity, along with all of its secondary entities.
- An entity's or document's **state** describes how complete it is. See
  [states](states.md) for more information.
- A **stage** refers to the current motivation of a document, or for the project
  overall. See [stages](stages.md) for more information.
