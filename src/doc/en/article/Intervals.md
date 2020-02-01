# Intervals
A numeric type may be described as having an **interval**. This indicates that
the value lies between a lower and upper bound.

The notation `(l, u)` indicates an **open** interval, where neither the lower or
upper bounds are included (`l` is the lower bound, and `u` is the upper bound).
The notation `[l, u]` indicates a **closed** interval, where both the lower and
upper bound are included within the interval. `(l, u]` is a **half-open**
interval, where the lower bound is excluded, but the upper bound is included.
`[l, u)` is also half-open, except the lower bound is included, and the upper
bound is excluded.

Notation | Expression          | Term
---------|---------------------|-----
(l, u)   | `l < N and N < u`   | Open
[l, u)   | `l <= N and N < u`  | Half-open
(l, u]   | `l < N and N <= u`  | Half-open
[l, u]   | `l <= N and N <= u` | Closed

For example, the `math.random` function returns a random number within the
interval [0, 1). That is, the result will be between 0 and 1, and may be 0, but
will never be 1.

## Constraints
A type may also be described as having a "constrained", "clamped", or "enforced"
interval. This indicates how values outside the interval are handled.

To illustrate each kind of constraint, imagine a "Lerp" function that receives
the two inputs *x* and *y*, as well as an *alpha* parameter. The function
returns a number that is the linear interpolation of *x* to *y*, according to
*alpha*.

	Lerp(x: number, y: number, alpha: number): number

### Unconstrained
An **unconstrained interval** indicates that the effective values of the number
lie between the specified interval, but values outside the interval can still
affect the result.

Consider the following definition of the Lerp function:

	function Lerp(x, y, alpha)
		return (1 - alpha) * x + alpha * y
	end

In this definition, *alpha* has the unconstrained interval of [0, 1]. A value
between the interval produces a result between *x* and *y* as expected. However,
a value outside the interval is still valid, and produces an extrapolated
result.

### Clamped
A **clamped interval** indicates that number is constrained to always lie within
the interval. Values less than the lower bound are set to the lower bound, and
values greater than the upper bound are set to the upper bound.

A Lerp function with the **alpha** parameter having a clamped interval of [0, 1]
might look like this:

	function Lerp(x, y, alpha)
		if alpha < 0 then
			alpha = 0
		elseif alpha > 1 then
			alpha = 1
		end
		return (1 - alpha) * x + alpha * y
	end

Certain APIs, such as properties, may allow any value, but produce a result that
is clamped. These are indicated as having an **effective clamped interval**.

For example, the [BasePart.Transparency](class:BasePart/Transparency) property
has an effective clamped interval of [0, 1]. The property can hold any value,
but the actual rendered transparency of the BasePart clamps the value between 0
and 1. This could be compared to [Camera.FieldOfView](class:Camera/FieldOfView),
where the value itself is clamped.

### Enforced
An **enforced interval** indicates that a value outside the interval results in
an error.

A Lerp function with the *alpha* parameter having an enforced interval of [0, 1]
might look like this:

	function Lerp(x, y, alpha)
		if alpha < 0 or alpha > 1 then
			error("alpha is out of bounds", 2)
		end
		return (1 - alpha) * x + alpha * y
	end
