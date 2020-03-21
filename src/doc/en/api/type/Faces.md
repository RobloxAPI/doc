# Summary
Represents a set of the six sides of a box that are considered active.

# Constructors

## `Faces.new(faces: ...Variant)`
All components of Faces are initialized to false. A variable list of arguments
is received, but only the first 6 arguments are traversed. When a
[NormalId](enum:NormalId) value is received, the component of Faces
corresponding to the value is set to true. Other values are ignored.

Value                                        | Component
---------------------------------------------|----------
[Enum.NormalId.Right](enum:NormalId/Right)   | Enables the [Right](#doc-field-Right) component.
[Enum.NormalId.Top](enum:NormalId/Top)       | Enables the [Top](#doc-field-Top) component.
[Enum.NormalId.Back](enum:NormalId/Back)     | Enables the [Back](#doc-field-Back) component.
[Enum.NormalId.Left](enum:NormalId/Left)     | Enables the [Left](#doc-field-Left) component.
[Enum.NormalId.Bottom](enum:NormalId/Bottom) | Enables the [Bottom](#doc-field-Bottom) component.
[Enum.NormalId.Front](enum:NormalId/Front)   | Enables the [Front](#doc-field-Front) component.

# Fields

## `Right: boolean`
A boolean indicating whether the Right face is enabled.

## `Top: boolean`
A boolean indicating whether the Top face is enabled.

## `Back: boolean`
A boolean indicating whether the Back face is enabled.

## `Left: boolean`
A boolean indicating whether the Left face is enabled.

## `Bottom: boolean`
A boolean indicating whether the Bottom face is enabled.

## `Front: boolean`
A boolean indicating whether the Front face is enabled.

# Operators

## `Faces == Faces`
Determines whether two Faces values are equal.

### Details
A Faces value is equal to another Faces value if their Right, Top, Back, Left,
Bottom, and Front fields are equal.
