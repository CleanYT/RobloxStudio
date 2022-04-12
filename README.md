local humanoid = script.Parent
local jumpHeight = 100
humanoid.JumpPower = jumpHeight

function onJumpRequest()
  if humanoid:GetState() == Enum.HumanoidStateType.Freefall then
    humanoid.JumpPower = jumpHeight * 1.5
    humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
  else
    humanoid.JumpPower = jumpHeight
  end
end

game:GetService("UserInputService").JumpRequest:connect(onJumpRequest)

---- Made By Emily's | Join Discord  https://discord.gg/cVMFNXDjBT
