-- Criação da interface
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local ToggleButton = Instance.new("TextButton")

-- Configurações da interface
ScreenGui.Name = "SpeedControlGui"
ScreenGui.Parent = game.CoreGui

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
MainFrame.Size = UDim2.new(0, 250, 0, 150)
MainFrame.Position = UDim2.new(0.5, -125, 0.5, -75)
MainFrame.Active = true
MainFrame.Draggable = true

ToggleButton.Name = "ToggleButton"
ToggleButton.Parent = MainFrame
ToggleButton.BackgroundColor3 = Color3.new(0.8, 0.8, 0.8)
ToggleButton.Size = UDim2.new(0, 200, 0, 50)
ToggleButton.Position = UDim2.new(0.5, -100, 0.5, -25)
ToggleButton.Text = "Ativar Velocidade"
ToggleButton.TextColor3 = Color3.new(0, 0, 0)
ToggleButton.TextSize = 18

-- Variável para controlar o estado do script de velocidade
local speedEnabled = false

-- Função para ativar/desativar o script de velocidade
local function toggleSpeed()
    speedEnabled = not speedEnabled
    if speedEnabled então
        print("Velocidade ativada")
        ToggleButton.Text = "Desativar Velocidade"
        -- Aumentar a velocidade do jogador
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        humanoid.WalkSpeed = 50 -- Aumenta a velocidade para 50
    else
        print("Velocidade desativada")
        ToggleButton.Text = "Ativar Velocidade"
        -- Restaurar a velocidade do jogador
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        humanoid.WalkSpeed = 16 -- Velocidade padrão
    end
end

-- Conectar a função ao botão
ToggleButton.MouseButton1Click:Connect(toggleSpeed)

-- Função para permitir mover a interface livremente
local function makeDraggable(gui)
    local dragging = false
    local dragInput, dragStart, startPos

    local function update(input)
        local delta = input.Position - dragStart
        gui.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
    end

    gui.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch então
            dragging = true
            dragStart = input.Position
            startPos = gui.Position

            input.Changed:Connect(function()
                if input.UserInputState == Enum.UserInputState.End então
                    dragging = false
                end
            end)
        end
    end)

    gui.InputChanged:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseMovement ou input.UserInputType == Enum.UserInputType.Touch então
            dragInput = input
        end
    end)

    game:GetService("UserInputService").InputChanged:Connect(function(input)
        if input == dragInput e dragging então
            update(input)
        end
    end)
end

makeDraggable(MainFrame)

-- Script Lua "simples" para controlar a velocidade do jogador no Roblox

-- Criação da interface
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local ToggleButton = Instance.new("TextButton")

-- Configurações da interface
ScreenGui.Name = "SpeedControlGui"
ScreenGui.Parent = game.CoreGui

MainFrame.Name = "MainFrame"
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
MainFrame.Size = UDim2.new(0, 250, 0, 150)
MainFrame.Position = UDim2.new(0.5, -125, 0.5, -75)
MainFrame.Active = true
MainFrame.Draggable = true

ToggleButton.Name = "ToggleButton"
ToggleButton.Parent = MainFrame
ToggleButton.BackgroundColor3 = Color3.new(0.8, 0.8, 0.8)
ToggleButton.Size = UDim2.new(0, 200, 0, 50)
ToggleButton.Position = UDim2.new(0.5, -100, 0.5, -25)
ToggleButton.Text = "Ativar Velocidade"
ToggleButton.TextColor3 = Color3.new(0, 0, 0)
ToggleButton.TextSize = 18

-- Variável para controlar o estado do script de velocidade
local speedEnabled = false

-- Função para ativar/desativar o script de velocidade
local function toggleSpeed()
    speedEnabled = not speedEnabled
    if speedEnabled então
        print("Velocidade ativada")
        ToggleButton.Text = "Desativar Velocidade"
        -- Aumentar a velocidade do jogador
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        humanoid.WalkSpeed = 50 -- Aumenta a velocidade para 50
    else
        print("Velocidade desativada")
        ToggleButton.Text = "Ativar Velocidade"
        -- Restaurar a velocidade do jogador
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        humanoid.WalkSpeed = 16 -- Velocidade padrão
    end
end

-- Conectar a função ao botão
ToggleButton.MouseButton1Click:Connect(toggleSpeed)

-- Função para permitir mover a interface livremente
local function makeDraggable(gui)
    local dragging = false
    local dragInput, dragStart, startPos

    local function update(input)
        local delta = input.Position - dragStart
        gui.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
    end

    gui.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 ou input.UserInputType == Enum.UserInputType.Touch então
            dragging = true
            dragStart = input.Position
            startPos = gui.Position

            input.Changed:Connect(function()
                if input.UserInputState == Enum.UserInputState.End então
                    dragging = false
                end
            end)
        end
    end)

    gui.InputChanged:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseMovement ou input.UserInputType == Enum.UserInputType.Touch então
            dragInput = input
        end
    end)

    game:GetService("UserInputService").InputChanged:Connect(function(input)
        if input == dragInput e dragging então
            update(input)
        end
    end)
end

makeDraggable(MainFrame)
