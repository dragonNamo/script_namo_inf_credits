local ScreenGui = Instance.new("ScreenGui") -- by dragon namo
local open = Instance.new("TextButton")     -- by dragon namo
local UICorner = Instance.new("UICorner")   -- by dragon namo
local frame = Instance.new("Frame")
local close = Instance.new("TextButton")    -- by dragon namo
local TextLabel = Instance.new("TextLabel") -- by dragon namo 
local aimbot = Instance.new("TextButton")
local UICorner_2 = Instance.new("UICorner")

--Properties:

ScreenGui.Parent = game.CoreGui

open.Name = "open"
open.Parent = ScreenGui
open.AnchorPoint = Vector2.new(1, 1)
open.BackgroundColor3 = Color3.fromRGB(63, 63, 63)
open.Position = UDim2.new(0.451809943, 0, 0.312941164, 0)
open.Size = UDim2.new(0, 353, 0, 30)
open.Font = Enum.Font.DenkOne
open.Text = "hax"
open.TextColor3 = Color3.fromRGB(255, 0, 0)
open.TextScaled = true
open.TextSize = 14.000
open.TextWrapped = true

UICorner.Parent = open

frame.Name = "frame"
frame.Parent = ScreenGui
frame.BackgroundColor3 = Color3.fromRGB(66, 66, 66)
frame.Position = UDim2.new(0.218782276, 0, 0.312549353, 0)
frame.Size = UDim2.new(0, 360, 0, 113)
frame.Visible = false

close.Name = "close"
close.Parent = frame
close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
close.BackgroundTransparency = 1.000
close.Position = UDim2.new(0.832106054, 0, 0, 0)
close.Size = UDim2.new(0, 60, 0, 47)
close.Font = Enum.Font.SourceSansBold
close.Text = "-"
close.TextColor3 = Color3.fromRGB(255, 0, 0)
close.TextScaled = true
close.TextSize = 14.000
close.TextWrapped = true

TextLabel.Parent = frame
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.Position = UDim2.new(0.0277381465, 0, 0.15338999, 0)
TextLabel.Size = UDim2.new(0, 350, 0, 28)
TextLabel.Font = Enum.Font.PermanentMarker
TextLabel.Text = "namo script"
TextLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextWrapped = true

aimbot.Name = "aimbot"
aimbot.Parent = frame
aimbot.BackgroundColor3 = Color3.fromRGB(80, 80, 80)
aimbot.Position = UDim2.new(0.0417827293, 0, 0.541923583, 0)
aimbot.Size = UDim2.new(0, 327, 0, 48)
aimbot.Font = Enum.Font.FredokaOne
aimbot.Text = "credits: Off"
aimbot.TextColor3 = Color3.fromRGB(159, 0, 0)
aimbot.TextScaled = true
aimbot.TextSize = 14.000
aimbot.TextWrapped = true

UICorner_2.Parent = frame

-- Scripts:

local function SDLTHU_fake_script() -- open.LocalScript 
	local script = Instance.new('LocalScript', open)

	local UIS = game:GetService('UserInputService')

	local frame = script.Parent



	local dragToggle = nil

	local dragSpeed = 0.25

	local dragStart = nil

	local startPos = nil



	local function updateInput(input)

		local delta = input.Position - dragStart

		local position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,

			startPos.Y.Scale, startPos.Y.Offset + delta.Y)

		game:GetService('TweenService'):Create(frame, TweenInfo.new(dragSpeed), {Position = position}):Play()

	end



	frame.InputBegan:Connect(function(input)

		if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then 

			dragToggle = true

			dragStart = input.Position

			startPos = frame.Position

			input.Changed:Connect(function()

				if input.UserInputState == Enum.UserInputState.End then

					dragToggle = false

				end

			end)

		end

	end)



	UIS.InputChanged:Connect(function(input)

		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then

			if dragToggle then

				updateInput(input)

			end

		end

	end)

end
coroutine.wrap(SDLTHU_fake_script)()
local function RANGC_fake_script() -- aimbot.on/off 
	local script = Instance.new('LocalScript', aimbot)

	_G. aimbot = false

	script.Parent.MouseButton1Click:Connect(function()
		if _G.aimbot == false then
			_G.aimbot = true
			script.Parent.TextColor3 = Color3.fromRGB(0,170,0)
			script.Parent.Text = 'credits: On'
		else
			_G.aimbot = false
			script.Parent.TextColor3 = Color3.fromRGB(250,0,0)
			script.Parent.Text = 'credits: Off'
		end
	end)
end
coroutine.wrap(RANGC_fake_script)()
local function DAHWF_fake_script() -- frame.open/close 
	local script = Instance.new('LocalScript', frame)

	local frame = script.Parent
	local open = frame.Parent:WaitForChild("open")
	local close = frame:WaitForChild("close")

	open.MouseButton1Click:connect(function()
		frame.Visible = true
	end)

	close.MouseButton1Click:connect(function()
		frame.Visible = false
	end)
end
coroutine.wrap(DAHWF_fake_script)()
local function TDRI_fake_script() -- frame.smoth frame 
	local script = Instance.new('LocalScript', frame)

	local UIS = game:GetService('UserInputService')

	local frame = script.Parent



	local dragToggle = nil

	local dragSpeed = 0.25

	local dragStart = nil

	local startPos = nil



	local function updateInput(input)

		local delta = input.Position - dragStart

		local position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X,

			startPos.Y.Scale, startPos.Y.Offset + delta.Y)

		game:GetService('TweenService'):Create(frame, TweenInfo.new(dragSpeed), {Position = position}):Play()

	end



	frame.InputBegan:Connect(function(input)

		if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) then 

			dragToggle = true

			dragStart = input.Position

			startPos = frame.Position

			input.Changed:Connect(function()

				if input.UserInputState == Enum.UserInputState.End then

					dragToggle = false

				end

			end)

		end

	end)



	UIS.InputChanged:Connect(function(input)

		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then

			if dragToggle then

				updateInput(input)

			end

		end

	end)

end
coroutine.wrap(TDRI_fake_script)()
