
Snippet to create blips
```lua
-- client
local blipLocations = {
    { coords = vector3(-1637.07, 4567.14, 43.11), blipId = 1, color = 3, scale = 1.0, name = "Test Location 1" },
    { coords = vector3(-1647.07, 4577.14, 43.11),        blipId = 2, color = 5, scale = 1.0, name = "Test Location 2" },
}

local function createBlip(location)
    local blip = AddBlipForCoord(location.coords)

    SetBlipSprite(blip, location.blipId)  
    SetBlipDisplay(blip, 4)               
    SetBlipScale(blip, location.scale)    
    SetBlipColour(blip, location.color)  
    BeginTextCommandSetBlipName("STRING")
    AddTextComponentString(location.name)
    EndTextCommandSetBlipName(blip)
end

for _, location in ipairs(blipLocations) do
    createBlip(location)
end
```
