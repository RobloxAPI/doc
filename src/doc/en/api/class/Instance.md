# Summary
The root class of all classes in the API.

# Details

# Members

## AncestryChanged
Fired after the ancestry of the object changes.

## Archivable
Determines whether the object can be serialized.

## Changed
Fired after a property of the object changes.

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
Specifies a value used to identify the object.

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
