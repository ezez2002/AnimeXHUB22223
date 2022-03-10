

            game.StarterGui:SetCore("SendNotification", {
                Title = "Welecome To Anime X hub", 
                Text = "Script Anime X hub",
                Icon = "",
                Duration = 2
            })


local DiscordLib = loadstring(game:HttpGet"https://raw.githubusercontent.com/dawid-scripts/UI-Libs/main/discord%20lib.txt")()

local win = DiscordLib:Window("Anime X hub Auto Farm Mode | Sam City")

local serv = win:Server("Menu", "")



local tgls = serv:Channel("Auto Farm all")



tgls:Toggle("Auto Farm Money",false, function(e)
_G.Autofarms = e

while _G.Autofarms do wait ()

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(143.070572, 2.91853189, 184.472519, -0.0588405021, -0.434383333, -0.898804247, 0.140513867, 0.887796283, -0.438262075, 0.988328695, -0.152082026, 0.00879849866)
Weapon = "Combat"
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end)

tgls:Toggle("Auto Farm Money + hop",false, function(t)
_G.Autofarm = t

while _G.Autofarm do wait ()

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(142.486664, 4.06002617, 183.540009, -0.017452389, 6.76843186e-08, -0.99984771, 7.45090531e-08, 1, 6.63940725e-08, 0.99984771, -7.33389669e-08, -0.017452389)
repeat
    wait(5)
until game:IsLoaded()
game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId,game.JobId)
Weapon = "Combat"
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end)


tgls:Toggle("Auto Click",true, function(abc)
_G.Autoclick = abc

while _G.Autoclick do wait ()

game:GetService'VirtualUser':CaptureController()game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
end
end)

local drops = serv:Channel("Players")


players = {}

for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
end




local drop = drops:Dropdown("Select Players", players, function(abc)
    Select = abc
end)


drops:Toggle("Auto Kill Players",false, function(b)
_G.Autotp = b

while _G.Autotp do wait ()

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Select].Character.HumanoidRootPart.CFrame
end
end)

drops:Button("Refesh Players", function()
    table.clear(players)
for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
end
end)



local Weaponlist = {}
local Weapon = nil

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end






local drop = drops:Dropdown("Use Kill Players", Weaponlist, function(currentOption)
    Weapon = currentOption
end)


drops:Toggle("Auto Equip",false, function(exe)
AutoEquiped = exe
end)

spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end
end)



local btns = serv:Channel("Credit")

btns:Button("Credit", function()
DiscordLib:Notification("Credit", "Credit By x2Andssyz", "Okay")
end)




