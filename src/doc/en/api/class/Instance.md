# Summary
The root class of all classes in the API.

# Details

## Hierarchy
Objects are arranged in a tree structure. An object can have zero or more
**child** objects, which are below it in the tree. Conversely, an object can
have at most one **parent** object, which is above it in the tree. The **root**
of a tree can have children, but has no parent. Objects that share the same
parent are referred to as **siblings**.

An **ancestor** is any object that is reachable by repeatedly moving from child
to parent. That is, an ancestor is the parent of an object, or the parent's
parent, and so on, all the way to the root of the tree. A **descendant** is any
object that is reachable by repeatedly moving from parent to child. That is, a
descendant is a child of an object, or a child of the child, and so on.

## References
Whenever Lua accesses an object for the first time, a userdata is created. This
userdata acts as a "proxy" or "bridge" that enables the object to be accessed in
Lua. The userdata will be reused while it exists, and recreated when it doesn't,
which is a process that is meant to be completely opaque to Lua. For all intents
and purposes, the userdata *is* the object. As such, almost no distinction will
be made between the two in this reference.

In regards to garbage collection, Lua's garbage collector has no knowledge of
the object, and does not affect the object in any way. The memory allocated to
the object is managed by a separate, internal system. On the other hand, the
userdata *is* known by the garbage collector, and may therefore be collected
when it has no more strong references in Lua, just as any other Lua value.

It must be noted that an object makes no strong references to its userdata. A
consequence of this is that, when there are only weak references to the
userdata, **the userdata can be garbage collected while the object is still
accessible.** For example, if the userdata's only reference is in a weak table,
and the object is in the game tree, then userdata will be collected, removing it
from the weak table. Despite this, the object still exists in the game tree, and
can be accessed as usual.

# Examples
Demonstration of an object's weak reference behavior. An object's userdata can
be garbage collected while the object is in the game tree.

```lua
-- Table with weak value references.
local weakTable = setmetatable({}, {__mode='v'})

-- Create an object, then add it to the game tree and the weak table.
local object = Instance.new("BoolValue")
object.Parent = workspace
weakTable[1] = object
object = nil -- Remove strong reference to the object.

print("Reference:", weakTable[1])
--> Reference: Value (userdata still exists)

-- Wait until the userdata is collected.
while #weakTable > 0 do
	wait()
end

print("Reference:", weakTable[1])
--> Reference: nil (userdata was collected)

print("Object:", workspace.Value)
--> Object: Value (object still exists)
```

# Members

## AncestryChanged
Fired after the ancestry of the object changes.

### Details
AncestryChanged fires after the [Parent](member:Parent) of the object or any
ancestor has changed. *child* is the object whose Parent has changed, and is
never nil. *parent* is the new value of the Parent, which may be nil.

If changes only to the Parent of the object need to be detected, then
[GetPropertyChangedSignal][GPCS] should be used instead.

AncestryChanged is affected by [parent locking](#doc-locking). Modifying the
Parent of *child* before it has resolved should be avoided.

## Archivable
Determines whether the object can be serialized.

### Details
When Archivable is false, the object will not be included when it is a part of a
place or model that is saved to a file or published to Roblox. The object is
also excluded from being copied with [Clone](member:Clone).

### Examples
Avoid cloning descendants by temporarily setting Archivable.
```lua
function CopyObject(object)
	local children = object:GetChildren()
	local currentState = {}
	for i, child in pairs(children) do
		currentState[i] = child.Archivable
		child.Archivable = false
	end
	local copy = object:Clone()
	for i, child in pairs(children) do
		child.Archivable = currentState[i]
	end
	return copy
end

local part = Instance.new("Part")
part.Name = "Original"
part.Color = BrickColor.Red().Color
local smoke = Instance.new("Smoke", part)
smoke.Archivable = false
Instance.new("Fire", part)
part.Parent = workspace

local copy = CopyObject(part)
copy.Name = "Copy"
copy.Position = Vector3.new(8, 0, 0)
copy.Parent = workspace
```

## Changed
Fired after a property of the object changes.

### Details
*property* is the name of the property that changed. This can be used to index
the object to get the property's new value.

Changed is fired by changes to *all* properties of the object. If only one or a
few properties need to be monitored, [GetPropertyChangedSignal][GPCS] should be
used instead.

For performance reasons, changes to a property made by the physics engine will
not cause Changed to fire. For example, Changed will fire when the
[Position](class:Part/Position) of a [Part](class:Part) is modified by a script,
but will not fire while the part is falling.

#### Bugs
Certain classes have hidden properties that cannot be indexed, but can still
cause Changed to fire. When indexing such an object with *property* unguarded,
using pcall is recommended.

### Examples
Copy changes in appearance from one part to another.
```lua
local appearance = {
	Color        = true,
	Material     = true,
	Reflectance  = true,
	Transparency = true,
}
local original = Instance.new("Part", workspace)
local copy = Instance.new("Part", workspace)
original.Changed:Connect(function(property)
	if not appearance[property] then
		return
	end
	copy[property] = original[property]
end)

original.Position = Vector3.new(8, 0, 0)
original.Color = BrickColor.Blue().Color
```

Safely copy all changes from one part to another.
```lua
local original = Instance.new("Part", workspace)
local copy = Instance.new("Part", workspace)
original.Changed:Connect(function(property)
	local ok, value = pcall(function()
		return original[property]
	end)
	if not ok then
		return
	end
	copy[property] = value
end)

copy.Position = Vector3.new(8, 0, 0)
original.Color = BrickColor.Blue().Color
```

## ChildAdded
Fired after a child is added to the object.

## ChildRemoved
Fired after a child is removed from the object.

## ClassName
Returns the name of the object's class.

## ClearAllChildren
Removes all of the children from the object.

## Clone
Creates a deep copy of the object.

## DataCost
Returns the cost of saving the object to data persistence, in data units.

## DescendantAdded
Fired after a descendant of the object is added.

## DescendantRemoving
Fired before a descendant of the object is removed.

## Destroy
Removes the object and marks it as destroyed, preventing reuse.

## FindFirstAncestor
Returns the first ancestor of the object whose [Name](member:Name) matches the
given name.

## FindFirstAncestorOfClass
Returns the first ancestor of the object whose [ClassName](member:ClassName)
matches the given name.

## FindFirstAncestorWhichIsA
Returns the first ancestor of the object whose class inherits a class of the
given name.

## FindFirstChild
Returns the first child of the object whose [Name](member:Name) matches the given
name.

## FindFirstChildOfClass
Returns the first child of the object whose [ClassName](member:ClassName)
matches the given name.

## FindFirstChildWhichIsA
Returns the first child of the object whose class inherits a class of the given
name.

## GetChildren
Returns a list of the object's children.

## GetDebugId
Returns a value that uniquely identifies the object.

## GetDescendants
Returns a list of all the descendants of the object.

## GetFullName
Returns a name formatted according to the ascendants of the object.

## GetPropertyChangedSignal
[GPCS]: member:GetPropertyChangedSignal

Returns a [signal](type:RBXScriptSignal) that fires after a property of the
given name changes.

## IsA
Returns whether the object's class inherits from a class of the given name.

## IsAncestorOf
Returns whether the object is an ancestor of a given object.

### Details
`nil` can be passed as an argument. Because `nil` is not a real object, and
therefore can never be a child, passing `nil` always returns false.

## IsDescendantOf
Returns whether the object is a descendant of a given object.

### Details
`nil` can be passed as an argument. Because the root of a tree always has a nil
parent, passing `nil` always returns true.

## Name
Specifies a string used to identify the object.

The value of Name is constrained to a maximum length of 100 bytes. On
assignment, extra bytes are truncated.

### Details
While Name is generally used to differentiate between sibling objects, no
attempts to enforce the uniqueness of the value are made.

## Parent
Specifies an object that the current object is a child of.

### Details
An object cannot be its own parent. Attempting to set Parent to the object
results in the following error:

```
Attempt to set OBJECT as its own parent
```

Where `OBJECT` is the [full name](member:GetFullName) of the object.

An object also cannot be a child of one of its descendants. Attempting to set
Parent to a descendant results in the following error:

```
Attempt to set parent of OBJECT to VALUE would result in circular reference
```

Where `OBJECT` is the full name of the object, and `VALUE` is the full name of
the descendant.

#### Locking
After its value is changed, the Parent property is locked, and cannot be
changed. This is to prevent events from recursively firing themselves.
Attempting to set Parent while it is locked fails without throwing an error, and
the following warning is emitted:

```
Something unexpectedly tried to set the parent of OBJECT to NEWVALUE while trying to set the parent of OBJECT. Current parent is VALUE.
```

`OBJECT` is the [Name](member:Name) of the object whose Parent is being
modified. `NEWVALUE` is the Name of the object to which the Parent was attempted
to be set. `VALUE` is the Name of the current parent. "NULL" is used if either
value is nil.

Once all listeners from associated events have resolved, the Parent is unlocked.
A listener is resolved when its thread is either dead or has yielded.

<!-- OBJECT appears twice in the message. Find out if its possible for these two
fragments to be different. -->

## Remove
Removes the object from its parent.

## RobloxLocked
Determines the restrictions of indexing the object.

## WaitForChild
Blocks until an object of the given name is a child of the object.

## archivable
Determines whether the object can be serialized.

## childAdded
Fired after a child is added to the object.

## children
Returns a list of the object's children.

## className
Returns the name of the object's class.

## clone
Creates a deep copy of the object.

## destroy
Removes the object and marks it as destroyed, preventing reuse.

## findFirstChild
Returns the first child of the object whose [Name](member:Name) matches the given
name.

## getChildren
Returns a list of the object's children.

## isA
Returns whether the object's class inherits from a class of the given name.

## isDescendantOf
Returns whether the object is a descendant of a given object.

## remove
Removes the object from its parent.
