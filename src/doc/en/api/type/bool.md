# Summary
A type for representing a Boolean value.

# Details
The bool type is used to signal one of two distinct options (either `true` or
`false`). Its semantics vary widely depending on the context.

# Examples
[FindFirstChild](class:Instance/FindFirstChild) has a boolean argument,
*recursive*. When `true`, the method operates recursively:

```lua
local folder = Instance.new("Folder")
local middle = Instance.new("Folder", folder)
middle.Name = "Middle"
local inner = Instance.new("Folder", middle)
inner.Name = "Inner"

print(folder:FindFirstChild("Inner", false))
--> nil

print(folder:FindFirstChild("Inner", true))
--> Inner
```
