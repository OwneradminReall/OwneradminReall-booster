--[[
    OwneradminReall Booster - Menülü Hız & FPS
]]

-- Ana GUI Oluşturma
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local SpeedInput = Instance.new("TextBox")
local ApplyButton = Instance.new("TextButton")
local UICorner = Instance.new("UICorner")

-- GUI Ayarları
ScreenGui.Parent = game:GetService("CoreGui")
ScreenGui.Name = "OwneradminReallMenu"

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
MainFrame.Position = UDim2.new(0.5, -100, 0.5, -75)
MainFrame.Size = UDim2.new(0, 200, 0, 150)
MainFrame.Active = true
MainFrame.Draggable = true -- Menüyü ekranda sürükleyebilirsin

UICorner.Parent = MainFrame

Title.Parent = MainFrame
Title.Size = UDim2.new(1, 0, 0, 40)
Title.Text = "OwneradminReall"
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.BackgroundTransparency = 1
Title.TextSize = 18
Title.Font = Enum.Font.GothamBold

SpeedInput.Parent = MainFrame
SpeedInput.Position = UDim2.new(0.1, 0, 0.4, 0)
SpeedInput.Size = UDim2.new(0.8, 0, 0, 30)
SpeedInput.PlaceholderText = "Hız Yaz (Örn: 100)"
SpeedInput.Text = ""
SpeedInput.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
SpeedInput.TextColor3 = Color3.fromRGB(255, 255, 255)

ApplyButton.Parent = MainFrame
ApplyButton.Position = UDim2.new(0.1, 0, 0.7, 0)
ApplyButton.Size = UDim2.new(0.8, 0, 0, 35)
ApplyButton.Text = "Hızı Ayarla"
ApplyButton.BackgroundColor3 = Color3.fromRGB(0, 150, 255)
ApplyButton.TextColor3 = Color3.fromRGB(255, 255, 255)

-- Hız Uygulama Fonksiyonu
ApplyButton.MouseButton1Click:Connect(function()
    local speed = tonumber(SpeedInput.Text)
    if speed then
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = speed
        print("Hız Ayarlandı: " .. speed)
    end
end)

-- FPS Booster Kısmı (Otomatik Çalışır)
for _, v in pairs(game:GetDescendants()) do
    if v:IsA("BasePart") then
    
