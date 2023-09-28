-- Create a ScreenGui
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

-- Create a Frame for the GUI
local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(0, 300, 0, 400)
Frame.Position = UDim2.new(0.5, -150, 0.5, -200)
Frame.BackgroundTransparency = 0.2
Frame.BackgroundColor3 = Color3.new(0, 0, 0)
Frame.BorderColor3 = Color3.new(0, 0, 0)
Frame.BorderSizePixel = 3
Frame.Parent = ScreenGui

-- Create a function for button properties
local function createButton(text, yPosition, textColor, onClick)
    local button = Instance.new("TextButton")
    button.Text = text
    button.Size = UDim2.new(0.8, 0, 0, 40)
    button.Position = UDim2.new(0.1, 0, yPosition, 0)
    button.BackgroundColor3 = Color3.new(1, 1, 1)
    button.BackgroundTransparency = 0.5
    button.BorderSizePixel = 0
    button.Font = Enum.Font.SourceSansBold
    button.TextColor3 = textColor
    button.TextSize = 24
    button.Parent = Frame

    button.MouseButton1Click:Connect(onClick)
end

-- Create buttons
createButton("ANTI AFK", 0.05, Color3.new(1, 0, 0), function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/KazeOnTop/Rice-Anti-Afk/main/Wind", true))()
end)

createButton("RED BLUE", 0.15, Color3.new(0, 0, 1), function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/JustAP1ayer/PlayerHubOther/main/PlayerHubIngameUgcLimiteds.lua"))()
end)

createButton("INFINITY YIELD", 0.25, Color3.new(0, 1, 0), function()
    loadstring(game:HttpGet(('https://pastebin.com/raw/rShQCVmL')))()
end)

createButton("DEX EXPLORER", 0.35, Color3.new(1, 0, 1), function()
    loadstring(game:HttpGet(('https://pastebin.com/raw/SPPeSXEE')))()
end)

createButton("NO E WAIT", 0.45, Color3.new(0, 1, 1), function()
    for _, v in pairs(workspace:GetDescendants()) do
        if v:IsA("ProximityPrompt") then
            v.HoldDuration = 0
            task.wait()
        end
    end
end)

createButton("SERVER BROWSER", 0.55, Color3.new(1, 1, 0), function()
    loadstring(game:HttpGet("https://www.scriptblox.com/raw/Server-Browser_80", true))()
end)

createButton("HIDE ALL", 0.65, Color3.new(1, 0.5, 0), function()
    _G.HideAll = true
    while _G.HideAll and task.wait() do
        for i, v in pairs(game.Players:GetPlayers()) do
            if v.Name ~= game.Players.LocalPlayer.Name and v.Character then
                v.Character:Destroy()
            end
        end
    end
end)

createButton("EXIT", 0.75, Color3.new(0, 0, 0), function()
    ScreenGui:Destroy()
end)
