# Summary
Controls the behavior of [BasePart](class:BasePart) SurfaceInputs.

# Details
InputType determines how the ParamA and ParamB properties of a BasePart are
used.

# Members

## NoInput
Causes a surface motor to remain stationary.

## Constant
Causes a surface motor to rotate at a constant velocity.

### Details
The angular velocity of the rotation is calculated according to the following
formula (in radians):

	ParamB * math.rad(31)

## Sin
Causes a surface motor to rotate according to a sine wave.

### Details
The angular velocity of the rotation is calculated according to the following
formula (in radians):

	ParamA * math.sin(time() * ParamB) * math.rad(31)

## Throtle
Replaced by Throttle.

## Action3
Performs Action3.

### Details
Action3 does something. Who knows what.

