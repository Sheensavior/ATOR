-- =========================
-- CHỈ CHẠY Ở PLACE ID NÀY
-- =========================
local TARGET_PLACE_ID = 14916516914

if game.PlaceId ~= TARGET_PLACE_ID then
    warn("Sai PlaceId - Script không chạy")
    return
end

-- =========================
-- UI THÔNG BÁO SCRIPT ĐANG CHẠY
-- =========================
local Players = game:GetService("Players")
local player = Players.LocalPlayer

local screenGui = Instance.new("ScreenGui")
screenGui.Name = "AutoSmartUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = player:WaitForChild("PlayerGui")

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 260, 0, 60)
frame.Position = UDim2.new(0.5, -130, 0.08, 0)
frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
frame.BorderSizePixel = 0
frame.Parent = screenGui

local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 10)
corner.Parent = frame

local label = Instance.new("TextLabel")
label.Size = UDim2.new(1, 0, 1, 0)
label.BackgroundTransparency = 1
label.Text = "Auto Smart automatic"
label.TextColor3 = Color3.fromRGB(255, 255, 255)
label.TextScaled = true
label.Font = Enum.Font.GothamBold
label.Parent = frame

print("Auto Smart automatic đang hoạt động")

repeat task.wait() until game:IsLoaded()

local Players = game:GetService("Players")
local TeleportService = game:GetService("TeleportService")
local HttpService = game:GetService("HttpService")

local player = Players.LocalPlayer

-- =========================
-- PATH FILE
-- =========================
local configPath = "Violet/AOTR/Lobby/settings/Auto Farm Gem.json"
local slotPath = "Violet/AOTR/Menu/settings/autoload.txt"

-- =========================
-- READ FILE SAFE
-- =========================
local function safeRead(path)
    if not isfile(path) then
        warn("Không tìm thấy file: " .. path)
        return nil
    end

    local success, result = pcall(function()
        return readfile(path)
    end)

    return success and result or nil
end

-- =========================
-- LOAD JSON
-- =========================
local function loadConfig()
    local raw = safeRead(configPath)
    if not raw then
        return nil
    end

    local success, decoded = pcall(function()
        return HttpService:JSONDecode(raw)
    end)

    if success then
        return decoded
    end

    return nil
end

-- =========================
-- SAVE JSON
-- =========================
local function saveConfig(data)
    writefile(configPath, HttpService:JSONEncode(data))
end

-- =========================
-- FIND IDX
-- =========================
local function findObj(data, idx)
    for _, obj in pairs(data.objects) do
        if obj.idx == idx then
            return obj
        end
    end
end

-- =========================
-- UI VALUES
-- =========================
local function parseNumber(text)
    text = tostring(text)
    text = text:gsub(",", "")

    local num = tonumber(text)
    return num or 0
processLogic()
