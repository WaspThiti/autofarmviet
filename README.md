function CheckLevel()
    local MyLevel = game.Players.LocalPlayer.Data.Levels.Value
    if MyLevel == 1 or MyLevel <= 14 then
        MON = "Bandit LV. 1"
    elseif MyLevel >= 100000 or MyLevel <= 100000000 then
        MON = "Grab"
    end
end
 
_G.AutoLV = true --true/false
 
    spawn(function()
       game:GetService("RunService").RenderStepped:Connect(function()
        pcall(function()
            if _G.AutoLV then
CheckLevel()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["NPC DAMAGE"][MON].HumanoidRootPart.CFrame * CFrame.new(0,-5,0)
            end
        end)
       end)
    end)
 
