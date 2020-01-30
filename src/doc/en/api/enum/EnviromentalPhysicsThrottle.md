# Summary
Determines how physics simulation is throttled. 100% is the normal simulation
rate.

# Members

## DefaultAuto
Throttling determined dynamically.

### Details
Throttling is determined by the amount of work required to simulate physics. For
heavy simulations, smoother framerates are maintained at the cost of a slower
simulation.

## Disabled
Throttling is 100%.

## Always
Throttling is 0%.

## Skip2
Throttling is 50%.

## Skip4
Throttling is 25%.

## Skip8
Throttling is 12.5%.

## Skip16
Throttling is 6.25%.
