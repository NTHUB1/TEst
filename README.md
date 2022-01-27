local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Blox Fruit-Night Hub", "BloodTheme")


local Tab = Window:NewTab("MAIN MENU")
local Section = Tab:NewSection("FAST ATTACK")

Section:NewButton("USE", "Click", function()
spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        local Combat = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
        local Cemara = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework.CameraShaker)
        Cemara.CameraShakeInstance.CameraShakeState = {FadingIn = 3, FadingOut = 2, Sustained = 0, Inactive = 1}
        Combat.activeController.timeToNextAttack = 0
    end)
end) 
end)


spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        game:GetService'VirtualUser':CaptureController()
        game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
    end)
end) 
end)
end)
