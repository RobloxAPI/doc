# Summary
Configures settings specific to Roblox Studio.

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

When Animate Hover Over is enabled, the hover-over box will animate between two
colors determined by [Select Color][SelectColor] and [Hover Over Color][HOC].
The speed of this animation is determined by [Hover Animate Speed][HAS].

## Auto Closing Brackets
[ACB]: member:Auto%20Closing%20Brackets

Determines whether opening brackets are automatically closed while typing in the
script editor.

### Details
While enabled, when a `(`, `[` or `{` character is typed in the script editor,
the corresponding closing bracket is inserted after the cursor. The character is
not inserted if there is a non-whitespace character directly after the cursor.

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
While enabled, when a `"` or `'` character is typed to open a Lua string in the
script editor, the corresponding character to close the string is inserted after
the cursor.

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

Determines the directory in the file system to which recovery files will be
written.

## Background Color
[BC]: member:Background%20Color

## Basic Objects Display Mode
[BODM]: member:Basic%20Objects%20Display%20Mode

## Built-in Function Color
[BiFC]: member:Built-in%20Function%20Color

## Camera Mouse Wheel Speed
[CMWS]: member:Camera%20Mouse%20Wheel%20Speed

## Camera Shift Speed
[CSS]: member:Camera%20Shift%20Speed

## Camera Speed
[CS]: member:Camera%20Speed

## Camera Zoom to Mouse Position
[CZtMP]: member:Camera%20Zoom%20to%20Mouse%20Position

## Clear Output On Start
[COOS]: member:Clear%20Output%20On%20Start

## Comment Color
[CC]: member:Comment%20Color

## DefaultScriptFileDir
[DSFD]: member:DefaultScriptFileDir

## DeprecatedObjectsShown
[DOS]: member:DeprecatedObjectsShown

## Device Pairing Code
[DPC]: member:Device%20Pairing%20Code

## Disable Accurate Play Solo
[DAPS]: member:Disable%20Accurate%20Play%20Solo

## Drag Multiple Parts As Single Part
[DMPASP]: member:Drag%20Multiple%20Parts%20As%20Single%20Part

## Enable Autocomplete
[EA]: member:Enable%20Autocomplete

## Enable CoreScript Debugger
[ECSD]: member:Enable%20CoreScript%20Debugger

## Enable Intellisense
[EI]: member:Enable%20Intellisense

## Error Color
[EC]: member:Error%20Color

## Find Selection Background Color
[FSBC]: member:Find%20Selection%20Background%20Color

## Font
[Font]: member:Font

## GetAvailableThemes
[GAT]: member:GetAvailableThemes

Returns a list of available studio themes as a list of
[StudioThemes](class:StudioTheme) objects.

## Hover Animate Speed
[HAS]: member:Hover%20Animate%20Speed

Determines the speed at which the hover-over box animates.

### Details
See [Show Hover Over][SHO] for a description of the hover-over box.

The value is a [HoverAnimateSpeed](enum:HoverAnimateSpeed) enum, which
determines the rate at which the color of the hover-over box transitions between
the [Select Color][SelectColor] and the [Hover Over Color][HOC].

## Hover Over Color
[HOC]: member:Hover%20Over%20Color

Determines the secondary color of the hover-over box.

### Details
See [Show Hover Over][SHO] for a description of the hover-over box.

When [Hover Animate Speed][HAS] is enabled, the hover-over box will transition
between the [Select Color][SelectColor] and this color.

## Keyword Color
[KC]: member:Keyword%20Color

## Language
[Language]: member:Language

## Line Thickness
[LT]: member:Line%20Thickness

## LuaDebuggerEnabled
[LDE]: member:LuaDebuggerEnabled

## LuaDebuggerEnabledAtStartup
[LDEAS]: member:LuaDebuggerEnabledAtStartup

## Matching Word Background Color
[MWBC]: member:Matching%20Word%20Background%20Color

## Maximum Output Lines
[MOL]: member:Maximum%20Output%20Lines

## Number Color
[NC]: member:Number%20Color

## Only Play Audio from Window in Focus
[OPAfWiF]: member:Only%20Play%20Audio%20from%20Window%20in%20Focus

## Operator Color
[OC]: member:Operator%20Color

## Output Font
[OutputFont]: member:Output%20Font

## Output Layout Mode
[OLM]: member:Output%20Layout%20Mode

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

## Selection Color
[SionC]: member:Selection%20Color

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
If Show Hover Over is enabled, then when the mouse hovers over a selectable 3D
object in the viewport, a "hover-over" selection box will be shown around the
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
While enabled, when typing in the script editor, if the typed character is a
closing bracket or quote that equals the next character after the cursor, and
the character has a matching opening character, then the cursor moves one
character forward instead of typing.

This is used in conjunction with [Auto Closing Brackets][ACB] and [Auto Closing
Quotes][ACQ] to skip over characters that have been inserted automatically.

## String Color
[StringColor]: member:String%20Color

## Tab Width
[TabWidth]: member:Tab%20Width

## Text Color
[TextColor]: member:Text%20Color

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

