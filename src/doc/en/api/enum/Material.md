# Details

## PhysicalProperties

Name          | Density | Friction | Elasticity | FrictionWeight | ElasticityWeight
--------------|---------|----------|------------|----------------|-----------------
Plastic       | 0.7     | 0.3      | 0.5        | 1              | 1
Wood          | 0.35    | 0.48     | 0.2        | 1              | 1
Slate         | 2.691   | 0.4      | 0.2        | 1              | 1
Concrete      | 2.403   | 0.7      | 0.2        | 0.3            | 1
CorrodedMetal | 7.85    | 0.7      | 0.2        | 1              | 1
DiamondPlate  | 7.85    | 0.35     | 0.25       | 1              | 1
Foil          | 2.7     | 0.4      | 0.25       | 1              | 1
Grass         | 0.9     | 0.4      | 0.1        | 1              | 1
Ice           | 0.919   | 0.02     | 0.15       | 3              | 1
Marble        | 2.563   | 0.2      | 0.17       | 1              | 1
Granite       | 2.691   | 0.4      | 0.2        | 1              | 1
Brick         | 1.922   | 0.8      | 0.15       | 0.3            | 1
Pebble        | 2.403   | 0.4      | 0.17       | 1              | 1
Sand          | 1.602   | 0.5      | 0.05       | 5              | 1
Fabric        | 0.7     | 0.35     | 0.05       | 1              | 1
SmoothPlastic | 0.7     | 0.2      | 0.5        | 1              | 1
Metal         | 7.85    | 0.4      | 0.25       | 1              | 1
WoodPlanks    | 0.35    | 0.48     | 0.2        | 1              | 1
Cobblestone   | 2.691   | 0.5      | 0.17       | 1              | 1
Air           | 0.01    | 0.01     | 0.01       | 1              | 1
Water         | 1       | 0.005    | 0.01       | 1              | 1
Rock          | 2.691   | 0.5      | 0.17       | 1              | 1
Glacier       | 0.919   | 0.05     | 0.15       | 1              | 1
Snow          | 0.9     | 0.3      | 0.03       | 1              | 1
Sandstone     | 2.691   | 0.5      | 0.15       | 5              | 1
Mud           | 0.9     | 0.3      | 0.07       | 1              | 1
Basalt        | 2.691   | 0.7      | 0.15       | 0.3            | 1
Ground        | 0.9     | 0.45     | 0.1        | 1              | 1
CrackedLava   | 2.691   | 0.65     | 0.15       | 1              | 1
Neon          | 0.7     | 0.3      | 0.2        | 1              | 1
Glass         | 2.403   | 0.25     | 0.2        | 1              | 1
Asphalt       | 2.36    | 0.8      | 0.2        | 0.3            | 1
LeafyGrass    | 0.9     | 0.4      | 0.1        | 1              | 1
Salt          | 2.165   | 0.5      | 0.05       | 1              | 1
Limestone     | 2.691   | 0.5      | 0.15       | 1              | 1
Pavement      | 2.691   | 0.5      | 0.17       | 1              | 1
ForceField    | 2.403   | 0.25     | 0.2        | 1              | 1

<!-- Generate table
print([[Name          | Density | Friction | Elasticity | FrictionWeight | ElasticityWeight]])
print([[--------------|---------|----------|------------|----------------|-----------------]])
for _,m in pairs(Enum.Material:GetEnumItems()) do
	local p = PhysicalProperties.new(m)
	print(string.format("%-13s | %-7g | %-8g | %-10g | %-14g | %-16g",
		m.Name,
		p.Density,
		p.Friction,
		p.Elasticity,
		p.FrictionWeight,
		p.ElasticityWeight
	))
end
-->
