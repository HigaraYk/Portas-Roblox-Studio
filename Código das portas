--Vídeo das portas: https://www.youtube.com/watch?v=B1sRQObBWm4


-- Porta 1 (The Plaza) 

   Apenas desabilite a opção de CanCollide da porta que deseja usar

----------------------------------------------------------------------

-- Porta 2 (Urbis) 

local porta = script.Parent -- Pega a porta principal e armazena em uma variável (O script está dentro da porta)

local subporta = porta.Parent.SubPorta -- Pega a segunnda porta e armazena em uma variável

porta.ClickDetector.MouseClick:Connect(function() -- Ao clicar na porta
	print("porta 2") -- Print de confirmação
	porta.Transparency = 1 -- Transparencia da porta = Invisivel
	subporta.Transparency = 0 -- Transparencia da porta = Visivel 
	porta.ClickDetector.MaxActivationDistance = 0 -- Tira a opção de clicar na porta
	porta.CanCollide = false -- Colisão da porta principal desativada
	task.wait(2)
	porta.Transparency = 0 -- Transparencia da porta = Visivel 
	subporta.Transparency = 1 -- Transparencia da porta = Invisivel
	porta.ClickDetector.MaxActivationDistance = 15
	porta.CanCollide = true -- Colisão da porta principal ativada
end)

----------------------------------------------------------------------

-- Porta 3 (Flee The Facility) 

local porta = script.Parent

local debounce = true -- Intervalo de tempo

porta.ClickDetector.MouseClick:Connect(function()
	if debounce == true then
		
		debounce = false
		
		for i = 1,20 do 
			porta:PivotTo(
				porta:GetPivot() * CFrame.Angles(math.rad(5),0,0)
			)
			wait(0,1)
		end
		
	elseif debounce == false then
		
		debounce = true
		
		for i = 1,20 do 
			porta:PivotTo(
				porta:GetPivot() * CFrame.Angles(math.rad(-5),0,0)
			)
			wait(0,1)
		end
		
	end
end)

----------------------------------------------------------------------

-- Porta 4 (Area 51) 

local porta = script.Parent

-------------------------------------------------------------

local BotaoFechar = porta.Parent["Botão"].BotaoFechar -- Obter o potão do painel
local BotaoAbrir = porta.Parent["Botão"].BotaoAbrir

-------------------------------------------------------------

local debounce = true -- Controle de ações 

-------------------------------------------------------------

local TweenService = game:GetService("TweenService")  --  Animação avançada

local TweenInfo = TweenInfo.new(
	2, -- Duração da Animação
	Enum.EasingStyle.Sine, -- Movimento Suave
	Enum.EasingDirection.Out -- Direção Reservada
)

local portaFechada = porta.Position -- Posição original
local portaAberta = porta.Position + Vector3.new(5) -- Posição Final

local Abrir = TweenService:Create(porta, TweenInfo, {
	Position = portaAberta
})

local Fechar = TweenService:Create(porta, TweenInfo, {
	Position = portaFechada
})
-------------------------------------------------------------

BotaoAbrir.ClickDetector.MouseClick:Connect(function()
	if debounce == true then
		debounce = false
		
		Abrir:Play()
		
		wait(2)
	end

end)

-------------------------------------------------------------

BotaoFechar.ClickDetector.MouseClick:Connect(function()
	if debounce == false then
		debounce = true
		
		Fechar:Play()
		
		wait(2)
	end
	
end)
