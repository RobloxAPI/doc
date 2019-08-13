# Summary
Represents a set of the six sides of a box that are considered active.

# Details

## Constructors

### `Faces.new(...)`
All components of Faces are initialized to false. A variable list of arguments
is received. The first 6 arguments are traversed, and when a
[NormalId](enum:NormalId) value is encountered, the component of Faces
corresponding to the value is set to true. Other values are ignored.

Value                                        | Component
---------------------------------------------|----------
[Enum.NormalId.Right](enum:NormalId/Right)   | Enables the [Right](#doc-right) component.
[Enum.NormalId.Top](enum:NormalId/Top)       | Enables the [Top](#doc-top) component.
[Enum.NormalId.Back](enum:NormalId/Back)     | Enables the [Back](#doc-back) component.
[Enum.NormalId.Left](enum:NormalId/Left)     | Enables the [Left](#doc-left) component.
[Enum.NormalId.Bottom](enum:NormalId/Bottom) | Enables the [Bottom](#doc-bottom) component.
[Enum.NormalId.Front](enum:NormalId/Front)   | Enables the [Front](#doc-front) component.

## Components

### Right
A boolean indicating whether the Right face is enabled.

### Top
A boolean indicating whether the Top face is enabled.

### Back
A boolean indicating whether the Back face is enabled.

### Left
A boolean indicating whether the Left face is enabled.

### Bottom
A boolean indicating whether the Bottom face is enabled.

### Front
A boolean indicating whether the Front face is enabled.

