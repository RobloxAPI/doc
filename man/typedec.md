# Type declarations
This page describes the syntax of a Lua type declaration for use in documents.

Sometimes, a document must provide its own description of a type. For
consistency, this description has a particular format, which is specified by
this page. The format is designed to be intuitive; a reader does not have to
view this page in order to grasp how the type is structured.

## Declaration order
Type declarations have a left-to-right (L2R) syntax, where the type is defined
*after* the name, rather than before. This deviates from formats used by other
documentation, which use a C-like syntax.

To get an idea of the difference, here is a comparison between C and TypeScript:

```c
// C syntax
int name = 42;
```

```typescript
// TypeScript syntax
let name: number = 42;
```

Most modern languages have a L2R syntax, which was determined to be more
beneficial than C. The [Go's Declaration Syntax][blogpost] blog post has more
information.

[blogpost]: https://blog.golang.org/gos-declaration-syntax

## Syntax
A declaration maps a name to a type. Generally, a declaration has the form:

	Name: Type

Where `Name` is the name of the declaration, and `Type` is the value type.

The name may have a qualifier, separated by the dot (`.`) character. Method
declarations should use a colon (`:`) instead.

	math.huge: number
	Instance:GetChildren(): Objects

For API declarations, a type must be the name of a type that exists in the API.
Pure-Lua declarations should use the types that exist in Lua.

	position: Vector3
	math.pi: number

A particular class of the Instance type can be indicated with the `Class.`
prefix. An item of a particular enum can be indicated with the `Enum.` prefix.

	part: Class.BasePart
	surface: Enum.NormalId

### Functions
Function types, which consist of parameters and return values, have their own
syntax:

	Name(Parameters): Returns

Where `Name` is the name of the function, `Parameters` lists each parameter
passed to the function, and `Returns` lists values returned by the function.

#### Parameters
Parameters are separated by commas (`,`). Each parameter is a name paired with a
type.

	CFrame.new(position: Vector3, lookAt: Vector3)

A parameter may be optional. This is indicated by `?` after the type.

	table.insert(list: table, position: int?, value: Variant)

A parameter may have a default value indicated after type with `=` followed by
text describing the value.

	FindFirstChild(name: string, recursive: bool = false)

The last parameter may be variable, indicated by `...` before the type. This
means any number of values of the type.

	coroutine.resume(co: thread, args: ...Variant)

#### Returns
Returns have a similar syntax to parameters, where each value is a name paired
with a type:

	ToEulerAnglesXYZ(): (x: float, y: float, z: float)

There are also several abbreviations. Return values can be unnamed:

	ToAxisAngle(): (Vector3, float)

Parentheses may be omitted for a single, unnamed value:

	GetFullName(): string

Return values may also be variable:

	string.byte(s: string, i: number?, j: number?): ...number
