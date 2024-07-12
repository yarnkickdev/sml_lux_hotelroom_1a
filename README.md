all credits go to : https://www.gta5-mods.com/maps/modern-hotel-room

i just moved the map to match the apartment building

replace your mythic-apartments/server/startup.lua with below
```lua
 _aptData = {
	{
		name = "Boring Tower",
		invEntity = 13,
		coords = vector3(-481.83, -690.74, 33.21),
		heading = 96.566,
		length = 8.4,
		width = 4.0,
		options = {
			heading = 0,
			--debugPoly=true,
			minZ = 32.21,
			maxZ = 36.21
		},
		interior = {
			wakeup = {
				x = -459.262,
				y = -682.010,
				z = 65.894,
				h = 90.0,
			},
			spawn = {
				x = -461.324,
				y = -685.468,
				z = 66.856,
				h = 356.578,
			},
			locations = {
				exit = {
					coords = vector3(-461.21, -686.15, 66.86),
					length = 0.8,
					width = 2.6,
					options = {
						heading = 0,
						--debugPoly=true,
						minZ = 65.86,
						maxZ = 68.46
					},
				},
				wardrobe = {
					coords = vector3(-461.71, -682.72, 66.86),
					length = 1.0,
					width = 2.0,
					options = {
						heading = 270,
						--debugPoly=true,
						minZ = 65.86,
						maxZ = 68.06
					},
				},
				stash = {
					coords = vector3(-456.63, -682.55, 66.89),
					length = 2.4,
					width = 1.0,
					options = {
						heading = 0,
						--debugPoly=true,
						minZ = 65.89,
						maxZ = 67.29
					},
				},
				logout = {
					coords = vector3(-458.43, -681.88, 66.89),
					length =3.0,
					width = 2.8,
					options = {
						heading = 0,
						--debugPoly=true,
						minZ = 65.89,
						maxZ = 67.09
					},
				},
			},
		},
	},
}

function Startup()
	local aptIds = {}

	for k, v in ipairs(_aptData) do
		v.id = k
		GlobalState[string.format("Apartment:%s", k)] = v
		table.insert(aptIds, k)
	end

	GlobalState["Apartments"] = aptIds
end

```
