local player = game.Players.LocalPlayer
local playerGui = player:FindFirstChild("PlayerGui")
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local rootPart = character:WaitForChild("HumanoidRootPart")
local animator = humanoid:FindFirstChild("Animator") or Instance.new("Animator", humanoid)
local TweenService = game:GetService("TweenService")

if playerGui then
    local hotbarFrame = playerGui:FindFirstChild("Hotbar") and playerGui.Hotbar:FindFirstChild("Backpack") and playerGui.Hotbar.Backpack:FindFirstChild("Hotbar")
    if hotbarFrame then
        local toolNames = { "Surprise Final Shot", "Consecutive Kicks", "Pass", "Rainbow Flick" }
        for i = 1, 4 do
            local baseButton = hotbarFrame:FindFirstChild(tostring(i)) and hotbarFrame[tostring(i)]:FindFirstChild("Base")
            if baseButton then
                baseButton.ToolName.Text = toolNames[i]
            end
        end
    end

    local function updateGuiText()
        local magicHealth = playerGui:FindFirstChild("ScreenGui") and playerGui.ScreenGui:FindFirstChild("MagicHealth")
        if magicHealth then
            local textLabel = magicHealth:FindFirstChild("TextLabel")
            if textLabel then
                textLabel.Text = "Best Striker Of The World"
            end
        end
    end

    updateGuiText()
    playerGui.DescendantAdded:Connect(updateGuiText)
end

local animations = {
    [10468665991] = "rbxassetid://94395585475029",
    [10466974800] = "rbxassetid://18179181663",
    [10471336737] = "rbxassetid://13376869471",
    [12510170988] = "rbxassetid://15295895753",
    [11343318134] = "rbxassetid://12983333733",
    [15955393872] = "rbxassetid://15944317351",
    [12983333733] = "rbxassetid://13073745835",
 
}

local function findClosestPlayer()
    local closestPlayer, minDistance = nil, math.huge
    for _, otherPlayer in ipairs(game.Players:GetPlayers()) do
        if otherPlayer ~= player and otherPlayer.Character then
            local otherRoot = otherPlayer.Character:FindFirstChild("HumanoidRootPart")
            if otherRoot then
                local distance = (rootPart.Position - otherRoot.Position).Magnitude
                if distance < minDistance then
                    minDistance, closestPlayer = distance, otherPlayer
                end
            end
        end
    end
    return closestPlayer
end

local function createTeleportTrail(startPos, endPos)
    local trailPart = Instance.new("Part")
    trailPart.Size = Vector3.new(0.5, 0.5, (startPos - endPos).Magnitude)
    trailPart.CFrame = CFrame.new(startPos, endPos) * CFrame.new(0, 0, -trailPart.Size.Z / 2)
    trailPart.Anchored = true
    trailPart.CanCollide = false
    trailPart.Material = Enum.Material.Neon
    trailPart.BrickColor = BrickColor.new("Bright blue")
    trailPart.Parent = workspace

    TweenService:Create(trailPart, TweenInfo.new(0.5, Enum.EasingStyle.Linear, Enum.EasingDirection.Out), { Transparency = 1 }):Play()
    game:GetService("Debris"):AddItem(trailPart, 0.5)
end

local function createOptimizedLight()
    local lightPart = Instance.new("Part")
    lightPart.Size = Vector3.new(2, 2, 2)
    lightPart.Shape = Enum.PartType.Ball
    lightPart.Anchored = true
    lightPart.CanCollide = false
    lightPart.Material = Enum.Material.Neon
    lightPart.Transparency = 1
    lightPart.Parent = workspace

    local light = Instance.new("PointLight", lightPart)
    light.Brightness = 2
    light.Range = 8

    local colors = { Color3.fromRGB(0, 120, 255), Color3.fromRGB(0, 60, 150) }
    local index = 1

    task.spawn(function()
        while lightPart.Parent do
            light.Color = colors[index]
            index = index == 1 and 2 or 1
            task.wait(0.5)
        end
    end)

    game:GetService("RunService").Stepped:Connect(function()
        local root = character:FindFirstChild("HumanoidRootPart")
        if root then
            lightPart.Position = root.Position + Vector3.new(0, 3, 0)
        end
    end)
end

local tackleTool = Instance.new("Tool")
tackleTool.Name = "Tackle"
tackleTool.RequiresHandle = false
tackleTool.Parent = player.Backpack

local tackleSound = Instance.new("Sound")
tackleSound.SoundId = "rbxassetid://9119331077"
tackleSound.Volume = 2
tackleSound.Parent = tackleTool

local tackleAnimation = Instance.new("Animation")
tackleAnimation.AnimationId = "rbxassetid://17858878027"

tackleTool.Activated:Connect(function()
    if humanoid and rootPart then
        local camera = workspace.CurrentCamera
        local lookVector = camera.CFrame.LookVector

        local animTrack = animator:LoadAnimation(tackleAnimation)
        animTrack:Play()

        tackleSound:Play()

        local moveSpeed = 80
        local connection
        connection = game:GetService("RunService").Heartbeat:Connect(function()
            if animTrack.IsPlaying then
                rootPart.Velocity = lookVector * moveSpeed
            else
                rootPart.Velocity = Vector3.new(0, rootPart.Velocity.Y, 0)
                connection:Disconnect()
            end
        end)
    end
end)

humanoid.AnimationPlayed:Connect(function(animTrack)
    local animId = tonumber(animTrack.Animation.AnimationId:match("%d+"))
    if animations[animId] then
        for _, track in pairs(humanoid:GetPlayingAnimationTracks()) do
            track:Stop()
        end

        local anim = Instance.new("Animation")
        anim.AnimationId = animations[animId]
        local loadedAnim = animator:LoadAnimation(anim)
        loadedAnim:Play()
        loadedAnim:AdjustSpeed(1)

        if animId == 10468665991 then
            local closestPlayer = findClosestPlayer()
            if closestPlayer and closestPlayer.Character then
                local targetRoot = closestPlayer.Character:FindFirstChild("HumanoidRootPart")
                if targetRoot then
                    local startPosition = rootPart.Position
                    rootPart.CFrame = targetRoot.CFrame * CFrame.new(0, 0, 1)
                    createTeleportTrail(startPosition, rootPart.Position)
                end
            end
        end
    end
end)

createOptimizedLight()

local screenGui = Instance.new("ScreenGui")
screenGui.Parent = playerGui

local textLabel = Instance.new("TextLabel")
textLabel.Size = UDim2.new(0.8, 0, 0.1, 0)
textLabel.Position = UDim2.new(0.1, 0, 0.5, 0)
textLabel.BackgroundTransparency = 1
textLabel.TextScaled = true
textLabel.TextColor3 = Color3.new(1, 1, 1)
textLabel.Font = Enum.Font.SourceSansBold
textLabel.Parent = screenGui

local function showText()
    local dialogue = "I came here to turn things around, to become the best in the world."
    textLabel.Text = ""

    for i = 1, #dialogue do
        textLabel.Text = string.sub(dialogue, 1, i)
        task.wait(0.05)
    end

    task.wait(2)
    screenGui:Destroy()
end

showText()
