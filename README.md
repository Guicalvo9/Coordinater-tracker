local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "Coordinate Tracker", HidePremium = false, SaveConfig = true, ConfigFolder = "OrionTest"})

local CoordinatesTab = Window:MakeTab({
Name = "Coordinates",
Icon = "rbxassetid://4483345998",
PremiumOnly = false
})

CoordinatesTab:AddLabel("Current Coordinates:")

local coordLabel = CoordinatesTab:AddLabel("X: 0, Y: 0, Z: 0")

game:GetService("RunService").RenderStepped:Connect(function()
local player = game.Players.LocalPlayer
if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
local pos = player.Character.HumanoidRootPart.Position
coordLabel:Set("X: " .. math.floor(pos.X) .. ", Y: " .. math.floor(pos.Y) .. ", Z: " .. math.floor(pos.Z))
end
end)

OrionLib:Init()
