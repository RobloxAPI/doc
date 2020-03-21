# Summary
Represents a color in the RGB color model.

# Constructors

## `Color3.new(r: number?, g: number?, b: number?)`
Returns a Color3 whose components correspond to the given parameters.

### Details
Each parameter defaults to 0.

Each parameter has an [unconstrained interval][uintv] of [0, 1].

## `Color3.fromRGB(r: number?, g: number?, b: number?)`
Returns a Color3 whose components correspond to the given parameters.

### Details
Each parameter defaults to 0.

Each parameter has an [unconstrained interval][uintv] of [0, 255].

## `Color3.fromHSV(hue: number, saturation: number, value: number)`
Returns a Color3 whose components are derived from the given *hue*,
*saturation*, and *value* parameters.

### Details
Each parameter has an [unconstrained interval][uintv] of [0, 1].

# Fields

## `R: number`
The red component of the color.

### Details
The field has an [unconstrained interval][uintv] of [0, 1].

## `G: number`
The green component of the color.

### Details
The field has an [unconstrained interval][uintv] of [0, 1].

## `B: number`
The blue component of the color.

### Details
The field has an [unconstrained interval][uintv] of [0, 1].

# Methods

## `Lerp(goal: Color3, alpha: number): Color3`
Returns a color interpolated linearly between the color and *goal*, according to
*alpha*.

### Details
*alpha* has an [unconstrained interval][uintv] of [0, 1]. Values outside the
interval extrapolate the result. If the color and *goal* are equal, then the
result is always the color.

## `Color3.toHSV(color: Color3): (hue: number, saturation: number, value: number)`
Returns *hue*, *saturation*, and *value* derived from the components of the
given *color*.

# Operators

## `Color3 == Color3`
Determines whether two Color3 values are equal.

### Details
A Color3 is equal to another Color3 if their R, G, and B fields are equal.

[uintv]: article:Intervals#unconstrained
