--[[
    OwneradminReall Booster
]]

-- AYARLAR (Buradaki sayıyı istediğin gibi değiştir)
local HizMiktari = 100 

-- Bildirim
game:GetService("StarterGui"):SetCore("SendNotification", {
    Title = "OwneradminReall Booster";
    Text = "Hız: " .. HizMiktari .. " olarak ayarlandı.";
    Duration = 5;
})

-- Karakter Hızını Uygulama
local player = game.Players.LocalPlayer
local function ApplySpeed(char)
    local hum = char:WaitForChild("Humanoid", 5)
    if hum then
        hum.WalkSpeed = HizMiktari
    end
end

player.CharacterAdded:Connect(ApplySpeed)
if player.Character then ApplySpeed(player.Character) end

-- Performans ve FPS Optimizasyonu
for _, v in pairs(game:GetDescendants()) do
    if v:IsA("BasePart") then
        v.Material = Enum.Material.SmoothPlastic
    elseif v:IsA("Decal") or v:IsA("Texture") then
        v:Destroy()
    elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
        v.Enabled = false
    end
end

game:GetService("Lighting").GlobalShadows = false
if setfpscap then setfpscap(999) end

print("OwneradminReall Booster: Hız ve Performans Aktif!")
