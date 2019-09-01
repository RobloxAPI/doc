# Members

## GetClassIcon
Gets the explorer icon for a given class.

### Details
GetClassIcon returns the icon for a class as displayed in Studio's explorer
panel. *className* is the name of an existing Roblox class. If successful, a
table with the following fields is returned:

- **Image**: [string](type:string)
- **ImageRectOffset**: [Vector2](type:Vector2)
- **ImageRectSize**: [Vector2](type:Vector2)

These correspond to the [Image](class:ImageLabel/Image),
[ImageRectOffset](class:ImageLabel/ImageRectOffset), and
[ImageRectSize](class:ImageLabel/ImageRectSize) properties of an
[ImageLabel](class:ImageLabel) or [ImageButton](class:ImageButton). The values
of each fields can be set directly to its corresponding property to display the
icon correctly.

If the given class does not exist, then following error is thrown:

	GetClassIcon: CLASS is not a Roblox class.

Where `CLASS` is the value of the given *className*.

### Examples
Generate a GUI displaying the entire game tree.

```lua
local StudioService = game:GetService("StudioService")
local TextService = game:GetService("TextService")
local StarterGui = game:GetService("StarterGui")

-- Get base size of icon, assuming all icons have the same size.
local iconSize = StudioService:GetClassIcon("Instance").ImageRectSize
local font = Enum.Font.SourceSans
local fontSize = iconSize.Y
local labelTextOffset = 2

-- Create label template.
local labelTemplate = Instance.new("Frame")
labelTemplate.Name = "ClassLabel"
labelTemplate.BackgroundTransparency = 1

local iconTemplate = Instance.new("ImageLabel", labelTemplate)
iconTemplate.Name = "IconLabel"
iconTemplate.Size = UDim2.new(0, iconSize.X, 0, iconSize.Y)
iconTemplate.BackgroundTransparency = 1

local textTemplate = Instance.new("TextLabel", labelTemplate)
textTemplate.Name = "TextLabel"
textTemplate.Position = UDim2.new(0, iconSize.X + labelTextOffset, 0, 0)
textTemplate.TextXAlignment = Enum.TextXAlignment.Left
textTemplate.BackgroundTransparency = 1
textTemplate.TextColor3 = Color3.new(1, 1, 1)

-- Generate labels.
local maxWidth = 0
local labels = {}
local function createLabels(objects, depth)
	for i, object in pairs(objects) do
		-- Some objects are not friendly to being indexed.
		local ok, name = pcall(function() return object.Name end)
		if ok and object.ClassName ~= "" then
			local icon = StudioService:GetClassIcon(object.ClassName)
			local textSize = TextService:GetTextSize(name, fontSize, font, Vector2.new(0, 0))
			local label = labelTemplate:Clone()
			label.Position = UDim2.new(0, depth * iconSize.X, 0, #labels * iconSize.Y)
			label.Size = UDim2.new(0, iconSize.X + textSize.X + labelTextOffset, 0, iconSize.Y)
			label.IconLabel.Image = icon.Image
			label.IconLabel.ImageRectOffset = icon.ImageRectOffset
			label.IconLabel.ImageRectSize = icon.ImageRectSize
			label.TextLabel.Text = name
			label.TextLabel.Size = UDim2.new(0, textSize.X, 0, iconSize.Y)
			local width = label.Position.X.Offset + label.Size.X.Offset
			if width > maxWidth then
				maxWidth = width
			end
			labels[#labels + 1] = label
			createLabels(object:GetChildren(), depth + 1)
		end
	end
end
createLabels(game:GetChildren(), 0)

-- Generate GUI.
local screen = Instance.new("ScreenGui")
local container = Instance.new("ScrollingFrame", screen)
local width = maxWidth + container.ScrollBarThickness
container.Position = UDim2.new(0, 10, 0, 10)
container.Size = UDim2.new(0, width, 1, -20)
container.CanvasSize = UDim2.new(0, width, 0, #labels * iconSize.Y)
container.BackgroundColor3 = Color3.new(0, 0, 0)
container.BackgroundTransparency = 0.3
container.BorderSizePixel = 0
for _, label in pairs(labels) do
	label.Parent = container
end
screen.Parent = game.StarterGui
```
