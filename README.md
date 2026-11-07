# Roblox-coin-generator
A script in luau for roblox
local Players = game:GetService("Players")

local COIN_REWARD = 10

local COOLDOWN = 2

local function giveCoins(player)

    local leaderstats = player:FindFirstChild("leaderstats")

    if not leaderstats then return end

    local coins = leaderstats:FindFirstChild("Coins")

    if coins then

        coins.Value += COIN_REWARD

        print(player.Name .. " earned " .. COIN_REWARD .. " coins!")

    end

end

Players.PlayerAdded:Connect(function(player)

    local leaderstats = Instance.new("Folder")

    leaderstats.Name = "leaderstats"

    leaderstats.Parent = player

    local coins = Instance.new("IntValue")

    coins.Name = "Coins"

    coins.Value = 0

    coins.Parent = leaderstats

    print(player.Name .. " joined the game!")

end)

print("Coin Generator System loaded!")
