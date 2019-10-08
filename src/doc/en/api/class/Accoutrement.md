# Summary
Functions as the container object to an item worn on the head of a [Humanoid](class:Humanoid).

# Details
In order to use the Accoutrement as intended, it must have a child [part](class:BasePart) named "Handle". Upon being parented to the [character model](class:Model) of a Humanoid, the Accoutrement will look for a part named "Head" inside of its parent model. If the head is found, then the Accoutrement's handle will be welded to the top of that head part, offsetted by the [AttachmentPoint](member:AttachmentPoint) defined by the Accoutrement.

If an Accoutrement isn't attached to a character's head, then it creates a [TouchTransmitter](class:TouchTransmitter) in its handle and starts listening for any contacts made with a character. If such a contact occurs, and the character has no Accoutrements attached to it, then the character will equip the Accoutrement automatically.

# Members

## AttachmentForward
Gets or sets the **forward** column of the [AttachmentPoint](member:AttachmentPoint)'s rotation matrix.

## AttachmentPoint
Describes the object-space attachment point of the Accoutrement's Handle, relative to the point it attaches to on a Humanoid's Head part.

## AttachmentPos
Gets or sets the position of the [AttachmentPoint](member:AttachmentPoint).

## AttachmentRight
Gets or sets the **right** column of the [AttachmentPoint](member:AttachmentPoint)'s rotation matrix.

## AttachmentUp
Gets or sets the **up** column of the [AttachmentPoint](member:AttachmentPoint)'s rotation matrix.
