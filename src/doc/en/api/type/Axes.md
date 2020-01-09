# Summary
Represents a set of coordinate axes that are considered active.

# Constructors

## `Axes.new(components: ...Variant)`
All components of Axes are initialized to false. A variable list of arguments is
received, but only the first 6 arguments are traversed. When an
[Axis](enum:Axis) or [NormalId](enum:NormalId) value is received, the component
of Axes corresponding to the value is set to true. Other values are ignored.

Value                                        | Component
---------------------------------------------|----------
[Enum.Axis.X](enum:Axis/X)                   | Enables the [X](#doc-field-X) component.
[Enum.Axis.Y](enum:Axis/X)                   | Enables the [Y](#doc-field-Y) component.
[Enum.Axis.Z](enum:Axis/X)                   | Enables the [Z](#doc-field-Z) component.
[Enum.NormalId.Right](enum:NormalId/Right)   | Enables the [X](#doc-field-X) component.
[Enum.NormalId.Top](enum:NormalId/Top)       | Enables the [Y](#doc-field-Y) component.
[Enum.NormalId.Back](enum:NormalId/Back)     | Enables the [Z](#doc-field-Z) component.
[Enum.NormalId.Left](enum:NormalId/Left)     | Enables the [X](#doc-field-X) component.
[Enum.NormalId.Bottom](enum:NormalId/Bottom) | Enables the [Y](#doc-field-Y) component.
[Enum.NormalId.Front](enum:NormalId/Front)   | Enables the [Z](#doc-field-Z) component.

# Fields

## `Back: boolean`
Whether the back face is enabled. Corresponds to the Z axis.

## `Bottom: boolean`
Whether the bottom face is enabled. Corresponds to the Y axis.

## `Front: boolean`
Whether the frony face is enabled. Corresponds to the Z axis.

## `Left: boolean`
Whether the left face is enabled. Corresponds to the X axis.

## `Right: boolean`
Whether the right face is enabled. Corresponds to the X axis.

## `Top: boolean`
Whether the top face is enabled. Corresponds to the Y axis.

## `X: boolean`
Whether the X axis is enabled.

## `Y: boolean`
Whether the Y axis is enabled.

## `Z: boolean`
Whether the Z axis is enabled.
