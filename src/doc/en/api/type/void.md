# Summary
A stand-in representing no type.

# Details
The void type is used within the API as the return type of a function to
indicate that no value is returned.

# Examples
Show that void represents no value, opposed to a nil value.

```lua
local value = Instance.new("BoolValue")
print(type(value:FindFirstChild("")))
--> nil
print(type(value:Destroy()))
--> bad argument #1 to 'type' (value expected)
```
