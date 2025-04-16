local Players = game:GetService("Players") local player = Players.LocalPlayer player.CameraMode = Enum.CameraMode.Classic local runService = game:GetService("RunService") local StarterGui = game:GetService("StarterGui") local camera = workspace.CurrentCamera

StarterGui:SetCore("SendNotification", { Title = "Code by GioBolqvi", -- dont skid ðŸ™�ðŸ’” Text = "on Roblox", Duration = 3 })

local screenGui = Instance.new("ScreenGui") screenGui.Name = "NPC_Lock_GUI" screenGui.Parent = game:GetService("CoreGui")

local button = Instance.new("TextButton") button.Name = "NPC Lock: ON/OFF" button.Size = UDim2.new(0, 150, 0, 50) button.Position = UDim2.new(0.5, -75, 0.9, -25) button.BackgroundColor3 = Color3.new(0, 0, 0) button.TextColor3 = Color3.new(1, 1, 1) button.Text = "NPC Lock: OFF" button.Font = Enum.Font.Fantasy button.TextScaled = true button.TextSize = 20 button.Parent = screenGui

local uicorner = Instance.new("UICorner") uicorner.CornerRadius = UDim.new(0, 12) uicorner.Parent = button

local dragging = false local dragInput, dragStart, startPos

local function update(input) local delta = input.Position - dragStart button.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y) end

button.InputBegan:Connect(function(input) if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then dragging = true dragStart = input.Position startPos = button.Position

    input.Changed:Connect(function()
        if input.UserInputState == Enum.UserInputState.End then
            dragging = false
        end
    end)
end
