local gplrs = game.Players:GetPlayers()
local plr = game.Players.LocalPlayer
local TorsoEsp = Instance.new("Part")
TorsoEsp.Anchored = true
TorsoEsp.BottomSurface = Enum.SurfaceType.Smooth
TorsoEsp.CFrame = CFrame.new(-153.01, 3, -34.152)
TorsoEsp.Name = "TorsoEsp"
TorsoEsp.Reflectance = 1
TorsoEsp.Size = Vector3.new(0.05, 1.66, 0.05)
TorsoEsp.TopSurface = Enum.SurfaceType.Smooth
TorsoEsp.Transparency = 1
TorsoEsp.Parent = game:GetService("Workspace")
TorsoEsp.CanCollide = false

local BoxHandleAdornment = Instance.new("BoxHandleAdornment")
BoxHandleAdornment.Adornee = nil
BoxHandleAdornment.AlwaysOnTop = true
BoxHandleAdornment.Color3 = Color3.fromRGB(0, 255, 8)
BoxHandleAdornment.Size = Vector3.new(2, 2, 1)
BoxHandleAdornment.Transparency = 0.5
BoxHandleAdornment.ZIndex = 2
BoxHandleAdornment.Parent = TorsoEsp



game.Players.PlayerAdded:Connect(function(plr)
	TorsoEsp:Clone()
	TorsoEsp.Parent = game.Workspace:WaitForChild(plr.Name)
	TorsoEsp.BoxHandleAdornment.Adornee = game.Workspace:WaitForChild(plr.Name).HumanoidRootPart
end)


for i, v in pairs(gplrs) do
	local BoxHandleAdornment = Instance.new("BoxHandleAdornment")
	BoxHandleAdornment.Adornee = v.Character.HumanoidRootPart
	BoxHandleAdornment.AlwaysOnTop = true
	BoxHandleAdornment.Color3 = Color3.fromRGB(0, 255, 8)
	BoxHandleAdornment.Size = Vector3.new(2, 2, 1)
	BoxHandleAdornment.Transparency = 0.5
	BoxHandleAdornment.ZIndex = 2
	BoxHandleAdornment.Parent = v.Character
end

wait()
local plr = game.Players.LocalPlayer
game.Workspace:WaitForChild(plr.Name).BoxHandleAdornment:Destroy()
