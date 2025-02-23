local kavoUi = loadstring(game:HttpGet("https://pastebin.com/raw/vff1bQ9F"))()
local Window = kavoUi.CreateLib("DeadlyHub","DarkTheme")



local MainTab = Window:NewTab("Main")
local MainSection = 
MainTab:NewSection("MainSection")

MainSection:NewButton("Destroy safe zone", "VERY COOL!", function()

local m=workspace:FindFirstChild("CurrentMap")
if m then
 local f=m:FindFirstChild("SpawnsAndOthers")
 if f then f:Destroy() end
end

local kavoUi = loadstring(game:HttpGet("https://pastebin.com/raw/vff1bQ9F"))()
local Window = kavoUi.CreateLib("DeadlyHub","DarkTheme")



local MainTab = Window:NewTab("Main")
local MainSection = 
MainTab:NewSection("MainSection")


MainSection:NewButton("ESP", "you see people behind the wall", function()
  local FillColor = Color3.fromRGB(175,25,255)
local DepthMode = "AlwaysOnTop"
local FillTransparency = 0.5
local OutlineColor = Color3.fromRGB(255,255,255)
local OutlineTransparency = 0

local CoreGui = game:FindService("CoreGui")
local Players = game:FindService("Players")
local lp = Players.LocalPlayer
local connections = {}

local Storage = Instance.new("Folder")
Storage.Parent = CoreGui
Storage.Name = "Highlight_Storage"

local function Highlight(plr)
    local Highlight = Instance.new("Highlight")
    Highlight.Name = plr.Name
    Highlight.FillColor = FillColor
    Highlight.DepthMode = DepthMode
    Highlight.FillTransparency = FillTransparency
    Highlight.OutlineColor = OutlineColor
    Highlight.OutlineTransparency = 0
    Highlight.Parent = Storage
    
    local plrchar = plr.Character
    if plrchar then
        Highlight.Adornee = plrchar
    end

    connections[plr] = plr.CharacterAdded:Connect(function(char)
        Highlight.Adornee = char
    end)
end

Players.PlayerAdded:Connect(Highlight)
for i,v in next, Players:GetPlayers() do
    Highlight(v)
end

Players.PlayerRemoving:Connect(function(plr)
    local plrname = plr.Name
    if Storage[plrname] then
        Storage[plrname]:Destroy()
    end
    if connections[plr] then
        connections[plr]:Disconnect()
    end
end)
end)



local Misc = Window:NewTab("Misc")
local MiscSection = Misc:NewSection("Misc")



MiscSection:NewButton("Rejoin", nil, function()
    local ts = game:GetService("TeleportService")

local p = game:GetService("Players").LocalPlayer

 

ts:Teleport(game.PlaceId, p)
end)



local Admins = Window:NewTab("Admins")
local AdminsSection = Admins:NewSection("Admins")

AdminsSection:NewButton("Infinite Yield", nil, function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)



local Credits = Window:NewTab("Credits")
local CreditsSection = Credits:NewSection("Credits")


CreditsSection:NewLabel("Made by isssacque1234")
