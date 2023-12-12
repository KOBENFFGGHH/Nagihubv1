local HubName = "Alchemy Hub"
local LogoImage = "http://www.roblox.com/asset/?id=14981376704"
local ColorTheme = Color3.fromRGB(0, 255, 145)
local BountyWhenStart = game:GetService("Players").LocalPlayer.leaderstats["Bounty/Honor"].Value
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
function dragify(Frame, object)
    dragToggle = nil
    dragSpeed = .25
    dragInput = nil
    dragStart = nil
    dragPos = nil
    function updateInput(input)
        Delta = input.Position - dragStart
        Position =
            UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
        game:GetService("TweenService"):Create(object, TweenInfo.new(dragSpeed), {Position = Position}):Play()
    end
    Frame.InputBegan:Connect(
        function(input)
            if
                (input.UserInputType == Enum.UserInputType.MouseButton1 or
                    input.UserInputType == Enum.UserInputType.Touch)
            then
                dragToggle = true
                dragStart = input.Position
                startPos = object.Position
                input.Changed:Connect(
                    function()
                        if (input.UserInputState == Enum.UserInputState.End) then
                            dragToggle = false
                        end
                    end
                )
            end
        end
    )
    Frame.InputChanged:Connect(
        function(input)
            if
                (input.UserInputType == Enum.UserInputType.MouseMovement or
                    input.UserInputType == Enum.UserInputType.Touch)
            then
                dragInput = input
            end
        end
    )
    game:GetService("UserInputService").InputChanged:Connect(
    function(input)
        if (input == dragInput and dragToggle) then
            updateInput(input)
        end
    end
    )
end
local MINIGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Logo = Instance.new("ImageLabel")
local MainCorner = Instance.new("UICorner")
local Name = Instance.new("TextLabel")
local Text_1 = Instance.new("TextLabel")
local Text_2 = Instance.new("TextLabel")
local Text_3 = Instance.new("TextLabel")
local ProfileName = Instance.new("TextLabel")
local ProfileImage = Instance.new("ImageLabel")
MINIGui.Name = "MINIGui"
MINIGui.Parent = game.CoreGui
MINIGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
MainFrame.Name = "MainFrame"
MainFrame.Parent = MINIGui
MainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
MainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
MainFrame.Position = UDim2.new(0.499723464, 0, 0.499925077, 0)
MainFrame.Size = UDim2.new(0, 502, 0, 263)
MainFrame.ZIndex = 0
MainCorner.Name = "MainCorner"
MainCorner.Parent = MainFrame
Logo.AnchorPoint = Vector2.new(0.5, 0.5)
Logo.Name = "Logo"
Logo.Parent = MainFrame
Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Logo.BackgroundTransparency = 1.000
Logo.BorderColor3 = Color3.fromRGB(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0.5, 0, 0.5, 0)
Logo.Size = UDim2.new(0, 300, 0, 300)
Logo.Image = LogoImage
Logo.ImageTransparency = 0.8
Name.Name = "Name"
Name.Parent = MainFrame
Name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Name.BackgroundTransparency = 1.000
Name.ClipsDescendants = true
Name.Position = UDim2.new(0.0520229861, 0, 0.0283840168, 0)
Name.Size = UDim2.new(0, 448, 0, 39)
Name.Font = Enum.Font.GothamBold
Name.Text = HubName
Name.TextColor3 = Color3.fromRGB(255, 255, 255)
Name.TextSize = 32.000
ProfileName.Name = "ProfileName"
ProfileName.Parent = MainFrame
ProfileName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.BackgroundTransparency = 1.000
ProfileName.ClipsDescendants = true
ProfileName.Position = UDim2.new(0.38, 0, 0.28, 0)
ProfileName.Size = UDim2.new(0, 318, 0, 25)
ProfileName.Font = Enum.Font.Gotham
ProfileName.Text = "Target Name : "..game.Players.LocalPlayer.Name
ProfileName.TextColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.TextSize = 22.000
ProfileName.TextXAlignment = Enum.TextXAlignment.Left
Text_1.Name = "Text_1"
Text_1.Parent = MainFrame
Text_1.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Text_1.BackgroundTransparency = 1.000
Text_1.ClipsDescendants = true
Text_1.Position = UDim2.new(0.38, 0, 0.40, 0)
Text_1.Size = UDim2.new(0, 318, 0, 25)
Text_1.Font = Enum.Font.Gotham
Text_1.Text = "Current Bounty : 10,000,000"
Text_1.TextColor3 = Color3.fromRGB(255, 255, 255)
Text_1.TextSize = 22.000
Text_1.TextXAlignment = Enum.TextXAlignment.Left
Text_2.Name = "Text_2"
Text_2.Parent = MainFrame
Text_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Text_2.BackgroundTransparency = 1.000
Text_2.ClipsDescendants = true
Text_2.Position = UDim2.new(0.38, 0, 0.52, 0)
Text_2.Size = UDim2.new(0, 317, 0, 25)
Text_2.Font = Enum.Font.Gotham
Text_2.Text = "Earned Bounty : 10,000,000"
Text_2.TextColor3 = Color3.fromRGB(255, 255, 255)
Text_2.TextSize = 22.000
Text_2.TextXAlignment = Enum.TextXAlignment.Left
Text_3.Name = "Text_3"
Text_3.Parent = MainFrame
Text_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Text_3.BackgroundTransparency = 1.000
Text_3.ClipsDescendants = true
Text_3.Position = UDim2.new(0.38, 0, 0.64, 0)
Text_3.Size = UDim2.new(0, 317, 0, 25)
Text_3.Font = Enum.Font.Gotham
Text_3.Text = "Time Elapsed : 59 M - 59 S"
Text_3.TextColor3 = Color3.fromRGB(255, 255, 255)
Text_3.TextSize = 22.000
Text_3.TextXAlignment = Enum.TextXAlignment.Left
ProfileImage.Parent = MainFrame
ProfileImage.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
ProfileImage.BackgroundTransparency = 0
ProfileImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileImage.BorderSizePixel = 0
ProfileImage.Position = UDim2.new(0.0517928302, 0, 0.243346125, 0)
ProfileImage.Size = UDim2.new(0, 148, 0, 148)
ProfileImage.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. game.Players.LocalPlayer.UserId .. "&width=420&height=420&format=png"
local UiToggle_UiStroke1 = Instance.new("UIStroke")
UiToggle_UiStroke1.Color = ColorTheme
UiToggle_UiStroke1.Thickness = 2
UiToggle_UiStroke1.Name = "UiToggle_UiStroke1"
UiToggle_UiStroke1.Parent = MainFrame
local Corner1 = Instance.new("UICorner")
Corner1.Name = "Corner"
Corner1.Parent = ProfileImage
Corner1.CornerRadius = UDim.new(0, 100)
local UiStroke1_1 = Instance.new("UIStroke")
UiStroke1_1.Color = ColorTheme
UiStroke1_1.Thickness = 2
UiStroke1_1.Name = "UiToggle_UiStroke1"
UiStroke1_1.Parent = ProfileImage
dragify(MainFrame, MainFrame)
local TimeElapsed = true
local TimeCount_S = 0
local TimeCount_M = 0
while TimeElapsed do
    wait(1)
    TimeCount_S = TimeCount_S + 1
    if TimeCount_S > 60 then
        TimeCount_S = 0
        TimeCount_M = TimeCount_M + 1
    end
    Text_3.Text = "Time Elapsed : "..TimeCount_M.." M - "..TimeCount_S.." S"
end
Text_1.Text = "Current Bounty : 10,000,000"
Text_2.Text = "Earned Bounty : 10,000,000"
