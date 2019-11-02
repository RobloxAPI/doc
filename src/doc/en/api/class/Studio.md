# Summary
Configures settings specific to Roblox Studio.

# Details
The Studio class only exists on the Studio build of Roblox. As such, it is not
relevant for game clients or servers.

# Members
## Always Save Script Changes
[ASSC]: member:Always%20Save%20Script%20Changes

Sets whether scripts will be updated when modified while the game is running.

### Details
When a user is testing a script by running Play Solo, they may accidentally make
modifications to the script while Play Solo is still running, which would
normally be discarded once Play Solo is stopped. Studio handles this problem by
prompting the user to propagate the changes back to scripts in the non-running
game tree.

When enabled, this setting suppresses the prompt and propagates script changes
automatically.

## Animate Hover Over
[AHO]: member:Animate%20Hover%20Over

Determines whether the hover-over box is animated.

### Details
See [Show Hover Over][SHO] for a description of the hover-over box.

While enabled, the hover-over box will animate between two colors determined by
[Select Color][SelectColor] and [Hover Over Color][HOC]. The speed of this
animation is determined by [Hover Animate Speed][HAS].

## Auto Closing Brackets
[ACB]: member:Auto%20Closing%20Brackets

Determines whether opening brackets are automatically closed while typing in the
script editor.

### Details
When a `(`, `[` or `{` character is typed in the script editor while this
setting is enabled, the corresponding closing bracket is inserted after the
cursor. The character is not inserted if there is a non-whitespace character
directly after the cursor.

If an opening bracket is deleted while the cursor is directly between the two
matching brackets (that is, both characters are adjacent), then both characters
will be deleted.

#### Bugs
When deleting an opening bracket as described previously, the matching closing
bracket may not always be deleted.

## Auto Closing Quotes
[ACQ]: member:Auto%20Closing%20Quotes

Determines whether opening strings quotes are automatically closed while typing
in the script editor.

### Details
When a `"` or `'` character is typed to open a Lua string in the script editor
while this setting is enabled, the corresponding character to close the string
is inserted after the cursor.

The closing character is inserted only within the scope of a quoted Lua string.
For example, it will not be inserted while in the scope of a comment or a
multiline string.

## Auto Indent
[AI]: member:Auto%20Indent

Determines whether indentation is automatically inserted while typing in the
script editor.

### Details
While enabled, when a new block is opened (such as typing `function`, `while`,
or `if`), tab characters will be inserted until the cursor is one indentation
level deeper. The `end` keyword will also be inserted on the next line to close
the block. After typing certain keywords like `elseif` or `else`, their
indentation will be adjusted automatically.

## Auto-Recovery Enabled
[ARE]: member:Auto-Recovery%20Enabled

Determines whether the current place file is periodically backed up to a
recovery file.

### Details
When Studio is closed, all recovery files are deleted. In the event of a crash,
such files will not be deleted. Whenever Studio starts up, if it is the only
instance of Studio running, it will detect existing recovery files, and ask the
user what to do with them. The user may open a file, ignore, or delete all
recovery files.

## Auto-Recovery Interval (Minutes)
[ARI]: member:Auto-Recovery%20Interval%20%28Minutes%29

Determines how often a recovery file is made, in minutes.

## Auto-Recovery Path
[ARP]: member:Auto-Recovery%20Path

Determines the location in the file system to which recovery files will be
written.

## Background Color
[BC]: member:Background%20Color

Determines the background color in the script editor.

## Basic Objects Display Mode
[BODM]: member:Basic%20Objects%20Display%20Mode

Determines the direction of classes listed in the Advanced Objects panel.

### Details
Classes are listed in multiple columns when Horizontal, and a single column when
Vertical.

## Built-in Function Color
[BiFC]: member:Built-in%20Function%20Color

Determines the color of built-in variables in the script editor.

## Camera Mouse Wheel Speed
[CMWS]: member:Camera%20Mouse%20Wheel%20Speed

Determines how many studs the camera moves when scrolling the mouse wheel.

### Details
The mouse wheel is used to "zoom" the camera. Rather than performing a focal
zoom or magnification, the camera is translated forwards or backwards. This
setting determines how many studs the camera moves every tick of the mouse
wheel. The direction the camera moves is determined by [Camera Zoom to Mouse
Position][CZtMP].

## Camera Shift Speed
[CSS]: member:Camera%20Shift%20Speed

Determines the movement speed of the camera while the shift key is held.

### Details
The "base speed" of the camera (as determined by [Camera Speed][CS]) is
multiplied by the value of this setting to determine the "shift speed", in studs
per second. This will be the camera's velocity when the camera is moving while
the shift key is held. Unlike the active speed, which accelerates, this speed is
constant.

## Camera Speed
[CS]: member:Camera%20Speed

Determines the base movement speed of the camera.

### Details
The value of this setting is multiplied by 30, which determines the "base speed"
of the camera in studs per second.

When the camera starts moving, this base speed is used as the "active speed",
which is the velocity of the camera while no modifiers (such as [Camera Shift
Speed][CSS]) are held.

2 seconds after movement starts, the active speed begins accelerating at a rate
of half the base speed (`CameraSpeed * 30 / 2`), and will continue accelerating
in the background even while modifiers are held. The active speed resets only
after the camera stops moving.

Note that the camera is considered moving while any of the camera movement keys
are held. The camera will still be "moving" even while two opposing keys that
cancel each other out are held (such as left and right, or forward and back).

## Camera Zoom to Mouse Position
[CZtMP]: member:Camera%20Zoom%20to%20Mouse%20Position

Determines the direction in which the camera zooms.

### Details
When this setting is enabled, the camera will zoom in the direction of the
position of the mouse cursor. When disabled, the camera will zoom in the
direction of its [look vector](type:CFrame). <!-- TODO:LookVector -->

## Clear Output On Start
[COOS]: member:Clear%20Output%20On%20Start

Determines whether the output panel is cleared when the place runs.

### Details
When the place is tested with Run or Play Solo while this setting is enabled,
the output panel will be cleared.

## Comment Color
[CC]: member:Comment%20Color

Determines the color of Lua comments in the script editor.

## DefaultScriptFileDir
[DSFD]: member:DefaultScriptFileDir

Determines the starting location of the file dialog when choosing a script to
run.

### Details
When the Run Script action is activated, a dialog prompts the user to choose a
file to run as a script. This setting determines the starting location of the
dialog, and is updated, after a file is selected, to the location of the
selection.

#### Bugs
After selecting a file, the displayed value of the setting is not updated,
although the value will be updated after Studio is restarted.

## DeprecatedObjectsShown
[DOS]: member:DeprecatedObjectsShown

Determines whether deprecated APIs are visible in the Object Browser.

### Details
This setting does not affect autocomplete or menus that insert objects.

## Device Pairing Code
[DPC]: member:Device%20Pairing%20Code

A code used to associate Studio sessions with a mobile device.

## Disable Accurate Play Solo
[DAPS]: member:Disable%20Accurate%20Play%20Solo

Determines whether Accurate Play Solo is disabled.

### Details
While this setting is disabled, running Play Solo causes two separate data
models to be simulated, one each for the client and the server. While enabled,
Play Solo will simulate both the client and the server in a single data model.

While Accurate Play Solo is running, the viewport will have a colored border
indicating which data model is being viewed, as well as where the command bar
runs. The current view can be toggled by an action visible while Play Solo is
running. In the output panel, messages are marked with the color that
corresponds to the data model from which the message originates. Green indicates
the server, and blue indicates the client.

## Drag Multiple Parts As Single Part
[DMPASP]: member:Drag%20Multiple%20Parts%20As%20Single%20Part

Causes multiple parts to behave as a single part while being dragged.

### Details
While this setting is enabled, the collision of dragged parts is determined by
the bounding box formed by the entire selection. While disabled, collisions are
performed on each selection individually.

## Enable Autocomplete
[EA]: member:Enable%20Autocomplete

Determines whether code completion is enabled while typing in the script editor
or command bar.

### Details
When the user types in the script editor or command bar while this setting is
enabled, a menu will pop up next to the cursor, displaying a list of words
relevant to the context of what has been typed. `ctrl+space` can also be used to
display the menu. While displayed, the up and down arrow keys can be used to
highlight an element, or the user may continue typing to further reduce the
list. When the user presses enter on a highlighted element, the rest of the
typed word will be filled in with that element.

Several kinds of elements can be completed:

- Lua keywords.
- built-in shared variables.
- Local and global variables.
- Indices of such variables, including members and children of objects.

Variables that cannot be inferred statically cannot be completed. For example, a
function parameter can have an arbitrary value passed to it, so its value can
only be determined at runtime when the function is actually called.

## Enable CoreScript Debugger
[ECSD]: member:Enable%20CoreScript%20Debugger

## Enable Intellisense
[EI]: member:Enable%20Intellisense

Replaced by [Enable Autocomplete][EA].

## Error Color
[EC]: member:Error%20Color

Determines the color of text decorations indicating an error in the script
editor.

## Find Selection Background Color
[FSBC]: member:Find%20Selection%20Background%20Color

Determines the background color of text highlighted by the Find action.

## Font
[Font]: member:Font

Determines the script editor font.

## GetAvailableThemes
[GAT]: member:GetAvailableThemes

Returns available studio themes as a list of [StudioThemes](class:StudioTheme)
objects.

## Hover Animate Speed
[HAS]: member:Hover%20Animate%20Speed

Determines the speed at which the hover-over box animates.

### Details
See [Show Hover Over][SHO] for a description of the hover-over box.

This setting determines the rate at which the color of the hover-over box
transitions between the [Select Color][SelectColor] and the [Hover Over
Color][HOC].

## Hover Over Color
[HOC]: member:Hover%20Over%20Color

Determines the secondary color of the hover-over box.

### Details
See [Show Hover Over][SHO] for a description of the hover-over box.

When [Hover Animate Speed][HAS] is enabled, the hover-over box will transition
between the [Select Color][SelectColor] and this color.

## Keyword Color
[KC]: member:Keyword%20Color

Determines the color of Lua keywords in the script editor.

## Language
[Language]: member:Language

Determines the language displayed in the Studio interface.

### Details
Studio must be restarted for changes to this setting to take effect.

## Line Thickness
[LT]: member:Line%20Thickness

Determines the thickness, in studs, of the box displayed around the
[PrimaryPart](class:Model/PrimaryPart) while a [Model](class:Model) is selected.

### Details
The value has an interval of `(0, 0.05)`, or a minimum limit of 0 exclusive, and
a maximum limit of 0.05 exclusive.

#### Bugs
Setting the value to 0 will display the error used for the maximum limit, rather
than the minimum.

## LuaDebuggerEnabled
[LDE]: member:LuaDebuggerEnabled

Determines whether the Lua debugger is enabled or disabled when Studio starts
up.

### Details
Studio must be restarted for changes to the debugger to take effect.

## LuaDebuggerEnabledAtStartup
[LDEAS]: member:LuaDebuggerEnabledAtStartup

Returns whether the Lua debugger is currently enabled.

### Details
This value indicates the enabled state of the debugger in the current session,
regardless of the value of [LuaDebuggerEnabled][LDE].

## Matching Word Background Color
[MWBC]: member:Matching%20Word%20Background%20Color

Determines the background color of matched words in the script editor.

### Details
When a word is selected in the script editor while this setting is enabled,
other occurrences of the word in the script will be highlighted with this color.

## Maximum Output Lines
[MOL]: member:Maximum%20Output%20Lines

Determines the number of lines that persist in the Output panel.

### Details
A value of 0 or less causes no limit to be enforced. When set to a value less
than the current, the oldest lines in the Output panel will be truncated.

## Number Color
[NC]: member:Number%20Color

Determines the color of Lua numbers in the script editor.

## Only Play Audio from Window in Focus
[OPAfWiF]: member:Only%20Play%20Audio%20from%20Window%20in%20Focus

Determines whether audio will be played only from the Studio window currently in
focus.

## Operator Color
[OC]: member:Operator%20Color

Determines the color of Lua operators in the script editor.

## Output Font
[OutputFont]: member:Output%20Font

Determines the Output panel font.

## Output Layout Mode
[OLM]: member:Output%20Layout%20Mode

Determines the layout of vertical panels versus horizontal panels.

### Details
When set to Vertical, panels on the left and right sides of the screen will be
laid out with priority over panels on the bottom of the screen. When set to
Horizontal, panels on the bottom of the screen will have priority.

## OverrideCoreScripts
[OCS]: member:OverrideCoreScripts

## OverrideCoreScriptsDir
[OCSD]: member:OverrideCoreScriptsDir

## PermissionLevelShown
[PLS]: member:PermissionLevelShown

## PluginsDir
[PD]: member:PluginsDir

## Preprocessor Color
[PC]: member:Preprocessor%20Color

The determines the color of preprocessors in the script editor.

### Details
Older versions of Lua (up to 3.2) had a
[preprocessor](https://www.lua.org/manual/3.2/manual.html#4.2), in which lines
beginning with a `$` character were interpreted as directives. The preprocessor
was removed in version 4.0, so this value is unused.

## RecentSavesDir
[RSD]: member:RecentSavesDir

## Render Throttle Percentage
[RTP]: member:Render%20Throttle%20Percentage

## Respect Studio shortcuts when game has focus
[RSswghf]: member:Respect%20Studio%20shortcuts%20when%20game%20has%20focus

## RuntimeUndoBehavior
[RUB]: member:RuntimeUndoBehavior

## ScriptTimeoutLength
[STL]: member:ScriptTimeoutLength

## Select Color
[SelectColor]: member:Select%20Color

Determines the color of selection boxes, as well as the hover-over box.

### Details
While an object in the viewport is selected, a bounding-box will be displayed
around it. Select Color determines the color of this box.

When [Hover Animate Speed][HAS] is enabled, the hover-over box will transition
between the this color and the [Hover Over Color][HOC]. See [Show Hover
Over][SHO] for a description of the hover-over box.

## Select/Hover Color
[SHC]: member:Select%2FHover%20Color

Determines the color of the box displayed around the
[PrimaryPart](class:Model/PrimaryPart) while a [Model](class:Model) is selected.

## Selection Background Color
[SBC]: member:Selection%20Background%20Color

Determines the background color of selected text in the script editor.

## Selection Color
[SionC]: member:Selection%20Color

Determines the color of selected text in the script editor.

## Server Audio Behavior
[SAB]: member:Server%20Audio%20Behavior

## Show Core GUI in Explorer while Playing
[SCGiEwP]: member:Show%20Core%20GUI%20in%20Explorer%20while%20Playing

## Show Diagnostics Bar
[SDB]: member:Show%20Diagnostics%20Bar

## Show Hidden Objects in Explorer
[SHOiE]: member:Show%20Hidden%20Objects%20in%20Explorer

## Show Hover Over
[SHO]: member:Show%20Hover%20Over

Sets whether selectable objects in the viewport show an indicator when hovered
over with the mouse.

### Details
When the mouse hovers over a selectable 3D object in the viewport while this
setting is enabled, a "hover-over" selection box will be shown around the
object. The appearance of this box can be configured with the following
settings:

- [Animate Hover Over][AHO]
- [Hover Animate Speed][HAS]
- [Select Color][SelectColor]
- [Hover Over Color][HOC]

## Show Navigation Mesh
[SNM]: member:Show%20Navigation%20Mesh

## Show Plugin GUI Service in Explorer
[SPGSiE]: member:Show%20Plugin%20GUI%20Service%20in%20Explorer

## Show plus button on hover in Explorer
[SpbohiE]: member:Show%20plus%20button%20on%20hover%20in%20Explorer

## Show QT warnings in output
[SQwio]: member:Show%20QT%20warnings%20in%20output

## Show Roblox Plugin GUI Service in Explorer
[SRPGSiE]: member:Show%20Roblox%20Plugin%20GUI%20Service%20in%20Explorer

## Skip Closing Brackets and Quotes
[SCBaQ]: member:Skip%20Closing%20Brackets%20and%20Quotes

Determines whether automatically inserted characters are skipped over while
typing.

### Details
When typing in the script editor while this setting is enabled, if the typed
character is a closing bracket or quote that equals the next character after the
cursor, and the character has a matching opening character, then the cursor
moves one character forward instead of typing.

This is used in conjunction with [Auto Closing Brackets][ACB] and [Auto Closing
Quotes][ACQ] to skip over characters that have been inserted automatically.

## String Color
[StringColor]: member:String%20Color

Determines the color of Lua strings in the script editor.

## Tab Width
[TabWidth]: member:Tab%20Width

## Text Color
[TextColor]: member:Text%20Color

Determines the color of general text in the script editor.

## Text Wrapping
[TextWrapping]: member:Text%20Wrapping

## Theme
[Theme]: member:Theme

Determines the current studio theme.

### Details
Theme expects a [StudioTheme](class:StudioTheme) object. A list of available
themes can be acquired with [GetAvailableThemes][GAT].

## ThemeChanged
[ThemeChanged]: member:ThemeChanged

Fires after the [Theme][Theme] property changes.

### Details

## UI Theme
[UT]: member:UI%20Theme

## Warning Color
[WC]: member:Warning%20Color

Determines the color of text decorations indicating a warning in the script
editor.
