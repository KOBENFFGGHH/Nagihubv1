(getgenv()).Key = "Admin-888-999"

local keys = {
     "SPEED-YUYOIP-UJUM9",
     "SPEED-HUYHGU-7676",
     "SPEED-JUOP-UNM0",
     "SPEED-HJOP-MKOP0",
     "SPEED-MOKP-89MK",
     "SPEED-LOVE-KUY",
     "SPEED-YUYOIP-UJUM9",
     "SPEED-HUYHGU-7676",
     "SPEED-UJUKM-898M",
     "SPEED-87879-NESKJ",
     "SEED-NHUIL-7890M",
     "SPEED-NJKOL-78U8U",
     "SPEED-787-MJMKO",
     "SPEED-JKOPY-9MLO",
     "SPEED-MKLL-POI0",
     "SPEED-HIOPT-MKO9",
     "Admin-888-999",
     "OOOOOOOOOOOO",
}

local counter = 1
local keyCheck
for i,v in pairs(keys) do
    if counter == #keys then
        keys = ""
        game.Players.LocalPlayer:Kick("please enter your key")
    else
        if v == getgenv().Key then 
            -- check succes
            print("Succesfully, enjoy :]")
            -- your script

   if game:GetService("Players").LocalPlayer.PlayerGui.Main:FindFirstChild("ChooseTeam") then
        repeat wait()
            if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
                if _G.Team == "Pirate" then
                    for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
                        v.Function()
                    end
                elseif _G.Team == "Marine" then
                    for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
                        v.Function()
                    end
                else
                    for i, v in pairs(getconnections(game:GetService("Players").LocalPlayer.PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Activated)) do                                                                                                
                        v.Function()
                    end
                end
            end
        until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded()
    end
    
    if game:IsLoaded() then
    pcall(function()
        repeat wait()
        	game:GetService("ReplicatedStorage").Effect.Container.Respawn:Destroy()
            game:GetService("ReplicatedStorage").Effect.Container.Death:Destroy()
            game:GetService("ReplicatedStorage").Util.Sound.Storage.Swing:Destroy()
        until not game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Death") or not game:GetService("ReplicatedStorage").Effect.Container:FindFirstChild("Respawn")
    end)
end

    _G.Settings = {
        AutoFarm = false;
        AutoFarmFast = true;
        BringMonster = true;
        FastAttack = true;
        Select_Fast_Attack = {};
        Auto_Buso = true;
        DeleteDamageFx = true;
        AutoSetSpawnPoint = true;
        AutoSaber = false;
        AutoSaberHop = false;
        AutoPole = false;
        AutoPoleHop = false;
        AutoDeathStep = false;
        AutoSharkman = false;
        Auto_New_World = false;
        AutoFullyGodhuman = false;
        AutoFullySuperhuman = false;
        AutoElectricClaw = false;
        AutoDragonTalon = false;
        Point = 100;
        ShowFov = false;
        Aimbot_Skill = false;
        Select_Size_Fov = false;
        Aimbot_Gun = false;
        Select_Chips = {};
        Kill_Aura = false;
        Next_Island = false;
        Auto_Awakener = false;
        AutoSelectDungeon = {};
        StartDungeon = false;
    }
    
    local foldername = "NAGI HUB"
    local filename = "BloxFruit "..game.Players.LocalPlayer.Name.." Config.json"
     
    function saveSettings()
        local HttpService = game:GetService("HttpService")
        local json = HttpService:JSONEncode(_G.Settings)
        if (writefile) then
            if isfolder(foldername) then
                if isfile(foldername.."\\"..filename) then
                    writefile(foldername.."\\"..filename, json)
                else
                    writefile(foldername.."\\"..filename, json)
                end
            else
                makefolder(foldername)
                writefile(foldername.."\\"..filename, json)
            end
        end
    end
    
    function loadSettings()
        local HttpService = game:GetService("HttpService")
        if isfile(foldername.."\\"..filename) then
            _G.Settings = HttpService:JSONDecode(readfile(foldername.."\\"..filename))
        end
    end
     
    loadSettings()
    
    if _G.Settings.Select_Weapon == nil then
        for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
            if v.ToolTip == "Melee" then
                if game.Players.LocalPlayer.Backpack:FindFirstChild(tostring(v.Name)) then
                    _G.Settings.Select_Weapon = tostring(v.Name)
                end
            end
        end
    end

-------------->> // FN Webhook \\ <<-------------

local WebHookLog = {}

local AllRequest = http_request or request or HttpPost or syn.request
function WebHookLog:WebHookKaiTanSend(WebHookUrl)

	function GetFightingStyle(Style)
		ReturnText = ""
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetAwaken()
		ReturnText = ""
		Awakened_Z = ":x:"
		Awakened_X = ":x:"
		Awakened_C = ":x:"
		Awakened_V = ":x:"
		Awakened_F = ":x:"
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = ":white_check_mark:"
						end
						ReturnText = ":regional_indicator_z:"..Awakened_Z..
							"\n"..":regional_indicator_x:"..Awakened_X..
							"\n"..":regional_indicator_c:"..Awakened_C..
							"\n"..":regional_indicator_v:"..Awakened_V..
							"\n"..":regional_indicator_f:"..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = ":white_check_mark:"
						end
						ReturnText = ":regional_indicator_z:"..Awakened_Z..
							"\n"..":regional_indicator_x:"..Awakened_X..
							"\n"..":regional_indicator_c:"..Awakened_C..
							"\n"..":regional_indicator_v:"..Awakened_V..
							"\n"..":regional_indicator_f:"..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetWeapon(Rare)
		if Rare == "Common" then
			RareNumber = 0
		elseif Rare == "Uncommon" then
			RareNumber = 1
		elseif Rare == "Rare" then
			RareNumber = 2
		elseif Rare == "Legendary" then
			RareNumber = 3
		elseif Rare == "Mythical" then
			RareNumber = 4
		else
			return "Worng InPut"
		end
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryWeapons")) do
			if type(v) == "table" then
				if v.Rarity then
					if tonumber(v.Rarity) == RareNumber then
						ReturnText = ReturnText .. v.Name .. "\n"
					end
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetFruitInU()
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryFruits")) do
			if type(v) == "table" then
				if v ~= nil then
					ReturnText = ReturnText .. v.Name .. " : " .. v.Price .. "\n"
				end
			end
		end

		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetAllMelee()
		BuyDragonTalon = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true))
		if BuyDragonTalon then
			if BuyDragonTalon == 1 then
				TalComplete = true
			end
		end
		BuySuperhuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true))
		if BuySuperhuman then
			if BuySuperhuman == 1 then
				SupComplete = true
			end
		end
		BuySharkmanKarate = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true))
		if BuySharkmanKarate then
			if BuySharkmanKarate == 1 then
				SharkComplete = true
			end
		end
		BuyDeathStep = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true))
		if BuyDeathStep then
			if BuyDeathStep == 1 then
				DeathComplete = true
			end
		end
		BuyElectricClaw = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true))
		if BuyElectricClaw then
			if BuyElectricClaw == 1 then
				EClawComplete = true
			end
		end
		BuyGod = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true))
		if BuyGod then
			if BuyGod == 1 then
				GodComplete = true
			end
		end
		ReturnText = {}
		if SupComplete == true then
			table.insert(ReturnText,"SuperHuman")
		end
		if EClawComplete == true then
			table.insert(ReturnText,"Electric Claw")
		end
		if TalComplete == true then
			table.insert(ReturnText,"Dragon Talon")
		end
		if SharkComplete == true then
			table.insert(ReturnText,"Sharkman Karate")
		end
		if DeathComplete == true then
			table.insert(ReturnText,"Death Step")
		end
		if GodComplete == true then
			table.insert(ReturnText,"God Human")
		end

		if #ReturnText ~= 0 then
			return table.concat(ReturnText,",")
		else
			return "Not Have"
		end
	end

	local Embeds = {{
		["title"] = "Nagi Hub Webhooks Status**",
		["color"] = 1127128,
		["fields"] = {
			{
				["name"] = "User Name",
				["value"] = "||"..tostring(game.Players.LocalPlayer.Name).."||",
				["inline"] = true
			},
			{
				["name"] = "Level",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Level").Value),
				["inline"] = true
			},
			{
				["name"] = "Fragments",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Fragments").Value),
				["inline"] = true
			},
			{
				["name"] = "Bounty/Honor",
				["value"] = tostring(game:GetService("Players").LocalPlayer.leaderstats["Bounty/Honor"].Value),
				["inline"] = true
			},
			{
				["name"] = "Beli",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Beli").Value),
				["inline"] = true
			},
			{
				["name"] = "Fighting Style",
				["value"] = GetFightingStyle("Melee"),
				["inline"] = true
			},
			{
				["name"] = "Sword",
				["value"] = GetFightingStyle("Sword"),
				["inline"] = true
			},
			{
				["name"] = "Devil Fruit",
				["value"] = GetFightingStyle("Blox Fruit"),
				["inline"] = true
			},
			{
				["name"] = "Gun",
				["value"] = GetFightingStyle("Gun"),
				["inline"] = true
			},
			{
				["name"] = "Accessory",
				["value"] = GetFightingStyle("Wear"),
				["inline"] = true
			},
			{
				["name"] = "Race",
				["value"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Race").Value),
				["inline"] = true
			},
			{
				["name"] = "Awakened",
				["value"] = tostring(GetAwaken()),
				["inline"] = true
			},
			{
				["name"] = "Status",
				["value"] = "```sml\n"..tostring("Melee : "..game:GetService("Players").LocalPlayer.Data.Stats.Melee:WaitForChild("Level").Value .. 
					"\nDefense : "..game:GetService("Players").LocalPlayer.Data.Stats.Defense:WaitForChild("Level").Value .. 
					"\nSword : "..game:GetService("Players").LocalPlayer.Data.Stats.Sword:WaitForChild("Level").Value.. 
					"\nGun : "..game:GetService("Players").LocalPlayer.Data.Stats.Gun:WaitForChild("Level").Value .. 
					"\nDevil Fruit : "..game:GetService("Players").LocalPlayer.Data.Stats["Demon Fruit"]:WaitForChild("Level").Value).."```",
				["inline"] = true
			},
			{
				["name"] = "Common :blue_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Common")).."```",
				["inline"] = true
			},
			{
				["name"] = "Uncommon :green_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Uncommon")).."```",
				["inline"] = true
			},
			{
				["name"] = "Rare :yellow_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Rare")).."```",
				["inline"] = true
			},
			{
				["name"] = "Legendary :purple_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Legendary")).."```",
				["inline"] = true
			},
			{
				["name"] = "Mythical :red_circle:",
				["value"] = "```sml\n"..tostring(GetWeapon("Mythical")).."```",
				["inline"] = true
			},
			{
				["name"] = "Fruit In Inventory",
				["value"] = "```sml\n"..tostring(GetFruitInU()).."```",
				["inline"] = true
			},
			{
				["name"] = "All Melee",
				["value"] = "```sml\n"..tostring(GetAllMelee()).."```",
				["inline"] = true
			},



			{
				["name"] = "ㅤ",
				["value"] = tostring("ㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤㅤ"),
				["inline"] = false
			}},
		["footer"] = {
			["text"] = "Made by ! Speed".."\nTime".." : "..os.date("%c").." ("..os.date("%X")..")",
			["icon_url"] = "https://media.discordapp.net/attachments/991643580361867335/1036591759238627409/20221031_170501.jpg"
		},
	}}

	local Message
	if _G.SendWebHookPing then
		Message = {
			['username'] = "Under Webhook",
			["avatar_url"] = "https://media.discordapp.net/attachments/991643580361867335/1036591759238627409/20221031_170501.jpg",
			["content"] = "@everyone",
			["embeds"] = Embeds,
		}
	else
		Message = {
			['username'] = "Under Webhook",
			["avatar_url"] = "https://media.discordapp.net/attachments/991643580361867335/1036591759238627409/20221031_170501.jpg",
			["embeds"] = Embeds,
		}
	end

	local DataCallBack = AllRequest({
		Url = WebHookUrl,
		Method = 'POST',
		Headers = {
			["Content-Type"] = "application/json"
		},
		Body = game:GetService("HttpService"):JSONEncode(Message)
	})
	return DataCallBack
end

function WebHookLog:SheetBestLogSend(SheetBestUrl)

	function GetFightingStyle(Style)
		ReturnText = ""
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v.Name
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetAllMelee()
		BuyDragonTalon = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true))
		if BuyDragonTalon then
			if BuyDragonTalon == 1 then
				TalComplete = true
			end
		end
		BuySuperhuman = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true))
		if BuySuperhuman then
			if BuySuperhuman == 1 then
				SupComplete = true
			end
		end
		BuySharkmanKarate = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true))
		if BuySharkmanKarate then
			if BuySharkmanKarate == 1 then
				SharkComplete = true
			end
		end
		BuyDeathStep = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true))
		if BuyDeathStep then
			if BuyDeathStep == 1 then
				DeathComplete = true
			end
		end
		BuyElectricClaw = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true))
		if BuyElectricClaw then
			if BuyElectricClaw == 1 then
				EClawComplete = true
			end
		end
		BuyGod = tonumber(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true))
		if BuyGod then
			if BuyGod == 1 then
				GodComplete = true
			end
		end
		ReturnText = {}
		if SupComplete == true then
			table.insert(ReturnText,"SuperHuman")
		end
		if EClawComplete == true then
			table.insert(ReturnText,"Electric Claw")
		end
		if TalComplete == true then
			table.insert(ReturnText,"Dragon Talon")
		end
		if SharkComplete == true then
			table.insert(ReturnText,"Sharkman Karate")
		end
		if DeathComplete == true then
			table.insert(ReturnText,"Death Step")
		end
		if GodComplete == true then
			table.insert(ReturnText,"God Human")
		end

		if #ReturnText ~= 0 then
			return table.concat(ReturnText,",")
		else
			return "Not Have"
		end
	end

	function GetAwaken()
		ReturnText = ""
		Awakened_Z = "❌"
		Awakened_X = "❌"
		Awakened_C = "❌"
		Awakened_V = "❌"
		Awakened_F = "❌"
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = "Z"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = "X"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = "C"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = "V"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = "F"
						end
						ReturnText = Awakened_Z..
							" : "..Awakened_X..
							" : "..Awakened_C..
							" : "..Awakened_V..
							" : "..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == "Blox Fruit" then
					if v:FindFirstChild("AwakenedMoves") then
						if v.AwakenedMoves:FindFirstChild("Z") then
							Awakened_Z = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("X") then
							Awakened_X = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("C") then
							Awakened_C = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("V") then
							Awakened_V = ":white_check_mark:"
						end
						if v.AwakenedMoves:FindFirstChild("F") then
							Awakened_F = ":white_check_mark:"
						end
						ReturnText = ":regional_indicator_z:"..Awakened_Z..
							" : "..":regional_indicator_x:"..Awakened_X..
							" : "..":regional_indicator_c:"..Awakened_C..
							" : "..":regional_indicator_v:"..Awakened_V..
							" : "..":regional_indicator_f:"..Awakened_F
					else
						ReturnText = "This Fruit Can't Awakened"
					end
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetWeapon()
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryWeapons")) do
			if type(v) == "table" then
				if v.Name then
					ReturnText = ReturnText .. v.Name .. " "
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetFruitInU()
		local ReturnText = ""
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryFruits")) do
			if type(v) == "table" then
				if v ~= nil then
					ReturnText = ReturnText .. v.Name .. " "
				end
			end
		end

		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function GetWeaponMastery(Style)
		ReturnText = ""
		for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v:FindFirstChild("Level").Value
				end
			end
		end
		for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
			if v:IsA("Tool") then
				if v.ToolTip == Style then
					ReturnText = v:FindFirstChild("Level").Value
				end
			end
		end
		if ReturnText ~= "" then
			return ReturnText
		else
			return "Not Have"
		end
	end

	function Abbreviate(x)
		local abbreviations = {
			"K", -- 4 digits
			"M", -- 7 digits
			"B", -- 10 digits
			"T", -- 13 digits
			"QD", -- 16 digits
			"QT", -- 19 digits
			"SXT", -- 22 digits
			"SEPT", -- 25 digits
			"OCT", -- 28 digits
			"NON", -- 31 digits
			"DEC", -- 34 digits
			"UDEC", -- 37 digits
			"DDEC", -- 40 digits
		}
		if x < 1000 then 
			return tostring(x)
		end

		local digits = math.floor(math.log10(x)) + 1
		local index = math.min(#abbreviations, math.floor((digits - 1) / 3))
		local front = x / math.pow(10, index * 3)

		return string.format("%i%s+", front, abbreviations[index])
	end

	local Message
	Message = {
		["UserName"] = tostring(game.Players.LocalPlayer.Name),
		["Level"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Level").Value),
		["Weapon inventory"] = tostring(GetWeapon()),
		["Fruit inventory"] = tostring(GetFruitInU()),
		["Melee"] = tostring(GetAllMelee()),
		["Fruit"] = tostring(GetFightingStyle("Blox Fruit")),
		["Fruit Mastery"] = tostring(GetWeaponMastery("Blox Fruit")),
		["Fruit Awake"] = tostring(GetAwaken()),
		["Beli"] = tostring(Abbreviate(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Beli").Value)),
		["Fragment"] = tostring(Abbreviate(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Fragments").Value)),
		["Race"] = tostring(game:GetService("Players").LocalPlayer.Data:FindFirstChild("Race").Value)
	}

	local DataCallBack = AllRequest({
		Url = SheetBestUrl,
		Method = 'POST',
		Headers = {
			["Content-Type"] = "application/json"
		},
		Body = game:GetService("HttpService"):JSONEncode(Message)
	})
	return DataCallBack
end

-------------->> // FN Main \\ <<-------------

W1 = false
W2 = false
W3 = false
if game.PlaceId == 2753915549 then
W1 = true
elseif game.PlaceId == 4442272183 then
W2 = true
elseif game.PlaceId == 7449423635 then
W3 = true
end

function CheckQuest() 
	local MyLevel = game:GetService("Players").LocalPlayer.Data.Level.Value
	if game.PlaceId == 2753915549 then
		if MyLevel == 1 or MyLevel <= 9 then -- Bandit
		Mon = "Bandit [Lv. 5]"
		NameQuest = "BanditQuest1"
		LevelQuest = 1
		NameMon = "Bandit"
		CFrameQuest = CFrame.new(1061.66699, 16.5166187, 1544.52905, -0.942978859, -3.33851502e-09, 0.332852632, 7.04340497e-09, 1, 2.99841325e-08, -0.332852632, 3.06188177e-08, -0.942978859)
		CFrameMon = CFrame.new(1057.55151, 27.1278248, 1564.76013, -0.16377756, -1.13282092e-10, -0.986497283, 3.48445752e-08, 1, -5.89970339e-09, 0.986497283, -3.53403173e-08, -0.16377756)
	elseif MyLevel == 10 or MyLevel <= 14 then -- Bandit
	   Mon = "Monkey [Lv. 14]"
	   NameQuest = "JungleQuest"
		LevelQuest = 1
		NameMon = "Monkey"
		CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
		CFrameMon = CFrame.new(-1449.94617, 67.9777908, 12.3050404, -0.643440843, 2.02988506e-08, 0.765495837, 2.12389017e-09, 1, -2.4732012e-08, -0.765495837, -1.42877576e-08, -0.643440843)
	elseif MyLevel == 15 or MyLevel <= 29 then -- Gorilla
		Mon = "Gorilla [Lv. 20]"
		NameQuest = "JungleQuest"
		LevelQuest = 2
		NameMon = "Gorilla"
		CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
		CFrameMon = CFrame.new(-1142.0293, 40.5877495, -516.118103, 0.55559355, 7.58965513e-08, 0.831454039, 1.24594361e-08, 1, -9.96073553e-08, -0.831454039, 6.57006538e-08, 0.55559355)
	elseif MyLevel == 30 or MyLevel <= 39 then -- Pirat
		Mon = "Pirate [Lv. 35]"
		NameQuest = "BuggyQuest1"
		LevelQuest = 1
		NameMon = "Pirate"
		CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
		CFrameMon = CFrame.new(-1151.29663, 44.207077, 3873.34937, -0.879714787, 3.81559784e-10, 0.475501686, -2.18363772e-09, 1, -4.84233453e-09, -0.475501686, -5.29819655e-09, -0.879714787)
	elseif MyLevel == 40 or MyLevel <= 59 then -- Brute
		Mon = "Brute [Lv. 45]"
		NameQuest = "BuggyQuest1"
		LevelQuest = 2
		NameMon = "Brute"
		CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
		CFrameMon = CFrame.new(-1131.66699, 14.3651161, 4191.79199, -0.968309462, -1.36864942e-09, 0.24975352, -9.80991288e-09, 1, -3.25536256e-08, -0.24975352, -3.3972043e-08, -0.968309462)
	elseif MyLevel == 60 or MyLevel <= 74 then -- Desert Bandit
		Mon = "Desert Bandit [Lv. 60]"
		NameQuest = "DesertQuest"
		LevelQuest = 1
		NameMon = "Desert Bandit"
		CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
		CFrameMon = CFrame.new(1054.79053, 52.5889473, 4490.35693, 0.280815929, -6.18912255e-09, 0.95976162, 4.50181625e-09, 1, 5.13142062e-09, -0.95976162, 2.87968605e-09, 0.280815929)
	elseif MyLevel == 75 or MyLevel <= 89 then -- Desert Officre
		Mon = "Desert Officer [Lv. 70]"
		NameQuest = "DesertQuest"
		LevelQuest = 2
		NameMon = "Desert Officer"
		CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.97168, -0.804044724, 3.68233266e-08, 0.594568789, 6.97835176e-08, 1, 3.24365246e-08, -0.594568789, 6.75715199e-08, -0.804044724)
		CFrameMon = CFrame.new(1658.0708, 10.0252256, 4452.83154, 0.826960921, -2.71145932e-08, 0.562259436, -9.74775904e-09, 1, 6.25611705e-08, -0.562259436, -5.72164147e-08, 0.826960921)
	elseif MyLevel == 90 or MyLevel <= 99 then -- Snow Bandits
		Mon = "Snow Bandit [Lv. 90]"
		NameQuest = "SnowQuest"
		LevelQuest = 1
		NameMon = "Snow Bandits"
		CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
		CFrameMon = CFrame.new(1381.81982, 88.3774796, -1395.56738, -0.0662302524, 5.15531262e-08, 0.997804344, 3.78975749e-08, 1, -4.91510797e-08, -0.997804344, 3.45590756e-08, -0.0662302524)
	elseif MyLevel == 100 or MyLevel <= 119 then -- Snowman
		Mon = "Snowman [Lv. 100]"
		NameQuest = "SnowQuest"
		LevelQuest = 2
		NameMon = "Snowman"
		CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482, 0.348555952, -2.53947841e-09, -0.937287986, 1.49860568e-08, 1, 2.86358204e-09, 0.937287986, -1.50443711e-08, 0.348555952)
		CFrameMon = CFrame.new(1171.65784, 106.437271, -1514.53918, -0.726554573, 7.11920691e-08, -0.687108815, 6.82555807e-08, 1, 3.14370361e-08, 0.687108815, -2.40582896e-08, -0.726554573)
	elseif MyLevel == 120 or MyLevel <= 149 then -- Chief Petty Officer
		Mon = "Chief Petty Officer [Lv. 120]"
		NameQuest = "MarineQuest2"
		LevelQuest = 1
		NameMon = "Chief Petty Officer"
		CFrameQuest = CFrame.new(-5035.0835, 28.6520386, 4325.29443, 0.0243340395, -7.08064647e-08, 0.999703884, -6.36926814e-08, 1, 7.23777944e-08, -0.999703884, -6.54350671e-08, 0.0243340395)
		CFrameMon = CFrame.new(-4908.62207, 51.0889473, 4296.17578, 0.851993144, 6.76871537e-08, -0.523552954, -6.00756422e-08, 1, 3.15213882e-08, 0.523552954, 4.59677496e-09, 0.851993144)
	elseif MyLevel == 150 or MyLevel <= 174 then -- Sky Bandit
		Mon = "Sky Bandit [Lv. 150]"
		NameQuest = "SkyQuest"
		LevelQuest = 1
		NameMon = "Sky Bandit"
		CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
		CFrameMon = CFrame.new(-4971.60254, 364.723907, -2860.88965, -0.967084885, 8.0616207e-09, 0.254453957, 1.28277495e-08, 1, 1.7071466e-08, -0.254453957, 1.97736281e-08, -0.967084885)
	elseif MyLevel == 175 or MyLevel <= 189 then -- Dark Master
		Mon = "Dark Master [Lv. 175]"
		NameQuest = "SkyQuest"
		LevelQuest = 2
		NameMon = "Dark Master"
		CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436, -0.875942111, 5.59710216e-08, -0.482416272, 3.04023082e-08, 1, 6.08195947e-08, 0.482416272, 3.86078725e-08, -0.875942111)
		CFrameMon = CFrame.new(-5234.49463, 472.219452, -2260.2998, 0.0978341922, 4.7624173e-08, -0.99520272, 1.3983859e-07, 1, 6.16006801e-08, 0.99520272, -1.45194406e-07, 0.0978341922)
	elseif MyLevel == 190 or MyLevel <= 209 then
		Mon = "Prisoner [Lv. 190]"
		NameQuest = "PrisonerQuest"
		LevelQuest = 1
		NameMon = "Prisoner"
		CFrameQuest = CFrame.new(5308.5595703125, 1.655185341835022, 475.2810363769531 )
		CFrameMon = CFrame.new(5282.37548828125, 15.651934623718262, 356.1692810058594)
	elseif MyLevel == 210 or MyLevel <= 249 then
		Mon = "Dangerous Prisoner [Lv. 210]"
		NameQuest = "PrisonerQuest"
		LevelQuest = 2
		NameMon = "Dangerous Prisoner"
		CFrameQuest = CFrame.new(5308.5595703125, 1.655185341835022, 475.2810363769531 )
		CFrameMon = CFrame.new(5549.43359375, 15.635162353515625, 868.7542724609375)
	elseif MyLevel == 250 or MyLevel <= 274 then -- Toga Warrior
		Mon = "Toga Warrior [Lv. 250]"
		NameQuest = "ColosseumQuest"
		LevelQuest = 1
		NameMon = "Toga Warrior"
		CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
		CFrameMon = CFrame.new(-1716.77588, 105.825844, -2809.25977, -0.188207448, 2.83339467e-08, 0.982129276, 1.10813891e-08, 1, -2.67259583e-08, -0.982129276, 5.85333249e-09, -0.188207448)
	elseif MyLevel == 275 or MyLevel <= 299 then -- Gladiato
		Mon = "Gladiator [Lv. 275]"
		NameQuest = "ColosseumQuest"
		LevelQuest = 2
		NameMon = "Gladiato"
		CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
		CFrameMon = CFrame.new(-1440.1282958984375, 7.567874431610107, -3171.48388671875)
	elseif MyLevel == 300 or MyLevel <= 324 then -- Military Soldier
		Mon = "Military Soldier [Lv. 300]"
		NameQuest = "MagmaQuest"
		LevelQuest = 1
		NameMon = "Military Soldier"
		CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
		CFrameMon = CFrame.new(-5334.42627, 50.9436913, 8647.35156, -0.54487282, 0, 0.838518679, 0, 1, 0, -0.838518679, 0, -0.54487282)
	elseif MyLevel == 325 or MyLevel <= 374 then -- Military Spy
		Mon = "Military Spy [Lv. 325]"
		NameQuest = "MagmaQuest"
		LevelQuest = 2
		NameMon = "Military Spy"
		CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
		CFrameMon = CFrame.new(-5772.66113, 81.4496155, 8722.71973, 0.0485868454, 5.5336308e-08, 0.998818934, 6.85331543e-08, 1, -5.8735484e-08, -0.998818934, 7.13059833e-08, 0.0485868454)
	elseif MyLevel == 375 or MyLevel <= 399 then -- Fishman Warrior
		FM = true
		Mon = "Fishman Warrior [Lv. 375]"
		NameQuest = "FishmanQuest"
		LevelQuest = 1
		NameMon = "Fishman Warrior"
		CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
		CFrameMon = CFrame.new(60955.0625, 48.7988472, 1543.7168, -0.831178129, 6.20639318e-09, -0.556006253, 7.20035302e-08, 1, -9.64761853e-08, 0.556006253, -1.20223305e-07, -0.831178129)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
		end
	elseif MyLevel == 400 or MyLevel <= 449 then -- Fishman Commando
		FM = true
		Mon = "Fishman Commando [Lv. 400]"
		NameQuest = "FishmanQuest"
		LevelQuest = 2
		NameMon = "Fishman Commando"
		CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
		CFrameMon = CFrame.new(61872.3008, 75.5976562, 1394.83484, -0.922134459, 4.36911973e-09, -0.38686946, -2.54707899e-08, 1, 7.20052e-08, 0.38686946, 7.62523484e-08, -0.922134459)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
		end
	elseif MyLevel == 450 or MyLevel <= 474 then -- God's Guards
		FM = false
		Mon = "God's Guard [Lv. 450]"
		NameQuest = "SkyExp1Quest"
		LevelQuest = 1
		NameMon = "God's Guards"
		CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105, -0.999277651, -5.56969759e-09, 0.0380011722, -4.14751478e-09, 1, 3.75035256e-08, -0.0380011722, 3.73188307e-08, -0.999277651)
		CFrameMon = CFrame.new(-4719.61719, 853.174927, -1935.9231, 0.871468067, -2.79222032e-08, 0.49045223, 3.73774967e-08, 1, -9.48327372e-09, -0.49045223, 2.6596247e-08, 0.871468067)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
		end
	elseif MyLevel == 475 or MyLevel <= 524 then -- Shandas
		sky = false
		Mon = "Shanda [Lv. 475]"
		NameQuest = "SkyExp1Quest"
		LevelQuest = 2
		NameMon = "Shandas"
		CFrameQuest = CFrame.new(-7863.63672, 5545.49316, -379.826324, 0.362120807, -1.98046344e-08, -0.93213129, 4.05822291e-08, 1, -5.48095125e-09, 0.93213129, -3.58431969e-08, 0.362120807)
		CFrameMon = CFrame.new(-7661.34229, 5548.00732, -506.59787, 0.0389961377, 4.86564531e-08, 0.999239385, -1.10884022e-08, 1, -4.82607554e-08, -0.999239385, -9.1979846e-09, 0.0389961377)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
		end
	elseif MyLevel == 525 or MyLevel <= 549 then -- Royal Squad
		sky = true
		Mon = "Royal Squad [Lv. 525]"
		NameQuest = "SkyExp2Quest"
		LevelQuest = 1
		NameMon = "Royal Squad"
		CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
		CFrameMon = CFrame.new(-7646.49707, 5608.40625, -1422.51074, 0.901955545, 9.02816666e-08, 0.431828916, -7.36900176e-08, 1, -5.51527428e-08, -0.431828916, 1.7923842e-08, 0.901955545)
	elseif MyLevel == 550 or MyLevel <= 624 then -- Royal Soldier
		Dis = 240
		sky = true
		Mon = "Royal Soldier [Lv. 550]"
		NameQuest = "SkyExp2Quest"
		LevelQuest = 2
		NameMon = "Royal Soldier"
		CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802, 0.0504222959, 2.5710392e-08, 0.998727977, 1.12541557e-07, 1, -3.14249675e-08, -0.998727977, 1.13982921e-07, 0.0504222959)
		CFrameMon = CFrame.new(-8004.89062, 5645.15723, -1960.63599, 0.805200279, 3.47631635e-09, 0.593002975, -2.96576697e-09, 1, -1.83520144e-09, -0.593002975, -2.8100397e-10, 0.805200279)
	elseif MyLevel == 625 or MyLevel <= 649 then -- Galley Pirate
		Dis = 240
		sky = false
		Mon = "Galley Pirate [Lv. 625]"
		NameQuest = "FountainQuest"
		LevelQuest = 1
		NameMon = "Galley Pirate"
		CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
		CFrameMon = CFrame.new(5618.82129, 152.426666, 3994.08472, 0.926358402, 2.57817536e-08, 0.3766433, 1.30540767e-09, 1, -7.16620505e-08, -0.3766433, 6.68764102e-08, 0.926358402)
	elseif MyLevel >= 650 then -- Galley Captain
		Dis = 240
		Mon = "Galley Captain [Lv. 650]"
		NameQuest = "FountainQuest"
		LevelQuest = 2
		NameMon = "Galley Captain"
		CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678, -0.0504891425, -3.62066501e-08, -0.998724639, -9.87921389e-09, 1, -3.57534553e-08, 0.998724639, 8.06145284e-09, -0.0504891425)
		CFrameMon = CFrame.new(5804.62451, 54.212822, 4895.91602, -0.889353693, -2.71176837e-09, -0.457219929, 2.99581409e-08, 1, -6.42035687e-08, 0.457219929, -7.07971424e-08, -0.889353693)
	end
	elseif game.PlaceId == 4442272183 then
		if MyLevel == 700 or MyLevel <= 724 then -- Raider [Lv. 700]
		Mon = "Raider [Lv. 700]"
		NameQuest = "Area1Quest"
		LevelQuest = 1
		NameMon = "Raider"
		CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
		CFrameMon = CFrame.new(-737.026123, 39.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
	elseif MyLevel == 725 or MyLevel <= 774 then -- Mercenary [Lv. 725]
		Mon = "Mercenary [Lv. 725]"
		NameQuest = "Area1Quest"
		LevelQuest = 2
		NameMon = "Mercenary"
		CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
		CFrameMon = CFrame.new(-973.731995, 95.8733215, 1836.46936, 0.999135971, 2.02326991e-08, -0.0415605344, -1.90767793e-08, 1, 2.82094952e-08, 0.0415605344, -2.73922804e-08, 0.999135971)
	elseif MyLevel == 775 or MyLevel <= 799 then -- Swan Pirate [Lv. 775]
		Mon = "Swan Pirate [Lv. 775]"
		NameQuest = "Area2Quest"
		LevelQuest = 1
		NameMon = "Swan Pirate"
		CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
		CFrameMon = CFrame.new(970.369446, 142.653198, 1217.3667, 0.162079468, -4.85452638e-08, -0.986777723, 1.03357589e-08, 1, -4.74980872e-08, 0.986777723, -2.50063148e-09, 0.162079468)
	elseif MyLevel == 800 or MyLevel <= 874 then -- Factory Staff [Lv. 800]
		Mon = "Factory Staff [Lv. 800]"
		NameQuest = "Area2Quest"
		LevelQuest = 2
		NameMon = "Factory Staff"
		CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
		CFrameMon = CFrame.new(296.786499, 72.9948196, -57.1298141, -0.876037002, -5.32364979e-08, 0.482243896, -3.87658332e-08, 1, 3.99718729e-08, -0.482243896, 1.63222538e-08, -0.876037002)
	elseif MyLevel == 875 or MyLevel <= 899 then -- Marine Lieutenant [Lv. 875]
		Mon = "Marine Lieutenant [Lv. 875]"
		NameQuest = "MarineQuest3"
		LevelQuest = 1
		NameMon = "Marine Lieutenant"
		CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
		CFrameMon = CFrame.new(-2913.26367, 73.0011826, -2971.64282, 0.910507619, 0, 0.413492233, 0, 1.00000012, 0, -0.413492233, 0, 0.910507619)
	elseif MyLevel == 900 or MyLevel <= 949 then -- Marine Captain [Lv. 900]
		Mon = "Marine Captain [Lv. 900]"
		NameQuest = "MarineQuest3"
		LevelQuest = 2
		NameMon = "Marine Captain"
		CFrameQuest = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
		CFrameMon = CFrame.new(-1868.67688, 73.0011826, -3321.66333, -0.971402287, 1.06502087e-08, 0.237439692, 3.68856199e-08, 1, 1.06050372e-07, -0.237439692, 1.11775684e-07, -0.971402287)
	elseif MyLevel == 950 or MyLevel <= 974 then -- Zombie [Lv. 950]
		Mon = "Zombie [Lv. 950]"
		NameQuest = "ZombieQuest"
		LevelQuest = 1
		NameMon = "Zombie"
		CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
		CFrameMon = CFrame.new(-5634.83838, 126.067039, -697.665039, -0.992770672, 6.77618939e-09, 0.120025545, 1.65461245e-08, 1, 8.04023372e-08, -0.120025545, 8.18070234e-08, -0.992770672)
	elseif MyLevel == 975 or MyLevel <= 999 then -- Vampire [Lv. 975]
		Mon = "Vampire [Lv. 975]"
		NameQuest = "ZombieQuest"
		LevelQuest = 2
		NameMon = "Vampire"
		CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571, 0.321800292, -6.24695815e-08, 0.946807742, 4.05616092e-08, 1, 5.21931227e-08, -0.946807742, 2.16082796e-08, 0.321800292)
		CFrameMon = CFrame.new(-6030.32031, 6.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
	elseif MyLevel == 1000 or MyLevel <= 1049 then -- Snow Trooper [Lv. 1000] **
		Mon = "Snow Trooper [Lv. 1000]"
		NameQuest = "SnowMountainQuest"
		LevelQuest = 1
		NameMon = "Snow Trooper"
		CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
		CFrameMon = CFrame.new(535.893433, 401.457062, -5329.6958, -0.999524176, 0, 0.0308452044, 0, 1, -0, -0.0308452044, 0, -0.999524176)
	elseif MyLevel == 1050 or MyLevel <= 1099 then -- Winter Warrior [Lv. 1050]
		Mon = "Winter Warrior [Lv. 1050]"
		NameQuest = "SnowMountainQuest"
		LevelQuest = 2
		NameMon = "Winter Warrior"
		CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287, 0.353063971, 1.89520435e-08, -0.935599446, -5.81846002e-08, 1, -1.70033754e-09, 0.935599446, 5.50377841e-08, 0.353063971)
		CFrameMon = CFrame.new(1223.7417, 454.575226, -5170.02148, 0.473996818, 2.56845354e-08, 0.880526543, -5.62456428e-08, 1, 1.10811016e-09, -0.880526543, -5.00510211e-08, 0.473996818)
	elseif MyLevel == 1100 or MyLevel <= 1124 then -- Lab Subordinate [Lv. 1100]
		Mon = "Lab Subordinate [Lv. 1100]"
		NameQuest = "IceSideQuest"
		LevelQuest = 1
		NameMon = "Lab Subordinate"
		CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
		CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
	elseif MyLevel == 1125 or MyLevel <= 1174 then -- Horned Warrior [Lv. 1125]
		Mon = "Horned Warrior [Lv. 1125]"
		NameQuest = "IceSideQuest"
		LevelQuest = 2
		NameMon = "Horned Warrior"
		CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876, -0.411000341, -5.06538868e-07, 0.91163528, 1.26306062e-07, 1, 6.12581289e-07, -0.91163528, 3.66916197e-07, -0.411000341)
		CFrameMon = CFrame.new(-6400.85889, 24.7645149, -5818.63574, -0.964845479, 8.65926566e-08, -0.262817472, 3.98261392e-07, 1, -1.13260398e-06, 0.262817472, -1.19745812e-06, -0.964845479)
	elseif MyLevel == 1175 or MyLevel <= 1199 then -- Magma Ninja [Lv. 1175]
		Mon = "Magma Ninja [Lv. 1175]"
		NameQuest = "FireSideQuest"
		LevelQuest = 1
		NameMon = "Magma Ninja"
		CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
		CFrameMon = CFrame.new(-5496.65576, 58.6890411, -5929.76855, -0.885073781, 0, -0.465450764, 0, 1.00000012, -0, 0.465450764, 0, -0.885073781)
	elseif MyLevel == 1200 or MyLevel <= 1249 then -- Lava Pirate [Lv. 1200]
		Mon = "Lava Pirate [Lv. 1200]"
		NameQuest = "FireSideQuest"
		LevelQuest = 2
		NameMon = "Lava Pirate"
		CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
		CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
	elseif MyLevel == 1250 or MyLevel <= 1274 then -- Ship Deckhand [Lv. 1250]
		Mon = "Ship Deckhand [Lv. 1250]"
		NameQuest = "ShipQuest1"
		LevelQuest = 1
		NameMon = "Ship Deckhand"
		CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
		CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
		end
	elseif MyLevel == 1275 or MyLevel <= 1299 then -- Ship Engineer [Lv. 1275]
		Mon = "Ship Engineer [Lv. 1275]"
		NameQuest = "ShipQuest1"
		LevelQuest = 2
		NameMon = "Ship Engineer"
		CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
		CFrameMon = CFrame.new(916.666504, 44.0920448, 32917.207, -0.99746871, -4.85034697e-08, -0.0711069331, -4.8925461e-08, 1, 4.19294288e-09, 0.0711069331, 7.66126895e-09, -0.99746871)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
		end
	elseif MyLevel == 1300 or MyLevel <= 1324 then -- Ship Steward [Lv. 1300]
		Mon = "Ship Steward [Lv. 1300]"
		NameQuest = "ShipQuest2"
		LevelQuest = 1
		NameMon = "Ship Steward"
		CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
		CFrameMon = CFrame.new(918.743286, 129.591064, 33443.4609, -0.999792814, -1.7070947e-07, -0.020350717, -1.72559169e-07, 1, 8.91351277e-08, 0.020350717, 9.2628369e-08, -0.999792814)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
		end
	elseif MyLevel == 1325 or MyLevel <= 1349 then -- Ship Officer [Lv. 1325]
		Mon = "Ship Officer [Lv. 1325]"
		NameQuest = "ShipQuest2"
		LevelQuest = 2
		NameMon = "Ship Officer"
		CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
		CFrameMon = CFrame.new(786.051941, 181.474106, 33303.2969, 0.999285698, -5.32193063e-08, 0.0377905183, 5.68968588e-08, 1, -9.62386864e-08, -0.0377905183, 9.83201005e-08, 0.999285698)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
		end
	elseif MyLevel == 1350 or MyLevel <= 1374 then -- Arctic Warrior [Lv. 1350]
		Mon = "Arctic Warrior [Lv. 1350]"
		NameQuest = "FrostQuest"
		LevelQuest = 1
		NameMon = "Arctic Warrior"
		CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
		CFrameMon = CFrame.new(5995.07471, 57.3188477, -6183.47314, 0.702747107, -1.53454167e-07, -0.711440146, -1.08168464e-07, 1, -3.22542007e-07, 0.711440146, 3.03620908e-07, 0.702747107)
		if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 20000 then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
		end
	elseif MyLevel == 1375 or MyLevel <= 1424 then -- Snow Lurker [Lv. 1375]
		Mon = "Snow Lurker [Lv. 1375]"
		NameQuest = "FrostQuest"
		LevelQuest = 2
		NameMon = "Snow Lurker"
		CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107, 0.888092756, 1.02705066e-07, 0.459664226, -6.20391774e-08, 1, -1.03572376e-07, -0.459664226, 6.34646895e-08, 0.888092756)
		CFrameMon = CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
	elseif MyLevel == 1425 or MyLevel <= 1449 then -- Sea Soldier [Lv. 1425]
		Mon = "Sea Soldier [Lv. 1425]"
		NameQuest = "ForgottenQuest"
		LevelQuest = 1
		NameMon = "Sea Soldier"
		CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
		CFrameMon = CFrame.new(-3029.78467, 66.944252, -9777.38184, -0.998552859, 1.09555076e-08, 0.0537791774, 7.79564235e-09, 1, -5.89660658e-08, -0.0537791774, -5.84614881e-08, -0.998552859)
	elseif MyLevel >= 1450 then -- Water Fighter [Lv. 1450]
		Mon = "Water Fighter [Lv. 1450]"
		NameQuest = "ForgottenQuest"
		LevelQuest = 2
		NameMon = "Water Fighter"
		CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943, -0.997911751, 4.42321983e-08, 0.064591676, 4.90968759e-08, 1, 7.37270085e-08, -0.064591676, 7.67442998e-08, -0.997911751)
		CFrameMon = CFrame.new(-3262.00098, 298.699615, -10553.6943, -0.233570755, -4.57538185e-08, 0.972339869, -5.80986068e-08, 1, 3.30992194e-08, -0.972339869, -4.87605725e-08, -0.233570755)
	end
	elseif game.PlaceId == 7449423635 then
		if MyLevel == 1500 or MyLevel <= 1524 then
		Mon = "Pirate Millionaire [Lv. 1500]"
		NameQuest = "PiratePortQuest"
		LevelQuest = 1
		NameMon = "Pirate Millionaire"
		CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
		CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
	elseif MyLevel == 1525 or MyLevel <= 1574 then
		Mon = "Pistol Billionaire [Lv. 1525]"
		NameQuest = "PiratePortQuest"
		LevelQuest = 2
		NameMon = "Pistol Billionaire"
		CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
		CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
	elseif MyLevel == 1575 or MyLevel <= 1599 then
		Mon = "Dragon Crew Warrior [Lv. 1575]"
		NameQuest = "AmazonQuest"
		LevelQuest = 1
		NameMon = "Dragon Crew Warrior"
		CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
		CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
	elseif MyLevel == 1600 or MyLevel <= 1624 then
		Mon = "Dragon Crew Archer [Lv. 1600]"
		NameQuest = "AmazonQuest"
		LevelQuest = 2
		NameMon = "Dragon Crew Archer"
		CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
		CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
	elseif MyLevel == 1625 or MyLevel <= 1649 then
		Mon = "Female Islander [Lv. 1625]"
		NameQuest = "AmazonQuest2"
		LevelQuest = 1
		NameMon = "Female Islander"
		CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
		CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
	elseif MyLevel == 1650 or MyLevel <= 1699 then
		Mon = "Giant Islander [Lv. 1650]"
		NameQuest = "AmazonQuest2"
		LevelQuest = 2
		NameMon = "Giant Islander"
		CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
		CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
	elseif MyLevel == 1700 or MyLevel <= 1724 then
		Mon = "Marine Commodore [Lv. 1700]"
		NameQuest = "MarineTreeIsland"
		LevelQuest = 1
		NameMon = "Marine Commodore"
		CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
		CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
	elseif MyLevel == 1725 or MyLevel <= 1774 then
		Mon = "Marine Rear Admiral [Lv. 1725]"
		NameQuest = "MarineTreeIsland"
		LevelQuest = 2
		NameMon = "Marine Rear Admiral"
		CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
		CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
	elseif MyLevel == 1775 or MyLevel <= 1799 then
		Mon = "Fishman Raider [Lv. 1775]"
		NameQuest = "DeepForestIsland3"
		LevelQuest = 1
		NameMon = "Fishman Raider"
		CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
		CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
	elseif MyLevel == 1800 or MyLevel <= 1824 then
		Mon = "Fishman Captain [Lv. 1800]"
		NameQuest = "DeepForestIsland3"
		LevelQuest = 2
		NameMon = "Fishman Captain"
		CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
		CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
	elseif MyLevel == 1825 or MyLevel <= 1849 then
		Mon = "Forest Pirate [Lv. 1825]"
		NameQuest = "DeepForestIsland"
		LevelQuest = 1
		NameMon = "Forest Pirate"
		CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
		CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
	elseif MyLevel == 1850 or MyLevel <= 1899 then
		Mon = "Mythological Pirate [Lv. 1850]"
		NameQuest = "DeepForestIsland"
		LevelQuest = 2
		NameMon = "Mythological Pirate"
		CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
		CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
	elseif MyLevel == 1900 or MyLevel <= 1924 then
		Mon = "Jungle Pirate [Lv. 1900]"
		NameQuest = "DeepForestIsland2"
		LevelQuest = 1
		NameMon = "Jungle Pirate"
		CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
		CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
	elseif MyLevel == 1925 or MyLevel <= 1974 then
		Mon = "Musketeer Pirate [Lv. 1925]"
		NameQuest = "DeepForestIsland2"
		LevelQuest = 2
		NameMon = "Musketeer Pirate"
		CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
		CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
	elseif MyLevel == 1975 or MyLevel <= 1999 then
		Mon = "Reborn Skeleton [Lv. 1975]"
		NameQuest = "HauntedQuest1"
		LevelQuest = 1
		NameMon = "Reborn Skeleton"
		CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
		CFrameMon = CFrame.new(-8761.3154296875, 164.85829162598, 6161.1567382813)
	elseif MyLevel == 2000 or MyLevel <= 2024 then
		Mon = "Living Zombie [Lv. 2000]"
		NameQuest = "HauntedQuest1"
		LevelQuest = 2
		NameMon = "Living Zombie"
		CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
		CFrameMon = CFrame.new(-10093.930664063, 237.38233947754, 6180.5654296875)
	elseif MyLevel == 2025 or MyLevel <= 2049 then
		Mon = "DeMonic Soul [Lv. 2025]"
		NameQuest = "HauntedQuest2"
		LevelQuest = 1
		NameMon = "DeMonic Soul"
		CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
		CFrameMon = CFrame.new(-9466.72949, 171.162918, 6132.01514)
	elseif MyLevel == 2050 or MyLevel <= 2074 then
		Mon = "Posessed Mummy [Lv. 2050]" 
		NameQuest = "HauntedQuest2"
		LevelQuest = 2
		NameMon = "Posessed Mummy"
		CFrameQuest = CFrame.new(-9514.78027, 171.162918, 6078.82373, 0.301918149, 7.4535027e-09, 0.953333855, -3.22802141e-09, 1, -6.79604995e-09, -0.953333855, -1.02553133e-09, 0.301918149)
		CFrameMon = CFrame.new(-9589.93848, 4.85058546, 6190.27197)
	elseif MyLevel == 2075 or MyLevel <= 2099 then
		Mon = "Peanut Scout [Lv. 2075]"
		NameQuest = "NutsIslandQuest"
		LevelQuest = 1
		NameMon = "Peanut Scout"
		CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
		CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
	elseif MyLevel == 2100 or MyLevel <= 2124 then
		Mon = "Peanut President [Lv. 2100]"
		NameQuest = "NutsIslandQuest"
		LevelQuest = 2
		NameMon = "Peanut President"
		CFrameQuest = CFrame.new(-2103.9375, 38.139019012451, -10192.702148438)
		CFrameMon = CFrame.new(-2150.587890625, 122.49767303467, -10358.994140625)
	elseif MyLevel == 2125 or MyLevel <= 2149 then
		Mon = "Ice Cream Chef [Lv. 2125]"
		NameQuest = "IceCreamIslandQuest"
		LevelQuest = 1
		NameMon = "Ice Cream Chef"
		CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
		CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
	elseif MyLevel == 2150 or MyLevel <= 2199 then
		Mon = "Ice Cream Commander [Lv. 2150]"
		NameQuest = "IceCreamIslandQuest"
		LevelQuest = 2
		NameMon = "Ice Cream Commander"
		CFrameQuest = CFrame.new(-819.84533691406, 65.845329284668, -10965.487304688)
		CFrameMon = CFrame.new(-890.55895996094, 186.34135437012, -11127.306640625)
	elseif MyLevel == 2200 or MyLevel <= 2224 then
		Mon = "Cookie Crafter [Lv. 2200]"
		NameQuest = "CakeQuest1"
		LevelQuest = 1
		NameMon = "Cookie Crafter"
		CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
		CFrameMon = CFrame.new(-2273.00244140625, 90.22590637207031, -12151.62109375)
	elseif MyLevel == 2225 or MyLevel <= 2249 then
		Mon = "Cake Guard [Lv. 2225]"
		NameQuest = "CakeQuest1"
		LevelQuest = 2
		NameMon = "Cake Guard"
		CFrameQuest = CFrame.new(-2021.5509033203125, 37.798221588134766, -12028.103515625)
		CFrameMon = CFrame.new(-1442.373046875, 158.14111328125, -12277.37109375)
	elseif MyLevel == 2250 or MyLevel <= 2274 then
		Mon = "Baking Staff [Lv. 2250]"
		NameQuest = "CakeQuest2"
		LevelQuest = 1
		NameMon = "Baking Staff"
		CFrameQuest = CFrame.new(-1927.9107666015625, 37.79813003540039, -12843.78515625)
		CFrameMon = CFrame.new(-1837.2803955078125, 129.0594482421875, -12934.5498046875)
	elseif MyLevel == 2275 or MyLevel <= 2299 then
		Mon = "Head Baker [Lv. 2275]"
		LevelQuest = 2
		NameQuest = "CakeQuest2"
		NameMon = "Head Baker"
		CFrameQuest = CFrame.new(-1927.91602, 37.7981339, -12842.5391, -0.96804446, 4.22142143e-08, 0.250778586, 4.74911062e-08, 1, 1.49904711e-08, -0.250778586, 2.64211941e-08, -0.96804446)
		CFrameMon = CFrame.new(-1837.2803955078125, 129.0594482421875, -12934.5498046875)
	elseif MyLevel == 2300 or MyLevel <= 2324 then
		Mon = "Cocoa Warrior [Lv. 2300]"
		LevelQuest = 1
		NameQuest = "ChocQuest1"
		NameMon = "Cocoa Warrior"
		CFrameQuest = CFrame.new(-237.279648, 24.760088, -12194.0879, 0.37110126, 0, -0.928592443, -0, 1.00000012, -0, 0.928592443, 0, 0.37110126)
		CFrameMon = CFrame.new(4.03491974, 68.286705, -12170.5713, 4.76837158e-05, -0.996190667, 0.0872024298, -1, -4.76837158e-05, 2.08243728e-06, 2.08243728e-06, -0.0872024298, -0.996190667)
	elseif MyLevel == 2325 or MyLevel <= 2349 then
		Mon = "Chocolate Bar Battler [Lv. 2325]"
		LevelQuest = 2
		NameQuest = "ChocQuest1"
		NameMon = "Chocolate Bar Battler"
		CFrameQuest = CFrame.new(149.342697, 24.8196201, -12775.0957, -0.344634354, -2.06621564e-08, -0.938736975, 5.85849484e-08, 1, -4.35186216e-08, 0.938736975, -6.99938667e-08, -0.344634354)
		CFrameMon = CFrame.new(4.03491974, 68.286705, -12170.5713, 4.76837158e-05, -0.996190667, 0.0872024298, -1, -4.76837158e-05, 2.08243728e-06, 2.08243728e-06, -0.0872024298, -0.996190667)
	elseif MyLevel == 2350 or MyLevel <= 2374 then
		Mon = "Sweet Thief [Lv. 2350]"
		LevelQuest = 1
		NameQuest =   "ChocQuest2"
	    NameMon = "Sweet Thief"
		CFrameQuest = CFrame.new(149.814438, 24.8196201, -12775.6064, -0.329403073, -1.39752903e-08, -0.94418937, -1.07108015e-07, 1, 2.25658319e-08, 0.94418937, 1.08563505e-07, -0.329403073)
		CFrameMon = CFrame.new(-13.8405685, 13.8881378, -12845.4707, 0.819155693, 0, 0.573571265, 0, 1, 0, -0.573571265, 0, 0.819155693)
	elseif MyLevel >= 2375 then
		Mon = "Candy Rebel [Lv. 2375]"
		LevelQuest = 2
		NameQuest = "ChocQuest2"
	    NameMon = "Candy Rebel"
		CFrameQuest = CFrame.new(149.814438, 24.8196201, -12775.6064, -0.329403073, -1.39752903e-08, -0.94418937, -1.07108015e-07, 1, 2.25658319e-08, 0.94418937, 1.08563505e-07, -0.329403073)
		CFrameMon = CFrame.new(-244.225952, 77.8919601, -13067.8477, 0.642763317, 0, 0.766064942, 0, 1, 0, -0.766064942, 0, 0.642763317)
		end
	end
end
	
function ByPass(Position)
game.Players.LocalPlayer.Character.Head:Destroy()game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Position 
wait(.5)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Position
wait(.5)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5555,5555,5555)
end

function UnEquipWeapon(Weapon)
    if game.Players.LocalPlayer.Character:FindFirstChild(Weapon) then
        _G.NotAutoEquip = true
        wait(.5)
        game.Players.LocalPlayer.Character:FindFirstChild(Weapon).Parent = game.Players.LocalPlayer.Backpack
        wait(.1)
        _G.NotAutoEquip = false
    end
end
	
	function EquipWeapon(ToolSe)
        if not _G.NotAutoEquip then
            if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
                Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
                wait(.1)
                game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
            end
        end
    end

  getgenv().ToTarget=function(Pos)
    Distance = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
        if game.Players.LocalPlayer.Character.Humanoid.Sit == true then game.Players.LocalPlayer.Character.Humanoid.Sit = false end
        pcall(function() tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/350, Enum.EasingStyle.Linear),{CFrame = Pos}) end)
        tween:Play()
        if Distance <= 250 then
            tween:Cancel()
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Pos
        end
        if _G.StopTween == true then
            tween:Cancel()
            _G.Clip = false
        end
     end
	
 spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        if _G.Settings.autofarmlevel or _G.AutoSaber or _G.AutoSaberHop or _G.AutoPole or _G.AutoPoleHop or _G.Next_Island or _G.AutoFarmBoss or _G.AutoFarmBossAll or _G.Teleport_to_Sea_Beast or _G.Teleport or _G.AutoSharkman or _G.AutoElectricClaw then
            if not game:GetService("Workspace"):FindFirstChild("Part") then
                local Part = Instance.new("Part")
                Part.Name = "Part"
                Part.Parent = game.Workspace
                Part.Anchored = true
				Part.Color = Color3.fromRGB(255, 255, 0)
                Part.Transparency = 1
                Part.Size = Vector3.new(40,40,40)
            elseif game:GetService("Workspace"):FindFirstChild("Part") then
                game.Workspace["Part"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y - 3.92,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
            end
        else
            if game:GetService("Workspace"):FindFirstChild("Part") then
                game:GetService("Workspace"):FindFirstChild("Part"):Destroy()
            end
        end
    end)
end)
spawn(function()
    game:GetService("RunService").Stepped:Connect(function()
        if _G.AutoFarm or _G.AutoSaber or _G.AutoSaberHop or _G.AutoPole or _G.AutoPoleHop or _G.Next_Island or _G.AutoFarmBoss or _G.AutoFarmBossAll or _G.Teleport_to_Sea_Beast or _G.Teleport or _G.AutoSharkman or _G.AutoElectricClaw then
            for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                if v:IsA("BasePart") then
                    v.CanCollide = false    
                end
            end
        end
    end)
end)
function changestate()
    game.Workspace["Part"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y - 3.92,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
end

spawn(function()
    while task.wait() do
        pcall(function()
            if _G.Settings.autofarmlevel or _G.AutoSaber or _G.AutoSaberHop or _G.AutoPole or _G.AutoPoleHop or _G.Next_Island or _G.AutoFarmBoss or _G.AutoFarmBossAll or _G.Teleport_to_Sea_Beast or _G.Teleport or _G.AutoSharkman or _G.AutoElectricClaw then
                if not game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
                    local Noclip = Instance.new("BodyVelocity")
                    Noclip.Name = "BodyClip"
                    Noclip.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
                    Noclip.MaxForce = Vector3.new(100000,100000,100000)
                    Noclip.Velocity = Vector3.new(0,0,0)
                end
            else
                game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
            end
        end)
    end
end)

function CheckMaterial(matname)
	for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventory")) do
		if type(v) == "table" then
			if v.Type == "Material" then
				if v.Name == matname then
					return v.Count
				end
			end
		end
	end
	return 0
end

function TPPlayer(Pos)
    repeat wait()
        Distance = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
        if game.Players.LocalPlayer.Character.Humanoid.Sit == true then game.Players.LocalPlayer.Character.Humanoid.Sit = false end
        pcall(function() tween = game:GetService("TweenService"):Create(game.Players.LocalPlayer.Character.HumanoidRootPart,TweenInfo.new(Distance/200, Enum.EasingStyle.Linear),{CFrame = Pos}) end)
        tween:Play()
        if Distance <= 350 then
            tween:Cancel()
            game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Pos
        end
        if Distance >= 3000 then
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Pos
              game.Players.LocalPlayer.Character.Humanoid.Health =- math.huge
              game:GetService("ReplicatedStorage").Remotes.CommF_:invokeServer("SetSpawnPoint")
              game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5555,5555,5555)
          end
        if _G.StopTween == true then
            tween:Cancel()
            _G.Clip = false
        end
    until Distance <= 3000
end

        function Hop()
        local PlaceID = game.PlaceId
        local AllIDs = {}
        local foundAnything = ""
        local actualHour = os.date("!*t").hour
        local Deleted = false
        function TPReturner()
            local Site;
            if foundAnything == "" then
                Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
            else
                Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
            end
            local ID = ""
            if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
                foundAnything = Site.nextPageCursor
            end
            local num = 0;
            for i,v in pairs(Site.data) do
                local Possible = true
                ID = tostring(v.id)
                if tonumber(v.maxPlayers) > tonumber(v.playing) then
                    for _,Existing in pairs(AllIDs) do
                        if num ~= 0 then
                            if ID == tostring(Existing) then
                                Possible = false
                            end
                        else
                            if tonumber(actualHour) ~= tonumber(Existing) then
                                local delFile = pcall(function()
                                    AllIDs = {}
                                    table.insert(AllIDs, actualHour)
                                end)
                            end
                        end
                        num = num + 1
                    end
                    if Possible == true then
                        table.insert(AllIDs, ID)
                        wait()
                        pcall(function()
                            wait()
                            game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
                        end)
                        wait(4)
                    end
                end
            end
        end
        function Teleport() 
            while wait() do
                pcall(function()
                    TPReturner()
                    if foundAnything ~= "" then
                        TPReturner()
                    end
                end)
            end
        end
        Teleport()
    end
	
local CombatFramework = require(game:GetService("Players").LocalPlayer.PlayerScripts:WaitForChild("CombatFramework"))
local CombatFrameworkR = getupvalues(CombatFramework)[2]
local RigController = require(game:GetService("Players")["LocalPlayer"].PlayerScripts.CombatFramework.RigController)
local RigControllerR = getupvalues(RigController)[2]
local realbhit = require(game.ReplicatedStorage.CombatFramework.RigLib)
local cooldownfastattack = tick()

function CurrentWeapon()
	local ac = CombatFrameworkR.activeController
	local ret = ac.blades[1]
	if not ret then return game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name end
	pcall(function()
		while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
	end)
	if not ret then return game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").Name end
	return ret
end

function getAllBladeHitsPlayers(Sizes)
	local Hits = {}
	local Client = game.Players.LocalPlayer
	local Characters = game:GetService("Workspace").Characters:GetChildren()
	for i=1,#Characters do local v = Characters[i]
		local Human = v:FindFirstChildOfClass("Humanoid")
		if v.Name ~= game.Players.LocalPlayer.Name and Human and Human.RootPart and Human.Health > 0 and Client:DistanceFromCharacter(Human.RootPart.Position) < Sizes+5 then
			table.insert(Hits,Human.RootPart)
		end
	end
	return Hits
end

function getAllBladeHits(Sizes)
	local Hits = {}
	local Client = game.Players.LocalPlayer
	local Enemies = game:GetService("Workspace").Enemies:GetChildren()
	for i=1,#Enemies do local v = Enemies[i]
		local Human = v:FindFirstChildOfClass("Humanoid")
		if Human and Human.RootPart and Human.Health > 0 and Client:DistanceFromCharacter(Human.RootPart.Position) < Sizes+5 then
			table.insert(Hits,Human.RootPart)
		end
	end
	return Hits
end

function AttackFunction()
	local ac = CombatFrameworkR.activeController
	if ac and ac.equipped then
		for indexincrement = 1, 1 do
			local bladehit = getAllBladeHits(50)
			if #bladehit > 0 then
				local AcAttack8 = debug.getupvalue(ac.attack, 5)
				local AcAttack9 = debug.getupvalue(ac.attack, 6)
				local AcAttack7 = debug.getupvalue(ac.attack, 4)
				local AcAttack10 = debug.getupvalue(ac.attack, 7)
				local NumberAc12 = (AcAttack8 * 798405 + AcAttack7 * 727595) % AcAttack9
				local NumberAc13 = AcAttack7 * 798405
				(function()
					NumberAc12 = (NumberAc12 * AcAttack9 + NumberAc13) % 1099511627776
					AcAttack8 = math.floor(NumberAc12 / AcAttack9)
					AcAttack7 = NumberAc12 - AcAttack8 * AcAttack9
				end)()
				AcAttack10 = AcAttack10 + 1
				debug.setupvalue(ac.attack, 5, AcAttack8)
				debug.setupvalue(ac.attack, 6, AcAttack9)
				debug.setupvalue(ac.attack, 4, AcAttack7)
				debug.setupvalue(ac.attack, 7, AcAttack10)
				for k, v in pairs(ac.animator.anims.basic) do
					v:Play(0.01,0.01,0.01)
				end                 
				if game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool") and ac.blades and ac.blades[1] then 
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(CurrentWeapon()))
					game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(NumberAc12 / 1099511627776 * 16777215), AcAttack10)
					game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, 2, "") 
				end
			end
		end
	end
end

    function SkyJumpNoCoolDown()
        if _G.Infinit_SkyJump then
            for i,v in next, getgc() do
                if game.Players.LocalPlayer.Character.Geppo then
                    if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Geppo then
                        for i2,v2 in next, getupvalues(v) do
                            if tostring(v2) == "0" then
                                repeat wait(.1)
                                    setupvalue(v,i2,0)
                                until not _G.Infinit_SkyJump
                            end
                        end
                    end
                end
            end
        end
    end
    
    function InfAbility()
        if _G.Infinit_Ability then
            if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
                local inf = Instance.new("ParticleEmitter")
                inf.Acceleration = Vector3.new(0,0,0)
                inf.Archivable = true
                inf.Drag = 20
                inf.EmissionDirection = Enum.NormalId.Top
                inf.Enabled = true
                inf.Lifetime = NumberRange.new(0.2,0.2)
                inf.LightInfluence = 0
                inf.LockedToPart = true
                inf.Name = "Agility"
                inf.Rate = 500
                local numberKeypoints2 = {
                    NumberSequenceKeypoint.new(0, 0); 
                    NumberSequenceKeypoint.new(1, 4); 
                }
    
                inf.Size = NumberSequence.new(numberKeypoints2)
                inf.RotSpeed = NumberRange.new(999, 9999)
                inf.Rotation = NumberRange.new(0, 0)
                inf.Speed = NumberRange.new(30, 30)
                inf.SpreadAngle = Vector2.new(360,360)
                inf.Texture = "rbxassetid://243098098"
                inf.VelocityInheritance = 0
                inf.ZOffset = 2
                inf.Transparency = NumberSequence.new(0)
                inf.Color = ColorSequence.new(Color3.fromRGB(0, 255, 255),Color3.fromRGB(0, 255, 255))
                inf.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
            end
        else
            if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
                game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility"):Destroy()
            end
        end
    end
    
    _G.Dodge_No_CoolDown = false
    function DodgeNoCoolDown()
        if _G.Dodge_No_CoolDown then
            for i,v in next, getgc() do
                if game.Players.LocalPlayer.Character.Dodge then
                    if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Dodge then
                        for i2,v2 in next, getupvalues(v) do
                            if tostring(v2) == "0.4" then
                                repeat wait(.1)
                                    setupvalue(v,i2,0)
                                until not _G.Dodge_No_CoolDown
                            end
                        end
                    end
                end
            end
        end
    end
    
    local LocalPlayer = game:GetService'Players'.LocalPlayer
    local originalstam = LocalPlayer.Character.Energy.Value
    function InfinitEnergy()
        game:GetService'Players'.LocalPlayer.Character.Energy.Changed:connect(function()
            if _G.Infinit_Energy then
                LocalPlayer.Character.Energy.Value = originalstam
            end 
        end)
    end
    
    function SoruNoCoolDown()
        for i, v in pairs(getgc()) do
            if type(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character:WaitForChild("Soru") then
                for i2,v2 in pairs(debug.getupvalues(v)) do
                    if type(v2) == 'table' then
                        if v2.LastUse then
                            repeat wait()
                                setupvalue(v, i2, {LastAfter = 0,LastUse = 0})
                            until not _G.Infinit_Soru
                        end
                    end
                end
            end
        end
    end
	
if game.CoreGui:FindFirstChild("PepsiUi") then
    game.CoreGui:FindFirstChild("PepsiUi"):Destroy()
end

local library = {
	WorkspaceName = "NAGI Hub",
	flags = {},
	signals = {},
	objects = {},
	elements = {},
	globals = {},
	subs = {},
	colored = {},
	configuration = {
		hideKeybind = Enum.KeyCode.RightControl,
		smoothDragging = false,
		easingStyle = Enum.EasingStyle.Quart,
		easingDirection = Enum.EasingDirection.Out
	},
	colors = {
		main = Color3.fromRGB(46, 204, 113),
		background = Color3.fromRGB(40, 40, 40),
		outerBorder = Color3.fromRGB(46, 204, 113),
		innerBorder = Color3.fromRGB(73, 63, 73),
		topGradient = Color3.fromRGB(35, 35, 35),
		bottomGradient = Color3.fromRGB(29, 29, 29),
		sectionBackground = Color3.fromRGB(35, 34, 34),
		section = Color3.fromRGB(176, 175, 176),
		otherElementText = Color3.fromRGB(129, 127, 129),
		elementText = Color3.fromRGB(147, 145, 147),
		elementBorder = Color3.fromRGB(20, 20, 20),
		selectedOption = Color3.fromRGB(55, 55, 55),
		unselectedOption = Color3.fromRGB(40, 40, 40),
		hoveredOptionTop = Color3.fromRGB(65, 65, 65),
		unhoveredOptionTop = Color3.fromRGB(50, 50, 50),
		hoveredOptionBottom = Color3.fromRGB(45, 45, 45),
		unhoveredOptionBottom = Color3.fromRGB(35, 35, 35),
		tabText = Color3.fromRGB(20, 90, 50)
	},
	gui_parent = (function()
		local x, c = pcall(function()
			return game:GetService("CoreGui")
		end)
		if x and c then
			return c
		end
		x, c = pcall(function()
			return (game:IsLoaded() or (game.Loaded:Wait() or 1)) and game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui")
		end)
		if x and c then
			return c
		end
		x, c = pcall(function()
			return game:GetService("StarterGui")
		end)
		if x and c then
			return c
		end
		return error("Seriously bad exploit. Can't find a place to store the GUI. Robust code can't help here.")
	end)(),
	colorpicker = false,
	colorpickerconflicts = {},
	rainbowflags = {},
	rainbows = 0,
	rainbowsg = 0
}
library.Subs = library.subs
local library_flags = library.flags
local destroyrainbows, destroyrainbowsg = nil
function darkenColor(clr, intensity)
	if not intensity or intensity == 1 then
		return clr
	end
	if clr and (typeof(clr) == "Color3" or type(clr) == "table") then
		return Color3.new(clr.R / intensity, clr.G / intensity, clr.B / intensity)
	end
end
library.subs.darkenColor = darkenColor
local __runscript = true
local function wait_check(...)
	if __runscript then
		return wait(...)
	else
		wait()
		return false
	end
end
library.subs.Wait, library.subs.wait = wait_check, wait_check
local lasthidebing = 0
local temp = game:FindService("MarketplaceService") or game:GetService("MarketplaceService")
local Marketplace = (temp and (cloneref and cloneref(temp))) or temp
local resolvevararg, temp = nil
do
	local lwr = string.lower
	function library.defaultSort(a, b)
		return lwr(tostring(b)) > lwr(tostring(a))
	end
end
do
	local varargresolve = {
		Window = {"Name", "Theme"},
		Tab = {"Name", "Image"},
		Section = {"Name", "Side"},
		Label = {"Text", "Flag", "UnloadValue", "UnloadFunc"},
		Toggle = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "Locked", "Keybind", "Condition", "AllowDuplicateCalls"},
		Textbox = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "Placeholder", "Type", "Min", "Max", "Decimals", "Hex", "Binary", "Base", "RichTextBox", "MultiLine", "TextScaled", "TextFont", "PreFormat", "PostFormat", "CustomProperties", "AllowDuplicateCalls"},
		Slider = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "Min", "Max", "Decimals", "Format", "IllegalInput", "Textbox", "AllowDuplicateCalls"},
		Button = {"Name", "Callback", "Locked", "Condition"},
		Keybind = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "Pressed", "KeyNames", "AllowDuplicateCalls"},
		Dropdown = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "List", "Filter", "Method", "Nothing", "Sort", "MultiSelect", "ItemAdded", "ItemRemoved", "ItemChanged", "ItemsCleared", "ScrollUpButton", "ScrollDownButton", "ScrollButtonRate", "DisablePrecisionScrolling", "AllowDuplicateCalls"},
		SearchBox = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "List", "Filter", "Method", "Nothing", "Sort", "MultiSelect", "ItemAdded", "ItemRemoved", "ItemChanged", "ItemsCleared", "ScrollUpButton", "ScrollDownButton", "ScrollButtonRate", "DisablePrecisionScrolling", "RegEx", "AllowDuplicateCalls"},
		Colorpicker = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "Rainbow", "Random", "AllowDuplicateCalls"},
		Persistence = {"Name", "Value", "Callback", "Flag", "Location", "LocationFlag", "UnloadValue", "UnloadFunc", "Workspace", "Persistive", "Suffix", "LoadCallback", "SaveCallback", "PostLoadCallback", "PostSaveCallback", "ScrollUpButton", "ScrollDownButton", "ScrollButtonRate", "DisablePrecisionScrolling", "AllowDuplicateCalls"},
		Designer = {"Backdrop", "Image", "Info", "Credit"}
	}
	function resolvevararg(objtype, ...)
		local data = varargresolve[objtype]
		local t = {}
		if data then
			for index, value in next, {...} do
				t[data[index]] = value
			end
		end
		return t
	end
end
local resolvercache = {}
library.resolvercache = resolvercache
local function resolveid(image, flag)
	if image then
		if type(image) == "string" then
			if (#image > 14 and string.sub(image, 1, 13) == "rbxassetid://") or (#image > 12 and string.sub(image, 1, 11) == "rbxasset://") or (#image > 12 and string.sub(image, 1, 11) ~= "rbxthumb://") then
				if flag then
					local thing = library.elements[flag] or library.designerelements[flag]
					if thing and thing.Set then
						task.spawn(thing.Set, thing, image)
					end
				end
				return image
			end
		end
		local orig = image
		if resolvercache[orig] then
			if flag then
				local thing = library.elements[flag] or library.designerelements[flag]
				if thing and thing.Set then
					task.spawn(thing.Set, thing, resolvercache[orig])
				end
			end
			return resolvercache[orig]
		end
		image = tonumber(image) or image
		local succezz = pcall(function()
			local typ = type(image)
			if typ == "string" then
				if getsynasset then
					if #image > 11 and string.sub(image, 1, 11) == "synasset://" then
						return getsynasset(string.sub(image, 12))
					elseif #image > 14 and string.sub(image, 1, 14) == "synasseturl://" then
						local x, e = pcall(function()
							local codename, fixes = string.gsub(image, ".", function(c)
								if c:lower() == c:upper() and not tonumber(c) then
									return ""
								end
							end)
							codename = string.sub(codename, 1, 24) .. tostring(fixes)
							local fold = isfolder("./Function Lib")
							if not fold then
								makefolder("./Function Lib")
							end
							fold = isfolder("./Function Lib/Themes")
							if not fold then
								makefolder("./Function Lib/Themes")
							end
							fold = isfolder("./Function Lib/Themes/SynapseAssetsCache")
							if not fold then
								makefolder("./Function Lib Themes/SynapseAssetsCache")
							end
							if not fold or not isfile("./Function Lib/Themes/SynapseAssetsCache/" .. codename .. ".dat") then
								local res = game:HttpGet(string.sub(image, 15))
								if res ~= nil then
									writefile("./Function Lib/Themes/SynapseAssetsCache/" .. codename .. ".dat", res)
								end
							end
							return getsynasset(readfile("./Function Lib/Themes/SynapseAssetsCache/" .. codename .. ".dat"))
						end)
						if x and e ~= nil then
							return e
						end
					end
				end
				if #image < 11 or (string.sub(image, 1, 13) ~= "rbxassetid://" and string.sub(image, 1, 11) ~= "rbxasset://" and string.sub(image, 1, 11) ~= "rbxthumb://") then
					image = tonumber(image:gsub("%D", ""), 10) or image
					typ = type(image)
				end
			end
			if typ == "number" and image > 0 then
				pcall(function()
					local nfo = Marketplace and Marketplace:GetProductInfo(image)
					image = tostring(image)
					if nfo and nfo.AssetTypeId == 1 then
						image = "rbxassetid://" .. image
					elseif nfo.AssetTypeId == 13 then
						local decal = game:GetObjects("rbxassetid://" .. image)[1]
						image = "rbxassetid://" .. decal.Texture:match("%d+$")
						decal = (decal and decal:Destroy() and nil) or nil
					end
				end)
			else
				image = nil
			end
		end)
		if succezz and image then
			if orig then
				resolvercache[orig] = image
			end
			resolvercache[image] = image
			if flag then
				local thing = library.elements[flag] or library.designerelements[flag]
				if thing and thing.Set then
					task.spawn(thing.Set, thing, image)
				end
			end
		end
	end
	return image
end
library.subs.ResolveID = resolveid
library.resolvercache = resolvercache
local colored = library.colored
local colors = library.colors
local tweenService = game:GetService("TweenService")
local updatecolors = nil
do
	function updatecolors(tweenit)
		if library.objects and (#library.objects > 0 or next(library.objects)) then
			for _, data in next, colored do
				local x, e
				if tweenit then
					x, e = pcall(function()
						local cclr = colors[data[3]]
						local darkness = data[4]
						tweenService:Create(data[1], TweenInfo.new(tweenit, library.configuration.easingStyle, library.configuration.easingDirection), {
							[data[2]] = (darkness and darkness ~= 1 and darkenColor(cclr, darkness)) or cclr
						}):Play()
					end)
				end
				if not x then
					local x, e = pcall(function()
						local cclr = colors[data[3]]
						local darkness = data[4]
						data[1][data[2]] = (darkness and darkness ~= 1 and darkenColor(cclr, darkness)) or cclr
					end)
					if not x and e then
						warn(debug.traceback(e))
					end
				end
			end
			pcall(function()
				if library.Backdrop then
					library.Backdrop.Visible = not not library_flags["__Designer.Background.UseBackgroundImage"]
					library.Backdrop.Image = resolveid(library_flags["__Designer.Background.ImageAssetID"], "__Designer.Background.ImageAssetID") or ""
					library.Backdrop.ImageColor3 = library_flags["__Designer.Background.ImageColor"] or Color3.new(1, 1, 1)
					library.Backdrop.ImageTransparency = (library_flags["__Designer.Background.ImageTransparency"] or 95) / 100
				end
			end)
		end
	end
	library.subs.UpdateColors = updatecolors
end
local function updatecolorsnotween()
	updatecolors()
end
library.subs.updatecolors = updatecolors
library.colors = setmetatable({}, {
	__index = colors,
	__newindex = function(_, k, v)
		if colors[k] ~= v then
			colors[k] = v
			spawn(updatecolorsnotween)
		end
	end
})
local elements = library.elements
shared.libraries = shared.libraries or {}
local colorpickerconflicts = library.colorpickerconflicts
local keyHandler = {
	notAllowedKeys = {
		[Enum.KeyCode.Return] = true,
		[Enum.KeyCode.Space] = true,
		[Enum.KeyCode.Tab] = true,
		[Enum.KeyCode.Unknown] = true,
		[Enum.KeyCode.Backspace] = true
	},
	notAllowedMouseInputs = {
		[Enum.UserInputType.MouseMovement] = true,
		[Enum.UserInputType.MouseWheel] = true,
		[Enum.UserInputType.MouseButton1] = true,
		[Enum.UserInputType.MouseButton2] = true,
		[Enum.UserInputType.MouseButton3] = true
	},
	allowedKeys = {
		[Enum.KeyCode.LeftShift] = "LShift",
		[Enum.KeyCode.RightShift] = "RShift",
		[Enum.KeyCode.LeftControl] = "LCtrl",
		[Enum.KeyCode.RightControl] = "RCtrl",
		[Enum.KeyCode.LeftAlt] = "LAlt",
		[Enum.KeyCode.RightAlt] = "RAlt",
		[Enum.KeyCode.CapsLock] = "CAPS",
		[Enum.KeyCode.One] = "1",
		[Enum.KeyCode.Two] = "2",
		[Enum.KeyCode.Three] = "3",
		[Enum.KeyCode.Four] = "4",
		[Enum.KeyCode.Five] = "5",
		[Enum.KeyCode.Six] = "6",
		[Enum.KeyCode.Seven] = "7",
		[Enum.KeyCode.Eight] = "8",
		[Enum.KeyCode.Nine] = "9",
		[Enum.KeyCode.Zero] = "0",
		[Enum.KeyCode.KeypadOne] = "Num-1",
		[Enum.KeyCode.KeypadTwo] = "Num-2",
		[Enum.KeyCode.KeypadThree] = "Num-3",
		[Enum.KeyCode.KeypadFour] = "Num-4",
		[Enum.KeyCode.KeypadFive] = "Num-5",
		[Enum.KeyCode.KeypadSix] = "Num-6",
		[Enum.KeyCode.KeypadSeven] = "Num-7",
		[Enum.KeyCode.KeypadEight] = "Num-8",
		[Enum.KeyCode.KeypadNine] = "Num-9",
		[Enum.KeyCode.KeypadZero] = "Num-0",
		[Enum.KeyCode.Minus] = "-",
		[Enum.KeyCode.Equals] = "=",
		[Enum.KeyCode.Tilde] = "~",
		[Enum.KeyCode.LeftBracket] = "[",
		[Enum.KeyCode.RightBracket] = "]",
		[Enum.KeyCode.RightParenthesis] = ")",
		[Enum.KeyCode.LeftParenthesis] = "(",
		[Enum.KeyCode.Semicolon] = ";",
		[Enum.KeyCode.Quote] = "'",
		[Enum.KeyCode.BackSlash] = "\\",
		[Enum.KeyCode.Comma] = ",",
		[Enum.KeyCode.Period] = ".",
		[Enum.KeyCode.Slash] = "/",
		[Enum.KeyCode.Asterisk] = "*",
		[Enum.KeyCode.Plus] = "+",
		[Enum.KeyCode.Period] = ".",
		[Enum.KeyCode.Backquote] = "`"
	}
}
local function hardunload(library)
	if library.UnloadCallback and type(library.UnloadCallback) == "function" then
		local x, e = pcall(library.UnloadCallback)
		if not x and e then
			task.spawn(error, e, 2)
		end
	end
	for cflag, data in next, elements do
		if data.Type ~= "Persistence" then
			if data.Set and data.Options.UnloadValue ~= nil then
				data.Set(data.Options.UnloadValue)
			end
			if data.Options.UnloadFunc then
				local y, u = pcall(data.Options.UnloadFunc)
				if not y and u then
					warn(debug.traceback("Error unloading '" .. tostring(cflag) .. "'\n" .. u))
				end
			end
		end
	end
	for _, v in next, {library.signals, library.objects} do
		for k, o in next, v do
			if o then
				local te = typeof(o)
				if te == "RBXScriptConnection" then
					o:Disconnect()
				elseif te == "Instance" then
					o:Destroy()
				end
			end
			v[k] = nil
		end
	end
	library.signals = nil
	library.objects = nil
end
library.Subs.UnloadArg = hardunload
local function unloadall()
	if shared.libraries then
		local b = 50
		while #shared.libraries > 0 do
			b = b - 1
			if b < 0 then
				b = 50
				wait(warn("Looped 50 times while unloading....?"))
			end
			local v = shared.libraries[1]
			if v and v.unload and type(v.unload) == "function" then
				if not pcall(v.unload) then
					pcall(hardunload, v)
					for k in next, v do
						v[k] = nil
					end
				end
				table.remove(shared.libraries, 1)
			end
		end
	end
	shared.libraries = nil
end
shared.unloadall = unloadall
library.unloadall = unloadall
shared.libraries[1 + #shared.libraries] = library
function library.unload()
	__runscript = nil
	hardunload(library)
	if shared.libraries then
		for k, v in next, shared.libraries or {} do
			if v == library then
				for k in next, table.remove(shared.libraries, k) do
					v[k] = nil
				end
				break
			end
		end
		if #shared.libraries == 0 then
			shared.libraries = nil
		end
	end
	warn("Unloaded")
end
library.Unload = library.unload
local Instance_new = (syn and syn.protect_gui and function(...)
	local x = {Instance.new(...)}
	if x[1] then
		library.objects[1 + #library.objects] = x[1]
		pcall(syn.protect_gui, x[1])
	end
	return unpack(x)
end) or function(...)
	local x = {Instance.new(...)}
	if x[1] then
		library.objects[1 + #library.objects] = x[1]
	end
	return unpack(x)
end
library.subs.Instance_new = Instance_new
local playersservice = game:GetService("Players")
local function getresolver(listt, filter, method, _)
	local huo, args = type(filter), {}
	local hou = typeof(listt)
	return (hou == "table" and function()
		return listt
	end) or function()
		local hardtype = nil
		local g = listt
		for _ = 1, 5 do
			hardtype = typeof(g)
			if hardtype == "function" then
				local x, e = pcall(listt)
				if x and e then
					g = e
				end
				hardtype = typeof(g)
			end
			if hardtype == "Instance" then
				local lastg = g
				if method == nil and listt == playersservice then
					g = listt:GetPlayers()
				end
				if method then
					local metype = type(method)
					if metype == "table" then
						method = method.Method or method[1]
						args = method.Args or method.Arguments or unpack(method, (method.Method ~= nil and 1) or 2)
						metype = type(method)
					end
					local y, u = nil, nil
					if metype == "function" then
						y, u = pcall(method, listt, unpack(args))
					elseif metype == "string" then
						local y, u = pcall(function()
							return listt[method](listt, unpack(args))
						end)
					else
						warn("Idk how to handle method type of", metype, debug.traceback(""))
					end
					if u then
						if y then
							g = u
						else
							warn("Error trying method", method, "on", listt, debug.traceback(u))
						end
					end
				end
				if g == lastg then
					g = listt:GetChildren()
				end
			end
			if hardtype == "Enum" then
				g = listt:GetEnumItems()
			end
			hardtype = typeof(g)
			if hardtype == "table" then
				break
			end
		end
		hardtype = typeof(g)
		if hardtype ~= "table" then
			warn("Could not resolve " .. hou .. " type to a list.")
			return {}
		end
		if filter then
			if huo == "function" then
				local accept = {}
				for _, v in next, g do
					local x, e = pcall(filter, v)
					if x and e then
						accept[1 + #accept] = (e == true and v) or e
					end
				end
				g = accept
			elseif huo == "string" then
				local accept = {}
				for _, v in next, g do
					if tostring(v):lower():find(huo) then
						accept[1 + #accept] = v
					end
				end
				g = accept
			elseif huo == "table" then
				local accept = {}
				if type(filter[1]) == "string" then
					for _, v in next, g do
						if tostring(v):lower():find(huo) then
							accept[1 + #accept] = v
						elseif filter[0] then
							accept[1 + #accept] = v
						end
					end
				else
					for _, v in next, g do
						if not table.find(filter, v) and not table.find(filter, tostring(v)) then
							accept[1 + #accept] = v
						elseif not filter[0] then
							accept[1 + #accept] = v
						end
					end
				end
				g = accept
			end
		end
		return g
	end
end
library.subs.GetResolver = getresolver
local function resetall()
	destroyrainbowsg = true
	pcall(function()
		for k, v in next, elements do
			if v and k and v.Set and v.Default ~= nil and library_flags[k] ~= v.Default and string.sub(k, 1, 11) ~= "__Designer." then
				v:Set(v.Default)
			end
		end
	end)
end
library.ResetAll = resetall
local textService = game:GetService("TextService")
local userInputService = game:GetService("UserInputService")
local runService = game:GetService("RunService")
local LP = playersservice.LocalPlayer
library.LP = LP
library.Players = playersservice
library.UserInputService = userInputService
library.RunService = runService
local mouse = LP and LP:GetMouse()
if not mouse and PluginManager and runService:IsStudio() then
	shared.library_plugin = shared.library_plugin or print("Creating Studio Test-Plugin...") or PluginManager():CreatePlugin()
	mouse = shared.library_plugin:GetMouse()
	library.plugin = shared.library_plugin
end
library.Mouse = mouse
local function textToSize(object)
	if object ~= nil then
		local output = textService:GetTextSize(object.Text, object.TextSize, object.Font, Vector2.new(math.huge, math.huge))
		return {
			X = output.X,
			Y = output.Y
		}
	end
end
library.subs.textToSize = textToSize
local function removeSpaces(str)
	if str then
		local newStr = str:gsub(" ", "")
		return newStr
	end
end
library.subs.removeSpaces = removeSpaces
local function Color3FromHex(hex)
	hex = hex:gsub("#", ""):upper():gsub("0X", "")
	return Color3.fromRGB(tonumber(hex:sub(1, 2), 16), tonumber(hex:sub(3, 4), 16), tonumber(hex:sub(5, 6), 16))
end
library.subs.Color3FromHex = Color3FromHex
local floor = math.floor
local function Color3ToHex(color)
	local r, g, b = string.format("%X", floor(color.R * 255)), string.format("%X", floor(color.G * 255)), string.format("%X", floor(color.B * 255))
	if #r < 2 then
		r = "0" .. r
	end
	if #g < 2 then
		g = "0" .. g
	end
	if #b < 2 then
		b = "0" .. b
	end
	return string.format("%s%s%s", r, g, b)
end
if Color3.ToHex and not shared.overridecolortohex then
	local x, e = pcall(Color3.ToHex, Color3.new())
	if x and type(e) == "string" and #e == 6 then
		Color3ToHex = Color3.ToHex
	end
end
library.subs.Color3ToHex = Color3ToHex
local isDraggingSomething = false
local function makeDraggable(topBarObject, object)
	local dragging = nil
	local dragInput = nil
	local dragStart = nil
	local startPosition = nil
	library.signals[1 + #library.signals] = topBarObject.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
			dragging = true
			dragStart = input.Position
			startPosition = object.Position
			input.Changed:Connect(function()
				if input.UserInputState == Enum.UserInputState.End then
					dragging = false
				end
			end)
		end
	end)
	library.signals[1 + #library.signals] = topBarObject.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
			dragInput = input
		end
	end)
	library.signals[1 + #library.signals] = userInputService.InputChanged:Connect(function(input)
		if input == dragInput and dragging then
			local delta = input.Position - dragStart
			if not isDraggingSomething and library.configuration.smoothDragging then
				tweenService:Create(object, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
					Position = UDim2.new(startPosition.X.Scale, startPosition.X.Offset + delta.X, startPosition.Y.Scale, startPosition.Y.Offset + delta.Y)
				}):Play()
			elseif not isDraggingSomething and not library.configuration.smoothDragging then
				object.Position = UDim2.new(startPosition.X.Scale, startPosition.X.Offset + delta.X, startPosition.Y.Scale, startPosition.Y.Offset + delta.Y)
			end
		end
	end)
end
library.subs.makeDraggable = makeDraggable
local JSONEncode, JSONDecode = nil, nil
do
	local temp_http = game:FindService("HttpService") or game:GetService("HttpService")
	local httpservice = temp_http
	if cloneref and type(cloneref) == "function" then
		httpservice, temp_http = cloneref(httpservice), nil
	end
	library.Http = httpservice
	local JSONEncodeFunc = httpservice.JSONEncode
	function JSONEncode(...)
		return pcall(JSONEncodeFunc, httpservice, ...)
	end
	library.JSONEncode = JSONEncode
	local JSONDecodeFunc = httpservice.JSONDecode
	function JSONDecode(...)
		return pcall(JSONDecodeFunc, httpservice, ...)
	end
	library.JSONDecode = JSONDecode
end
local convertfilename
do
	local string_gsub = string.gsub
	function convertfilename(str, default, replace)
		replace = replace or "_"
		local corrections = 0
		local predname = string_gsub(str, "%W", function(c)
			local byt = c:byte()
			if not (byt == 0 or byt == 32 or byt == 33 or byt == 59 or byt == 61 or (byt >= 35 and byt <= 41) or (byt >= 43 and byt <= 57) or (byt >= 64 and byt <= 123) or (byt >= 125 and byt <= 127)) then
				corrections = 1 + corrections
				return replace
			end
		end)
		return (default and corrections == #predname and tostring(default)) or predname
	end
	library.subs.ConvertFilename = convertfilename
end
function library:CreateWindow(options, ...)
	options = (options and type(options) == "string" and resolvevararg("Window", options, ...)) or options
	local homepage = nil
	local windowoptions = options
	local windowName = options.Name or "Unnamed Window"
	options.Name = windowName
	if windowName and #windowName > 0 and library.WorkspaceName == "Function Lib" then
		library.WorkspaceName = convertfilename(windowName, "Function Lib")
	end
	local FunctionLibrary = Instance_new("ScreenGui")
	local main = Instance_new("Frame")
	local mainBorder = Instance_new("Frame")
	local tabSlider = Instance_new("Frame")
	local innerMain = Instance_new("Frame")
	local innerMainBorder = Instance_new("Frame")
	local innerBackdrop = Instance_new("ImageLabel")
	local innerMainHolder = Instance_new("Frame")
	local tabsHolder = Instance_new("ImageLabel")
	local tabHolderList = Instance_new("UIListLayout")
	local tabHolderPadding = Instance_new("UIPadding")
	local headline = Instance_new("TextLabel")
	local splitter = Instance_new("TextLabel")
	local submenuOpen = nil
	library.globals["__Window" .. options.Name] = {
		submenuOpen = submenuOpen
	}
	FunctionLibrary.Name = "PepsiUi"
	FunctionLibrary.Parent = library.gui_parent
	FunctionLibrary.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
	FunctionLibrary.DisplayOrder = 10
	FunctionLibrary.ResetOnSpawn = false
	main.Name = "main"
	main.Parent = FunctionLibrary
	main.AnchorPoint = Vector2.new(0.5, 0.5)
	main.BackgroundColor3 = library.colors.background
	colored[1 + #colored] = {main, "BackgroundColor3", "background"}
	main.BorderColor3 = library.colors.outerBorder
	colored[1 + #colored] = {main, "BorderColor3", "outerBorder"}
	main.Position = UDim2.fromScale(0.5, 0.5)
	main.Size = UDim2.fromOffset(500, 545)
	makeDraggable(main, main)
	mainBorder.Name = "mainBorder"
	mainBorder.Parent = main
	mainBorder.AnchorPoint = Vector2.new(0.5, 0.5)
	mainBorder.BackgroundColor3 = library.colors.background
	colored[1 + #colored] = {mainBorder, "BackgroundColor3", "background"}
	mainBorder.BorderColor3 = library.colors.innerBorder
	colored[1 + #colored] = {mainBorder, "BorderColor3", "innerBorder"}
	mainBorder.BorderMode = Enum.BorderMode.Inset
	mainBorder.Position = UDim2.fromScale(0.5, 0.5)
	mainBorder.Size = UDim2.fromScale(1, 1)
	innerMain.Name = "innerMain"
	innerMain.Parent = main
	innerMain.AnchorPoint = Vector2.new(0.5, 0.5)
	innerMain.BackgroundColor3 = library.colors.background
	colored[1 + #colored] = {innerMain, "BackgroundColor3", "background"}
	innerMain.BorderColor3 = library.colors.outerBorder
	colored[1 + #colored] = {innerMain, "BorderColor3", "outerBorder"}
	innerMain.Position = UDim2.fromScale(0.5, 0.5)
	innerMain.Size = UDim2.new(1, -14, 1, -14)
	innerMainBorder.Name = "innerMainBorder"
	innerMainBorder.Parent = innerMain
	innerMainBorder.AnchorPoint = Vector2.new(0.5, 0.5)
	innerMainBorder.BackgroundColor3 = library.colors.background
	colored[1 + #colored] = {innerMainBorder, "BackgroundColor3", "background"}
	innerMainBorder.BorderColor3 = library.colors.innerBorder
	colored[1 + #colored] = {innerMainBorder, "BorderColor3", "innerBorder"}
	innerMainBorder.BorderMode = Enum.BorderMode.Inset
	innerMainBorder.Position = UDim2.fromScale(0.5, 0.5)
	innerMainBorder.Size = UDim2.fromScale(1, 1)
	innerMainHolder.Name = "innerMainHolder"
	innerMainHolder.Parent = innerMain
	innerMainHolder.BackgroundColor3 = Color3.new(1, 1, 1)
	innerMainHolder.BackgroundTransparency = 1
	innerMainHolder.Position = UDim2:fromOffset(25)
	innerMainHolder.Size = UDim2.new(1, 0, 1, -25)
	innerBackdrop.Name = "innerBackdrop"
	innerBackdrop.Parent = innerMainHolder
	innerBackdrop.BackgroundColor3 = Color3.new(1, 1, 1)
	innerBackdrop.BackgroundTransparency = 1
	innerBackdrop.Size = UDim2.fromScale(1, 1)
	innerBackdrop.ZIndex = -1
	innerBackdrop.Visible = not not library_flags["__Designer.Background.UseBackgroundImage"]
	innerBackdrop.ImageColor3 = library_flags["__Designer.Background.ImageColor"] or Color3.new(1, 1, 1)
	innerBackdrop.ImageTransparency = (library_flags["__Designer.Background.ImageTransparency"] or 95) / 100
	innerBackdrop.Image = resolveid(library_flags["__Designer.Background.ImageAssetID"], "__Designer.Background.ImageAssetID") or ""
	library.Backdrop = innerBackdrop
	tabsHolder.Name = "tabsHolder"
	tabsHolder.Parent = innerMain
	tabsHolder.BackgroundColor3 = library.colors.topGradient
	colored[1 + #colored] = {tabsHolder, "BackgroundColor3", "topGradient"}
	tabsHolder.BorderSizePixel = 0
	tabsHolder.Position = UDim2.fromOffset(1, 1)
	tabsHolder.Size = UDim2.new(1, -2, 0, 23)
	tabsHolder.Image = "rbxassetid://2454009026"
	tabsHolder.ImageColor3 = library.colors.bottomGradient
	colored[1 + #colored] = {tabsHolder, "ImageColor3", "bottomGradient"}
	tabHolderList.Name = "tabHolderList"
	tabHolderList.Parent = tabsHolder
	tabHolderList.FillDirection = Enum.FillDirection.Horizontal
	tabHolderList.SortOrder = Enum.SortOrder.LayoutOrder
	tabHolderList.VerticalAlignment = Enum.VerticalAlignment.Center
	tabHolderList.Padding = UDim:new(3)
	tabHolderPadding.Name = "tabHolderPadding"
	tabHolderPadding.Parent = tabsHolder
	tabHolderPadding.PaddingLeft = UDim:new(7)
	headline.Name = "headline"
	headline.Parent = tabsHolder
	headline.BackgroundColor3 = Color3.new(1, 1, 1)
	headline.BackgroundTransparency = 1
	headline.LayoutOrder = 1
	headline.Font = Enum.Font.Code
	headline.Text = (windowName and tostring(windowName)) or "???"
	headline.TextColor3 = library.colors.main
	colored[1 + #colored] = {headline, "TextColor3", "main"}
	headline.TextSize = 14
	headline.TextStrokeColor3 = library.colors.outerBorder
	colored[1 + #colored] = {headline, "TextStrokeColor3", "outerBorder"}
	headline.TextStrokeTransparency = 0.75
	headline.Size = UDim2:new(textToSize(headline).X + 4, 1)
	splitter.Name = "splitter"
	splitter.Parent = tabsHolder
	splitter.BackgroundColor3 = Color3.new(1, 1, 1)
	splitter.BackgroundTransparency = 1
	splitter.LayoutOrder = 2
	splitter.Size = UDim2:new(6, 1)
	splitter.Font = Enum.Font.Code
	splitter.Text = "|"
	splitter.TextColor3 = library.colors.tabText
	colored[1 + #colored] = {splitter, "TextColor3", "tabText"}
	splitter.TextSize = 14
	splitter.TextStrokeColor3 = library.colors.tabText
	colored[1 + #colored] = {splitter, "TextStrokeColor3", "tabText"}
	splitter.TextStrokeTransparency = 0.75
	tabSlider.Name = "tabSlider"
	tabSlider.Parent = main
	tabSlider.BackgroundColor3 = library.colors.main
	colored[1 + #colored] = {tabSlider, "BackgroundColor3", "main"}
	tabSlider.BorderSizePixel = 0
	tabSlider.Position = UDim2.fromOffset(100, 30)
	tabSlider.Size = UDim2:fromOffset(1)
	tabSlider.Visible = false
	do
		local os_clock = os.clock
		library.signals[1 + #library.signals] = userInputService.InputBegan:Connect(function(keyCode, gameProcessedEvent)
			gameProcessedEvent = gameProcessedEvent or userInputService:GetFocusedTextBox()
			if not gameProcessedEvent and keyCode.KeyCode == library.configuration.hideKeybind then
				if not lasthidebing or os_clock() - lasthidebing > 12 then
					main.Visible = not main.Visible
				end
				lasthidebing = nil
			end
		end)
	end
	local windowFunctions = {
		tabCount = 0,
		selected = {},
		Flags = elements
	}
	library.globals["__Window" .. windowName].windowFunctions = windowFunctions
	function windowFunctions:Show(x)
		main.Visible = x == nil or x == true or x == 1
	end
	function windowFunctions:Hide(x)
		main.Visible = x == false or x == 0
	end
	function windowFunctions:Visibility(x)
		if x == nil then
			main.Visible = not main.Visible
		else
			main.Visible = not not x
		end
	end
	function windowFunctions:MoveTabSlider(tabObject)
		spawn(function()
			tabSlider.Visible = true
			tweenService:Create(tabSlider, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
				Size = UDim2.fromOffset(tabObject.AbsoluteSize.X, 1),
				Position = UDim2.fromOffset(tabObject.AbsolutePosition.X, tabObject.AbsolutePosition.Y + tabObject.AbsoluteSize.Y) - UDim2.fromOffset(main.AbsolutePosition.X, main.AbsolutePosition.Y)
			}):Play()
		end)
	end
	windowFunctions.LastTab = nil
	function windowFunctions:CreateTab(options, ...)
		options = (options and type(options) == "string" and resolvevararg("Tab", options, ...)) or options or {
			Name = "Function Style: Elite Hax"
		}
		local image = options.Image
		if image then
			image = resolveid(image)
		end
		local tabName = options.Name or "Unnamed Tab"
		options.Name = tabName
		windowFunctions.tabCount = windowFunctions.tabCount + 1
		local newTab = Instance_new((image and "ImageButton") or "TextButton")
		local newTabHolder = Instance_new("Frame")
		library.globals["__Window" .. windowName].newTabHolder = newTabHolder
		local left = Instance_new("ScrollingFrame")
		local leftList = Instance_new("UIListLayout")
		local leftPadding = Instance_new("UIPadding")
		local right = Instance_new("ScrollingFrame")
		local rightList = Instance_new("UIListLayout")
		local rightPadding = Instance_new("UIPadding")
		newTab.Name = removeSpaces((tabName and tostring(tabName):lower() or "???") .. "Tab")
		newTab.Parent = tabsHolder
		newTab.BackgroundTransparency = 1
		newTab.LayoutOrder = (options.LastTab and 99999) or tonumber(options.TabOrder or options.LayoutOrder) or (2 + windowFunctions.tabCount)
		local colored_newTab_TextColor3 = nil
		if image then
			newTab.Image = image
			newTab.ImageColor3 = options.ImageColor or options.Color or Color3.new(1, 1, 1)
			newTab.Size = UDim2:new(tabsHolder.AbsoluteSize.Y, 1)
		else
			colored_newTab_TextColor3 = {newTab, "TextColor3", "tabText"}
			colored[1 + #colored] = colored_newTab_TextColor3
			newTab.Font = Enum.Font.Code
			newTab.Text = (tabName and tostring(tabName)) or "???"
			if windowFunctions.tabCount ~= 1 then
				colored_newTab_TextColor3[4] = 1.35
				newTab.TextColor3 = darkenColor(library.colors.tabText, 1.35)
			else
				newTab.TextColor3 = library.colors.tabText
			end
			newTab.TextSize = 14
			newTab.TextStrokeColor3 = Color3.fromRGB(42, 42, 42)
			newTab.TextStrokeTransparency = 0.75
			newTab.Size = UDim2:new(textToSize(newTab).X + 4, 1)
		end
		local function goto()
			if not library.colorpicker and not submenuOpen and windowFunctions.selected.button ~= newTab then
				pcall(function()
					for _, e in next, library.elements do
						if e and type(e) == "table" and e.Update then
							pcall(e.Update)
						end
					end
				end)
				if windowFunctions.LastTab then
					windowFunctions.LastTab[4] = 1.35
				end
				windowFunctions:MoveTabSlider(newTab)
				if windowFunctions.selected.button.ClassName == "TextButton" then
					tweenService:Create(windowFunctions.selected.button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						TextColor3 = darkenColor(library.colors.tabText, 1.35)
					}):Play()
				end
				if colored_newTab_TextColor3 then
					colored_newTab_TextColor3[4] = nil
				end
				windowFunctions.selected.holder.Visible = false
				windowFunctions.selected.button = newTab
				windowFunctions.selected.holder = newTabHolder
				if windowFunctions.selected.button.ClassName == "TextButton" then
					tweenService:Create(windowFunctions.selected.button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						TextColor3 = library.colors.tabText
					}):Play()
				end
				windowFunctions.selected.holder.Visible = true
				windowFunctions.LastTab = colored_newTab_TextColor3
			end
		end
		if not homepage and newTab.LayoutOrder <= 4 then
			homepage = goto
		end
		library.signals[1 + #library.signals] = newTab.MouseButton1Click:Connect(goto)
		if windowFunctions.tabCount == 1 then
			tabSlider.Size = UDim2.fromOffset(newTab.AbsoluteSize.X, 1)
			tabSlider.Position = UDim2.fromOffset(newTab.AbsolutePosition.X, newTab.AbsolutePosition.Y + newTab.AbsoluteSize.Y) - UDim2.fromOffset(main.AbsolutePosition.X, main.AbsolutePosition.Y)
			tabSlider.Visible = true
			windowFunctions.selected.holder = newTabHolder
			windowFunctions.selected.button = newTab
		end
		newTabHolder.Name = removeSpaces((tabName and tabName:lower()) or "???") .. "TabHolder"
		newTabHolder.Parent = innerMainHolder
		newTabHolder.BackgroundColor3 = Color3.new(1, 1, 1)
		newTabHolder.BackgroundTransparency = 1
		newTabHolder.Size = UDim2.fromScale(1, 1)
		newTabHolder.Visible = windowFunctions.tabCount == 1
		left.Name = "left"
		left.Parent = newTabHolder
		left.BackgroundColor3 = Color3.new(1, 1, 1)
		left.BackgroundTransparency = 1
		left.Size = UDim2.fromScale(0.5, 1)
		left.CanvasSize = UDim2.new()
		left.ScrollBarThickness = 0
		leftList.Name = "leftList"
		leftList.Parent = left
		leftList.HorizontalAlignment = Enum.HorizontalAlignment.Center
		leftList.SortOrder = Enum.SortOrder.LayoutOrder
		leftList.Padding = UDim:new(14)
		leftPadding.Name = "leftPadding"
		leftPadding.Parent = left
		leftPadding.PaddingTop = UDim:new(12)
		right.Name = "right"
		right.Parent = newTabHolder
		right.BackgroundColor3 = Color3.new(1, 1, 1)
		right.BackgroundTransparency = 1
		right.Size = UDim2.fromScale(0.5, 1)
		right.CanvasSize = UDim2.new()
		right.ScrollBarThickness = 0
		right.Position = UDim2.new(0.5)
		rightList.Name = "rightList"
		rightList.Parent = right
		rightList.HorizontalAlignment = Enum.HorizontalAlignment.Center
		rightList.SortOrder = Enum.SortOrder.LayoutOrder
		rightList.Padding = UDim:new(14)
		rightPadding.Name = "rightPadding"
		rightPadding.Parent = right
		rightPadding.PaddingTop = UDim:new(12)
		local tabFunctions = {
			Flags = {}
		}
		function tabFunctions:CreateSection(options, ...)
			options = (options and type(options) == "string" and resolvevararg("Tab", options, ...)) or options
			local sectionName, holderSide = options.Name or "Unnamed Section", options.Side
			options.Name = sectionName
			local newSection = Instance_new("Frame")
			local newSectionBorder = Instance_new("Frame")
			local insideBorderHider = Instance_new("Frame")
			local outsideBorderHider = Instance_new("Frame")
			local sectionHolder = Instance_new("Frame")
			local sectionList = Instance_new("UIListLayout")
			local sectionPadding = Instance_new("UIPadding")
			local sectionHeadline = Instance_new("TextLabel")
			colorpickerconflicts[1 + #colorpickerconflicts] = insideBorderHider
			colorpickerconflicts[1 + #colorpickerconflicts] = outsideBorderHider
			colorpickerconflicts[1 + #colorpickerconflicts] = sectionHeadline
			newSection.Name = removeSpaces((sectionName and sectionName:lower() or "???") .. "Section")
			newSection.Parent = (holderSide and ((holderSide:lower() == "left" and left) or right)) or left
			newSection.BackgroundColor3 = library.colors.sectionBackground
			colored[1 + #colored] = {newSection, "BackgroundColor3", "sectionBackground"}
			newSection.BorderColor3 = library.colors.outerBorder
			colored[1 + #colored] = {newSection, "BorderColor3", "outerBorder"}
			newSection.Size = UDim2.new(1, -20)
			newSection.Visible = false
			newSectionBorder.Name = "newSectionBorder"
			newSectionBorder.Parent = newSection
			newSectionBorder.BackgroundColor3 = library.colors.sectionBackground
			colored[1 + #colored] = {newSectionBorder, "BackgroundColor3", "sectionBackground"}
			newSectionBorder.BorderColor3 = library.colors.innerBorder
			colored[1 + #colored] = {newSectionBorder, "BorderColor3", "innerBorder"}
			newSectionBorder.BorderMode = Enum.BorderMode.Inset
			newSectionBorder.Size = UDim2.fromScale(1, 1)
			sectionHolder.Name = "sectionHolder"
			sectionHolder.Parent = newSection
			sectionHolder.BackgroundColor3 = Color3.new(1, 1, 1)
			sectionHolder.BackgroundTransparency = 1
			sectionHolder.Size = UDim2.fromScale(1, 1)
			sectionList.Name = "sectionList"
			sectionList.Parent = sectionHolder
			sectionList.HorizontalAlignment = Enum.HorizontalAlignment.Center
			sectionList.SortOrder = Enum.SortOrder.LayoutOrder
			sectionList.Padding = UDim:new(1)
			sectionPadding.Name = "sectionPadding"
			sectionPadding.Parent = sectionHolder
			sectionPadding.PaddingTop = UDim:new(9)
			sectionHeadline.Name = "sectionHeadline"
			sectionHeadline.Parent = newSection
			sectionHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
			sectionHeadline.BackgroundTransparency = 1
			sectionHeadline.Position = UDim2.fromOffset(18, -8)
			sectionHeadline.ZIndex = 2
			sectionHeadline.Font = Enum.Font.Code
			sectionHeadline.LineHeight = 1.15
			sectionHeadline.Text = (sectionName and sectionName or "???")
			sectionHeadline.TextColor3 = library.colors.section
			colored[1 + #colored] = {sectionHeadline, "TextColor3", "section"}
			sectionHeadline.TextSize = 14
			sectionHeadline.Size = UDim2.fromOffset(textToSize(sectionHeadline).X + 4, 12)
			insideBorderHider.Name = "insideBorderHider"
			insideBorderHider.Parent = newSection
			insideBorderHider.BackgroundColor3 = library.colors.sectionBackground
			colored[1 + #colored] = {insideBorderHider, "BackgroundColor3", "sectionBackground"}
			insideBorderHider.BorderSizePixel = 0
			insideBorderHider.Position = UDim2.fromOffset(15)
			insideBorderHider.Size = UDim2.fromOffset(sectionHeadline.AbsoluteSize.X + 3, 1)
			outsideBorderHider.Name = "outsideBorderHider"
			outsideBorderHider.Parent = newSection
			outsideBorderHider.BackgroundColor3 = library.colors.background
			colored[1 + #colored] = {outsideBorderHider, "BackgroundColor3", "background"}
			outsideBorderHider.BorderSizePixel = 0
			outsideBorderHider.Position = UDim2.fromOffset(15, -1)
			outsideBorderHider.Size = UDim2.fromOffset(sectionHeadline.AbsoluteSize.X + 3, 1)
			local sectionFunctions = {
				Flags = {}
			}
			function sectionFunctions:Update(extra)
				local currentHolder = newSection.Parent
				if not newSection.Visible then
					newSection.Visible = true
				end
				newSection.Size = UDim2.new(1, -20, 0, (sectionList.AbsoluteContentSize.Y + 15))
				currentHolder.CanvasSize = UDim2:fromOffset(currentHolder:FindFirstChildOfClass("UIListLayout").AbsoluteContentSize.Y + 22 + (extra and extra or 0))
			end
			function sectionFunctions:AddToggle(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Tab", options, ...)) or options
				local toggleName, alreadyEnabled, callback, flagName = assert(options.Name, "Missing Name for new toggle."), options.Value or options.Enabled, options.Callback, options.Flag or (function()
					library.unnamedtoggles = 1 + (library.unnamedtoggles or 0)
					return "Toggle" .. tostring(library.unnamedtoggles)
				end)()
				if elements[flagName] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
				end
				local newToggle = Instance_new("Frame")
				local toggle = Instance_new("ImageLabel")
				local toggleInner = Instance_new("ImageLabel")
				local toggleButton = Instance_new("TextButton")
				local toggleHeadline = Instance_new("TextLabel")
				local keybindPositioner = Instance_new("Frame")
				local keybindList = Instance_new("UIListLayout")
				local keybindButton = Instance_new("TextButton")
				local lockedup = options.Locked
				newToggle.Name = removeSpaces((toggleName and toggleName:lower() or "???") .. "Toggle")
				newToggle.Parent = sectionHolder
				newToggle.BackgroundColor3 = Color3.new(1, 1, 1)
				newToggle.BackgroundTransparency = 1
				newToggle.Size = UDim2.new(1, 0, 0, 19)
				toggle.Name = "toggle"
				toggle.Parent = newToggle
				toggle.Active = true
				toggle.BackgroundColor3 = library.colors.topGradient
				local colored_toggle_BackgroundColor3 = {toggle, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_toggle_BackgroundColor3
				toggle.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {toggle, "BorderColor3", "elementBorder"}
				toggle.Position = UDim2.fromScale(0.0308237672, 0.165842205)
				toggle.Selectable = true
				toggle.Size = UDim2.fromOffset(12, 12)
				toggle.Image = "rbxassetid://2454009026"
				toggle.ImageColor3 = library.colors.bottomGradient
				local colored_toggle_ImageColor3 = {toggle, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_toggle_ImageColor3
				toggleInner.Name = "toggleInner"
				toggleInner.Parent = toggle
				toggleInner.Active = true
				toggleInner.AnchorPoint = Vector2.new(0.5, 0.5)
				toggleInner.BackgroundColor3 = library.colors.topGradient
				local colored_toggleInner_BackgroundColor3 = {toggleInner, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_toggleInner_BackgroundColor3
				toggleInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {toggleInner, "BorderColor3", "elementBorder"}
				toggleInner.Position = UDim2.fromScale(0.5, 0.5)
				toggleInner.Selectable = true
				toggleInner.Size = UDim2.new(1, -4, 1, -4)
				toggleInner.Image = "rbxassetid://2454009026"
				toggleInner.ImageColor3 = library.colors.bottomGradient
				local colored_toggleInner_ImageColor3 = {toggleInner, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_toggleInner_ImageColor3
				toggleButton.Name = "toggleButton"
				toggleButton.Parent = newToggle
				toggleButton.BackgroundColor3 = Color3.new(1, 1, 1)
				toggleButton.BackgroundTransparency = 1
				toggleButton.Size = UDim2.fromScale(1, 1)
				toggleButton.ZIndex = 5
				toggleButton.Font = Enum.Font.SourceSans
				toggleButton.Text = ""
				toggleButton.TextColor3 = Color3.new()
				toggleButton.TextSize = 14
				toggleButton.TextTransparency = 1
				toggleHeadline.Name = "toggleHeadline"
				toggleHeadline.Parent = newToggle
				toggleHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				toggleHeadline.BackgroundTransparency = 1
				toggleHeadline.Position = UDim2.fromScale(0.123, 0.165842161)
				toggleHeadline.Size = UDim2.fromOffset(170, 11)
				toggleHeadline.Font = Enum.Font.Code
				toggleHeadline.Text = toggleName or "???"
				toggleHeadline.TextColor3 = library.colors.elementText
				local colored_toggleHeadline_TextColor3 = {toggleHeadline, "TextColor3", "elementText", (lockedup and 0.5) or nil}
				colored[1 + #colored] = colored_toggleHeadline_TextColor3
				toggleHeadline.TextSize = 14
				toggleHeadline.TextXAlignment = Enum.TextXAlignment.Left
				local last_v = nil
				local function Set(t, newStatus)
					if nil == newStatus and t ~= nil then
						newStatus = t
					end
					last_v = library_flags[flagName]
					if options.Condition ~= nil then
						if type(options.Condition) == "function" then
							local v, e = pcall(options.Condition, newStatus, last_v)
							if e then
								if not v then
									warn(debug.traceback(string.format("Error in toggle %s's Condition function: %s", flagName, e), 2))
								end
							else
								return last_v
							end
						end
					end
					if newStatus ~= nil and type(newStatus) == "boolean" then
						library_flags[flagName] = newStatus
						if options.Location then
							options.Location[options.LocationFlag or flagName] = newStatus
						end
						if callback and (last_v ~= newStatus or options.AllowDuplicateCalls) then
							colored_toggleInner_BackgroundColor3[3] = (newStatus and "main") or "topGradient"
							colored_toggleInner_BackgroundColor3[4] = (newStatus and 1.5) or nil
							colored_toggleInner_ImageColor3[3] = (newStatus and "main") or "bottomGradient"
							colored_toggleInner_ImageColor3[4] = (newStatus and 2.5) or nil
							tweenService:Create(toggleInner, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
								BackgroundColor3 = (newStatus and darkenColor(library.colors.main, 1.5)) or library.colors.topGradient,
								ImageColor3 = (newStatus and darkenColor(library.colors.main, 2.5)) or library.colors.bottomGradient
							}):Play()
							task.spawn(callback, newStatus, last_v)
						end
					end
					return newStatus
				end
				options.Keybind = options.Keybind or options.Key or options.KeyBind
				local haskbflag, kbUpdate, kbData = nil, nil, nil
				if options.Keybind then
					local options = options.Keybind
					local htyp = typeof(options)
					if htyp == "EnumItem" then
						options = {
							Value = options
						}
					elseif htyp ~= "table" then
						options = {}
					end
					local presetKeybind, callback, kbpresscallback, kbflag = options.Value or options.Key, options.Callback, options.Pressed, options.Flag or (function()
						if flagName then
							return flagName .. "_ToggleKeybind"
						end
						library.unnamedkeybinds = 1 + (library.unnamedkeybinds or 0)
						return "Keybind" .. tostring(library.unnamedkeybinds)
					end)()
					if elements[kbflag] ~= nil or kbflag == flagName then
						warn(debug.traceback("Warning! Re-used flag '" .. kbflag .. "'", 3))
					end
					haskbflag = kbflag
					library.keyHandler = keyHandler
					local keyHandler = options.KeyNames or keyHandler
					local bindedKey = presetKeybind
					local justBinded = false
					local keyName = keyHandler.allowedKeys[bindedKey] or (bindedKey and (bindedKey.Name or tostring(bindedKey):gsub("Enum.KeyCode.", ""))) or "NONE"
					local newKeybind = newToggle
					keybindPositioner.Name = "keybindPositioner"
					keybindPositioner.Parent = newKeybind
					keybindPositioner.BackgroundColor3 = Color3.new(1, 1, 1)
					keybindPositioner.BackgroundTransparency = 1
					keybindPositioner.Position = UDim2.new(0.00448430516)
					keybindPositioner.Size = UDim2.fromOffset(214, 19)
					keybindPositioner.ZIndex = 1 + toggleButton.ZIndex
					keybindList.Name = "keybindList"
					keybindList.Parent = keybindPositioner
					keybindList.FillDirection = Enum.FillDirection.Horizontal
					keybindList.HorizontalAlignment = Enum.HorizontalAlignment.Right
					keybindList.SortOrder = Enum.SortOrder.LayoutOrder
					keybindList.VerticalAlignment = Enum.VerticalAlignment.Center
					keybindButton.Name = "keybindButton"
					keybindButton.Parent = keybindPositioner
					keybindButton.Active = false
					keybindButton.BackgroundColor3 = Color3.new(1, 1, 1)
					keybindButton.BackgroundTransparency = 1
					keybindButton.Position = UDim2.fromScale(0.598130822, 0.184210524)
					keybindButton.Selectable = false
					keybindButton.Size = UDim2.fromOffset(46, 12)
					keybindButton.Font = Enum.Font.Code
					keybindButton.Text = keyName or (presetKeybind and tostring(presetKeybind):gsub("Enum.KeyCode.", "")) or "[NONE]"
					keybindButton.TextColor3 = library.colors.otherElementText
					local colored_keybindButton_TextColor3 = {keybindButton, "TextColor3", "otherElementText"}
					colored[1 + #colored] = colored_keybindButton_TextColor3
					keybindButton.TextSize = 14
					keybindButton.TextXAlignment = Enum.TextXAlignment.Right
					keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
					local klast_v = bindedKey or presetKeybind
					local function newkey()
						if lockedup then
							return
						end
						local old_texts = keybindButton.Text
						colored_keybindButton_TextColor3[3] = "main"
						colored_keybindButton_TextColor3[4] = nil
						tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							TextColor3 = library.colors.main
						}):Play()
						if klast_v then
							keybindButton.Text = "(Was " .. (klast_v and tostring(klast_v):gsub("Enum.KeyCode.", "") or "[NONE]") .. ") [...]"
						else
							keybindButton.Text = "[...]"
						end
						local receivingKey = nil
						receivingKey = userInputService.InputBegan:Connect(function(key)
							if lockedup then
								return receivingKey:Disconnect()
							end
							klast_v = library_flags[kbflag]
							if not keyHandler.notAllowedKeys[key.KeyCode] then
								if key.KeyCode ~= Enum.KeyCode.Unknown then
									bindedKey = (key.KeyCode ~= Enum.KeyCode.Escape and key.KeyCode) or library_flags[kbflag]
									library_flags[kbflag] = bindedKey
									if options.Location then
										options.Location[options.LocationFlag or kbflag] = bindedKey
									end
									if bindedKey then
										keyName = keyHandler.allowedKeys[bindedKey] or (bindedKey and (bindedKey.Name or tostring(bindedKey):gsub("Enum.KeyCode.", ""))) or "NONE"
										keybindButton.Text = "[" .. (keyName or (bindedKey and bindedKey.Name) or "NONE") .. "]"
										keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
										justBinded = true
										colored_keybindButton_TextColor3[3] = "otherElementText"
										colored_keybindButton_TextColor3[4] = nil
										tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
											TextColor3 = library.colors.otherElementText
										}):Play()
										receivingKey:Disconnect()
									end
									if callback and klast_v ~= bindedKey then
										task.spawn(callback, bindedKey, klast_v)
									end
									return
								elseif key.KeyCode == Enum.KeyCode.Unknown and not keyHandler.notAllowedMouseInputs[key.UserInputType] then
									bindedKey = key.UserInputType
									library_flags[kbflag] = bindedKey
									if options.Location then
										options.Location[options.LocationFlag or kbflag] = bindedKey
									end
									keyName = keyHandler.allowedKeys[bindedKey]
									keybindButton.Text = "[" .. (keyName or (bindedKey and bindedKey.Name) or tostring(bindedKey.KeyCode):gsub("Enum.KeyCode.", "")) .. "]"
									keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
									justBinded = true
									colored_keybindButton_TextColor3[3] = "otherElementText"
									colored_keybindButton_TextColor3[4] = nil
									tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
										TextColor3 = library.colors.otherElementText
									}):Play()
									receivingKey:Disconnect()
									if callback and klast_v ~= bindedKey then
										task.spawn(callback, bindedKey, klast_v)
									end
									return
								end
							end
							if key.KeyCode == Enum.KeyCode.Backspace or Enum.KeyCode.Escape == key.KeyCode then
								old_texts, bindedKey = "[NONE]", nil
							end
							keybindButton.Text = old_texts
							colored_keybindButton_TextColor3[3] = "otherElementText"
							colored_keybindButton_TextColor3[4] = nil
							tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
								TextColor3 = library.colors.otherElementText
							}):Play()
							receivingKey:Disconnect()
							if callback and klast_v ~= bindedKey then
								task.spawn(callback, bindedKey, klast_v)
							end
						end)
						library.signals[1 + #library.signals] = receivingKey
					end
					library.signals[1 + #library.signals] = keybindButton.MouseButton1Click:Connect(newkey)
					if kbpresscallback and not justBinded then
						library.signals[1 + #library.signals] = userInputService.InputBegan:Connect(function(key, chatting)
							chatting = chatting or not not userInputService:GetFocusedTextBox()
							if not chatting and not justBinded then
								if not keyHandler.notAllowedKeys[key.KeyCode] and not keyHandler.notAllowedMouseInputs[key.UserInputType] then
									if bindedKey == key.UserInputType or not justBinded and bindedKey == key.KeyCode then
										if kbpresscallback then
											task.spawn(kbpresscallback, key, chatting)
										end
									end
									justBinded = false
								end
							end
						end)
					end
					options.Mode = (options.Mode and string.lower(tostring(options.Mode))) or "dynamic"
					local modes = {
						dynamic = 1,
						hold = 1,
						toggle = 1
					}
					library.signals[1 + #library.signals] = userInputService.InputBegan:Connect(function(input, chatting)
						if justBinded then
							wait(0.1)
							justBinded = false
							return
						elseif lockedup then
							return
						end
						chatting = chatting or userInputService:GetFocusedTextBox()
						if not chatting then
							local key = library_flags[kbflag]
							local mode = options.Mode
							if not modes[mode] then
								mode = "dynamic"
								options.Mode = mode
							end
							if key == input.KeyCode or key == input.UserInputType then
								if mode == "dynamic" or mode == "both" or mode == "hold" then
									if mode == "dynamic" and library_flags[flagName] then
										return Set(false)
									end
									Set(true)
									local now = os.clock()
									local waittil = nil
									if mode == "dynamic" then
										waittil = Instance.new("BindableEvent")
									end
									local xconnection = nil
									xconnection = userInputService.InputEnded:Connect(function(input, chatting)
										chatting = chatting or userInputService:GetFocusedTextBox()
										if not chatting and (key == input.KeyCode or key == input.UserInputType) then
											xconnection = (xconnection and xconnection:Disconnect() and nil) or nil
											if mode == "hold" or os.clock() - now > math.clamp(tonumber(options.DynamicTime) or 0.65, 0.05, 20) then
												Set(false)
											end
										end
									end)
									library.signals[1 + #library.signals] = xconnection
								else
									Set(not library_flags[flagName])
								end
							end
						end
					end)
					local function kbset(t, key)
						if nil == key and t ~= nil then
							key = t
						end
						if key == "nil" or key == "NONE" or key == "none" then
							key = nil
						end
						last_v = library_flags[kbflag]
						bindedKey = key
						library_flags[kbflag] = key
						if options.Location then
							options.Location[options.LocationFlag or kbflag] = key
						end
						keyName = (key == nil and "NONE") or keyHandler.allowedKeys[key]
						keybindButton.Text = "[" .. (keyName or key.Name or tostring(key):gsub("Enum.KeyCode.", "")) .. "]"
						keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
						justBinded = true
						colored_keybindButton_TextColor3[3] = "otherElementText"
						colored_keybindButton_TextColor3[4] = nil
						tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							TextColor3 = library.colors.otherElementText
						}):Play()
						if callback and (last_v ~= key or options.AllowDuplicateCalls) then
							task.spawn(callback, key, last_v)
						end
						return key
					end
					if presetKeybind ~= nil then
						kbset(presetKeybind)
					else
						library_flags[kbflag] = bindedKey
						if options.Location then
							options.Location[options.LocationFlag or kbflag] = bindedKey
						end
					end
					local default = library_flags[kbflag]
					local function UpdateKb()
						callback, kbpresscallback = options.Callback, options.Pressed
						local key = library_flags[kbflag]
						bindedKey = key
						keyName = keyHandler.allowedKeys[bindedKey] or (bindedKey and (bindedKey.Name or tostring(bindedKey):gsub("Enum.KeyCode.", ""))) or "NONE"
						keybindButton.Text = "[" .. (keyName or (key and key.Name) or tostring(key):gsub("Enum.KeyCode.", "")) .. "]"
						keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
						colored_keybindButton_TextColor3[3] = "otherElementText"
						colored_keybindButton_TextColor3[4] = (lockedup and 2.5) or nil
						tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							TextColor3 = (lockedup and darkenColor(library.colors.otherElementText, colored_keybindButton_TextColor3[4])) or library.colors.otherElementText
						}):Play()
						return key
					end
					kbUpdate = UpdateKb
					local objectdata = {
						Options = options,
						Name = kbflag,
						Flag = kbflag,
						Type = "Keybind",
						Default = default,
						Parent = sectionFunctions,
						Instance = keybindButton,
						Get = function()
							return library_flags[kbflag]
						end,
						Set = kbset,
						RawSet = function(t, key)
							if t ~= nil and key == nil then
								key = t
							end
							library_flags[kbflag] = key
							UpdateKb()
							return key
						end,
						Update = UpdateKb,
						Reset = function()
							return kbset(nil, default)
						end
					}
					kbData = objectdata
					tabFunctions.Flags[kbflag], sectionFunctions.Flags[kbflag], elements[kbflag] = objectdata, objectdata, objectdata
				end
				sectionFunctions:Update()
				library.signals[1 + #library.signals] = toggleButton.MouseButton1Click:Connect(function()
					if not library.colorpicker and not submenuOpen and not lockedup then
						local newval = not library_flags[flagName]
						if options.Condition ~= nil then
							if type(options.Condition) == "function" then
								local v, e = pcall(options.Condition, newval, not newval)
								if e then
									if not v then
										warn(debug.traceback(string.format("Error in toggle %s's Condition function: %s", flagName, e), 2))
									end
								else
									return last_v
								end
							end
						end
						library_flags[flagName] = newval
						if options.Location then
							options.Location[options.LocationFlag or flagName] = newval
						end
						colored_toggleInner_BackgroundColor3[3] = (newval and "main") or "topGradient"
						colored_toggleInner_BackgroundColor3[4] = (newval and 1.5) or nil
						colored_toggleInner_ImageColor3[3] = (newval and "main") or "bottomGradient"
						colored_toggleInner_ImageColor3[4] = (newval and 2.5) or nil
						tweenService:Create(toggleInner, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = (newval and darkenColor(library.colors.main, 1.5)) or library.colors.topGradient,
							ImageColor3 = (newval and darkenColor(library.colors.main, 2.5)) or library.colors.bottomGradient
						}):Play()
						if callback then
							task.spawn(callback, newval)
						end
					end
				end)
				library.signals[1 + #library.signals] = newToggle.MouseEnter:Connect(function()
					colored_toggle_BackgroundColor3[3] = "main"
					colored_toggle_BackgroundColor3[4] = 1.5
					colored_toggle_ImageColor3[3] = "main"
					colored_toggle_ImageColor3[4] = 2.5
					tweenService:Create(toggle, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
				end)
				library.signals[1 + #library.signals] = newToggle.MouseLeave:Connect(function()
					colored_toggle_BackgroundColor3[3] = "topGradient"
					colored_toggle_BackgroundColor3[4] = nil
					colored_toggle_ImageColor3[3] = "bottomGradient"
					colored_toggle_ImageColor3[4] = nil
					tweenService:Create(toggle, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = library.colors.topGradient,
						ImageColor3 = library.colors.bottomGradient
					}):Play()
				end)
				if library_flags[flagName] then
					colored_toggleInner_BackgroundColor3[3] = "main"
					colored_toggleInner_BackgroundColor3[4] = 1.5
					colored_toggleInner_ImageColor3[3] = "main"
					colored_toggleInner_ImageColor3[4] = 2.5
					tweenService:Create(toggleInner, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
				end
				local function Update()
					toggleName, callback = options.Name or toggleName, options.Callback
					local boolstatus = library_flags[flagName]
					colored_toggleInner_BackgroundColor3[3] = (boolstatus and "main") or "topGradient"
					colored_toggleInner_BackgroundColor3[4] = (boolstatus and 1.5) or nil
					colored_toggleInner_ImageColor3[3] = (boolstatus and "main") or "bottomGradient"
					colored_toggleInner_ImageColor3[4] = (boolstatus and 2.5) or nil
					if lockedup then
						colored_toggleInner_BackgroundColor3[4] = 1 + (colored_toggleInner_BackgroundColor3[4] or 1)
						colored_toggleInner_ImageColor3[4] = 1 + (colored_toggleInner_ImageColor3[4] or 1)
					end
					tweenService:Create(toggleInner, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = (boolstatus and darkenColor(library.colors.main, colored_toggleInner_BackgroundColor3[4])) or library.colors.topGradient,
						ImageColor3 = (boolstatus and darkenColor(library.colors.main, colored_toggleInner_ImageColor3[4])) or library.colors.bottomGradient
					}):Play()
					colored_toggleHeadline_TextColor3[4] = (lockedup and 2.5) or nil
					tweenService:Create(toggleHeadline, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						TextColor3 = (lockedup and darkenColor(library.colors.elementText, colored_toggleHeadline_TextColor3[4])) or library.colors.elementText
					}):Play()
					toggleHeadline.Text = toggleName or "???"
					return boolstatus
				end
				if alreadyEnabled ~= nil then
					Set(alreadyEnabled)
				else
					library_flags[flagName] = not not alreadyEnabled
					if options.Location then
						options.Location[options.LocationFlag or flagName] = not not alreadyEnabled
					end
				end
				local default = not not library_flags[flagName]
				Update()
				if kbUpdate then
					kbUpdate()
				end
				local objectdata = {
					Options = options,
					Type = "Toggle",
					Name = flagName,
					Flag = flagName,
					Default = default,
					Parent = sectionFunctions,
					Instance = toggleButton,
					Set = Set,
					RawSet = function(t, newStatus, condition)
						if t ~= nil and type(t) ~= "table" then
							newStatus, condition = t, newStatus
						end
						last_v = library_flags[flagName]
						if condition ~= false and condition ~= 0 then
							local overridecondition = condition and type(condition) == "function" and condition
							if overridecondition or options.Condition ~= nil then
								if type(overridecondition or options.Condition) == "function" then
									local v, e = pcall(overridecondition or options.Condition, newStatus, last_v)
									if e then
										if not v then
											warn(debug.traceback(string.format("Error in toggle (RawSet) %s's Condition function: %s", flagName, e), 2))
										end
									else
										return last_v
									end
								end
							end
						end
						library_flags[flagName] = newStatus
						if options.Location then
							options.Location[options.LocationFlag or flagName] = newStatus
						end
						Update()
						return newStatus
					end,
					KeybindData = kbData,
					Get = function()
						return library_flags[flagName]
					end,
					Update = Update,
					Reset = function()
						return Set(nil, default)
					end,
					SetLocked = function(t, state)
						if type(t) ~= "table" then
							state = t
						end
						local last_v = lockedup
						if state == nil then
							lockedup = not lockedup
						else
							lockedup = state
						end
						if lockedup ~= last_v then
							colored_toggleHeadline_TextColor3[4] = (lockedup and 2.5) or nil
							Update()
							if kbUpdate then
								kbUpdate()
							end
						end
						return lockedup
					end,
					Lock = function()
						if not lockedup then
							lockedup = true
							colored_toggleHeadline_TextColor3[4] = 2.5
							Update()
							if kbUpdate then
								kbUpdate()
							end
						end
						return lockedup
					end,
					Unlock = function()
						if lockedup then
							lockedup = false
							colored_toggleHeadline_TextColor3[4] = nil
							Update()
							if kbUpdate then
								kbUpdate()
							end
						end
						return lockedup
					end,
					SetCondition = function(t, condition)
						if type(t) ~= "table" and condition == nil then
							condition = t
						end
						options.Condition = condition
						return condition
					end
				}
				if kbData then
					kbData.ToggleData = objectdata
				end
				tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.CreateToggle = sectionFunctions.AddToggle
			sectionFunctions.NewToggle = sectionFunctions.AddToggle
			sectionFunctions.Toggle = sectionFunctions.AddToggle
			sectionFunctions.Tog = sectionFunctions.AddToggle
			function sectionFunctions:AddButton(...)
				local args = nil
				if ... and not select(2, ...) and type(...) == "table" and #... > 0 and type((...)[1]) == "table" and (...)[1].Name then
					args = ...
				else
					args = {...}
				end
				local buttons, offset = {}, 0
				local fram = nil
				for _, options in next, args do
					options = (options and options[1] and type(options[1]) == "string" and resolvevararg("Button", unpack(options))) or options
					local buttonName, callback = assert(options.Name, "Missing Name for new button."), options.Callback or (warn("AddButton missing callback. Name:", options.Name or "No Name", debug.traceback("")) and nil) or function()
					end
					local lockedup = options.Locked
					local realButton = Instance_new("TextButton")
					realButton.Name = "realButton"
					realButton.BackgroundColor3 = Color3.new(1, 1, 1)
					realButton.BackgroundTransparency = 1
					realButton.Size = UDim2.fromScale(1, 1)
					realButton.ZIndex = 5
					realButton.Font = Enum.Font.Code
					realButton.Text = (buttonName and tostring(buttonName)) or "???"
					realButton.TextColor3 = library.colors.elementText
					local colored_realButton_TextColor3 = {realButton, "TextColor3", "elementText"}
					colored[1 + #colored] = colored_realButton_TextColor3
					realButton.TextSize = 14
					local textsize = textToSize(realButton).X + 14
					if newSection.Parent.AbsoluteSize.X < offset + textsize + 8 then
						offset, fram = 0, nil
					end
					local newButton = fram or Instance_new("Frame")
					fram = newButton
					local button = Instance_new("ImageLabel")
					newButton.Name = removeSpaces((buttonName and buttonName:lower() or "???") .. "Holder")
					newButton.Parent = sectionHolder
					newButton.BackgroundColor3 = Color3.new(1, 1, 1)
					newButton.BackgroundTransparency = 1
					newButton.Size = UDim2.new(1, 0, 0, 24)
					button.Name = "button"
					button.Parent = newButton
					button.Active = true
					button.BackgroundColor3 = library.colors.topGradient
					local colored_button_BackgroundColor3 = {button, "BackgroundColor3", "topGradient"}
					colored[1 + #colored] = colored_button_BackgroundColor3
					button.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {button, "BorderColor3", "elementBorder"}
					button.Position = UDim2.new(0.031, offset, 0.166)
					button.Selectable = true
					button.Size = UDim2.fromOffset(28, 18)
					button.Image = "rbxassetid://2454009026"
					button.ImageColor3 = library.colors.bottomGradient
					local colored_button_ImageColor3 = {button, "ImageColor3", "bottomGradient"}
					colored[1 + #colored] = colored_button_ImageColor3
					local buttonInner = Instance_new("ImageLabel")
					buttonInner.Name = "buttonInner"
					buttonInner.Parent = button
					buttonInner.Active = true
					buttonInner.AnchorPoint = Vector2.new(0.5, 0.5)
					buttonInner.BackgroundColor3 = library.colors.topGradient
					local colored_buttonInner_BackgroundColor3 = {buttonInner, "BackgroundColor3", "topGradient"}
					colored[1 + #colored] = colored_buttonInner_BackgroundColor3
					buttonInner.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {buttonInner, "BorderColor3", "elementBorder"}
					buttonInner.Position = UDim2.fromScale(0.5, 0.5)
					buttonInner.Selectable = true
					buttonInner.Size = UDim2.new(1, -4, 1, -4)
					buttonInner.Image = "rbxassetid://2454009026"
					buttonInner.ImageColor3 = library.colors.bottomGradient
					local colored_buttonInner_ImageColor3 = {buttonInner, "ImageColor3", "bottomGradient"}
					colored[1 + #colored] = colored_buttonInner_ImageColor3
					button.Size = UDim2.fromOffset(textsize, 18)
					realButton.Parent = button
					offset = offset + textsize + 6
					sectionFunctions:Update()
					local presses = 0
					library.signals[1 + #library.signals] = realButton.MouseButton1Click:Connect(function()
						if lockedup then
							return
						end
						if options.Condition ~= nil and type(options.Condition) == "function" then
							local v, e = pcall(options.Condition, presses)
							if e then
								if not v then
									warn(debug.traceback(string.format("Error in button %s's Condition function: %s", buttonName, e), 2))
								end
							else
								return
							end
						end
						if not library.colorpicker and not submenuOpen then
							presses = 1 + presses
							task.spawn(callback, presses)
						end
					end)
					local imin = nil
					library.signals[1 + #library.signals] = button.MouseEnter:Connect(function()
						imin = 1
						colored_button_BackgroundColor3[3] = "main"
						colored_button_BackgroundColor3[4] = 1.5
						colored_button_ImageColor3[3] = "main"
						colored_button_ImageColor3[4] = 2.5
						tweenService:Create(button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = darkenColor(library.colors.main, 1.5),
							ImageColor3 = darkenColor(library.colors.main, 2.5)
						}):Play()
					end)
					library.signals[1 + #library.signals] = button.MouseLeave:Connect(function()
						imin = nil
						colored_button_BackgroundColor3[3] = "topGradient"
						colored_button_BackgroundColor3[4] = nil
						colored_button_ImageColor3[3] = "bottomGradient"
						colored_button_ImageColor3[4] = nil
						tweenService:Create(button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = library.colors.topGradient,
							ImageColor3 = library.colors.bottomGradient
						}):Play()
					end)
					local function Update()
						buttonName, callback = options.Name or buttonName, options.Callback or (warn(debug.traceback("AddButton missing callback. Name:" .. (options.Name or buttonName or "No Name"), 2)) and nil) or function()
						end
						colored_button_BackgroundColor3[3] = (imin and "main") or "topGradient"
						colored_button_BackgroundColor3[4] = (imin and 1.5) or nil
						colored_button_ImageColor3[3] = (imin and "main") or "bottomGradient"
						colored_button_ImageColor3[4] = (imin and 2.5) or nil
						colored_buttonInner_BackgroundColor3[4] = nil
						colored_buttonInner_ImageColor3[4] = nil
						colored_realButton_TextColor3[4] = nil
						if lockedup then
							colored_button_BackgroundColor3[4] = 1.25
							colored_button_ImageColor3[4] = 1.25
							colored_buttonInner_BackgroundColor3[4] = 1.25
							colored_buttonInner_ImageColor3[4] = 1.25
							colored_realButton_TextColor3[4] = 1.75
						end
						tweenService:Create(button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = (imin and darkenColor(library.colors.main, colored_button_BackgroundColor3[4])) or darkenColor(library.colors.topGradient, colored_button_BackgroundColor3[4]),
							ImageColor3 = (imin and darkenColor(library.colors.main, colored_button_ImageColor3[4])) or darkenColor(library.colors.bottomGradient, colored_button_ImageColor3[4])
						}):Play()
						tweenService:Create(buttonInner, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = darkenColor(library.colors.topGradient, colored_buttonInner_BackgroundColor3[4]),
							ImageColor3 = darkenColor(library.colors.bottomGradient, colored_buttonInner_ImageColor3[4])
						}):Play()
						tweenService:Create(realButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							TextColor3 = darkenColor(library.colors.elementText, colored_realButton_TextColor3[4])
						}):Play()
						realButton.Text = (buttonName and tostring(buttonName)) or "???"
						return presses
					end
					Update()
					local objectdata = {
						Options = options,
						Name = buttonName,
						Flag = buttonName,
						Type = "Button",
						Parent = sectionFunctions,
						Instance = realButton,
						Press = function(...)
							if lockedup then
								return presses
							end
							if options.Condition ~= nil and type(options.Condition) == "function" then
								local v, e = pcall(options.Condition, presses)
								if e then
									if not v then
										warn(debug.traceback(string.format("Error in button %s's Condition function: %s", buttonName, e), 2))
									end
								else
									return presses
								end
							end
							local args = {...}
							local a1 = args[1]
							if a1 and type(a1) == "table" then
								table.remove(args, 1)
							end
							presses = 1 + presses
							task.spawn(callback, presses, ...)
							return presses
						end,
						RawPress = function(...)
							local args = {...}
							local a1 = args[1]
							if a1 and type(a1) == "table" then
								table.remove(args, 1)
							end
							task.spawn(callback, presses, ...)
							return presses
						end,
						Get = function()
							return callback, presses
						end,
						SetLocked = function(t, state)
							if type(t) ~= "table" then
								state = t
							end
							local last_v = lockedup
							if state == nil then
								lockedup = not lockedup
							else
								lockedup = state
							end
							if lockedup ~= last_v then
								Update()
							end
							return lockedup
						end,
						Lock = function()
							if not lockedup then
								lockedup = true
								Update()
							end
							return lockedup
						end,
						Unlock = function()
							if lockedup then
								lockedup = false
								Update()
							end
							return lockedup
						end,
						SetCondition = function(t, condition)
							if type(t) ~= "table" and condition == nil then
								condition = t
							end
							options.Condition = condition
							return condition
						end,
						Update = Update,
						SetText = function(t, str)
							if type(t) ~= "table" and str == nil then
								str = t
							end
							buttonName = str
							options.Name = str
							realButton.Text = (buttonName and tostring(buttonName)) or "???"
							return str
						end,
						SetCallback = function(t, call)
							if type(t) ~= "table" and call == nil then
								call = t
							end
							options.Callback = call
							callback = call
							return call
						end
					}
					tabFunctions.Flags[buttonName], sectionFunctions.Flags[buttonName], elements[buttonName] = objectdata, objectdata, objectdata
					buttons[1 + #buttons] = objectdata
				end
				function buttons.PressAll()
					for _, v in next, buttons do
						v.Press()
					end
				end
				function buttons.UpdateAll()
					for _, v in next, buttons do
						v.Update()
					end
				end
				if #buttons == 1 then
					for k, v in next, buttons[1] do
						if buttons[k] == nil then
							buttons[k] = v
						end
					end
				end
				return buttons
			end
			sectionFunctions.CreateButton = sectionFunctions.AddButton
			sectionFunctions.NewButton = sectionFunctions.AddButton
			sectionFunctions.Button = sectionFunctions.AddButton
			function sectionFunctions:AddTextbox(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Textbox", options, ...)) or options
				local textboxName, presetValue, placeholder, callback, flagName = assert(options.Name, "Missing Name for new textbox."), options.Value, options.Placeholder, options.Callback, options.Flag or (function()
					library.unnamedtextboxes = 1 + (library.unnamedtextboxes or 0)
					return "Textbox" .. tostring(library.unnamedtextboxes)
				end)()
				if elements[flagName] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
				end
				local requiredtype = options.Type
				local newTextbox = Instance_new("Frame")
				local textbox = Instance_new("ImageLabel")
				local textboxInner = Instance_new("ImageLabel")
				local realTextbox = Instance_new("TextBox")
				local textboxHeadline = Instance_new("TextLabel")
				newTextbox.Name = removeSpaces((textboxName and textboxName:lower()) or "???") .. "Holder"
				newTextbox.Parent = sectionHolder
				newTextbox.BackgroundColor3 = Color3.new(1, 1, 1)
				newTextbox.BackgroundTransparency = 1
				newTextbox.Size = UDim2.new(1, 0, 0, 42)
				textbox.Name = "textbox"
				textbox.Parent = newTextbox
				textbox.Active = true
				textbox.BackgroundColor3 = library.colors.topGradient
				local colored_textbox_BackgroundColor3 = {textbox, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_textbox_BackgroundColor3
				textbox.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {textbox, "BorderColor3", "elementBorder"}
				textbox.Position = UDim2.fromScale(0.031, 0.48)
				textbox.Selectable = true
				textbox.Size = UDim2.fromOffset(206, 18)
				textbox.Image = "rbxassetid://2454009026"
				textbox.ImageColor3 = library.colors.bottomGradient
				local colored_textbox_ImageColor3 = {textbox, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_textbox_ImageColor3
				textboxInner.Name = "textboxInner"
				textboxInner.Parent = textbox
				textboxInner.Active = true
				textboxInner.AnchorPoint = Vector2.new(0.5, 0.5)
				textboxInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {textboxInner, "BackgroundColor3", "topGradient"}
				textboxInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {textboxInner, "BorderColor3", "elementBorder"}
				textboxInner.Position = UDim2.fromScale(0.5, 0.5)
				textboxInner.Selectable = true
				textboxInner.Size = UDim2.new(1, -4, 1, -4)
				textboxInner.Image = "rbxassetid://2454009026"
				textboxInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {textboxInner, "ImageColor3", "bottomGradient"}
				realTextbox.Name = "realTextbox"
				if options.Rich or options.RichText or options.RichTextBox then
					realTextbox.RichText = true
				end
				if options.MultiLine or options.Lines then
					realTextbox.MultiLine = true
				end
				if options.Font or options.TextFont then
					realTextbox.Font = options.Font
				end
				if options.TextScaled or options.Scaled then
					realTextbox.TextScaled = true
				end
				realTextbox.BackgroundColor3 = Color3.new(1, 1, 1)
				realTextbox.BackgroundTransparency = 1
				realTextbox.Position = UDim2.new(0.0295485705)
				realTextbox.Size = UDim2.fromScale(0.97, 1)
				realTextbox.ZIndex = 5
				realTextbox.Font = Enum.Font.Code
				realTextbox.LineHeight = 1.15
				realTextbox.Text = tostring(presetValue)
				realTextbox.TextColor3 = library.colors.otherElementText
				colored[1 + #colored] = {realTextbox, "TextColor3", "otherElementText"}
				realTextbox.TextSize = 14
				if options.ClearTextOnFocus or options.ClearText then
					realTextbox.ClearTextOnFocus = true
				else
					realTextbox.ClearTextOnFocus = false
				end
				realTextbox.PlaceholderText = (placeholder ~= nil and tostring(placeholder)) or (presetValue ~= nil and tostring(presetValue)) or ""
				realTextbox.TextXAlignment = Enum.TextXAlignment.Left
				if options.CustomProperties and type(options.CustomProperties) == "table" then
					for k, v in next, options.CustomProperties do
						local oof, e = pcall(function()
							realTextbox[k] = v
						end)
						if not oof and e then
							warn("Error setting Textbox", flagName, "|", e, debug.traceback(""))
						end
					end
				end
				realTextbox.Parent = textbox
				textboxHeadline.Name = "textboxHeadline"
				textboxHeadline.Parent = newTextbox
				textboxHeadline.Active = true
				textboxHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				textboxHeadline.BackgroundTransparency = 1
				textboxHeadline.Position = UDim2.new(0.031)
				textboxHeadline.Selectable = true
				textboxHeadline.Size = UDim2.fromOffset(206, 20)
				textboxHeadline.ZIndex = 5
				textboxHeadline.Font = Enum.Font.Code
				textboxHeadline.LineHeight = 1.15
				textboxHeadline.Text = (textboxName and tostring(textboxName)) or "???"
				textboxHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {textboxHeadline, "TextColor3", "elementText"}
				textboxHeadline.TextSize = 14
				textboxHeadline.TextXAlignment = Enum.TextXAlignment.Left
				sectionFunctions:Update()
				local last_v = presetValue
				local function resolvevalue(val)
					if options.PreFormat then
						local typ = type(options.PreFormat)
						if typ == "function" then
							local x, e = pcall(options.PreFormat, val)
							if not x and e then
								warn("Error in Pre-Format (Textbox " .. flagName .. "):", e)
							else
								val = e
							end
						end
					end
					if requiredtype == "number" then
						if not options.Hex and not options.Binary and not options.Base then
							val = tonumber(val) or tonumber(val:gsub("%D", ""), 10) or 0
						else
							val = tonumber(val, (options.Hex and 16) or (options.Binary and 2) or options.Base or 10) or 0
						end
						if options.Max or options.Min then
							val = math.clamp(val, options.Min or -math.huge, options.Max or math.huge)
						end
						local decimalprecision = tonumber(options.Decimals or options.Precision or options.Precise)
						if decimalprecision then
							val = tonumber(string.format("%0." .. tostring(decimalprecision) .. "f", val))
						end
					end
					if options.PostFormat then
						local typ = type(options.PostFormat)
						if typ == "function" then
							local x, e = pcall(options.PostFormat, val)
							if not x and e then
								warn("Error in Post-Format (Textbox " .. flagName .. "):", e)
							else
								val = e
							end
						end
					end
					return (val and tonumber(val)) or val
				end
				library.signals[1 + #library.signals] = realTextbox.FocusLost:Connect(function()
					last_v = library_flags[flagName]
					local val = resolvevalue(realTextbox.Text)
					library_flags[flagName] = val
					if options.Location then
						options.Location[options.LocationFlag or flagName] = val
					end
					if callback and last_v ~= val then
						task.spawn(callback, tostring(val), last_v, realTextbox)
					end
				end)
				library.signals[1 + #library.signals] = newTextbox.MouseEnter:Connect(function()
					colored_textbox_BackgroundColor3[3] = "main"
					colored_textbox_BackgroundColor3[4] = 1.5
					colored_textbox_ImageColor3[3] = "main"
					colored_textbox_ImageColor3[4] = 2.5
					tweenService:Create(textbox, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
				end)
				library.signals[1 + #library.signals] = newTextbox.MouseLeave:Connect(function()
					colored_textbox_BackgroundColor3[3] = "topGradient"
					colored_textbox_BackgroundColor3[4] = nil
					colored_textbox_ImageColor3[3] = "bottomGradient"
					colored_textbox_ImageColor3[4] = nil
					tweenService:Create(textbox, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = library.colors.topGradient,
						ImageColor3 = library.colors.bottomGradient
					}):Play()
				end)
				local function set(t, str)
					if nil == str and t ~= nil then
						str = t
					end
					last_v = library_flags[flagName]
					library_flags[flagName] = str
					if options.Location then
						options.Location[options.LocationFlag or flagName] = str
					end
					local sstr = (str ~= nil and tostring(str)) or "Empty Text"
					if realTextbox.Text ~= sstr then
						realTextbox.Text = sstr
					end
					if callback and (last_v ~= str or options.AllowDuplicateCalls) then
						task.spawn(callback, str, last_v, realTextbox)
					end
					return str
				end
				if presetValue ~= nil then
					set(presetValue)
				else
					library_flags[flagName] = presetValue
					if options.Location then
						options.Location[options.LocationFlag or flagName] = presetValue
					end
				end
				local default = library_flags[flagName]
				local function update()
					textboxName, placeholder, callback = options.Name or textboxName, options.Placeholder or placeholder, options.Callback
					local str = library_flags[flagName]
					str = (str ~= nil and tostring(str)) or "Empty Text"
					if realTextbox.Text ~= str then
						realTextbox.Text = str
					end
					textboxHeadline.Text = (textboxName and tostring(textboxName)) or "???"
					return str
				end
				local objectdata = {
					Options = options,
					Name = flagName,
					Flag = flagName,
					Type = "Textbox",
					Default = default,
					Parent = sectionFunctions,
					Instance = realTextbox,
					Get = function()
						return library_flags[flagName]
					end,
					Set = set,
					Update = update,
					RawSet = function(t, str)
						if t ~= nil and str == nil then
							str = t
						end
						last_v = library_flags[flagName]
						library_flags[flagName] = str
						if options.Location then
							options.Location[options.LocationFlag or flagName] = str
						end
						update()
						return str
					end,
					Reset = function()
						return set(nil, default)
					end
				}
				tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.AddTextBox = sectionFunctions.AddTextbox
			sectionFunctions.NewTextBox = sectionFunctions.AddTextbox
			sectionFunctions.CreateTextBox = sectionFunctions.AddTextbox
			sectionFunctions.TextBox = sectionFunctions.AddTextbox
			sectionFunctions.NewTextbox = sectionFunctions.AddTextbox
			sectionFunctions.CreateTextbox = sectionFunctions.AddTextbox
			sectionFunctions.Textbox = sectionFunctions.AddTextbox
			sectionFunctions.Box = sectionFunctions.AddTextbox
			function sectionFunctions:AddKeybind(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Keybind", options, ...)) or options
				local keybindName, presetKeybind, callback, presscallback, flag = assert(options.Name, "Missing Name for new keybind."), options.Value, options.Callback, options.Pressed, options.Flag or (function()
					library.unnamedkeybinds = 1 + (library.unnamedkeybinds or 0)
					return "Keybind" .. tostring(library.unnamedkeybinds)
				end)()
				if elements[flag] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flag .. "'", 3))
				end
				library.keyHandler = keyHandler
				local keyHandler = options.KeyNames or keyHandler
				local newKeybind = Instance_new("Frame")
				local keybindHeadline = Instance_new("TextLabel")
				local keybindPositioner = Instance_new("Frame")
				local keybindList = Instance_new("UIListLayout")
				local keybindButton = Instance_new("TextButton")
				local bindedKey = presetKeybind
				local justBinded = false
				local keyName = (presetKeybind and tostring(presetKeybind):gsub("Enum.KeyCode.", "") or "")
				newKeybind.Name = "newKeybind"
				newKeybind.Parent = sectionHolder
				newKeybind.BackgroundColor3 = Color3.new(1, 1, 1)
				newKeybind.BackgroundTransparency = 1
				newKeybind.Size = UDim2.new(1, 0, 0, 19)
				keybindHeadline.Name = "keybindHeadline"
				keybindHeadline.Parent = newKeybind
				keybindHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				keybindHeadline.BackgroundTransparency = 1
				keybindHeadline.Position = UDim2.fromScale(0.031, 0.165842161)
				keybindHeadline.Size = UDim2.fromOffset(215, 12)
				keybindHeadline.Font = Enum.Font.Code
				keybindHeadline.Text = (keybindName and tostring(keybindName)) or "???"
				keybindHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {keybindHeadline, "TextColor3", "elementText"}
				keybindHeadline.TextSize = 14
				keybindHeadline.TextXAlignment = Enum.TextXAlignment.Left
				keybindPositioner.Name = "keybindPositioner"
				keybindPositioner.Parent = newKeybind
				keybindPositioner.BackgroundColor3 = Color3.new(1, 1, 1)
				keybindPositioner.BackgroundTransparency = 1
				keybindPositioner.Position = UDim2.new(0.00448430516)
				keybindPositioner.Size = UDim2.fromOffset(214, 19)
				keybindList.Name = "keybindList"
				keybindList.Parent = keybindPositioner
				keybindList.FillDirection = Enum.FillDirection.Horizontal
				keybindList.HorizontalAlignment = Enum.HorizontalAlignment.Right
				keybindList.SortOrder = Enum.SortOrder.LayoutOrder
				keybindList.VerticalAlignment = Enum.VerticalAlignment.Center
				keybindButton.Name = "keybindButton"
				keybindButton.Parent = keybindPositioner
				keybindButton.Active = false
				keybindButton.BackgroundColor3 = Color3.new(1, 1, 1)
				keybindButton.BackgroundTransparency = 1
				keybindButton.Position = UDim2.fromScale(0.598130822, 0.184210524)
				keybindButton.Selectable = false
				keybindButton.Size = UDim2.fromOffset(46, 12)
				keybindButton.Font = Enum.Font.Code
				keybindButton.Text = (presetKeybind and tostring(presetKeybind):gsub("Enum.KeyCode.", "") or "[NONE]")
				keybindButton.TextColor3 = library.colors.otherElementText
				local colored_keybindButton_TextColor3 = {keybindButton, "TextColor3", "otherElementText"}
				colored[1 + #colored] = colored_keybindButton_TextColor3
				keybindButton.TextSize = 14
				keybindButton.TextXAlignment = Enum.TextXAlignment.Right
				keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
				sectionFunctions:Update()
				local last_v = bindedKey or presetKeybind
				local function newkey()
					local old_texts = keybindButton.Text
					colored_keybindButton_TextColor3[3] = "main"
					colored_keybindButton_TextColor3[4] = nil
					tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						TextColor3 = library.colors.main
					}):Play()
					if last_v then
						keybindButton.Text = "(Was " .. (last_v and tostring(last_v):gsub("Enum.KeyCode.", "") or "[NONE]") .. ") [...]"
					else
						keybindButton.Text = "[...]"
					end
					local receivingKey = nil
					receivingKey = userInputService.InputBegan:Connect(function(key)
						last_v = library_flags[flag]
						if not keyHandler.notAllowedKeys[key.KeyCode] then
							if key.KeyCode ~= Enum.KeyCode.Unknown then
								bindedKey = (key.KeyCode ~= Enum.KeyCode.Escape and key.KeyCode) or library_flags[flag]
								library_flags[flag] = bindedKey
								if options.Location then
									options.Location[options.LocationFlag or flag] = bindedKey
								end
								if bindedKey then
									keyName = keyHandler.allowedKeys[bindedKey]
									keybindButton.Text = "[" .. (keyName or bindedKey.Name or tostring(key.KeyCode):gsub("Enum.KeyCode.", "")) .. "]"
									keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
									justBinded = true
									colored_keybindButton_TextColor3[3] = "otherElementText"
									colored_keybindButton_TextColor3[4] = nil
									tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
										TextColor3 = library.colors.otherElementText
									}):Play()
									receivingKey:Disconnect()
								end
								if callback and last_v ~= bindedKey then
									task.spawn(callback, bindedKey, last_v)
								end
								return
							elseif key.KeyCode == Enum.KeyCode.Unknown and not keyHandler.notAllowedMouseInputs[key.UserInputType] then
								bindedKey = key.UserInputType
								library_flags[flag] = bindedKey
								if options.Location then
									options.Location[options.LocationFlag or flag] = bindedKey
								end
								keyName = keyHandler.allowedKeys[bindedKey]
								keybindButton.Text = "[" .. (keyName or bindedKey.Name or tostring(key.KeyCode):gsub("Enum.KeyCode.", "")) .. "]"
								keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
								justBinded = true
								colored_keybindButton_TextColor3[3] = "otherElementText"
								colored_keybindButton_TextColor3[4] = nil
								tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									TextColor3 = library.colors.otherElementText
								}):Play()
								receivingKey:Disconnect()
								if callback and last_v ~= bindedKey then
									task.spawn(callback, bindedKey, last_v)
								end
								return
							end
						end
						if key.KeyCode == Enum.KeyCode.Backspace or Enum.KeyCode.Escape == key.KeyCode then
							old_texts, bindedKey = "[NONE]", nil
						end
						keybindButton.Text = old_texts
						colored_keybindButton_TextColor3[3] = "otherElementText"
						colored_keybindButton_TextColor3[4] = nil
						tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							TextColor3 = library.colors.otherElementText
						}):Play()
						receivingKey:Disconnect()
						if callback and last_v ~= bindedKey then
							task.spawn(callback, bindedKey, last_v)
						end
					end)
					library.signals[1 + #library.signals] = receivingKey
				end
				library.signals[1 + #library.signals] = keybindButton.MouseButton1Click:Connect(newkey)
				library.signals[1 + #library.signals] = newKeybind.InputEnded:Connect(function(input)
					if not library.colorpicker and not submenuOpen and input.UserInputType == Enum.UserInputType.MouseButton1 then
						newkey()
					end
				end)
				if presscallback then
					library.signals[1 + #library.signals] = userInputService.InputBegan:Connect(function(key, chatting)
						if not keyHandler.notAllowedKeys[key.KeyCode] and not keyHandler.notAllowedMouseInputs[key.UserInputType] then
							if not justBinded and bindedKey == key.UserInputType or not justBinded and bindedKey == key.KeyCode and not chatting then
								if presscallback then
									task.spawn(presscallback, key, chatting)
								end
							end
							if justBinded then
								justBinded = false
							end
						end
					end)
				end
				local function set(t, key)
					if nil == key and t ~= nil then
						key = t
					end
					if key == "nil" or key == "NONE" or key == "none" then
						key = nil
					end
					last_v = library_flags[flag]
					bindedKey = key
					library_flags[flag] = key
					if options.Location then
						options.Location[options.LocationFlag or flag] = key
					end
					keyName = (key == nil and "NONE") or keyHandler.allowedKeys[key]
					keybindButton.Text = "[" .. (keyName or key.Name or tostring(key):gsub("Enum.KeyCode.", "")) .. "]"
					keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
					justBinded = true
					colored_keybindButton_TextColor3[3] = "otherElementText"
					colored_keybindButton_TextColor3[4] = nil
					tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						TextColor3 = library.colors.otherElementText
					}):Play()
					if callback and (last_v ~= key or options.AllowDuplicateCalls) then
						task.spawn(callback, key, last_v)
					end
					return key
				end
				if presetKeybind ~= nil then
					set(presetKeybind)
				else
					library_flags[flag] = bindedKey
					if options.Location then
						options.Location[options.LocationFlag or flag] = bindedKey
					end
				end
				local default = library_flags[flag]
				local function update()
					keybindName, callback, presscallback = options.Name or keybindName, options.Callback, options.Pressed
					local key = library_flags[flag]
					keyName = (key == nil and "NONE") or keyHandler.allowedKeys[key]
					keybindButton.Text = "[" .. (keyName or key.Name or tostring(key):gsub("Enum.KeyCode.", "")) .. "]"
					keybindButton.Size = UDim2.fromOffset(textToSize(keybindButton).X + 4, 12)
					colored_keybindButton_TextColor3[3] = "otherElementText"
					colored_keybindButton_TextColor3[4] = nil
					tweenService:Create(keybindButton, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						TextColor3 = library.colors.otherElementText
					}):Play()
					keybindHeadline.Text = (keybindName and tostring(keybindName)) or "???"
					return key
				end
				local objectdata = {
					Options = options,
					Name = flag,
					Flag = flag,
					Type = "Keybind",
					Default = default,
					Parent = sectionFunctions,
					Instance = keybindButton,
					Get = function()
						return library_flags[flag]
					end,
					Set = set,
					RawSet = function(t, key)
						if nil == key and t ~= nil then
							key = t
						end
						if key == "nil" or key == "NONE" or key == "none" then
							key = nil
						end
						last_v = library_flags[flag]
						bindedKey = key
						library_flags[flag] = key
						if options.Location then
							options.Location[options.LocationFlag or flag] = key
						end
						justBinded = true
						return key
					end,
					Update = update,
					Reset = function()
						return set(nil, default)
					end
				}
				tabFunctions.Flags[flag], sectionFunctions.Flags[flag], elements[flag] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.NewKeybind = sectionFunctions.AddKeybind
			sectionFunctions.CreateKeybind = sectionFunctions.AddKeybind
			sectionFunctions.Keybind = sectionFunctions.AddKeybind
			sectionFunctions.Bind = sectionFunctions.AddKeybind
			function sectionFunctions:AddLabel(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Label", options, ...)) or options
				local labelName, flag = options.Text or options.Value or options.Name, options.Flag or (function()
					library.unnamedlabels = 1 + (library.unnamedlabels or 0)
					return "Label" .. tostring(library.unnamedlabels)
				end)()
				if elements[flag] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flag .. "'", 3))
				end
				local newLabel = Instance_new("Frame")
				local labelHeadline = Instance_new("TextLabel")
				local labelPositioner = Instance_new("Frame")
				local labelButton = Instance_new("TextButton")
				newLabel.Name = "newLabel"
				newLabel.Parent = sectionHolder
				newLabel.BackgroundColor3 = Color3.new(1, 1, 1)
				newLabel.BackgroundTransparency = 1
				newLabel.Size = UDim2.new(1, 0, 0, 19)
				labelHeadline.Name = "labelHeadline"
				labelHeadline.Parent = newLabel
				labelHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				labelHeadline.BackgroundTransparency = 1
				labelHeadline.Position = UDim2.fromScale(0.031, 0.165842161)
				labelHeadline.Size = UDim2.fromOffset(215, 12)
				labelHeadline.Font = Enum.Font.Code
				labelHeadline.Text = (labelName and tostring(labelName)) or "Empty Text"
				labelHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {labelHeadline, "TextColor3", "elementText"}
				labelHeadline.TextSize = 14
				labelHeadline.TextXAlignment = Enum.TextXAlignment.Left
				labelPositioner.Name = "labelPositioner"
				labelPositioner.Parent = newLabel
				labelPositioner.BackgroundColor3 = Color3.new(1, 1, 1)
				labelPositioner.BackgroundTransparency = 1
				labelPositioner.Position = UDim2.new(0.00448430516)
				labelPositioner.Size = UDim2.fromOffset(214, 19)
				sectionFunctions:Update()
				local function set(t, str)
					if nil == str and t ~= nil then
						str = t
					end
					labelHeadline.Text = (nil ~= str and tostring(str)) or "Empty Text"
					return str
				end
				local default = labelHeadline.Text
				local objectdata = {
					Options = options,
					Name = flag,
					Flag = flag,
					Type = "Label",
					Default = default,
					Parent = sectionFunctions,
					Instance = labelHeadline,
					Get = function()
						return labelHeadline.Text, labelHeadline
					end,
					Set = set,
					RawSet = set,
					Update = function()
						return labelHeadline.Text
					end,
					Reset = function()
						return set(nil, default)
					end
				}
				tabFunctions.Flags[flag], sectionFunctions.Flags[flag], elements[flag] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.NewLabel = sectionFunctions.AddLabel
			sectionFunctions.CreateLabel = sectionFunctions.AddLabel
			sectionFunctions.Label = sectionFunctions.AddLabel
			sectionFunctions.Text = sectionFunctions.AddLabel
			function sectionFunctions:AddSlider(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Slider", options, ...)) or options
				local sliderName, maxValue, minValue, presetValue, callback, flagName = assert(options.Name, "Missing Name for new slider."), assert(options.Max, "Missing Max for new slider."), assert(options.Min, "Missing Min for new slider."), options.Value, options.Callback, options.Flag or (function()
					library.unnamedsliders = 1 + (library.unnamedsliders or 0)
					return "Slider" .. tostring(library.unnamedsliders)
				end)()
				if elements[flagName] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
				end
				local decimalprecision = tonumber(options.Decimals or options.Precision or options.Precise)
				if not decimalprecision and options.Max - options.Min <= 1 then
					decimalprecision = 1
				end
				if decimalprecision then
					decimalprecision = math.clamp(decimalprecision, 0, 99)
					if decimalprecision <= 0 then
						decimalprecision = nil
					end
					decimalprecision = tostring(decimalprecision)
				end
				local formattyp = options.Format and type(options.Format)
				local function resolvedisplay(val, was)
					local str = nil
					if decimalprecision then
						str = string.format("%0." .. decimalprecision .. "f", val)
					end
					str = str or tostring(val)
					if formattyp == "string" then
						return string.format(options.Format, val)
					elseif formattyp == "function" then
						local oof, g = pcall(options.Format, val, was)
						if not oof or not g then
							warn("Your format function for", sliderName, "Slider:", flagName, "has returned nothing. It should return a string to display.", debug.traceback(""))
							return "Format Function Errored"
						end
						return tostring(g)
					end
					return (sliderName or "???") .. ": " .. str
				end
				local usetextbox = options.Textbox or options.InputBox or options.CustomInput
				local newSlider = Instance_new("Frame")
				local slider = Instance_new("ImageLabel")
				local sliderInner = Instance_new("ImageLabel")
				local sliderColored = Instance_new("ImageLabel")
				local sliderHeadline = Instance_new("TextLabel")
				local startingValue = presetValue or minValue
				local sliderDragging = false
				newSlider.Name = "newSlider"
				newSlider.Parent = sectionHolder
				newSlider.BackgroundColor3 = Color3.new(1, 1, 1)
				newSlider.BackgroundTransparency = 1
				newSlider.Size = UDim2.new(1, 0, 0, 42)
				slider.Name = "slider"
				slider.Parent = newSlider
				slider.Active = true
				slider.BackgroundColor3 = library.colors.topGradient
				local colored_slider_BackgroundColor3 = {slider, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_slider_BackgroundColor3
				slider.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {slider, "BorderColor3", "elementBorder"}
				slider.Position = UDim2.fromScale(0.031, 0.48)
				slider.Selectable = true
				slider.Size = (usetextbox and UDim2.fromOffset(156, 18)) or UDim2.fromOffset(206, 18)
				slider.Image = "rbxassetid://2454009026"
				slider.ImageColor3 = library.colors.bottomGradient
				local colored_slider_ImageColor3 = {slider, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_slider_ImageColor3
				sliderInner.Name = "sliderInner"
				sliderInner.Parent = slider
				sliderInner.Active = true
				sliderInner.AnchorPoint = Vector2.new(0.5, 0.5)
				sliderInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {sliderInner, "BackgroundColor3", "topGradient"}
				sliderInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {sliderInner, "BorderColor3", "elementBorder"}
				sliderInner.Position = UDim2.fromScale(0.5, 0.5)
				sliderInner.Selectable = true
				sliderInner.Size = UDim2.new(1, -4, 1, -4)
				sliderInner.Image = "rbxassetid://2454009026"
				sliderInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {sliderInner, "ImageColor3", "bottomGradient"}
				sliderColored.Name = "sliderColored"
				sliderColored.Parent = sliderInner
				sliderColored.Active = true
				sliderColored.BackgroundColor3 = darkenColor(library.colors.main, 1.5)
				colored[1 + #colored] = {sliderColored, "BackgroundColor3", "main", 1.5}
				sliderColored.BorderSizePixel = 0
				sliderColored.Selectable = true
				sliderColored.Size = UDim2.fromScale(((startingValue or minValue) - minValue) / (maxValue - minValue), 1)
				sliderColored.Image = "rbxassetid://2454009026"
				sliderColored.ImageColor3 = darkenColor(library.colors.main, 2.5)
				colored[1 + #colored] = {sliderColored, "ImageColor3", "main", 2.5}
				sliderHeadline.Name = "sliderHeadline"
				sliderHeadline.Parent = newSlider
				sliderHeadline.Active = true
				sliderHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				sliderHeadline.BackgroundTransparency = 1
				sliderHeadline.Position = UDim2.new(0.031)
				sliderHeadline.Selectable = true
				sliderHeadline.Size = UDim2.fromOffset(206, 20)
				sliderHeadline.ZIndex = 5
				sliderHeadline.Font = Enum.Font.Code
				sliderHeadline.LineHeight = 1.15
				sliderHeadline.Text = resolvedisplay(startingValue)
				sliderHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {sliderHeadline, "TextColor3", "elementText"}
				sliderHeadline.TextSize = 14
				sliderHeadline.TextXAlignment = Enum.TextXAlignment.Left
				local realTextbox = nil
				local function Set(t, newValue)
					if nil == newValue and t ~= nil then
						newValue = t
					end
					minValue, maxValue = options.Min, options.Max
					if newValue and (options.IllegalInput or ((not minValue or newValue >= minValue) and (not maxValue or newValue <= maxValue))) then
						local last_val = library_flags[flagName]
						library_flags[flagName] = newValue
						if options.Location then
							options.Location[options.LocationFlag or flagName] = newValue
						end
						do
							local newValue = (options.IllegalInput and math.clamp(newValue, minValue or -math.huge, maxValue or math.huge)) or newValue
							tweenService:Create(sliderColored, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
								Size = UDim2.fromScale(((newValue or minValue) - minValue) / (maxValue - minValue), 1)
							}):Play()
						end
						sliderHeadline.Text = resolvedisplay(newValue, last_val)
						if usetextbox and realTextbox then
							realTextbox.Text = tostring(newValue)
						end
						if callback and (last_val ~= newValue or options.AllowDuplicateCalls) then
							task.spawn(callback, newValue, last_val)
						end
					end
					return newValue
				end
				if presetValue ~= nil then
					Set(presetValue)
				else
					library_flags[flagName] = startingValue
					if options.Location then
						options.Location[options.LocationFlag or flagName] = startingValue
					end
				end
				if usetextbox then
					if type(usetextbox) ~= "table" then
						usetextbox = options
					end
					local textbox = Instance_new("ImageLabel")
					local textboxInner = Instance_new("ImageLabel")
					realTextbox = Instance_new("TextBox")
					textbox.Name = "textbox"
					textbox.Parent = newSlider
					textbox.Active = true
					textbox.BackgroundColor3 = library.colors.topGradient
					local colored_textbox_BackgroundColor3 = {textbox, "BackgroundColor3", "topGradient"}
					colored[1 + #colored] = colored_textbox_BackgroundColor3
					textbox.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {textbox, "BorderColor3", "elementBorder"}
					textbox.Position = UDim2.new(1, -54, 0.48)
					textbox.Selectable = true
					textbox.Size = UDim2.fromOffset(43, 18)
					textbox.Image = "rbxassetid://2454009026"
					textbox.ImageColor3 = library.colors.bottomGradient
					local colored_textbox_ImageColor3 = {textbox, "ImageColor3", "bottomGradient"}
					colored[1 + #colored] = colored_textbox_ImageColor3
					textboxInner.Name = "textboxInner"
					textboxInner.Parent = textbox
					textboxInner.Active = true
					textboxInner.AnchorPoint = Vector2.new(0.5, 0.5)
					textboxInner.BackgroundColor3 = library.colors.topGradient
					colored[1 + #colored] = {textboxInner, "BackgroundColor3", "topGradient"}
					textboxInner.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {textboxInner, "BorderColor3", "elementBorder"}
					textboxInner.Position = UDim2.fromScale(0.5, 0.5)
					textboxInner.Selectable = true
					textboxInner.Size = UDim2.new(1, -4, 1, -4)
					textboxInner.Image = "rbxassetid://2454009026"
					textboxInner.ImageColor3 = library.colors.bottomGradient
					colored[1 + #colored] = {textboxInner, "ImageColor3", "bottomGradient"}
					realTextbox.Name = "realTextbox"
					realTextbox.Parent = textbox
					realTextbox.BackgroundColor3 = Color3.new(1, 1, 1)
					realTextbox.BackgroundTransparency = 1
					realTextbox.Position = UDim2.new(0.0295485705)
					realTextbox.Size = UDim2.fromScale(0.97, 1)
					realTextbox.ZIndex = 5
					realTextbox.ClearTextOnFocus = false
					realTextbox.Font = Enum.Font.Code
					realTextbox.LineHeight = 1.15
					realTextbox.Text = tostring(presetValue)
					realTextbox.TextColor3 = library.colors.otherElementText
					colored[1 + #colored] = {realTextbox, "TextColor3", "otherElementText"}
					realTextbox.TextSize = 14
					realTextbox.PlaceholderText = (presetValue ~= nil and tostring(presetValue)) or ""
					library.signals[1 + #library.signals] = realTextbox.FocusLost:Connect(function()
						local val = realTextbox.Text
						if usetextbox.PreFormat then
							local typ = type(usetextbox.PreFormat)
							if typ == "function" then
								local x, e = pcall(usetextbox.PreFormat, val)
								if not x and e then
									warn("Error in Pre-Format (Textbox " .. flagName .. "):", e)
								else
									val = e
								end
							end
						end
						val = (not usetextbox.Hex and not usetextbox.Binary and not usetextbox.Base and (tonumber(val) or tonumber(val:gsub("%D", ""), 10) or 0)) or tonumber(val, (usetextbox.Hex and 16) or (usetextbox.Binary and 2) or usetextbox.Base or 10) or 0
						if not options.IllegalInput and (options.Max or options.Min) then
							val = math.clamp(val, options.Min or -math.huge, options.Max or math.huge)
						end
						local decimalprecision = tonumber(options.Decimals or options.Precision or options.Precise)
						if decimalprecision then
							val = tonumber(string.format("%0." .. tostring(decimalprecision) .. "f", val))
						end
						if usetextbox.PostFormat then
							local typ = type(usetextbox.PostFormat)
							if typ == "function" then
								local x, e = pcall(usetextbox.PostFormat, val)
								if not x and e then
									warn("Error in Post-Format (Textbox " .. flagName .. "):", e)
								else
									val = e
								end
							end
						end
						Set((val and tonumber(val)) or presetValue or 0)
					end)
					library.signals[1 + #library.signals] = textbox.MouseEnter:Connect(function()
						colored_textbox_BackgroundColor3[3] = "main"
						colored_textbox_BackgroundColor3[4] = 1.5
						colored_textbox_ImageColor3[3] = "main"
						colored_textbox_ImageColor3[4] = 2.5
						tweenService:Create(textbox, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = darkenColor(library.colors.main, 1.5),
							ImageColor3 = darkenColor(library.colors.main, 2.5)
						}):Play()
					end)
					library.signals[1 + #library.signals] = textbox.MouseLeave:Connect(function()
						colored_textbox_BackgroundColor3[3] = "topGradient"
						colored_textbox_BackgroundColor3[4] = nil
						colored_textbox_ImageColor3[3] = "bottomGradient"
						colored_textbox_ImageColor3[4] = nil
						tweenService:Create(textbox, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = library.colors.topGradient,
							ImageColor3 = library.colors.bottomGradient
						}):Play()
					end)
				end
				sectionFunctions:Update()
				library.signals[1 + #library.signals] = slider.MouseEnter:Connect(function()
					colored_slider_BackgroundColor3[3] = "main"
					colored_slider_BackgroundColor3[4] = 1.5
					colored_slider_ImageColor3[3] = "main"
					colored_slider_ImageColor3[4] = 2.5
					tweenService:Create(slider, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
				end)
				library.signals[1 + #library.signals] = slider.MouseLeave:Connect(function()
					colored_slider_BackgroundColor3[3] = "topGradient"
					colored_slider_BackgroundColor3[4] = nil
					colored_slider_ImageColor3[3] = "bottomGradient"
					colored_slider_ImageColor3[4] = nil
					tweenService:Create(slider, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = library.colors.topGradient,
						ImageColor3 = library.colors.bottomGradient
					}):Play()
				end)
				local function sliding(input, sb, sc)
					local last_val = library_flags[flagName]
					local pos = UDim2.fromScale(math.clamp((input.Position.X - sb.AbsolutePosition.X) / sb.AbsoluteSize.X, 0, 1), 1)
					tweenService:Create(sc, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
						Size = pos
					}):Play()
					local sliderValue = nil
					if decimalprecision then
						sliderValue = tonumber(string.format("%0." .. decimalprecision .. "f", ((pos.X.Scale * maxValue) / maxValue) * (maxValue - minValue) + minValue))
					end
					sliderValue = sliderValue or tonumber(string.format("%0.2f", (floor(((pos.X.Scale * maxValue) / maxValue) * (maxValue - minValue) + minValue))))
					library_flags[flagName] = sliderValue
					if options.Location then
						options.Location[options.LocationFlag or flagName] = sliderValue
					end
					sliderHeadline.Text = resolvedisplay(sliderValue, last_val)
					if usetextbox and realTextbox then
						realTextbox.Text = tostring(sliderValue)
					end
					if callback and last_val ~= sliderValue then
						task.spawn(callback, sliderValue, last_val)
					end
					last_val = sliderValue
				end
				library.signals[1 + #library.signals] = newSlider.InputBegan:Connect(function(input)
					if not library.colorpicker and input.UserInputType == Enum.UserInputType.MouseButton1 then
						sliderDragging = true
						isDraggingSomething = true
					end
				end)
				library.signals[1 + #library.signals] = newSlider.InputEnded:Connect(function(input)
					if not library.colorpicker and input.UserInputType == Enum.UserInputType.MouseButton1 then
						sliderDragging = false
						isDraggingSomething = false
					end
				end)
				library.signals[1 + #library.signals] = newSlider.InputBegan:Connect(function(input)
					if not library.colorpicker and not isDraggingSomething and input.UserInputType == Enum.UserInputType.MouseButton1 then
						isDraggingSomething = true
						sliding(input, sliderInner, sliderColored)
					end
				end)
				library.signals[1 + #library.signals] = userInputService.InputChanged:Connect(function(input)
					if not library.colorpicker and sliderDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
						sliding(input, sliderInner, sliderColored)
					end
				end)
				local default = library_flags[flagName]
				local function Update(t, last_val)
					if last_val == nil and t ~= nil and type(t) ~= "table" then
						last_val = t
					end
					sliderName, maxValue, minValue, callback = options.Name or sliderName, options.Max or maxValue, options.Min or minValue, options.Callback
					local newValue = library_flags[flagName]
					do
						local newValue = math.clamp(newValue, options.Min or -math.huge, options.Max or math.huge)
						tweenService:Create(sliderColored, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
							Size = UDim2.fromScale(((newValue or minValue) - minValue) / (maxValue - minValue), 1)
						}):Play()
					end
					sliderHeadline.Text = resolvedisplay(newValue, last_val)
					if usetextbox and realTextbox then
						realTextbox.Text = tostring(newValue)
					end
					return newValue
				end
				local objectdata = {
					Options = options,
					Name = flagName,
					Flag = flagName,
					Type = "Slider",
					Default = default,
					Parent = sectionFunctions,
					Instance = sliderHeadline,
					Set = Set,
					Get = function()
						return library_flags[flagName]
					end,
					SetConstraints = function(t, min, max)
						if t and type(t) ~= "table" then
							min, max = t, min
						end
						if min then
							options.Min = min
						end
						if max then
							options.Max = max
						end
						Update()
					end,
					SetMin = function(t, min)
						if min == nil and t ~= nil then
							min = t
						end
						if min and min ~= options.Min then
							options.Min = min
							Update()
						end
					end,
					SetMax = function(t, max)
						if max == nil and t ~= nil then
							max = t
						end
						if max and max ~= options.Max then
							options.Max = max
							Update()
						end
					end,
					Update = Update,
					RawSet = function(t, newValue)
						if nil == newValue and t ~= nil then
							newValue = t
						end
						local last_val = library_flags[flagName]
						library_flags[flagName] = newValue
						if options.Location then
							options.Location[options.LocationFlag or flagName] = newValue
						end
						Update(nil, last_val)
					end,
					Reset = function()
						return Set(nil, default)
					end
				}
				tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.NewSlider = sectionFunctions.AddSlider
			sectionFunctions.CreateSlider = sectionFunctions.AddSlider
			sectionFunctions.NumberConstraint = sectionFunctions.AddSlider
			sectionFunctions.Slider = sectionFunctions.AddSlider
			sectionFunctions.Slide = sectionFunctions.AddSlider
			function sectionFunctions:AddSearchBox(options, ...)
				options = (options and type(options) == "string" and resolvevararg("SearchBox", options, ...)) or options
				local dropdownName, listt, val, callback, flagName = assert(options.Name, "Missing Name for new searchbox."), assert(options.List, "Missing List for new searchbox."), options.Value, options.Callback, options.Flag or (function()
					library.unnamedsearchbox = 1 + (library.unnamedsearchbox or 0)
					return "SearchBox" .. tostring(library.unnamedsearchbox)
				end)()
				if elements[flagName] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
				end
				local newDropdown = Instance_new("Frame")
				local dropdown = Instance_new("ImageLabel")
				local dropdownInner = Instance_new("ImageLabel")
				local dropdownToggle = Instance_new("ImageButton")
				local dropdownSelection = Instance_new("TextBox")
				local dropdownHeadline = Instance_new("TextLabel")
				local dropdownHolderFrame = Instance_new("ImageLabel")
				local dropdownHolderInner = Instance_new("ImageLabel")
				local realDropdownHolder = Instance_new("ScrollingFrame")
				local realDropdownHolderList = Instance_new("UIListLayout")
				local dropdownEnabled = false
				local resolvelist = getresolver(listt, options.Filter)
				local list = resolvelist()
				local multiselect = options.MultiSelect or options.Multi or options.Multiple
				local passed_multiselect = multiselect and type(multiselect)
				local blankstring = not multiselect and (options.BlankValue or options.NoValueString or options.Nothing)
				local selectedOption = val or list[1] or blankstring
				local addcallback = options.ItemAdded or options.AddedCallback
				local delcallback = options.ItemRemoved or options.RemovedCallback
				local clrcallback = options.ItemsCleared or options.ClearedCallback
				local modcallback = options.ItemChanged or options.ChangedCallback
				if blankstring and val == nil then
					val = blankstring
				end
				if val ~= nil then
					selectedOption = val
				end
				if multiselect and (not selectedOption or type(selectedOption) ~= "table") then
					selectedOption = {}
				end
				local selectedObjects = {}
				local optionCount = 0
				newDropdown.Name = "newDropdown"
				newDropdown.Parent = sectionHolder
				newDropdown.BackgroundColor3 = Color3.new(1, 1, 1)
				newDropdown.BackgroundTransparency = 1
				newDropdown.Size = UDim2.new(1, 0, 0, 42)
				dropdown.Name = "dropdown"
				dropdown.Parent = newDropdown
				dropdown.Active = true
				dropdown.BackgroundColor3 = library.colors.topGradient
				local colored_dropdown_BackgroundColor3 = {dropdown, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_dropdown_BackgroundColor3
				dropdown.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdown, "BorderColor3", "elementBorder"}
				dropdown.Position = UDim2.fromScale(0.027, 0.45)
				dropdown.Selectable = true
				dropdown.Size = UDim2.fromOffset(206, 18)
				dropdown.Image = "rbxassetid://2454009026"
				dropdown.ImageColor3 = library.colors.bottomGradient
				local colored_dropdown_ImageColor3 = {dropdown, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_dropdown_ImageColor3
				dropdownInner.Name = "dropdownInner"
				dropdownInner.Parent = dropdown
				dropdownInner.Active = true
				dropdownInner.AnchorPoint = Vector2.new(0.5, 0.5)
				dropdownInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {dropdownInner, "BackgroundColor3", "topGradient"}
				dropdownInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdownInner, "BorderColor3", "elementBorder"}
				dropdownInner.Position = UDim2.fromScale(0.5, 0.5)
				dropdownInner.Selectable = true
				dropdownInner.Size = UDim2.new(1, -4, 1, -4)
				dropdownInner.Image = "rbxassetid://2454009026"
				dropdownInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {dropdownInner, "ImageColor3", "bottomGradient"}
				dropdownToggle.Name = "dropdownToggle"
				dropdownToggle.Parent = dropdown
				dropdownToggle.BackgroundColor3 = Color3.new(1, 1, 1)
				dropdownToggle.BackgroundTransparency = 1
				dropdownToggle.Position = UDim2.fromScale(0.9, 0.17)
				dropdownToggle.Rotation = 90
				dropdownToggle.Size = UDim2.fromOffset(12, 12)
				dropdownToggle.ZIndex = 6
				dropdownToggle.Image = "rbxassetid://71659683"
				dropdownToggle.ImageColor3 = Color3.fromRGB(171, 171, 171)
				dropdownSelection.Name = "dropdownSelection"
				dropdownSelection.Parent = dropdown
				dropdownSelection.BackgroundColor3 = Color3.new(1, 1, 1)
				dropdownSelection.BackgroundTransparency = 1
				dropdownSelection.Position = UDim2.new(0.0295485705)
				dropdownSelection.Size = UDim2.fromScale(0.85, 1)
				dropdownSelection.ZIndex = 5
				dropdownSelection.Font = Enum.Font.Code
				dropdownSelection.LineHeight = 1.15
				dropdownSelection.Text = (passed_multiselect == "string" and multiselect) or (multiselect and (blankstring or "Select Item(s)")) or (selectedOption and tostring(selectedOption)) or blankstring or "No Blank String"
				dropdownSelection.TextColor3 = library.colors.otherElementText
				colored[1 + #colored] = {dropdownSelection, "TextColor3", "otherElementText"}
				dropdownSelection.TextSize = 14
				dropdownSelection.TextXAlignment = Enum.TextXAlignment.Left
				dropdownSelection.ClearTextOnFocus = true
				dropdownHeadline.Name = "dropdownHeadline"
				dropdownHeadline.Parent = newDropdown
				dropdownHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				dropdownHeadline.BackgroundTransparency = 1
				dropdownHeadline.Position = UDim2.fromScale(0.034, 0.03)
				dropdownHeadline.Size = UDim2.fromOffset(167, 11)
				dropdownHeadline.Font = Enum.Font.Code
				dropdownHeadline.Text = (dropdownName and tostring(dropdownName)) or "???"
				dropdownHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {dropdownHeadline, "TextColor3", "elementText"}
				dropdownHeadline.TextSize = 14
				dropdownHeadline.TextXAlignment = Enum.TextXAlignment.Left
				dropdownHolderFrame.Name = "dropdownHolderFrame"
				dropdownHolderFrame.Parent = newDropdown
				dropdownHolderFrame.Active = true
				dropdownHolderFrame.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {dropdownHolderFrame, "BackgroundColor3", "topGradient"}
				dropdownHolderFrame.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdownHolderFrame, "BorderColor3", "elementBorder"}
				dropdownHolderFrame.Position = UDim2.fromScale(0.025, 1.012)
				dropdownHolderFrame.Selectable = true
				dropdownHolderFrame.Size = UDim2.fromOffset(206, 22)
				dropdownHolderFrame.Visible = false
				dropdownHolderFrame.Image = "rbxassetid://2454009026"
				dropdownHolderFrame.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {dropdownHolderFrame, "ImageColor3", "bottomGradient"}
				dropdownHolderInner.Name = "dropdownHolderInner"
				dropdownHolderInner.Parent = dropdownHolderFrame
				dropdownHolderInner.Active = true
				dropdownHolderInner.AnchorPoint = Vector2.new(0.5, 0.5)
				dropdownHolderInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {dropdownHolderInner, "BackgroundColor3", "topGradient"}
				dropdownHolderInner.BorderColor3 = library.colors.elementBorder
				dropdownHolderInner.Position = UDim2.fromScale(0.5, 0.5)
				dropdownHolderInner.Selectable = true
				dropdownHolderInner.Size = UDim2.new(1, -4, 1, -4)
				dropdownHolderInner.Image = "rbxassetid://2454009026"
				dropdownHolderInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {dropdownHolderInner, "ImageColor3", "bottomGradient"}
				realDropdownHolder.Name = "realDropdownHolder"
				realDropdownHolder.Parent = dropdownHolderInner
				realDropdownHolder.BackgroundColor3 = Color3.new(1, 1, 1)
				realDropdownHolder.BackgroundTransparency = 1
				realDropdownHolder.Selectable = false
				realDropdownHolder.Size = UDim2.fromScale(1, 1)
				realDropdownHolder.CanvasSize = UDim2.new()
				realDropdownHolder.ScrollBarThickness = 5
				realDropdownHolder.ScrollingDirection = Enum.ScrollingDirection.Y
				realDropdownHolder.AutomaticCanvasSize = Enum.AutomaticSize.Y
				realDropdownHolder.ScrollBarImageTransparency = 0.5
				realDropdownHolder.ScrollBarImageColor3 = library.colors.section
				colored[1 + #colored] = {realDropdownHolder, "ScrollBarImageColor3", "section"}
				realDropdownHolderList.Name = "realDropdownHolderList"
				realDropdownHolderList.Parent = realDropdownHolder
				realDropdownHolderList.HorizontalAlignment = Enum.HorizontalAlignment.Center
				realDropdownHolderList.SortOrder = Enum.SortOrder.LayoutOrder
				sectionFunctions:Update()
				local restorezindex = {}
				library.signals[1 + #library.signals] = newDropdown.MouseEnter:Connect(function()
					colored_dropdown_BackgroundColor3[3] = "main"
					colored_dropdown_BackgroundColor3[4] = 1.5
					colored_dropdown_ImageColor3[3] = "main"
					colored_dropdown_ImageColor3[4] = 2.5
					tweenService:Create(dropdown, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
				end)
				library.signals[1 + #library.signals] = newDropdown.MouseLeave:Connect(function()
					if not dropdownEnabled then
						colored_dropdown_BackgroundColor3[3] = "topGradient"
						colored_dropdown_BackgroundColor3[4] = nil
						colored_dropdown_ImageColor3[3] = "bottomGradient"
						colored_dropdown_ImageColor3[4] = nil
						tweenService:Create(dropdown, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = library.colors.topGradient,
							ImageColor3 = library.colors.bottomGradient
						}):Play()
					end
				end)
				local function UpdateDropdownHolder()
					if optionCount >= 6 then
						realDropdownHolder.CanvasSize = UDim2:fromOffset(realDropdownHolderList.AbsoluteContentSize.Y + 2)
					elseif optionCount <= 5 then
						dropdownHolderFrame.Size = UDim2.fromOffset(206, realDropdownHolderList.AbsoluteContentSize.Y + 4)
					end
				end
				local function AddOptions(optionsTable, filter)
					if options.Sort then
						local didstuff, dosort = nil, options.Sort
						if type(dosort) == "function" then
							local g, h = pcall(table.sort, optionsTable, dosort)
							if g then
								didstuff = true
							elseif h then
								warn("Error sorting list:", h, debug.traceback(""))
							end
						end
						if not didstuff then
							table.sort(optionsTable, library.defaultSort)
						end
					end
					if blankstring and (optionsTable[1] ~= blankstring or table.find(optionsTable, blankstring, 2)) then
						local exists = table.find(optionsTable, blankstring)
						if exists then
							for _ = 1, 35 do
								table.remove(optionsTable, exists)
								exists = table.find(optionsTable, blankstring)
								if not exists then
									break
								end
							end
						end
						table.insert(optionsTable, 1, blankstring)
					end
					optionCount = 0
					realDropdownHolderList.Parent = nil
					realDropdownHolder:ClearAllChildren()
					realDropdownHolderList.Parent = realDropdownHolder
					for _, v in next, optionsTable do
						if not filter or tostring(v):lower():find(dropdownSelection.Text:lower(), 1, not options.RegEx) then
							optionCount = optionCount + 1
							UpdateDropdownHolder()
							local newOption = Instance_new("ImageLabel")
							local optionButton = Instance_new("TextButton")
							if selectedOption == v then
								selectedObjects[1] = newOption
								selectedObjects[2] = optionButton
							end
							newOption.Name = "Frame"
							newOption.Parent = realDropdownHolder
							local togged = (not multiselect and selectedOption == v) or (multiselect and table.find(selectedOption, v))
							newOption.BackgroundColor3 = (togged and library.colors.selectedOption) or library.colors.topGradient
							newOption.BorderSizePixel = 0
							newOption.Size = UDim2.fromOffset(202, 18)
							newOption.Image = "rbxassetid://2454009026"
							newOption.ImageColor3 = (togged and library.colors.unselectedOption) or library.colors.bottomGradient
							local stringed = tostring(v)
							optionButton.Name = stringed
							optionButton.Parent = newOption
							optionButton.Active = true
							optionButton.AnchorPoint = Vector2.new(0.5, 0.5)
							optionButton.BackgroundColor3 = Color3.new(1, 1, 1)
							optionButton.BackgroundTransparency = 1
							optionButton.Position = UDim2.fromScale(0.5, 0.5)
							optionButton.Selectable = true
							optionButton.Size = UDim2.new(1, -10, 1)
							optionButton.ZIndex = 5
							optionButton.Font = Enum.Font.Code
							optionButton.Text = (togged and (" " .. stringed)) or stringed
							optionButton.TextColor3 = (togged and library.colors.main) or library.colors.otherElementText
							optionButton.TextSize = 14
							optionButton.TextXAlignment = Enum.TextXAlignment.Left
							library.signals[1 + #library.signals] = optionButton[(multiselect and "MouseButton1Click") or "MouseButton1Down"]:Connect(function()
								if not library.colorpicker then
									dropdownSelection.Text = (passed_multiselect == "string" and multiselect) or blankstring or "Select Item(s)"
									restorezindex[newSection] = restorezindex[newSection] or newSection.ZIndex
									restorezindex[newDropdown] = restorezindex[newDropdown] or newDropdown.ZIndex
									restorezindex[sectionHolder] = restorezindex[sectionHolder] or sectionHolder.ZIndex
									if multiselect then
										local cloned = {unpack(selectedOption)}
										local togged = table.find(selectedOption, v)
										if togged then
											table.remove(selectedOption, togged)
										else
											selectedOption[1 + #selectedOption] = v
										end
										togged = table.find(selectedOption, v)
										optionButton.Text = (togged and (" " .. stringed)) or stringed
										newOption.BackgroundColor3 = (togged and library.colors.selectedOption) or library.colors.topGradient
										newOption.ImageColor3 = (togged and library.colors.unselectedOption) or library.colors.bottomGradient
										optionButton.TextColor3 = (togged and library.colors.main) or library.colors.otherElementText
										if callback then
											task.spawn(callback, selectedOption, cloned)
										end
										if togged then
											if addcallback then
												task.spawn(addcallback, v, selectedOption)
											end
										elseif delcallback then
											task.spawn(delcallback, v, selectedOption)
										end
										if modcallback then
											task.spawn(modcallback, v, togged, selectedOption)
										end
										if #selectedOption == 0 and clrcallback then
											task.spawn(clrcallback, selectedOption, cloned)
										end
										return
									else
										dropdownSelection.Text = stringed
										if selectedOption ~= v then
											local last_v = library_flags[flagName]
											selectedObjects[1].BackgroundColor3 = library.colors.topGradient
											selectedObjects[1].ImageColor3 = library.colors.bottomGradient
											selectedObjects[2].Text = selectedObjects[2].Name
											selectedObjects[2].TextColor3 = library.colors.otherElementText
											selectedOption = v
											selectedObjects[1] = newOption
											selectedObjects[2] = optionButton
											newOption.BackgroundColor3 = library.colors.selectedOption
											newOption.ImageColor3 = library.colors.unselectedOption
											optionButton.TextColor3 = library.colors.main
											dropdownHolderFrame.Visible = false
											dropdownToggle.Rotation = 90
											dropdownEnabled = false
											newDropdown.ZIndex = 1
											colored_dropdown_BackgroundColor3[3] = "topGradient"
											colored_dropdown_BackgroundColor3[4] = nil
											colored_dropdown_ImageColor3[3] = "bottomGradient"
											colored_dropdown_ImageColor3[4] = nil
											tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
												BackgroundColor3 = library.colors.topGradient,
												ImageColor3 = library.colors.bottomGradient
											}):Play()
											library_flags[flagName] = selectedOption
											if options.Location then
												options.Location[options.LocationFlag or flagName] = selectedOption
											end
											dropdownSelection.Text = tostring(selectedOption)
											if submenuOpen then
												submenuOpen = nil
											end
											if callback then
												task.spawn(callback, selectedOption, last_v)
											end
										else
											submenuOpen = nil
											dropdownToggle.Rotation = 90
											colored_dropdown_BackgroundColor3[3] = "topGradient"
											colored_dropdown_BackgroundColor3[4] = nil
											colored_dropdown_ImageColor3[3] = "bottomGradient"
											colored_dropdown_ImageColor3[4] = nil
											tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
												BackgroundColor3 = library.colors.topGradient,
												ImageColor3 = library.colors.bottomGradient
											}):Play()
											dropdownHolderFrame.Visible = false
										end
									end
									for ins, z in next, restorezindex do
										ins.ZIndex = z
									end
								end
							end)
							library.signals[1 + #library.signals] = optionButton.MouseEnter:Connect(function()
								tweenService:Create(newOption, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									BackgroundColor3 = library.colors.hoveredOptionTop,
									ImageColor3 = library.colors.hoveredOptionBottom
								}):Play()
							end)
							library.signals[1 + #library.signals] = optionButton.MouseLeave:Connect(function()
								local togged = (not multiselect and selectedOption == v) or (multiselect and table.find(selectedOption, v))
								tweenService:Create(newOption, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									BackgroundColor3 = (togged and library.colors.selectedOption) or library.colors.topGradient,
									ImageColor3 = (togged and library.colors.unselectedOption) or library.colors.bottomGradient
								}):Play()
							end)
							UpdateDropdownHolder()
						end
					end
				end
				local precisionscrolling = nil
				local showing = false
				local function display(dropdownEnabled, f)
					if submenuOpen == dropdown or submenuOpen == nil then
						if dropdownEnabled then
							list = resolvelist()
							AddOptions(list, f)
							submenuOpen = dropdown
							dropdownToggle.Rotation = 270
							restorezindex[newSection] = restorezindex[newSection] or newSection.ZIndex
							restorezindex[newDropdown] = restorezindex[newDropdown] or newDropdown.ZIndex
							restorezindex[sectionHolder] = restorezindex[sectionHolder] or sectionHolder.ZIndex
							newSection.ZIndex = 50 + newSection.ZIndex
							newDropdown.ZIndex = 2
							sectionHolder.ZIndex = 2
							colored_dropdown_BackgroundColor3[3] = "main"
							colored_dropdown_BackgroundColor3[4] = 1.5
							colored_dropdown_ImageColor3[3] = "main"
							colored_dropdown_ImageColor3[4] = 2.5
							tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
								BackgroundColor3 = darkenColor(library.colors.main, 1.5),
								ImageColor3 = darkenColor(library.colors.main, 2.5)
							}):Play()
							dropdownHolderFrame.Visible = true
							if not options.DisablePrecisionScrolling then
								local scrollrate = tonumber(options.ScrollButtonRate or options.ScrollRate) or 5
								local upkey = options.ScrollUpButton or library.scrollupbutton or shared.scrollupbutton or Enum.KeyCode.Up
								local downkey = options.ScrollDownButton or library.scrolldownbutton or shared.scrolldownbutton or Enum.KeyCode.Down
								precisionscrolling = (precisionscrolling and precisionscrolling:Disconnect() and nil) or userInputService.InputBegan:Connect(function(input)
									if input.UserInputType == Enum.UserInputType.Keyboard then
										local code = input.KeyCode
										local isup = code == upkey
										local isdown = code == downkey
										if isup or isdown then
											local txt = userInputService:GetFocusedTextBox()
											if not txt or txt == dropdownSelection then
												while wait_check() and userInputService:IsKeyDown(code) do
													realDropdownHolder.CanvasPosition = Vector2:new(math.clamp(realDropdownHolder.CanvasPosition.Y + ((isup and -scrollrate) or scrollrate), 0, realDropdownHolder.AbsoluteCanvasSize.Y))
												end
											end
										end
									end
								end)
								library.signals[1 + #library.signals] = precisionscrolling
							end
						else
							submenuOpen = nil
							dropdownToggle.Rotation = 90
							colored_dropdown_BackgroundColor3[3] = "topGradient"
							colored_dropdown_BackgroundColor3[4] = nil
							colored_dropdown_ImageColor3[3] = "bottomGradient"
							colored_dropdown_ImageColor3[4] = nil
							tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
								BackgroundColor3 = library.colors.topGradient,
								ImageColor3 = library.colors.bottomGradient
							}):Play()
							dropdownHolderFrame.Visible = false
							for ins, z in next, restorezindex do
								ins.ZIndex = z
							end
							precisionscrolling = (precisionscrolling and precisionscrolling:Disconnect() and nil) or nil
						end
					end
					showing = dropdownEnabled
				end
				local Set = (multiselect and function(t, dat)
					if nil == dat and t ~= nil then
						dat = t
					end
					local lastv = library_flags[flagName]
					if not lastv or selectedOption ~= lastv then
						if lastv and type(lastv) == "table" then
							selectedOption = library_flags[flagName]
						else
							library_flags[flagName] = selectedOption
						end
						warn("Attempting to use new table for", flagName, " Please use :Set(), because setting it through flags table may cause errors", debug.traceback(""))
						lastv = library_flags[flagName]
					end
					local cloned = {unpack(selectedOption)}
					if not dat then
						if #selectedOption ~= 0 then
							table.clear(selectedOption)
							if callback then
								task.spawn(callback, selectedOption, cloned)
							end
						end
						return selectedOption
					elseif type(dat) ~= "table" then
						warn("Expected table for argument #1 on Set for MultiSelect searchbox. Got", dat, debug.traceback(""))
						return selectedOption
					end
					for k = table.pack(unpack(dat)).n, 1, -1 do
						if dat[k] == nil then
							table.remove(dat, k)
						end
					end
					local proceed = #cloned ~= #dat
					table.clear(selectedOption)
					for k, v in next, dat do
						selectedOption[k] = v
						if not proceed and cloned[k] ~= v then
							proceed = 1
						end
					end
					dropdownSelection.Text = (passed_multiselect == "string" and multiselect) or blankstring or "Select Item(s)"
					if proceed and callback then
						task.spawn(callback, selectedOption, cloned)
					end
					return selectedOption
				end) or function(t, str)
					if nil == str and t then
						str = t
					end
					local last_v = library_flags[flagName]
					selectedOption = str
					library_flags[flagName] = str
					if options.Location then
						options.Location[options.LocationFlag or flagName] = str
					end
					local sstr = (selectedOption and tostring(selectedOption)) or blankstring or "No Blank String"
					if dropdownSelection.Text ~= sstr then
						dropdownSelection.Text = sstr
					end
					if callback and (last_v ~= str or options.AllowDuplicateCalls) then
						task.spawn(callback, str, last_v)
					end
					return str
				end
				if val ~= nil then
					Set(val)
				else
					library_flags[flagName] = selectedOption
					if options.Location then
						options.Location[options.LocationFlag or flagName] = selectedOption
					end
				end
				library.signals[1 + #library.signals] = dropdownToggle.MouseButton1Click:Connect(function()
					showing = not showing
					display(showing)
				end)
				library.signals[1 + #library.signals] = dropdownSelection.Focused:Connect(function()
					showing = true
					display(true)
				end)
				library.signals[1 + #library.signals] = dropdownSelection:GetPropertyChangedSignal("Text"):Connect(function()
					if showing then
						display(true, #dropdownSelection.Text > 0)
					end
				end)
				if not multiselect then
					library.signals[1 + #library.signals] = dropdownSelection.FocusLost:Connect(function(b)
						if showing then
							wait()
						end
						showing = false
						display(false)
						if b then
							Set(dropdownSelection.Text)
						end
					end)
				end
				AddOptions(list)
				local default = library_flags[flagName]
				local function update()
					dropdownName, callback = options.Name or dropdownName, options.Callback
					local sstr = (passed_multiselect == "string" and multiselect) or (not multiselect and library_flags[flagName] and tostring(library_flags[flagName])) or (not multiselect and selectedOption and tostring(selectedOption)) or blankstring or "Nothing"
					if dropdownSelection.Text ~= sstr then
						dropdownSelection.Text = sstr
					end
					dropdownHeadline.Text = (dropdownName and tostring(dropdownName)) or "???"
					return sstr
				end
				local function validate(fallbackValue)
					if list and table.find(list, library_flags[flagName]) then
						update()
						return true
					end
					if fallbackValue ~= nil then
						if fallbackValue == "__DEFAULT" then
							fallbackValue = default
						end
					else
						fallbackValue = list[1]
					end
					if multiselect and type(fallbackValue) ~= "table" then
						fallbackValue = {fallbackValue}
					end
					return Set(fallbackValue)
				end
				local objectdata = {
					Options = options,
					Name = flagName,
					Flag = flagName,
					Type = "SearchBox",
					Default = default,
					Parent = sectionFunctions,
					Instance = dropdownSelection,
					Validate = validate,
					Set = Set,
					RawSet = ((multiselect and function(t, dat)
						if nil == dat and t ~= nil then
							dat = t
						end
						local lastv = library_flags[flagName]
						if not lastv or selectedOption ~= lastv then
							if lastv and type(lastv) == "table" then
								selectedOption = library_flags[flagName]
							else
								library_flags[flagName] = selectedOption
							end
							warn("Attempting to use new table for", flagName, " Please use :Set(), as setting through flags table may cause errors", debug.traceback(""))
							lastv = library_flags[flagName]
						end
						local cloned = {unpack(selectedOption)}
						if not dat then
							if #selectedOption ~= 0 then
								table.clear(selectedOption)
								if callback then
									task.spawn(callback, selectedOption, cloned)
								end
							end
							return selectedOption
						elseif type(dat) ~= "table" then
							warn("Expected table for argument #1 on Set for MultiSelect searchbox. Got", dat, debug.traceback(""))
							return selectedOption
						end
						for k = table.pack(unpack(dat)).n, 1, -1 do
							if dat[k] == nil then
								table.remove(dat, k)
							end
						end
						local proceed = #cloned ~= #dat
						table.clear(selectedOption)
						for k, v in next, dat do
							selectedOption[k] = v
							if not proceed and cloned[k] ~= v then
								proceed = 1
							end
						end
						update()
						return selectedOption
					end) or function(t, str)
						if nil == str and t then
							str = t
						end
						selectedOption = str
						library_flags[flagName] = str
						if options.Location then
							options.Location[options.LocationFlag or flagName] = str
						end
						update()
						return str
					end),
					Get = function()
						return library_flags[flagName]
					end,
					Update = update,
					Reset = function()
						return Set(nil, default)
					end
				}
				function objectdata.UpdateList(t, listt, updateValues)
					if (nil == listt and t ~= nil) or (type(t) == "table" and type(listt) ~= "table") then
						listt, updateValues = t, listt
					end
					if listt == objectdata then
						listt = nil
					end
					resolvelist = getresolver(listt or options.List, options.Filter, options.Method)
					list = resolvelist()
					if updateValues then
						validate()
					end
					if showing then
						display(false)
						display(true)
					end
					return list
				end
				tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.NewSearchBox = sectionFunctions.AddSearchBox
			sectionFunctions.CreateSearchBox = sectionFunctions.AddSearchBox
			sectionFunctions.SearchBox = sectionFunctions.AddSearchBox
			sectionFunctions.CreateSearchbox = sectionFunctions.AddSearchBox
			sectionFunctions.NewSearchbox = sectionFunctions.AddSearchBox
			sectionFunctions.Searchbox = sectionFunctions.AddSearchBox
			sectionFunctions.Sbox = sectionFunctions.AddSearchBox
			sectionFunctions.SBox = sectionFunctions.AddSearchBox
			if isfolder and makefolder and listfiles and readfile and writefile then
				function sectionFunctions:AddPersistence(options, ...)
					options = (options and type(options) == "string" and resolvevararg("Tab", options, ...)) or options
					local dropdownName, custom_workspace, val, persistiveflags, suffix, callback, loadcallback, savecallback, postload, postsave, flagName = assert(options.Name, "Missing Name for new persistence."), options.Workspace or library.WorkspaceName, options.Value, options.Persistive or options.Flags or "all", options.Suffix, options.Callback, options.LoadCallback, options.SaveCallback, options.PostLoadCallback, options.PostSaveCallback, options.Flag or (function()
						library.unnamedpersistence = 1 + (library.unnamedpersistence or 0)
						return "Persistence" .. tostring(library.unnamedpersistence)
					end)()
					if elements[flagName] ~= nil then
						warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
					end
					local designerpersists = options.Desginer
					local newDropdown = Instance_new("Frame")
					local dropdown = Instance_new("ImageLabel")
					local dropdownInner = Instance_new("ImageLabel")
					local dropdownToggle = Instance_new("ImageButton")
					local dropdownSelection = Instance_new("TextBox")
					local dropdownHeadline = Instance_new("TextLabel")
					local dropdownHolderFrame = Instance_new("ImageLabel")
					local dropdownHolderInner = Instance_new("ImageLabel")
					local realDropdownHolder = Instance_new("ScrollingFrame")
					local realDropdownHolderList = Instance_new("UIListLayout")
					local dropdownEnabled = false
					if not isfolder("./Function Lib") then
						makefolder("./Function Lib")
					end
					local common_string = "./Function Lib/" .. tostring(custom_workspace or library.WorkspaceName)
					local function resolvelist(nofold)
						if custom_workspace ~= options.Workspace then
							custom_workspace = options.Workspace
							common_string = "./Function Lib/" .. tostring(custom_workspace or library.WorkspaceName)
						end
						if not isfolder or not makefolder or not listfiles then
							return {}
						end
						if not isfolder(common_string) then
							if nofold then
								return {}
							end
							makefolder(common_string)
						end
						assert(isfolder(common_string), "Couldn't create folder: " .. tostring(library.WorkspaceName or "No workspace name?"))
						local names, files = {}, listfiles(common_string)
						if #files > 0 then
							local len = #common_string + 2
							for _, f in next, files do
								names[1 + #names] = string.sub(f, len, -5)
							end
							table.sort(names)
						end
						return names
					end
					local list = resolvelist(true)
					local blankstring = options.BlankValue or options.NoValueString or options.Nothing
					local selectedObjects = {}
					local optionCount = 0
					if blankstring and val == nil then
						val = blankstring
					end
					local selectedOption = val or blankstring or list[1]
					newDropdown.Name = "newDropdown"
					newDropdown.Parent = sectionHolder
					newDropdown.BackgroundColor3 = Color3.new(1, 1, 1)
					newDropdown.BackgroundTransparency = 1
					newDropdown.Size = UDim2.new(1, 0, 0, 42)
					dropdown.Name = "dropdown"
					dropdown.Parent = newDropdown
					dropdown.Active = true
					dropdown.BackgroundColor3 = library.colors.topGradient
					local colored_dropdown_BackgroundColor3 = {dropdown, "BackgroundColor3", "topGradient"}
					colored[1 + #colored] = colored_dropdown_BackgroundColor3
					dropdown.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {dropdown, "BorderColor3", "elementBorder"}
					dropdown.Position = UDim2.fromScale(0.027, 0.45)
					dropdown.Selectable = true
					dropdown.Size = UDim2.fromOffset(206, 18)
					dropdown.Image = "rbxassetid://2454009026"
					dropdown.ImageColor3 = library.colors.bottomGradient
					local colored_dropdown_ImageColor3 = {dropdown, "ImageColor3", "bottomGradient"}
					colored[1 + #colored] = colored_dropdown_ImageColor3
					dropdownInner.Name = "dropdownInner"
					dropdownInner.Parent = dropdown
					dropdownInner.Active = true
					dropdownInner.AnchorPoint = Vector2.new(0.5, 0.5)
					dropdownInner.BackgroundColor3 = library.colors.topGradient
					colored[1 + #colored] = {dropdownInner, "BackgroundColor3", "topGradient"}
					dropdownInner.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {dropdownInner, "BorderColor3", "elementBorder"}
					dropdownInner.Position = UDim2.fromScale(0.5, 0.5)
					dropdownInner.Selectable = true
					dropdownInner.Size = UDim2.new(1, -4, 1, -4)
					dropdownInner.Image = "rbxassetid://2454009026"
					dropdownInner.ImageColor3 = library.colors.bottomGradient
					colored[1 + #colored] = {dropdownInner, "ImageColor3", "bottomGradient"}
					dropdownToggle.Name = "dropdownToggle"
					dropdownToggle.Parent = dropdown
					dropdownToggle.BackgroundColor3 = Color3.new(1, 1, 1)
					dropdownToggle.BackgroundTransparency = 1
					dropdownToggle.Position = UDim2.fromScale(0.9, 0.17)
					dropdownToggle.Rotation = 90
					dropdownToggle.Size = UDim2.fromOffset(12, 12)
					dropdownToggle.ZIndex = 2
					dropdownToggle.Image = "rbxassetid://71659683"
					dropdownToggle.ImageColor3 = Color3.fromRGB(171, 171, 171)
					dropdownSelection.Name = "dropdownSelection"
					dropdownSelection.Parent = dropdown
					dropdownSelection.BackgroundColor3 = Color3.new(1, 1, 1)
					dropdownSelection.BackgroundTransparency = 1
					dropdownSelection.Position = UDim2.new(0.0295485705)
					dropdownSelection.Size = UDim2.fromScale(0.97, 1)
					dropdownSelection.ZIndex = 5
					dropdownSelection.Font = Enum.Font.Code
					dropdownSelection.LineHeight = 1.15
					dropdownSelection.Text = (selectedOption and tostring(selectedOption)) or "nil"
					dropdownSelection.TextColor3 = library.colors.otherElementText
					colored[1 + #colored] = {dropdownSelection, "TextColor3", "otherElementText"}
					dropdownSelection.TextSize = 14
					dropdownSelection.TextXAlignment = Enum.TextXAlignment.Left
					dropdownHeadline.Name = "dropdownHeadline"
					dropdownHeadline.Parent = newDropdown
					dropdownHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
					dropdownHeadline.BackgroundTransparency = 1
					dropdownHeadline.Position = UDim2.fromScale(0.034, 0.03)
					dropdownHeadline.Size = UDim2.fromOffset(167, 11)
					dropdownHeadline.Font = Enum.Font.Code
					dropdownHeadline.Text = (dropdownName and tostring(dropdownName)) or "???"
					dropdownHeadline.TextColor3 = library.colors.elementText
					colored[1 + #colored] = {dropdownHeadline, "TextColor3", "elementText"}
					dropdownHeadline.TextSize = 14
					dropdownHeadline.TextXAlignment = Enum.TextXAlignment.Left
					dropdownHolderFrame.Name = "dropdownHolderFrame"
					dropdownHolderFrame.Parent = newDropdown
					dropdownHolderFrame.Active = true
					dropdownHolderFrame.BackgroundColor3 = library.colors.topGradient
					colored[1 + #colored] = {dropdownHolderFrame, "BackgroundColor3", "topGradient"}
					dropdownHolderFrame.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {dropdownHolderFrame, "BorderColor3", "elementBorder"}
					dropdownHolderFrame.Position = UDim2.fromScale(0.025, 1.012)
					dropdownHolderFrame.Selectable = true
					dropdownHolderFrame.Size = UDim2.fromOffset(206, 22)
					dropdownHolderFrame.Visible = false
					dropdownHolderFrame.Image = "rbxassetid://2454009026"
					dropdownHolderFrame.ImageColor3 = library.colors.bottomGradient
					colored[1 + #colored] = {dropdownHolderFrame, "ImageColor3", "bottomGradient"}
					dropdownHolderInner.Name = "dropdownHolderInner"
					dropdownHolderInner.Parent = dropdownHolderFrame
					dropdownHolderInner.Active = true
					dropdownHolderInner.AnchorPoint = Vector2.new(0.5, 0.5)
					dropdownHolderInner.BackgroundColor3 = library.colors.topGradient
					colored[1 + #colored] = {dropdownHolderInner, "BackgroundColor3", "topGradient"}
					dropdownHolderInner.BorderColor3 = library.colors.elementBorder
					colored[1 + #colored] = {dropdownHolderInner, "BorderColor3", "elementBorder"}
					dropdownHolderInner.Position = UDim2.fromScale(0.5, 0.5)
					dropdownHolderInner.Selectable = true
					dropdownHolderInner.Size = UDim2.new(1, -4, 1, -4)
					dropdownHolderInner.Image = "rbxassetid://2454009026"
					dropdownHolderInner.ImageColor3 = library.colors.bottomGradient
					colored[1 + #colored] = {dropdownHolderInner, "ImageColor3", "bottomGradient"}
					realDropdownHolder.Name = "realDropdownHolder"
					realDropdownHolder.Parent = dropdownHolderInner
					realDropdownHolder.BackgroundColor3 = Color3.new(1, 1, 1)
					realDropdownHolder.BackgroundTransparency = 1
					realDropdownHolder.Selectable = false
					realDropdownHolder.Size = UDim2.fromScale(1, 1)
					realDropdownHolder.CanvasSize = UDim2.new()
					realDropdownHolder.ScrollBarThickness = 5
					realDropdownHolder.ScrollingDirection = Enum.ScrollingDirection.Y
					realDropdownHolder.AutomaticCanvasSize = Enum.AutomaticSize.Y
					realDropdownHolder.ScrollBarImageTransparency = 0.5
					realDropdownHolder.ScrollBarImageColor3 = library.colors.section
					colored[1 + #colored] = {realDropdownHolder, "ScrollBarImageColor3", "section"}
					realDropdownHolderList.Name = "realDropdownHolderList"
					realDropdownHolderList.Parent = realDropdownHolder
					realDropdownHolderList.HorizontalAlignment = Enum.HorizontalAlignment.Center
					realDropdownHolderList.SortOrder = Enum.SortOrder.LayoutOrder
					sectionFunctions:Update()
					library.signals[1 + #library.signals] = newDropdown.MouseEnter:Connect(function()
						colored_dropdown_BackgroundColor3[3] = "main"
						colored_dropdown_BackgroundColor3[4] = 1.5
						colored_dropdown_ImageColor3[3] = "main"
						colored_dropdown_ImageColor3[4] = 2.5
						tweenService:Create(dropdown, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = darkenColor(library.colors.main, 1.5),
							ImageColor3 = darkenColor(library.colors.main, 2.5)
						}):Play()
					end)
					library.signals[1 + #library.signals] = newDropdown.MouseLeave:Connect(function()
						if not dropdownEnabled then
							colored_dropdown_BackgroundColor3[3] = "topGradient"
							colored_dropdown_BackgroundColor3[4] = nil
							colored_dropdown_ImageColor3[3] = "bottomGradient"
							colored_dropdown_ImageColor3[4] = nil
							tweenService:Create(dropdown, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
								BackgroundColor3 = library.colors.topGradient,
								ImageColor3 = library.colors.bottomGradient
							}):Play()
						end
					end)
					local restorezindex = {}
					local function UpdateDropdownHolder()
						if optionCount >= 6 then
							realDropdownHolder.CanvasSize = UDim2:fromOffset(realDropdownHolderList.AbsoluteContentSize.Y + 2)
						elseif optionCount <= 5 then
							dropdownHolderFrame.Size = UDim2.fromOffset(206, (realDropdownHolderList.AbsoluteContentSize.Y + 4))
						end
					end
					local function AddOptions(optionsTable, filter)
						if options.Sort then
							local didstuff, dosort = nil, options.Sort
							if type(dosort) == "function" then
								local g, h = pcall(table.sort, optionsTable, dosort)
								if g then
									didstuff = true
								elseif h then
									warn("Error sorting list:", h, debug.traceback(""))
								end
							end
							if not didstuff then
								table.sort(optionsTable, library.defaultSort)
							end
						end
						if blankstring and (optionsTable[1] ~= blankstring or table.find(optionsTable, blankstring, 2)) then
							local exists = table.find(optionsTable, blankstring)
							if exists then
								for _ = 1, 35 do
									table.remove(optionsTable, exists)
									exists = table.find(optionsTable, blankstring)
									if not exists then
										break
									end
								end
							end
							table.insert(optionsTable, 1, blankstring)
						end
						optionCount = 0
						realDropdownHolderList.Parent = nil
						realDropdownHolder:ClearAllChildren()
						realDropdownHolderList.Parent = realDropdownHolder
						for _, v in next, optionsTable do
							if not filter or tostring(v):lower():find(dropdownSelection.Text:lower(), 1, true) then
								optionCount = optionCount + 1
								UpdateDropdownHolder()
								local newOption = Instance_new("ImageLabel")
								local optionButton = Instance_new("TextButton")
								if selectedOption == v or not selectedObjects[1] or not selectedObjects[2] then
									selectedObjects[1] = newOption
									selectedObjects[2] = optionButton
								end
								newOption.Name = "Frame"
								newOption.Parent = realDropdownHolder
								newOption.BackgroundColor3 = (selectedOption == v and library.colors.selectedOption or library.colors.topGradient)
								newOption.BorderSizePixel = 0
								newOption.Size = UDim2.fromOffset(202, 18)
								newOption.Image = "rbxassetid://2454009026"
								newOption.ImageColor3 = (selectedOption == v and library.colors.unselectedOption or library.colors.bottomGradient)
								optionButton.Name = tostring(v)
								optionButton.Parent = newOption
								optionButton.AnchorPoint = Vector2.new(0.5, 0.5)
								optionButton.BackgroundColor3 = Color3.new(1, 1, 1)
								optionButton.BackgroundTransparency = 1
								optionButton.Position = UDim2.fromScale(0.5, 0.5)
								optionButton.Size = UDim2.new(1, -10, 1)
								optionButton.ZIndex = 5
								optionButton.Font = Enum.Font.Code
								optionButton.Text = (selectedOption == v and " " .. tostring(v)) or tostring(v)
								optionButton.TextColor3 = (selectedOption == v and library.colors.main or library.colors.otherElementText)
								optionButton.TextSize = 14
								optionButton.TextXAlignment = Enum.TextXAlignment.Left
								library.signals[1 + #library.signals] = optionButton.MouseButton1Down:Connect(function()
									dropdownSelection.Text = tostring(v)
									restorezindex[newSection] = restorezindex[newSection] or newSection.ZIndex
									restorezindex[newDropdown] = restorezindex[newDropdown] or newDropdown.ZIndex
									restorezindex[sectionHolder] = restorezindex[sectionHolder] or sectionHolder.ZIndex
									if selectedOption ~= v then
										local last_v = library_flags[flagName]
										selectedObjects[1].BackgroundColor3 = library.colors.topGradient
										selectedObjects[1].ImageColor3 = library.colors.bottomGradient
										selectedObjects[2].Text = selectedObjects[2].Name
										selectedObjects[2].TextColor3 = library.colors.otherElementText
										selectedOption = v
										selectedObjects[1] = newOption
										selectedObjects[2] = optionButton
										newOption.BackgroundColor3 = library.colors.selectedOption
										newOption.ImageColor3 = library.colors.unselectedOption
										optionButton.TextColor3 = library.colors.main
										dropdownHolderFrame.Visible = false
										dropdownToggle.Rotation = 90
										dropdownEnabled = false
										colored_dropdown_BackgroundColor3[3] = "topGradient"
										colored_dropdown_BackgroundColor3[4] = nil
										colored_dropdown_ImageColor3[3] = "bottomGradient"
										colored_dropdown_ImageColor3[4] = nil
										tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
											BackgroundColor3 = library.colors.topGradient,
											ImageColor3 = library.colors.bottomGradient
										}):Play()
										library_flags[flagName] = selectedOption
										if options.Location then
											options.Location[options.LocationFlag or flagName] = selectedOption
										end
										dropdownSelection.Text = tostring(selectedOption)
										if submenuOpen then
											submenuOpen = nil
										end
										if callback then
											task.spawn(callback, selectedOption, last_v)
										end
									else
										submenuOpen = nil
										dropdownToggle.Rotation = 90
										newDropdown.ZIndex = 1
										sectionHolder.ZIndex = 1
										colored_dropdown_BackgroundColor3[3] = "topGradient"
										colored_dropdown_BackgroundColor3[4] = nil
										colored_dropdown_ImageColor3[3] = "bottomGradient"
										colored_dropdown_ImageColor3[4] = nil
										tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
											BackgroundColor3 = library.colors.topGradient,
											ImageColor3 = library.colors.bottomGradient
										}):Play()
										dropdownHolderFrame.Visible = false
									end
									for ins, z in next, restorezindex do
										ins.ZIndex = z
									end
								end)
								library.signals[1 + #library.signals] = optionButton.MouseEnter:Connect(function()
									tweenService:Create(newOption, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
										BackgroundColor3 = library.colors.hoveredOptionTop,
										ImageColor3 = library.colors.hoveredOptionBottom
									}):Play()
								end)
								library.signals[1 + #library.signals] = optionButton.MouseLeave:Connect(function()
									tweenService:Create(newOption, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
										BackgroundColor3 = library.colors.unhoveredOptionTop,
										ImageColor3 = library.colors.unhoveredOptionBottom
									}):Play()
								end)
								UpdateDropdownHolder()
							end
						end
					end
					local precisionscrolling = nil
					local showing = false
					local function display(dropdownEnabled, f)
						if submenuOpen == dropdown or submenuOpen == nil then
							if dropdownEnabled then
								list = resolvelist(true)
								AddOptions(list, f)
								submenuOpen = dropdown
								restorezindex[newSection] = restorezindex[newSection] or newSection.ZIndex
								restorezindex[newDropdown] = restorezindex[newDropdown] or newDropdown.ZIndex
								restorezindex[sectionHolder] = restorezindex[sectionHolder] or sectionHolder.ZIndex
								newSection.ZIndex = 50 + newSection.ZIndex
								dropdownToggle.Rotation = 270
								newDropdown.ZIndex = 2
								sectionHolder.ZIndex = 2
								colored_dropdown_BackgroundColor3[3] = "main"
								colored_dropdown_BackgroundColor3[4] = 1.5
								colored_dropdown_ImageColor3[3] = "main"
								colored_dropdown_ImageColor3[4] = 2.5
								tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									BackgroundColor3 = darkenColor(library.colors.main, 1.5),
									ImageColor3 = darkenColor(library.colors.main, 2.5)
								}):Play()
								dropdownHolderFrame.Visible = true
								if not options.DisablePrecisionScrolling then
									local upkey = options.ScrollUpButton or library.scrollupbutton or shared.scrollupbutton or Enum.KeyCode.Up
									local downkey = options.ScrollDownButton or library.scrolldownbutton or shared.scrolldownbutton or Enum.KeyCode.Down
									precisionscrolling = (precisionscrolling and precisionscrolling:Disconnect() and nil) or userInputService.InputBegan:Connect(function(input)
										if input.UserInputType == Enum.UserInputType.Keyboard then
											local code = input.KeyCode
											local isup = code == upkey
											local isdown = code == downkey
											if isup or isdown then
												local txt = userInputService:GetFocusedTextBox()
												if not txt then
													while wait_check() and userInputService:IsKeyDown(code) do
														realDropdownHolder.CanvasPosition = Vector2:new(math.clamp(realDropdownHolder.CanvasPosition.Y + ((isup and -5) or 5), 0, realDropdownHolder.AbsoluteCanvasSize.Y))
													end
												end
											end
										end
									end)
									library.signals[1 + #library.signals] = precisionscrolling
								end
							else
								submenuOpen = nil
								dropdownToggle.Rotation = 90
								colored_dropdown_BackgroundColor3[3] = "topGradient"
								colored_dropdown_BackgroundColor3[4] = nil
								colored_dropdown_ImageColor3[3] = "bottomGradient"
								colored_dropdown_ImageColor3[4] = nil
								tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									BackgroundColor3 = library.colors.topGradient,
									ImageColor3 = library.colors.bottomGradient
								}):Play()
								dropdownHolderFrame.Visible = false
								for ins, z in next, restorezindex do
									ins.ZIndex = z
								end
								precisionscrolling = (precisionscrolling and precisionscrolling:Disconnect() and nil) or nil
							end
							showing = dropdownEnabled
						end
					end
					local last_v = nil
					local function Set(t, str)
						if nil == str and t then
							str = t
						end
						selectedOption = str
						last_v = library_flags[flagName]
						library_flags[flagName] = str
						if options.Location then
							options.Location[options.LocationFlag or flagName] = str
						end
						local sstr = (selectedOption and tostring(selectedOption)) or blankstring or "No Blank String"
						if dropdownSelection.Text ~= sstr then
							dropdownSelection.Text = sstr
						end
						if callback and (last_v ~= str or options.AllowDuplicateCalls) then
							task.spawn(callback, str, last_v)
						end
						return str
					end
					if val ~= nil then
						Set(val)
					else
						Set("Filename")
					end
					library.signals[1 + #library.signals] = dropdownSelection.Focused:Connect(function()
						showing = true
						display(true)
					end)
					library.signals[1 + #library.signals] = dropdownSelection:GetPropertyChangedSignal("Text"):Connect(function()
						if showing then
							display(true, #dropdownSelection.Text > 0)
						end
					end)
					library.signals[1 + #library.signals] = dropdownSelection.FocusLost:Connect(function(b)
						if showing then
							wait()
						end
						showing = false
						display(false)
						if b then
							Set(dropdownSelection.Text)
						end
					end)
					AddOptions(list)
					local function savestuff(s, get)
						if not s or type(s) ~= "string" then
							s = nil
						end
						local rawfile = "json__save"
						if not get then
							local filenameddst = string.gsub(s or dropdownSelection.Text or "", "%W", "")
							if #filenameddst == 0 then
								return
							end
							rawfile = string.format("%s/%s.txt", common_string, filenameddst)
						end
						if savecallback then
							local x, e = pcall(savecallback, rawfile, library_flags[flagName])
							if not x and e then
								warn("Error while calling the Pre-Save callback:", e, debug.traceback(""))
							end
						end
						local working_with = {}
						if persistiveflags == 1 or persistiveflags == true or persistiveflags == "*" then
							persistiveflags = "all"
						elseif persistiveflags == 2 then
							persistiveflags = "tab"
						elseif persistiveflags == 3 then
							persistiveflags = "section"
						end
						if persistiveflags == "all" or persistiveflags == "tab" or persistiveflags == "section" then
							for cflag, data in next, (persistiveflags == "all" and elements) or (persistiveflags == "tab" and tabFunctions.Flags) or (persistiveflags == "section" and sectionFunctions.Flags) do
								if data.Type ~= "Persistence" and (designerpersists or string.sub(cflag, 1, 11) ~= "__Designer.") then
									working_with[cflag] = data
								end
							end
						elseif type(persistiveflags) == "table" then
							if #persistiveflags > 0 then
								local inverted = persistiveflags[0] == false or persistiveflags.Inverted
								for k, cflag in next, persistiveflags do
									if k > 0 then
										local data = elements[cflag]
										if data and data.Type ~= "Persistence" and (designerpersists or string.sub(cflag, 1, 11) ~= "__Designer.") then
											working_with[cflag] = (not inverted and data) or nil
										end
									end
								end
							else
								for cflag, persists in next, elements do
									if persists and (designerpersists or string.sub(cflag, 1, 11) ~= "__Designer.") then
										local data = elements[cflag]
										if data then
											working_with[cflag] = data
										end
									end
								end
							end
						end
						local saving = {}
						for cflag in next, working_with do
							local value = library_flags[cflag]
							local good, jval = nil, nil
							if value ~= nil then
								good, jval = JSONEncode(value)
							else
								good, jval = true, "null"
							end
							if not good or (jval == "null" and value ~= nil) then
								local typ = typeof(value)
								if typ == "Color3" then
									value = (library.rainbowflags[cflag] and "rainbow") or Color3ToHex(value)
								end
								value = tostring(value)
								good, jval = JSONEncode(value)
								if not good or (jval == "null" and value ~= nil) then
									warn("Could not save value:", value, debug.traceback(""))
								end
							end
							if good and jval then
								saving[cflag] = value
							end
						end
						local ret = nil
						local good, content = JSONEncode(saving)
						if good and content then
							if not get then
								if not isfolder(common_string) then
									makefolder(common_string)
								end
								writefile(rawfile, content)
							else
								ret = content
							end
						end
						if postsave then
							local x, e = pcall(postsave, rawfile, library_flags[flagName])
							if not x and e then
								warn("Error while calling the Post-Save callback:", e, debug.traceback(""))
							end
						end
						return ret
					end
					local function loadstuff(s, jsonmode, silent)
						if not s or type(s) ~= "string" then
							s = nil
						end
						local filename = "json__load"
						if not jsonmode then
							local filenameddst = convertfilename(s or dropdownSelection.Text, nil, "")
							if #filenameddst == 0 then
								return
							end
							filename = string.format("%s/%s.txt", common_string, filenameddst)
						end
						if loadcallback then
							local x, e = pcall(loadcallback, (jsonmode and s) or filename, library_flags[flagName])
							if not x and e then
								warn("Error while calling the Pre-Load callback:", e, debug.traceback(""))
							end
						end
						if jsonmode or not isfile or isfile(filename) then
							local content = (jsonmode and s) or (not jsonmode and readfile(filename))
							if content and #content > 1 then
								local good, jcontent = JSONDecode(content)
								if good and jcontent then
									for cflag, val in next, jcontent do
										if val and type(val) == "string" and #val > 7 and #val < 64 and string.sub(val, 1, 5) == "Enum." then
											local e = string.find(val, ".", 6, true)
											if e then
												local en = Enum[string.sub(val, 6, e - 1)]
												en = en and en[string.sub(val, e + 1)]
												if en then
													val = en
												else
													warn("Tried & failed to convert '" .. val .. "' to EnumItem")
												end
											end
										end
										local data = elements[cflag]
										if data and data.Type ~= "Persistence" then
											if silent and data.RawSet then
												data:RawSet(val)
											elseif data.Set then
												data:Set(val)
											else
												library_flags[cflag] = val
											end
										end
									end
								end
							end
						end
						if postload then
							local x, e = pcall(postload, filename, library_flags[flagName])
							if not x and e then
								warn("Error while calling the Post-Load callback:", e, debug.traceback(""))
							end
						end
					end
					do
						local buttons, offset = {}, 0
						local fram = nil
						for _, options in next, {{
							Name = "Save" .. ((suffix and (" " .. tostring(suffix))) or ""),
							Callback = savestuff
							}, {
								Name = "Load" .. ((suffix and (" " .. tostring(suffix))) or ""),
								Callback = loadstuff
							}} do
							local buttonName, callback = options.Name, options.Callback
							local realButton = Instance_new("TextButton")
							realButton.Name = "realButton"
							realButton.BackgroundColor3 = Color3.new(1, 1, 1)
							realButton.BackgroundTransparency = 1
							realButton.Size = UDim2.fromScale(1, 1)
							realButton.ZIndex = 5
							realButton.Font = Enum.Font.Code
							realButton.Text = (buttonName and tostring(buttonName)) or "???"
							realButton.TextColor3 = library.colors.elementText
							colored[1 + #colored] = {realButton, "TextColor3", "elementText"}
							realButton.TextSize = 14
							local textsize = textToSize(realButton).X + 14
							if newSection.Parent.AbsoluteSize.X < offset + textsize + 8 then
								offset, fram = 0, nil
							end
							local newButton = fram or Instance_new("Frame")
							fram = newButton
							local button = Instance_new("ImageLabel")
							newButton.Name = removeSpaces((buttonName and buttonName:lower() or "???") .. "Holder")
							newButton.Parent = sectionHolder
							newButton.BackgroundColor3 = Color3.new(1, 1, 1)
							newButton.BackgroundTransparency = 1
							newButton.Size = UDim2.new(1, 0, 0, 24)
							button.Name = "button"
							button.Parent = newButton
							button.Active = true
							button.BackgroundColor3 = library.colors.topGradient
							local colored_button_BackgroundColor3 = {button, "BackgroundColor3", "topGradient"}
							colored[1 + #colored] = colored_button_BackgroundColor3
							button.BorderColor3 = library.colors.elementBorder
							colored[1 + #colored] = {button, "BorderColor3", "elementBorder"}
							button.Position = UDim2.new(0.031, offset, 0.166)
							button.Selectable = true
							button.Size = UDim2.fromOffset(28, 18)
							button.Image = "rbxassetid://2454009026"
							button.ImageColor3 = library.colors.bottomGradient
							local colored_button_ImageColor3 = {button, "ImageColor3", "bottomGradient"}
							colored[1 + #colored] = colored_button_ImageColor3
							local buttonInner = Instance_new("ImageLabel")
							buttonInner.Name = "buttonInner"
							buttonInner.Parent = button
							buttonInner.Active = true
							buttonInner.AnchorPoint = Vector2.new(0.5, 0.5)
							buttonInner.BackgroundColor3 = library.colors.topGradient
							colored[1 + #colored] = {buttonInner, "BackgroundColor3", "topGradient"}
							buttonInner.BorderColor3 = library.colors.elementBorder
							colored[1 + #colored] = {buttonInner, "BorderColor3", "elementBorder"}
							buttonInner.Position = UDim2.fromScale(0.5, 0.5)
							buttonInner.Selectable = true
							buttonInner.Size = UDim2.new(1, -4, 1, -4)
							buttonInner.Image = "rbxassetid://2454009026"
							buttonInner.ImageColor3 = library.colors.bottomGradient
							colored[1 + #colored] = {buttonInner, "ImageColor3", "bottomGradient"}
							button.Size = UDim2.fromOffset(textsize, 18)
							realButton.Parent = button
							offset = offset + textsize + 6
							sectionFunctions:Update()
							local presses = 0
							library.signals[1 + #library.signals] = realButton.MouseButton1Click:Connect(function()
								if not library.colorpicker and not submenuOpen then
									presses = 1 + presses
									task.spawn(callback, presses)
								end
							end)
							library.signals[1 + #library.signals] = button.MouseEnter:Connect(function()
								colored_button_BackgroundColor3[3] = "main"
								colored_button_BackgroundColor3[4] = 1.5
								colored_button_ImageColor3[3] = "main"
								colored_button_ImageColor3[4] = 2.5
								tweenService:Create(button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									BackgroundColor3 = darkenColor(library.colors.main, 1.5),
									ImageColor3 = darkenColor(library.colors.main, 2.5)
								}):Play()
							end)
							library.signals[1 + #library.signals] = button.MouseLeave:Connect(function()
								colored_button_BackgroundColor3[3] = "topGradient"
								colored_button_BackgroundColor3[4] = nil
								colored_button_ImageColor3[3] = "bottomGradient"
								colored_button_ImageColor3[4] = nil
								tweenService:Create(button, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
									BackgroundColor3 = library.colors.topGradient,
									ImageColor3 = library.colors.bottomGradient
								}):Play()
							end)
						end
					end
					local default = library_flags[flagName]
					local function update()
						dropdownName, custom_workspace, persistiveflags, suffix, callback, loadcallback, savecallback, postload, postsave = options.Name or dropdownName, options.Workspace or library.WorkspaceName, options.Persistive or options.Flags or "all", options.Suffix, options.Callback, options.LoadCallback, options.SaveCallback, options.PostLoadCallback, options.PostSaveCallback
						local sstr = tostring(library_flags[flagName])
						if dropdownSelection.Text ~= sstr then
							dropdownSelection.Text = sstr
						end
						dropdownHeadline.Text = (dropdownName and tostring(dropdownName)) or "???"
						return sstr
					end
					local objectdata = {
						Options = options,
						Name = flagName,
						Flag = flagName,
						Type = "Persistence",
						Default = default,
						Parent = sectionFunctions,
						Instance = dropdownSelection,
						Set = Set,
						SaveFile = function(t, str, ret)
							if t ~= nil and type(t) ~= "table" then
								str, ret = t, str
							end
							if type(str) == "string" then
								str = str:match("(.+)%..+$") or str
							end
							return savestuff(str, ret)
						end,
						LoadFile = function(t, str, jsonmode)
							if t ~= nil and type(t) ~= "table" then
								str, jsonmode = t, str
							end
							if isfile and isfile(str) then
								return loadstuff(readfile(str), true)
							elseif not jsonmode and type(str) == "string" then
								str = str:match("(.+)%..+$") or str
							end
							return loadstuff(str, jsonmode)
						end,
						LoadJSON = function(_, json)
							return loadstuff(json, true)
						end,
						LoadFileRaw = function(t, str, jsonmode)
							if t ~= nil and type(t) ~= "table" then
								str, jsonmode = t, str
							end
							if isfile and isfile(str) then
								return loadstuff(readfile(str), true, true)
							elseif not jsonmode and type(str) == "string" then
								str = str:match("(.+)%..+$") or str
							end
							return loadstuff(str, jsonmode, true)
						end,
						LoadJSONRaw = function(_, json)
							return loadstuff(json, true, true)
						end,
						GetJSON = function(t, clipboard)
							if nil == clipboard and t ~= nil then
								clipboard = t
							end
							local json = savestuff(nil, true)
							local clipfunc = (clipboard and type(clipboard) == "function" and clipboard) or setclipboard
							if clipboard and clipfunc then
								clipfunc(json)
							end
							return json
						end,
						RawSet = function(t, str)
							if nil == str and t ~= nil then
								str = t
							end
							selectedOption = str
							last_v = library_flags[flagName]
							library_flags[flagName] = str
							if options.Location then
								options.Location[options.LocationFlag or flagName] = str
							end
							update()
							return str
						end,
						Get = function()
							return library_flags[flagName]
						end,
						Update = update,
						Reset = function()
							return Set(nil, default)
						end
					}
					tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
					return objectdata
				end
			else
				function sectionFunctions.AddPersistence()
					if not library.warnedpersistance then
						library.warnedpersistance = 1
						warn(debug.traceback("Persistance not supported"))
					end
					function sectionFunctions.AddPersistence()
					end
				end
			end
			sectionFunctions.NewPersistence = sectionFunctions.AddPersistence
			sectionFunctions.CreatePersistence = sectionFunctions.AddPersistence
			sectionFunctions.Persistence = sectionFunctions.AddPersistence
			sectionFunctions.CreateSaveLoad = sectionFunctions.AddPersistence
			sectionFunctions.SaveLoad = sectionFunctions.AddPersistence
			sectionFunctions.SL = sectionFunctions.AddPersistence
			function sectionFunctions:AddDropdown(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Dropdown", options, ...)) or options
				local dropdownName, listt, val, callback, flagName = assert(options.Name, "Missing Name for new searchbox."), assert(options.List, "Missing List for new searchbox."), options.Value, options.Callback, options.Flag or (function()
					library.unnameddropdown = 1 + (library.unnameddropdown or 0)
					return "Dropdown" .. tostring(library.unnameddropdown)
				end)()
				if elements[flagName] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
				end
				local newDropdown = Instance_new("Frame")
				local dropdown = Instance_new("ImageLabel")
				local dropdownInner = Instance_new("ImageLabel")
				local dropdownToggle = Instance_new("ImageButton")
				local dropdownSelection = Instance_new("TextLabel")
				local dropdownHeadline = Instance_new("TextLabel")
				local dropdownHolderFrame = Instance_new("ImageLabel")
				local dropdownHolderInner = Instance_new("ImageLabel")
				local realDropdownHolder = Instance_new("ScrollingFrame")
				local realDropdownHolderList = Instance_new("UIListLayout")
				local dropdownEnabled = false
				local multiselect = options.MultiSelect or options.Multi or options.Multiple
				local addcallback = options.ItemAdded or options.AddedCallback
				local delcallback = options.ItemRemoved or options.RemovedCallback
				local clrcallback = options.ItemsCleared or options.ClearedCallback
				local modcallback = options.ItemChanged or options.ChangedCallback
				local blankstring = not multiselect and (options.BlankValue or options.NoValueString or options.Nothing)
				local resolvelist = getresolver(listt, options.Filter, options.Method)
				local list = resolvelist()
				local selectedOption = list[1]
				local passed_multiselect = multiselect and type(multiselect)
				if blankstring and val == nil then
					val = blankstring
				end
				if val ~= nil then
					selectedOption = val
				end
				if multiselect and (not selectedOption or type(selectedOption) ~= "table") then
					selectedOption = {}
				end
				local selectedObjects = {}
				local optionCount = 0
				newDropdown.Name = "newDropdown"
				newDropdown.Parent = sectionHolder
				newDropdown.BackgroundColor3 = Color3.new(1, 1, 1)
				newDropdown.BackgroundTransparency = 1
				newDropdown.Size = UDim2.new(1, 0, 0, 42)
				dropdown.Name = "dropdown"
				dropdown.Parent = newDropdown
				dropdown.Active = true
				dropdown.BackgroundColor3 = library.colors.topGradient
				local colored_dropdown_BackgroundColor3 = {dropdown, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_dropdown_BackgroundColor3
				dropdown.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdown, "BorderColor3", "elementBorder"}
				dropdown.Position = UDim2.fromScale(0.027, 0.45)
				dropdown.Selectable = true
				dropdown.Size = UDim2.fromOffset(206, 18)
				dropdown.Image = "rbxassetid://2454009026"
				dropdown.ImageColor3 = library.colors.bottomGradient
				local colored_dropdown_ImageColor3 = {dropdown, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_dropdown_ImageColor3
				dropdownInner.Name = "dropdownInner"
				dropdownInner.Parent = dropdown
				dropdownInner.Active = true
				dropdownInner.AnchorPoint = Vector2.new(0.5, 0.5)
				dropdownInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {dropdownInner, "BackgroundColor3", "topGradient"}
				dropdownInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdownInner, "BorderColor3", "elementBorder"}
				dropdownInner.Position = UDim2.fromScale(0.5, 0.5)
				dropdownInner.Selectable = true
				dropdownInner.Size = UDim2.new(1, -4, 1, -4)
				dropdownInner.Image = "rbxassetid://2454009026"
				dropdownInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {dropdownInner, "ImageColor3", "bottomGradient"}
				dropdownToggle.Name = "dropdownToggle"
				dropdownToggle.Parent = dropdown
				dropdownToggle.BackgroundColor3 = Color3.new(1, 1, 1)
				dropdownToggle.BackgroundTransparency = 1
				dropdownToggle.Position = UDim2.fromScale(0.9, 0.17)
				dropdownToggle.Rotation = 90
				dropdownToggle.Size = UDim2.fromOffset(12, 12)
				dropdownToggle.ZIndex = 2
				dropdownToggle.Image = "rbxassetid://71659683"
				dropdownToggle.ImageColor3 = Color3.fromRGB(171, 171, 171)
				dropdownSelection.Name = "dropdownSelection"
				dropdownSelection.Parent = dropdown
				dropdownSelection.Active = true
				dropdownSelection.BackgroundColor3 = Color3.new(1, 1, 1)
				dropdownSelection.BackgroundTransparency = 1
				dropdownSelection.Position = UDim2.new(0.0295)
				dropdownSelection.Selectable = true
				dropdownSelection.Size = UDim2.fromScale(0.97, 1)
				dropdownSelection.ZIndex = 5
				dropdownSelection.Font = Enum.Font.Code
				dropdownSelection.Text = (passed_multiselect == "string" and multiselect) or (multiselect and (blankstring or "Select Item(s)")) or (selectedOption and tostring(selectedOption)) or blankstring or "No Blank String"
				dropdownSelection.TextColor3 = library.colors.otherElementText
				colored[1 + #colored] = {dropdownSelection, "TextColor3", "otherElementText"}
				dropdownSelection.TextSize = 14
				dropdownSelection.TextXAlignment = Enum.TextXAlignment.Left
				dropdownHeadline.Name = "dropdownHeadline"
				dropdownHeadline.Parent = newDropdown
				dropdownHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				dropdownHeadline.BackgroundTransparency = 1
				dropdownHeadline.Position = UDim2.fromScale(0.034, 0.03)
				dropdownHeadline.Size = UDim2.fromOffset(167, 11)
				dropdownHeadline.Font = Enum.Font.Code
				dropdownHeadline.Text = (dropdownName and tostring(dropdownName)) or "???"
				dropdownHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {dropdownHeadline, "TextColor3", "elementText"}
				dropdownHeadline.TextSize = 14
				dropdownHeadline.TextXAlignment = Enum.TextXAlignment.Left
				dropdownHolderFrame.Name = "dropdownHolderFrame"
				dropdownHolderFrame.Parent = newDropdown
				dropdownHolderFrame.Active = true
				dropdownHolderFrame.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {dropdownHolderFrame, "BackgroundColor3", "topGradient"}
				dropdownHolderFrame.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdownHolderFrame, "BorderColor3", "elementBorder"}
				dropdownHolderFrame.Position = UDim2.fromScale(0.025, 1.012)
				dropdownHolderFrame.Selectable = true
				dropdownHolderFrame.Size = UDim2.fromOffset(206, 22)
				dropdownHolderFrame.Visible = false
				dropdownHolderFrame.Image = "rbxassetid://2454009026"
				dropdownHolderFrame.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {dropdownHolderFrame, "ImageColor3", "bottomGradient"}
				dropdownHolderInner.Name = "dropdownHolderInner"
				dropdownHolderInner.Parent = dropdownHolderFrame
				dropdownHolderInner.Active = true
				dropdownHolderInner.AnchorPoint = Vector2.new(0.5, 0.5)
				dropdownHolderInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {dropdownHolderInner, "BackgroundColor3", "topGradient"}
				dropdownHolderInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {dropdownHolderInner, "BorderColor3", "elementBorder"}
				dropdownHolderInner.Position = UDim2.fromScale(0.5, 0.5)
				dropdownHolderInner.Selectable = true
				dropdownHolderInner.Size = UDim2.new(1, -4, 1, -4)
				dropdownHolderInner.Image = "rbxassetid://2454009026"
				dropdownHolderInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {dropdownHolderInner, "ImageColor3", "bottomGradient"}
				realDropdownHolder.Name = "realDropdownHolder"
				realDropdownHolder.Parent = dropdownHolderInner
				realDropdownHolder.BackgroundColor3 = Color3.new(1, 1, 1)
				realDropdownHolder.BackgroundTransparency = 1
				realDropdownHolder.Selectable = false
				realDropdownHolder.Size = UDim2.fromScale(1, 1)
				realDropdownHolder.CanvasSize = UDim2.new()
				realDropdownHolder.ScrollBarThickness = 5
				realDropdownHolder.ScrollingDirection = Enum.ScrollingDirection.Y
				realDropdownHolder.AutomaticCanvasSize = Enum.AutomaticSize.Y
				realDropdownHolder.ScrollBarImageTransparency = 0.5
				realDropdownHolder.ScrollBarImageColor3 = library.colors.section
				colored[1 + #colored] = {realDropdownHolder, "ScrollBarImageColor3", "section"}
				realDropdownHolderList.Name = "realDropdownHolderList"
				realDropdownHolderList.Parent = realDropdownHolder
				realDropdownHolderList.HorizontalAlignment = Enum.HorizontalAlignment.Center
				realDropdownHolderList.SortOrder = Enum.SortOrder.LayoutOrder
				sectionFunctions:Update()
				local showing = false
				local function UpdateDropdownHolder()
					if optionCount >= 6 then
						realDropdownHolder.CanvasSize = UDim2:fromOffset(realDropdownHolderList.AbsoluteContentSize.Y + 2)
					elseif optionCount <= 5 then
						dropdownHolderFrame.Size = UDim2.fromOffset(206, realDropdownHolderList.AbsoluteContentSize.Y + 4)
					end
				end
				local restorezindex = {}
				local Set = (multiselect and function(t, dat)
					if nil == dat and t ~= nil then
						dat = t
					end
					local lastv = library_flags[flagName]
					if not lastv or selectedOption ~= lastv then
						if lastv and type(lastv) == "table" then
							selectedOption = library_flags[flagName]
						else
							library_flags[flagName] = selectedOption
						end
						warn("Attempting to use new table for", flagName, " Please use :Set(), as setting through flags table may cause errors", debug.traceback(""))
						lastv = library_flags[flagName]
					end
					local cloned = {unpack(selectedOption)}
					if not dat then
						if #selectedOption ~= 0 then
							table.clear(selectedOption)
							if callback then
								task.spawn(callback, selectedOption, cloned)
							end
						end
						return selectedOption
					elseif type(dat) ~= "table" then
						warn("Expected table for argument #1 on Set for MultiSelect dropdown. Got", dat, debug.traceback(""))
						return selectedOption
					end
					for k = table.pack(unpack(dat)).n, 1, -1 do
						if dat[k] == nil then
							table.remove(dat, k)
						end
					end
					local proceed = #cloned ~= #dat
					table.clear(selectedOption)
					for k, v in next, dat do
						selectedOption[k] = v
						if not proceed and cloned[k] ~= v then
							proceed = 1
						end
					end
					dropdownSelection.Text = (passed_multiselect == "string" and multiselect) or blankstring or "Select Item(s)"
					if proceed and callback then
						task.spawn(callback, selectedOption, cloned)
					end
					return selectedOption
				end) or function(t, str)
					if nil == str and t ~= nil then
						str = t
					end
					local last_v = library_flags[flagName]
					selectedOption = str
					library_flags[flagName] = str
					if options.Location then
						options.Location[options.LocationFlag or flagName] = str
					end
					local sstr = (selectedOption and tostring(selectedOption)) or blankstring or "No Blank String"
					if dropdownSelection.Text ~= sstr then
						dropdownSelection.Text = sstr
					end
					if callback and (last_v ~= str or options.AllowDuplicateCalls) then
						task.spawn(callback, str, last_v)
					end
					return str
				end
				if val ~= nil then
					Set(val)
				else
					library_flags[flagName] = selectedOption
					if options.Location then
						options.Location[options.LocationFlag or flagName] = selectedOption
					end
				end
				local function AddOptions(optionsTable)
					if options.Sort then
						local didstuff, dosort = nil, options.Sort
						if type(dosort) == "function" then
							local g, h = pcall(table.sort, optionsTable, dosort)
							if g then
								didstuff = true
							elseif h then
								warn("Error sorting list:", h, debug.traceback(""))
							end
						elseif dosort ~= 1 and dosort ~= true then
							warn("Potential mistake for passed Sort argument:", dosort, debug.traceback(""))
						end
						if not didstuff then
							table.sort(optionsTable, library.defaultSort)
						end
					end
					if blankstring and (optionsTable[1] ~= blankstring or table.find(optionsTable, blankstring, 2)) then
						local exists = table.find(optionsTable, blankstring)
						if exists then
							for _ = 1, 35 do
								table.remove(optionsTable, exists)
								exists = table.find(optionsTable, blankstring)
								if not exists then
									break
								end
							end
						end
						table.insert(optionsTable, 1, blankstring)
					end
					optionCount = 0
					realDropdownHolderList.Parent = nil
					realDropdownHolder:ClearAllChildren()
					realDropdownHolderList.Parent = realDropdownHolder
					for _, v in next, optionsTable do
						optionCount = optionCount + 1
						local newOption = Instance_new("ImageLabel")
						local optionButton = Instance_new("TextButton")
						if selectedOption == v then
							selectedObjects[1] = newOption
							selectedObjects[2] = optionButton
						end
						newOption.Name = "Frame"
						newOption.Parent = realDropdownHolder
						local togged = (not multiselect and selectedOption == v) or (multiselect and table.find(selectedOption, v))
						newOption.BackgroundColor3 = (togged and library.colors.selectedOption) or library.colors.topGradient
						newOption.BorderSizePixel = 0
						newOption.Size = UDim2.fromOffset(202, 18)
						newOption.Image = "rbxassetid://2454009026"
						newOption.ImageColor3 = (togged and library.colors.unselectedOption) or library.colors.bottomGradient
						local stringed = tostring(v)
						optionButton.Name = stringed
						optionButton.Parent = newOption
						optionButton.AnchorPoint = Vector2.new(0.5, 0.5)
						optionButton.BackgroundColor3 = Color3.new(1, 1, 1)
						optionButton.BackgroundTransparency = 1
						optionButton.Position = UDim2.fromScale(0.5, 0.5)
						optionButton.Size = UDim2.new(1, -10, 1)
						optionButton.ZIndex = 5
						optionButton.Font = Enum.Font.Code
						optionButton.Text = (togged and (" " .. stringed)) or stringed
						optionButton.TextColor3 = (togged and library.colors.main) or library.colors.otherElementText
						optionButton.TextSize = 14
						optionButton.TextXAlignment = Enum.TextXAlignment.Left
						library.signals[1 + #library.signals] = optionButton.MouseButton1Click:Connect(function()
							if not library.colorpicker then
								restorezindex[newSection] = restorezindex[newSection] or newSection.ZIndex
								restorezindex[newDropdown] = restorezindex[newDropdown] or newDropdown.ZIndex
								restorezindex[sectionHolder] = restorezindex[sectionHolder] or sectionHolder.ZIndex
								if multiselect then
									local cloned = {unpack(selectedOption)}
									local togged = table.find(selectedOption, v)
									if togged then
										table.remove(selectedOption, togged)
									else
										selectedOption[1 + #selectedOption] = v
									end
									togged = table.find(selectedOption, v)
									optionButton.Text = (togged and (" " .. stringed)) or stringed
									newOption.BackgroundColor3 = (togged and library.colors.selectedOption) or library.colors.topGradient
									newOption.ImageColor3 = (togged and library.colors.unselectedOption) or library.colors.bottomGradient
									optionButton.TextColor3 = (togged and library.colors.main) or library.colors.otherElementText
									dropdownSelection.Text = (passed_multiselect == "string" and multiselect) or blankstring or "Select Item(s)"
									if callback then
										task.spawn(callback, selectedOption, cloned)
									end
									if togged then
										if addcallback then
											task.spawn(addcallback, v, selectedOption)
										end
									elseif delcallback then
										task.spawn(delcallback, v, selectedOption)
									end
									if modcallback then
										task.spawn(modcallback, v, togged, selectedOption)
									end
									if #selectedOption == 0 and clrcallback then
										task.spawn(clrcallback, selectedOption, cloned)
									end
									return
								else
									if selectedOption ~= v then
										local last_v = library_flags[flagName]
										selectedObjects[1].BackgroundColor3 = library.colors.topGradient
										selectedObjects[1].ImageColor3 = library.colors.bottomGradient
										selectedObjects[2].Text = selectedObjects[2].Name
										selectedObjects[2].TextColor3 = library.colors.otherElementText
										selectedOption = v
										dropdownSelection.Text = stringed
										selectedObjects[1] = newOption
										selectedObjects[2] = optionButton
										newOption.BackgroundColor3 = library.colors.selectedOption
										newOption.ImageColor3 = library.colors.unselectedOption
										optionButton.Text = " " .. stringed
										optionButton.TextColor3 = library.colors.main
										dropdownHolderFrame.Visible = false
										dropdownToggle.Rotation = 90
										dropdownEnabled = false
										newDropdown.ZIndex = 1
										colored_dropdown_BackgroundColor3[3] = "topGradient"
										colored_dropdown_BackgroundColor3[4] = nil
										colored_dropdown_ImageColor3[3] = "bottomGradient"
										colored_dropdown_ImageColor3[4] = nil
										tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
											BackgroundColor3 = library.colors.topGradient,
											ImageColor3 = library.colors.bottomGradient
										}):Play()
										library_flags[flagName] = selectedOption
										if options.Location then
											options.Location[options.LocationFlag or flagName] = selectedOption
										end
										submenuOpen = nil
										showing = false
										if callback then
											task.spawn(callback, selectedOption, last_v)
										end
									else
										showing = false
										submenuOpen = nil
										dropdownToggle.Rotation = 90
										newDropdown.ZIndex = 1
										sectionHolder.ZIndex = 1
										colored_dropdown_BackgroundColor3[3] = "topGradient"
										colored_dropdown_BackgroundColor3[4] = nil
										colored_dropdown_ImageColor3[3] = "bottomGradient"
										colored_dropdown_ImageColor3[4] = nil
										tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
											BackgroundColor3 = library.colors.topGradient,
											ImageColor3 = library.colors.bottomGradient
										}):Play()
										dropdownHolderFrame.Visible = false
									end
								end
								for ins, z in next, restorezindex do
									ins.ZIndex = z
								end
							end
						end)
						library.signals[1 + #library.signals] = optionButton.MouseEnter:Connect(function()
							tweenService:Create(newOption, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
								BackgroundColor3 = library.colors.hoveredOptionTop,
								ImageColor3 = library.colors.hoveredOptionBottom
							}):Play()
						end)
						library.signals[1 + #library.signals] = optionButton.MouseLeave:Connect(function()
							local togged = (not multiselect and selectedOption == v) or (multiselect and table.find(selectedOption, v))
							tweenService:Create(newOption, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
								BackgroundColor3 = (togged and library.colors.selectedOption) or library.colors.topGradient,
								ImageColor3 = (togged and library.colors.unselectedOption) or library.colors.bottomGradient
							}):Play()
						end)
						UpdateDropdownHolder()
					end
				end
				local precisionscrolling = nil
				local function display(dropdownEnabled)
					list = resolvelist()
					if dropdownEnabled then
						AddOptions(list)
						submenuOpen = dropdown
						dropdownToggle.Rotation = 270
						restorezindex[newSection] = restorezindex[newSection] or newSection.ZIndex
						restorezindex[newDropdown] = restorezindex[newDropdown] or newDropdown.ZIndex
						restorezindex[sectionHolder] = restorezindex[sectionHolder] or sectionHolder.ZIndex
						newSection.ZIndex = 50 + newSection.ZIndex
						newDropdown.ZIndex = 2
						sectionHolder.ZIndex = 2
						colored_dropdown_BackgroundColor3[3] = "main"
						colored_dropdown_BackgroundColor3[4] = 1.5
						colored_dropdown_ImageColor3[3] = "main"
						colored_dropdown_ImageColor3[4] = 2.5
						tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = darkenColor(library.colors.main, 1.5),
							ImageColor3 = darkenColor(library.colors.main, 2.5)
						}):Play()
						dropdownHolderFrame.Visible = true
						if not options.DisablePrecisionScrolling then
							local upkey = options.ScrollUpButton or library.scrollupbutton or shared.scrollupbutton or Enum.KeyCode.Up
							local downkey = options.ScrollDownButton or library.scrolldownbutton or shared.scrolldownbutton or Enum.KeyCode.Down
							precisionscrolling = (precisionscrolling and precisionscrolling:Disconnect() and nil) or userInputService.InputBegan:Connect(function(input)
								if input.UserInputType == Enum.UserInputType.Keyboard then
									local code = input.KeyCode
									local isup = code == upkey
									local isdown = code == downkey
									if isup or isdown then
										local txt = userInputService:GetFocusedTextBox()
										if not txt or txt == dropdownSelection then
											while wait_check() and userInputService:IsKeyDown(code) do
												realDropdownHolder.CanvasPosition = Vector2:new(math.clamp(realDropdownHolder.CanvasPosition.Y + ((isup and -5) or 5), 0, realDropdownHolder.AbsoluteCanvasSize.Y))
											end
										end
									end
								end
							end)
							library.signals[1 + #library.signals] = precisionscrolling
						end
					else
						submenuOpen = nil
						dropdownToggle.Rotation = 90
						colored_dropdown_BackgroundColor3[3] = "topGradient"
						colored_dropdown_BackgroundColor3[4] = nil
						colored_dropdown_ImageColor3[3] = "bottomGradient"
						colored_dropdown_ImageColor3[4] = nil
						tweenService:Create(dropdown, TweenInfo.new(0.35, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = library.colors.topGradient,
							ImageColor3 = library.colors.bottomGradient
						}):Play()
						dropdownHolderFrame.Visible = false
						for ins, z in next, restorezindex do
							ins.ZIndex = z
						end
						precisionscrolling = (precisionscrolling and precisionscrolling:Disconnect() and nil) or nil
					end
					if not multiselect and (not next(list) or not table.find(list, library_flags[flagName])) then
						Set(list[1])
					end
					showing = dropdownEnabled
				end
				library.signals[1 + #library.signals] = newDropdown.InputEnded:Connect(function(input)
					if not library.colorpicker and input.UserInputType == Enum.UserInputType.MouseButton1 then
						showing = not showing
						display(showing)
					end
				end)
				library.signals[1 + #library.signals] = newDropdown.MouseEnter:Connect(function()
					colored_dropdown_BackgroundColor3[3] = "main"
					colored_dropdown_BackgroundColor3[4] = 1.5
					colored_dropdown_ImageColor3[3] = "main"
					colored_dropdown_ImageColor3[4] = 2.5
					tweenService:Create(dropdown, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
				end)
				library.signals[1 + #library.signals] = newDropdown.MouseLeave:Connect(function()
					if not dropdownEnabled then
						colored_dropdown_BackgroundColor3[3] = "topGradient"
						colored_dropdown_BackgroundColor3[4] = nil
						colored_dropdown_ImageColor3[3] = "bottomGradient"
						colored_dropdown_ImageColor3[4] = nil
						tweenService:Create(dropdown, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = library.colors.topGradient,
							ImageColor3 = library.colors.bottomGradient
						}):Play()
					end
				end)
				library.signals[1 + #library.signals] = dropdownToggle.MouseButton1Click:Connect(function()
					if not library.colorpicker then
						showing = not showing
						display(showing)
					end
				end)
				AddOptions(list)
				local default = library_flags[flagName]
				local function update()
					dropdownName, callback = options.Name or dropdownName, options.Callback
					local sstr = (passed_multiselect == "string" and multiselect) or (library_flags[flagName] and tostring(library_flags[flagName])) or (selectedOption and tostring(selectedOption)) or blankstring or "nil"
					if dropdownSelection.Text ~= sstr then
						dropdownSelection.Text = sstr
					end
					dropdownHeadline.Text = (dropdownName and tostring(dropdownName)) or "???"
					return sstr
				end
				local function validate(fallbackValue)
					if list and table.find(list, library_flags[flagName]) then
						update()
						return true
					end
					if fallbackValue ~= nil then
						if fallbackValue == "__DEFAULT" then
							fallbackValue = fallbackValue
						end
					else
						fallbackValue = list[1]
					end
					return Set((multiselect and {fallbackValue}) or fallbackValue)
				end
				local objectdata = {
					Options = options,
					Name = flagName,
					Flag = flagName,
					Type = "Dropdown",
					Default = default,
					Parent = sectionFunctions,
					Instance = dropdownSelection,
					Get = function()
						return library_flags[flagName]
					end,
					Set = Set,
					RawSet = ((multiselect and function(t, dat)
						if nil == dat and t ~= nil then
							dat = t
						end
						local lastv = library_flags[flagName]
						if not lastv or selectedOption ~= lastv then
							if lastv and type(lastv) == "table" then
								selectedOption = library_flags[flagName]
							else
								library_flags[flagName] = selectedOption
							end
							warn("Attempting to use new table for", flagName, " Please use :Set(), as setting through flags table may cause errors", debug.traceback(""))
							lastv = library_flags[flagName]
						end
						local cloned = {unpack(selectedOption)}
						if not dat then
							if #selectedOption ~= 0 then
								table.clear(selectedOption)
							end
							return selectedOption
						elseif type(dat) ~= "table" then
							warn("Expected table for argument #1 on Set for MultiSelect dropdown. Got", dat, debug.traceback(""))
							return selectedOption
						end
						for k = table.pack(unpack(dat)).n, 1, -1 do
							if dat[k] == nil then
								table.remove(dat, k)
							end
						end
						table.clear(selectedOption)
						for k, v in next, dat do
							selectedOption[k] = v
						end
						return selectedOption
					end) or function(t, str)
						if nil == str and t ~= nil then
							str = t
						end
						selectedOption = str
						library_flags[flagName] = str
						if options.Location then
							options.Location[options.LocationFlag or flagName] = str
						end
						update()
						return str
					end),
					Update = update,
					Reset = function()
						return Set(nil, default)
					end
				}
				function objectdata.UpdateList(t, listt, updateValues)
					if (nil == listt and t ~= nil) or (type(t) == "table" and type(listt) ~= "table") then
						listt, updateValues = t, listt
					end
					if listt == objectdata then
						listt = nil
					end
					resolvelist = getresolver(listt or options.List, options.Filter, options.Method)
					list = resolvelist()
					if updateValues then
						validate()
					end
					if showing then
						display(false)
						display(true)
					end
					return list
				end
				tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.AddDropDown = sectionFunctions.AddDropdown
			sectionFunctions.NewDropDown = sectionFunctions.AddDropdown
			sectionFunctions.NewDropdown = sectionFunctions.AddDropdown
			sectionFunctions.CreateDropdown = sectionFunctions.AddDropdown
			sectionFunctions.CreateDropdown = sectionFunctions.AddDropdown
			sectionFunctions.DropDown = sectionFunctions.AddDropdown
			sectionFunctions.Dropdown = sectionFunctions.AddDropdown
			sectionFunctions.DD = sectionFunctions.AddDropdown
			sectionFunctions.Dd = sectionFunctions.AddDropdown
			function sectionFunctions:AddColorpicker(options, ...)
				options = (options and type(options) == "string" and resolvevararg("Colorpicker", options, ...)) or options
				if options.Random == true then
					options.Value = "random"
				elseif options.Rainbow == true then
					options.Value = "rainbow"
				end
				local colorPickerName, presetColor, callback, flagName = assert(options.Name, "Missing Name for new colorpicker."), options.Value, options.Callback, options.Flag or (function()
					library.unnamedcolorpicker = 1 + (library.unnamedcolorpicker or 0)
					return "Colorpicker" .. tostring(library.unnamedcolorpicker)
				end)()
				if elements[flagName] ~= nil then
					warn(debug.traceback("Warning! Re-used flag '" .. flagName .. "'", 3))
				end
				local designers = options.__designer
				options.__designer = nil
				local rainbowColorMode = false
				if presetColor == "random" then
					presetColor = Color3.new(math.random(), math.random(), math.random())
				elseif presetColor == "rainbow" then
					presetColor = Color3.new(1, 1, 1)
					rainbowColorMode = true
				end
				local newColorPicker = Instance_new("Frame")
				local colorPicker = Instance_new("ImageLabel")
				local colorPickerInner = Instance_new("ImageLabel")
				local colorPickerHeadline = Instance_new("TextLabel")
				local colorPickerButton = Instance_new("TextButton")
				local colorPickerHolderFrame = Instance_new("ImageLabel")
				local colorPickerHolderInner = Instance_new("ImageLabel")
				local color = Instance_new("ImageLabel")
				local selectorColor = Instance_new("Frame")
				local hue = Instance_new("ImageLabel")
				local hueGradient = Instance_new("UIGradient")
				local selectorHue = Instance_new("Frame")
				local randomColor = Instance_new("ImageLabel")
				local randomColorInner = Instance_new("ImageLabel")
				local randomColorButton = Instance_new("ImageButton")
				local hexInputBox = Instance_new("TextBox")
				local hexInput = Instance_new("ImageLabel")
				local hexInputInner = Instance_new("ImageLabel")
				local rainbow = Instance_new("ImageLabel")
				local rainbowInner = Instance_new("ImageLabel")
				local rainbowButton = Instance_new("ImageButton")
				local startingColor = presetColor or Color3.new(1, 1, 1)
				local colorPickerEnabled = false
				local colorH, colorS, colorV = 1, 1, 1
				local colorInput, hueInput = nil, nil
				local oldBackgroundColor = Color3.new()
				local oldImageColor = oldBackgroundColor
				local oldColor = oldBackgroundColor
				local rainbowColorValue = 0
				newColorPicker.Name = "newColorPicker"
				newColorPicker.Parent = sectionHolder
				newColorPicker.BackgroundColor3 = Color3.new(1, 1, 1)
				newColorPicker.BackgroundTransparency = 1
				newColorPicker.Size = UDim2.new(1, 0, 0, 19)
				colorPicker.Name = "colorPicker"
				colorPicker.Parent = newColorPicker
				colorPicker.Active = true
				colorPicker.BackgroundColor3 = library.colors.topGradient
				local colored_colorPicker_BackgroundColor3 = {colorPicker, "BackgroundColor3", "topGradient"}
				colored[1 + #colored] = colored_colorPicker_BackgroundColor3
				colorPicker.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {colorPicker, "BorderColor3", "elementBorder"}
				colorPicker.Position = UDim2.fromScale(0.842, 0.113)
				colorPicker.Selectable = true
				colorPicker.Size = UDim2.fromOffset(24, 12)
				colorPicker.Image = "rbxassetid://2454009026"
				colorPicker.ImageColor3 = library.colors.bottomGradient
				local colored_colorPicker_ImageColor3 = {colorPicker, "ImageColor3", "bottomGradient"}
				colored[1 + #colored] = colored_colorPicker_ImageColor3
				colorPickerInner.Name = "colorPickerInner"
				colorPickerInner.Parent = colorPicker
				colorPickerInner.Active = true
				colorPickerInner.AnchorPoint = Vector2.new(0.5, 0.5)
				colorPickerInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {colorPickerInner, "BorderColor3", "elementBorder"}
				colorPickerInner.Position = UDim2.fromScale(0.5, 0.5)
				colorPickerInner.Selectable = true
				colorPickerInner.Size = UDim2.new(1, -4, 1, -4)
				colorPickerInner.Image = "rbxassetid://2454009026"
				colorPickerInner.BackgroundColor3 = darkenColor(startingColor, 1.5)
				colorPickerInner.ImageColor3 = darkenColor(startingColor, 2.5)
				colorPickerHeadline.Name = "colorPickerHeadline"
				colorPickerHeadline.Parent = newColorPicker
				colorPickerHeadline.BackgroundColor3 = Color3.new(1, 1, 1)
				colorPickerHeadline.BackgroundTransparency = 1
				colorPickerHeadline.Position = UDim2.fromScale(0.034, 0.113)
				colorPickerHeadline.Size = UDim2.fromOffset(173, 11)
				colorPickerHeadline.Font = Enum.Font.Code
				colorPickerHeadline.Text = colorPickerName or "???"
				colorPickerHeadline.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {colorPickerHeadline, "TextColor3", "elementText"}
				colorPickerHeadline.TextSize = 14
				colorPickerHeadline.TextXAlignment = Enum.TextXAlignment.Left
				colorPickerButton.Name = "colorPickerButton"
				colorPickerButton.Parent = newColorPicker
				colorPickerButton.BackgroundColor3 = Color3.new(1, 1, 1)
				colorPickerButton.BackgroundTransparency = 1
				colorPickerButton.Size = UDim2.fromScale(1, 1)
				colorPickerButton.ZIndex = 5
				colorPickerButton.Font = Enum.Font.SourceSans
				colorPickerButton.Text = ""
				colorPickerButton.TextColor3 = Color3.new()
				colorPickerButton.TextSize = 14
				colorPickerButton.TextTransparency = 1
				colorPickerButton.BorderColor3 = library.colors.elementBorder
				local colored_colorPickerButton_BorderColor3 = {colorPickerButton, "BorderColor3", "elementBorder"}
				colored[1 + #colored] = colored_colorPickerButton_BorderColor3
				local function UpdateColorPicker(force, rainbsow)
					local last_vv = library_flags[flagName]
					local newColor = force or Color3.fromHSV(colorH, colorS, colorV)
					if not force then
						colorH, colorS, colorV = newColor:ToHSV()
					end
					colorPickerInner.BackgroundColor3 = darkenColor(newColor, 1.5)
					colorPickerInner.ImageColor3 = darkenColor(newColor, 2.5)
					color.BackgroundColor3 = Color3.fromHSV(colorH, 1, 1)
					library_flags[flagName] = newColor
					if options.Location then
						options.Location[options.LocationFlag or flagName] = newColor
					end
					hexInputBox.Text = Color3ToHex(newColor)
					if force then
						color.BackgroundColor3 = force
						selectorColor.Position = UDim2.new(force and select(3, Color3.toHSV(force)))
					end
					local pos = 1 - (Color3.toHSV(newColor))
					local scalex = selectorHue.Position.X.Scale
					if scalex ~= pos and not ((pos == 0 or pos == 1) and (scalex == 1 or scalex == 0)) then
						selectorHue.Position = UDim2.new(pos)
					end
					if callback and last_vv ~= newColor then
						task.spawn(callback, newColor, last_vv, rainbsow)
					end
				end
				library.signals[1 + #library.signals] = colorPickerButton.MouseButton1Click:Connect(function()
					if submenuOpen == colorPicker or submenuOpen == nil then
						colorPickerEnabled = not colorPickerEnabled
						library.colorpicker = colorPickerEnabled
						colorPickerHolderFrame.Visible = colorPickerEnabled
						if colorPickerEnabled then
							for _, v in next, colorpickerconflicts do
								v.Visible = false
							end
							submenuOpen = colorPicker
							newColorPicker.ZIndex = 2
							newSection.ZIndex = 100 + newSection.ZIndex
							colorPickerButton.BorderColor3 = library.colors.main
							colored_colorPickerButton_BorderColor3[3] = "main"
							UpdateColorPicker()
						else
							for _, v in next, colorpickerconflicts do
								v.Visible = true
							end
							submenuOpen = nil
							newColorPicker.ZIndex = 0
							newSection.ZIndex = newSection.ZIndex - 100
							colorPickerButton.BorderColor3 = library.colors.elementBorder
							colored_colorPickerButton_BorderColor3[3] = "elementBorder"
						end
					end
				end)
				colorPickerHolderFrame.Name = "colorPickerHolderFrame"
				colorPickerHolderFrame.Parent = newColorPicker
				colorPickerHolderFrame.Active = true
				colorPickerHolderFrame.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {colorPickerHolderFrame, "BackgroundColor3", "topGradient"}
				colorPickerHolderFrame.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {colorPickerHolderFrame, "BorderColor3", "elementBorder"}
				colorPickerHolderFrame.Selectable = true
				colorPickerHolderFrame.Position = UDim2.fromScale(0.025, 1.012)
				colorPickerHolderFrame.Size = UDim2.fromOffset(206, 250)
				if math.ceil(colorPickerHolderFrame.AbsolutePosition.Y + colorPickerHolderFrame.AbsoluteSize.Y) > floor(newTabHolder.AbsoluteSize.Y + newTabHolder.AbsolutePosition.Y) then
					colorPickerHolderFrame.Position = UDim2.new(0.025, 0, 1.012, -colorPickerHolderFrame.AbsoluteSize.Y - colorPickerButton.AbsoluteSize.Y - 2)
				end
				colorPickerHolderFrame.Visible = false
				colorPickerHolderFrame.Image = "rbxassetid://2454009026"
				colorPickerHolderFrame.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {colorPickerHolderFrame, "ImageColor3", "bottomGradient"}
				colorPickerHolderInner.Name = "colorPickerHolderInner"
				colorPickerHolderInner.Parent = colorPickerHolderFrame
				colorPickerHolderInner.Active = true
				colorPickerHolderInner.AnchorPoint = Vector2.new(0.5, 0.5)
				colorPickerHolderInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {colorPickerHolderInner, "BackgroundColor3", "topGradient"}
				colorPickerHolderInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {colorPickerHolderInner, "BorderColor3", "elementBorder"}
				colorPickerHolderInner.Position = UDim2.fromScale(0.5, 0.5)
				colorPickerHolderInner.Selectable = true
				colorPickerHolderInner.Size = UDim2.new(1, -4, 1, -4)
				colorPickerHolderInner.Image = "rbxassetid://2454009026"
				colorPickerHolderInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {colorPickerHolderInner, "ImageColor3", "bottomGradient"}
				color.Name = "color"
				color.Parent = colorPickerHolderInner
				color.BackgroundColor3 = startingColor
				color.BorderSizePixel = 0
				color.Position = UDim2.fromOffset(5, 5)
				color.Size = UDim2.new(1, -10, 0, 192)
				color.Image = "rbxassetid://4155801252"
				selectorColor.Name = "selectorColor"
				selectorColor.Parent = color
				selectorColor.AnchorPoint = Vector2.new(0.5, 0.5)
				selectorColor.BackgroundColor3 = Color3.fromRGB(144, 144, 144)
				selectorColor.BorderColor3 = Color3.fromRGB(69, 65, 70)
				selectorColor.Position = UDim2.new(startingColor and select(3, Color3.toHSV(startingColor)))
				selectorColor.Size = UDim2.fromOffset(4, 4)
				hue.Name = "hue"
				hue.Parent = colorPickerHolderInner
				hue.BackgroundColor3 = Color3.new(1, 1, 1)
				hue.BorderSizePixel = 0
				hue.Position = UDim2.fromOffset(5, 202)
				hue.Size = UDim2.new(1, -10, 0, 14)
				hue.Image = "rbxassetid://3570695787"
				hue.ScaleType = Enum.ScaleType.Slice
				hue.SliceScale = 0.01
				hueGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromRGB(255, 0, 4)), ColorSequenceKeypoint.new(0.17, Color3.fromRGB(235, 7, 255)), ColorSequenceKeypoint.new(0.33, Color3:fromRGB(9, 189)), ColorSequenceKeypoint.new(0.5, Color3:fromRGB(193, 196)), ColorSequenceKeypoint.new(0.66, Color3:new(1)), ColorSequenceKeypoint.new(0.84, Color3.fromRGB(255, 247)), ColorSequenceKeypoint.new(1, Color3.new(1))})
				hueGradient.Name = "hueGradient"
				hueGradient.Parent = hue
				selectorHue.Name = "selectorHue"
				selectorHue.Parent = hue
				selectorHue.BackgroundColor3 = Color3:fromRGB(125, 255)
				selectorHue.BackgroundTransparency = 0.2
				selectorHue.BorderColor3 = Color3:fromRGB(84, 91)
				selectorHue.Position = UDim2.new(1 - (Color3.toHSV(startingColor)))
				selectorHue.Size = UDim2:new(2, 1)
				hexInput.Name = "hexInput"
				hexInput.Parent = colorPickerHolderInner
				hexInput.Active = true
				hexInput.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {hexInput, "BackgroundColor3", "topGradient"}
				hexInput.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {hexInput, "BorderColor3", "elementBorder"}
				hexInput.Position = UDim2.fromOffset(5, 223)
				hexInput.Selectable = true
				hexInput.Size = UDim2.fromOffset(150, 18)
				hexInput.Image = "rbxassetid://2454009026"
				hexInput.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {hexInput, "ImageColor3", "bottomGradient"}
				hexInputInner.Name = "hexInputInner"
				hexInputInner.Parent = hexInput
				hexInputInner.Active = true
				hexInputInner.AnchorPoint = Vector2.new(0.5, 0.5)
				hexInputInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {hexInputInner, "BackgroundColor3", "topGradient"}
				hexInputInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {hexInputInner, "BorderColor3", "elementBorder"}
				hexInputInner.Position = UDim2.fromScale(0.5, 0.5)
				hexInputInner.Selectable = true
				hexInputInner.Size = UDim2.new(1, -4, 1, -4)
				hexInputInner.Image = "rbxassetid://2454009026"
				hexInputInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {hexInputInner, "ImageColor3", "bottomGradient"}
				hexInputBox.Name = "hexInputBox"
				hexInputBox.Parent = hexInput
				hexInputBox.BackgroundColor3 = Color3.new(1, 1, 1)
				hexInputBox.BackgroundTransparency = 1
				hexInputBox.Size = UDim2.fromScale(1, 1)
				hexInputBox.ZIndex = 5
				hexInputBox.Font = Enum.Font.Code
				hexInputBox.PlaceholderText = "Hex Input"
				hexInputBox.Text = Color3ToHex(startingColor)
				hexInputBox.TextColor3 = library.colors.elementText
				colored[1 + #colored] = {hexInputBox, "TextColor3", "elementText"}
				hexInputBox.TextSize = 14
				hexInputBox.ClearTextOnFocus = false
				randomColor.Name = "randomColor"
				randomColor.Parent = colorPickerHolderInner
				randomColor.Active = true
				randomColor.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {randomColor, "BackgroundColor3", "topGradient"}
				randomColor.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {randomColor, "BorderColor3", "elementBorder"}
				randomColor.Position = UDim2.fromOffset(158, 223)
				randomColor.Selectable = true
				randomColor.Size = UDim2.fromOffset(18, 18)
				randomColor.Image = "rbxassetid://2454009026"
				randomColor.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {randomColor, "ImageColor3", "bottomGradient"}
				randomColorInner.Name = "randomColorInner"
				randomColorInner.Parent = randomColor
				randomColorInner.Active = true
				randomColorInner.AnchorPoint = Vector2.new(0.5, 0.5)
				randomColorInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {randomColorInner, "BackgroundColor3", "topGradient"}
				randomColorInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {randomColorInner, "BorderColor3", "elementBorder"}
				randomColorInner.Position = UDim2.fromScale(0.5, 0.5)
				randomColorInner.Selectable = true
				randomColorInner.Size = UDim2.new(1, -4, 1, -4)
				randomColorInner.Image = "rbxassetid://2454009026"
				randomColorInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {randomColorInner, "ImageColor3", "bottomGradient"}
				randomColorButton.Name = "randomColorButton"
				randomColorButton.Parent = randomColor
				randomColorButton.BackgroundColor3 = Color3.new(1, 1, 1)
				randomColorButton.BackgroundTransparency = 1
				randomColorButton.Size = UDim2.fromScale(1, 1)
				randomColorButton.ZIndex = 5
				randomColorButton.Image = "rbxassetid://7484765651"
				rainbow.Name = "rainbow"
				rainbow.Parent = colorPickerHolderInner
				rainbow.Active = true
				rainbow.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {rainbow, "BackgroundColor3", "topGradient"}
				rainbow.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {rainbow, "BorderColor3", "elementBorder"}
				rainbow.Position = UDim2.fromOffset(158 + 18 + 4, 223)
				rainbow.Selectable = true
				rainbow.Size = UDim2.fromOffset(18, 18)
				rainbow.Image = "rbxassetid://2454009026"
				rainbow.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {rainbow, "ImageColor3", "bottomGradient"}
				rainbowInner.Name = "rainbowInner"
				rainbowInner.Parent = randomColor
				rainbowInner.Active = true
				rainbowInner.AnchorPoint = Vector2.new(0.5, 0.5)
				rainbowInner.BackgroundColor3 = library.colors.topGradient
				colored[1 + #colored] = {rainbowInner, "BackgroundColor3", "topGradient"}
				rainbowInner.BorderColor3 = library.colors.elementBorder
				colored[1 + #colored] = {rainbowInner, "BorderColor3", "elementBorder"}
				rainbowInner.Position = UDim2.fromScale(0.5, 0.5)
				rainbowInner.Selectable = true
				rainbowInner.Size = UDim2.new(1, -4, 1, -4)
				rainbowInner.Image = "rbxassetid://2454009026"
				rainbowInner.ImageColor3 = library.colors.bottomGradient
				colored[1 + #colored] = {rainbowInner, "ImageColor3", "bottomGradient"}
				rainbowButton.Name = "rainbowButton"
				rainbowButton.Parent = rainbow
				rainbowButton.BackgroundColor3 = Color3.new(1, 1, 1)
				rainbowButton.BackgroundTransparency = 1
				rainbowButton.Size = UDim2.fromScale(1, 1)
				rainbowButton.ZIndex = 5
				rainbowButton.Image = "rbxassetid://7484772919"
				local indexwith = (designers and "rainbows") or "rainbowsg"
				local function setrainbow(t, rainbowColorMod)
					if nil == rainbowColorMod and t ~= nil then
						rainbowColorMod = t
					end
					if rainbowColorMod == nil or type(rainbowColorMod) ~= "boolean" then
						rainbowColorMode = not rainbowColorMode
					else
						rainbowColorMode = rainbowColorMod
					end
					if colorInput then
						colorInput = (colorInput:Disconnect() and nil) or nil
					end
					if hueInput then
						hueInput = (hueInput:Disconnect() and nil) or nil
					end
					pcall(function()
						if destroyrainbows and library.rainbows <= 0 then
							destroyrainbows = nil
						end
						if destroyrainbowsg and library.rainbowsg <= 0 then
							destroyrainbowsg = nil
						end
					end)
					if rainbowColorMode then
						pcall(function()
							if not library.rainbowflags[flagName] then
								library[indexwith] = 1 + library[indexwith]
							end
							library.rainbowflags[flagName] = true
							oldImageColor = colorPickerInner.ImageColor3
							oldBackgroundColor = colorPickerInner.BackgroundColor3
							oldColor = color.BackgroundColor3
							pcall(function()
								local common_float = 1 / 255
								while wait_check() and rainbowColorMode and (options.Value == "rainbow" or ((not designers and not destroyrainbowsg) or (designers and not destroyrainbows))) do
									rainbowColorValue = common_float + rainbowColorValue
									if rainbowColorValue > 1 then
										rainbowColorValue = 0
									end
									colorH = rainbowColorValue
									UpdateColorPicker(Color3.fromHSV(rainbowColorValue, 1, 1), true)
								end
							end)
						end)
						pcall(function()
							rainbowColorMode = nil
							if library.rainbowflags[flagName] then
								library[indexwith] = library[indexwith] - 1
							end
							library.rainbowflags[flagName] = nil
						end)
					end
					UpdateColorPicker(library_flags[flagName])
				end
				library.signals[1 + #library.signals] = randomColorButton.MouseButton1Click:Connect(function()
					if rainbowColorMode then
						setrainbow(false)
					end
					UpdateColorPicker(Color3.fromRGB(math.random(0, 255), math.random(0, 255), math.random(0, 255)))
				end)
				library.signals[1 + #library.signals] = rainbowButton.MouseButton1Click:Connect(setrainbow)
				sectionFunctions:Update()
				library.signals[1 + #library.signals] = newColorPicker.MouseEnter:Connect(function()
					tweenService:Create(colorPicker, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
						BackgroundColor3 = darkenColor(library.colors.main, 1.5),
						ImageColor3 = darkenColor(library.colors.main, 2.5)
					}):Play()
					colored_colorPicker_BackgroundColor3[3] = "main"
					colored_colorPicker_BackgroundColor3[4] = 1.5
					colored_colorPicker_ImageColor3[3] = "main"
					colored_colorPicker_ImageColor3[4] = 2.5
				end)
				library.signals[1 + #library.signals] = newColorPicker.MouseLeave:Connect(function()
					if not colorPickerEnabled then
						tweenService:Create(colorPicker, TweenInfo.new(0.25, library.configuration.easingStyle, library.configuration.easingDirection), {
							BackgroundColor3 = library.colors.topGradient,
							ImageColor3 = library.colors.bottomGradient
						}):Play()
						colored_colorPicker_BackgroundColor3[3] = "topGradient"
						colored_colorPicker_BackgroundColor3[4] = nil
						colored_colorPicker_ImageColor3[3] = "bottomGradient"
						colored_colorPicker_ImageColor3[4] = nil
					end
				end)
				hexInputBox.FocusLost:Connect(function()
					if #hexInputBox.Text > 5 then
						local last_vv = library_flags[flagName]
						local not_fucked, clr = pcall(Color3FromHex, hexInputBox.Text)
						UpdateColorPicker((not_fucked and clr) or last_vv)
					end
				end)
				colorH = 1 - (math.clamp(selectorHue.AbsolutePosition.X - hue.AbsolutePosition.X, 0, hue.AbsoluteSize.X) / hue.AbsoluteSize.X)
				colorS = (math.clamp(selectorColor.AbsolutePosition.X - color.AbsolutePosition.X, 0, color.AbsoluteSize.X) / color.AbsoluteSize.X)
				colorV = 1 - (math.clamp(selectorColor.AbsolutePosition.Y - color.AbsolutePosition.Y, 0, color.AbsoluteSize.Y) / color.AbsoluteSize.Y)
				library.signals[1 + #library.signals] = color.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						isDraggingSomething = true
						colorInput = (colorInput and colorInput:Disconnect() and nil) or runService.RenderStepped:Connect(function()
							local colorX = (math.clamp(mouse.X - color.AbsolutePosition.X, 0, color.AbsoluteSize.X) / color.AbsoluteSize.X)
							local colorY = (math.clamp(mouse.Y - color.AbsolutePosition.Y, 0, color.AbsoluteSize.Y) / color.AbsoluteSize.Y)
							selectorColor.Position = UDim2.fromScale(colorX, colorY)
							colorS = colorX
							colorV = 1 - colorY
							UpdateColorPicker()
						end)
						library.signals[1 + #library.signals] = colorInput
					end
				end)
				library.signals[1 + #library.signals] = color.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if colorInput then
							isDraggingSomething = false
							colorInput:Disconnect()
						end
					end
				end)
				library.signals[1 + #library.signals] = hue.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if hueInput then
							hueInput:Disconnect()
						end
						isDraggingSomething = true
						hueInput = runService.RenderStepped:Connect(function()
							local hueX = math.clamp(mouse.X - hue.AbsolutePosition.X, 0, hue.AbsoluteSize.X) / hue.AbsoluteSize.X
							selectorHue.Position = UDim2.new(hueX)
							colorH = 1 - hueX
							UpdateColorPicker()
						end)
						library.signals[1 + #library.signals] = hueInput
					end
				end)
				library.signals[1 + #library.signals] = hue.InputEnded:Connect(function(input)
					if hueInput and input.UserInputType == Enum.UserInputType.MouseButton1 then
						isDraggingSomething = false
						hueInput:Disconnect()
					end
				end)
				if rainbowColorMode then
					spawn(function()
						rainbowColorMode = nil
						setrainbow(true)
					end)
				end
				local function Set(t, clr)
					if clr == nil and t ~= nil then
						clr = t
					end
					if clr == "rainbow" then
						if not rainbowColorMode then
							task.spawn(setrainbow, true)
						end
						return
					elseif clr == "random" then
						clr = Color3.new(math.random(), math.random(), math.random())
					elseif type(clr) == "string" and tonumber(clr, 16) then
						clr = Color3FromHex(clr)
					end
					task.spawn(setrainbow, false)
					local last_v = library_flags[flagName]
					library_flags[flagName] = clr
					if options.Location then
						options.Location[options.LocationFlag or flagName] = clr
					end
					color.BackgroundColor3 = clr
					selectorColor.Position = UDim2.new(clr and select(3, Color3.toHSV(clr)))
					selectorHue.Position = UDim2.new(1 - (Color3.toHSV(clr)))
					colorPickerInner.BackgroundColor3 = darkenColor(clr, 1.5)
					colorPickerInner.ImageColor3 = darkenColor(clr, 2.5)
					hexInputBox.Text = Color3ToHex(clr)
					colorH, colorS, colorV = Color3.toHSV(clr)
					if callback and (last_v ~= clr or options.AllowDuplicateCalls) then
						task.spawn(callback, clr, last_v)
					end
					return clr
				end
				if presetColor ~= nil then
					Set(presetColor)
				else
					library_flags[flagName] = startingColor
					if options.Location then
						options.Location[options.LocationFlag or flagName] = startingColor
					end
				end
				local default = options.Value or startingColor or library_flags[flagName]
				local function update()
					colorPickerName, callback = options.Name or colorPickerName, options.Callback
					local clr = library_flags[flagName]
					color.BackgroundColor3 = clr
					selectorColor.Position = UDim2.new(clr and select(3, Color3.toHSV(clr)))
					selectorHue.Position = UDim2.new(1 - (Color3.toHSV(clr)))
					colorPickerInner.BackgroundColor3 = darkenColor(clr, 1.5)
					colorPickerInner.ImageColor3 = darkenColor(clr, 2.5)
					hexInputBox.Text = Color3ToHex(clr)
					colorPickerHeadline.Text = colorPickerName or "???"
					return clr
				end
				local objectdata = {
					Options = options,
					Name = flagName,
					Flag = flagName,
					Type = "Colorpicker",
					Default = default,
					Parent = sectionFunctions,
					Instance = newColorPicker,
					SetRainbow = setrainbow,
					Get = function()
						return library_flags[flagName]
					end,
					GetRainbow = function()
						return rainbowColorMode
					end,
					Set = Set,
					RawSet = function(t, clr)
						if clr == nil and t ~= nil then
							clr = t
						end
						if clr == "rainbow" then
							if not rainbowColorMode then
								task.spawn(setrainbow, true)
							end
							return clr
						elseif clr == "random" then
							clr = Color3.new(math.random(), math.random(), math.random())
						elseif clr and type(clr) == "string" and tonumber(clr, 16) then
							clr = Color3FromHex(clr)
						end
						task.spawn(setrainbow, false)
						library_flags[flagName] = clr
						if options.Location then
							options.Location[options.LocationFlag or flagName] = clr
						end
						return clr
					end,
					Update = update,
					Reset = function()
						return Set(nil, default)
					end
				}
				tabFunctions.Flags[flagName], sectionFunctions.Flags[flagName], elements[flagName] = objectdata, objectdata, objectdata
				return objectdata
			end
			sectionFunctions.AddColorPicker = sectionFunctions.AddColorpicker
			sectionFunctions.NewColorpicker = sectionFunctions.AddColorpicker
			sectionFunctions.NewColorPicker = sectionFunctions.AddColorpicker
			sectionFunctions.CreateColorPicker = sectionFunctions.AddColorpicker
			sectionFunctions.CreateColorpicker = sectionFunctions.AddColorpicker
			sectionFunctions.ColorPicker = sectionFunctions.AddColorpicker
			sectionFunctions.Colorpicker = sectionFunctions.AddColorpicker
			sectionFunctions.Cp = sectionFunctions.AddColorpicker
			sectionFunctions.CP = sectionFunctions.AddColorpicker
			function sectionFunctions:UpdateAll()
				local target = self or sectionFunctions
				if target and type(target) == "table" and target.Flags then
					for _, e in next, target.Flags do
						if e and type(e) == "table" and e.Update then
							pcall(e.Update)
						end
					end
				end
			end
			return sectionFunctions
		end
		tabFunctions.AddSection = tabFunctions.CreateSection
		tabFunctions.NewSection = tabFunctions.CreateSection
		tabFunctions.Section = tabFunctions.CreateSection
		tabFunctions.Sec = tabFunctions.CreateSection
		tabFunctions.S = tabFunctions.CreateSection
		function tabFunctions:UpdateAll()
			local target = self or tabFunctions
			if target and type(target) == "table" and target.Flags then
				for _, e in next, target.Flags do
					if e and type(e) == "table" and e.Update then
						pcall(e.Update)
					end
				end
			end
		end
		return tabFunctions
	end
	windowFunctions.AddTab = windowFunctions.CreateTab
	windowFunctions.NewTab = windowFunctions.CreateTab
	windowFunctions.Tab = windowFunctions.CreateTab
	windowFunctions.T = windowFunctions.CreateTab
	function windowFunctions:CreateDesigner(options, ...)
		options = (options and type(options) == "string" and resolvevararg("Tab", options, ...)) or options
		assert(shared.bypasstablimit or library.Designer == nil, "Designer already exists")
		options = options or {}
		options.Image = options.Image or 7483871523
		options.LastTab = true
		local designer = windowFunctions:CreateTab(options)
		local colorsection = designer:CreateSection({
			Name = "Colors"
		})
		local backgroundsection = designer:CreateSection({
			Name = "Background",
			Side = "right"
		})
		local detailssection = designer:CreateSection({
			Name = "Info"
		})
		local filessection = designer:CreateSection({
			Name = "Profiles",
			Side = "right"
		})
		local settingssection = designer:CreateSection({
			Name = "Settings",
			Side = "right"
		})
		local designerelements = {}
		library.designerelements = designerelements
		for _, v in next, {{"Main", "main"}, {"Background", "background"}, {"Outer Border", "outerBorder"}, {"Inner Border", "innerBorder"}, {"Top Gradient", "topGradient"}, {"Bottom Gradient", "bottomGradient"}, {"Section Background", "sectionBackground"}, {"Section", "section"}, {"Element Text", "elementText"}, {"Other Element Text", "otherElementText"}, {"Tab Text", "tabText"}, {"Element Border", "elementBorder"}, {"Selected Option", "selectedOption"}, {"Unselected Option", "unselectedOption"}, {"Hovered Option Top", "hoveredOptionTop"}, {"Unhovered Option Top", "unhoveredOptionTop"}, {"Hovered Option Bottom", "hoveredOptionBottom"}, {"Unhovered Option Bottom", "unhoveredOptionBottom"}} do
			local nam, codename = v[1], v[2]
			local cflag = "__Designer.Colors." .. codename
			designerelements[codename] = {
				Return = colorsection:AddColorpicker({
					Name = nam,
					Flag = cflag,
					Value = library.colors[codename],
					Callback = function(v, y)
						library.colors[codename] = v or y
					end,
					__designer = 1
				}),
				Flag = cflag
			}
		end
		local flags = {}
		local persistoptions = {
			Name = "Workspace Profile",
			Flag = "__Designer.Background.WorkspaceProfile",
			Flags = true,
			Suffix = "Config",
			Workspace = library.WorkspaceName or "Unnamed Workspace",
			Desginer = true
		}
		local daaata = {{"AddTextbox", "__Designer.Textbox.ImageAssetID", backgroundsection, {
			Name = "Image Asset ID",
			Placeholder = "rbxassetid://4427304036",
			Flag = "__Designer.Background.ImageAssetID",
			Value = "rbxassetid://4427304036",
			Callback = updatecolorsnotween
		}}, {"AddColorpicker", "__Designer.Colorpicker.ImageColor", backgroundsection, {
			Name = "Image Color",
			Flag = "__Designer.Background.ImageColor",
			Value = Color3.new(1, 1, 1),
			Callback = updatecolorsnotween,
			__designer = 1
		}}, {"AddSlider", "__Designer.Slider.ImageTransparency", backgroundsection, {
			Name = "Image Transparency",
			Flag = "__Designer.Background.ImageTransparency",
			Value = 95,
			Min = 0,
			Max = 100,
			Format = "Image Transparency: %s%%",
			Textbox = true,
			Callback = updatecolorsnotween
		}}, {"AddToggle", "__Designer.Toggle.UseBackgroundImage", backgroundsection, {
			Name = "Use Background Image",
			Flag = "__Designer.Background.UseBackgroundImage",
			Value = true,
			Callback = updatecolorsnotween
		}}, {"AddPersistence", "__Designer.Persistence.ThemeFile", filessection, {
			Name = "Theme Profile",
			Flag = "__Designer.Files.ThemeFile",
			Workspace = "Function Lib Themes",
			Flags = flags,
			Suffix = "Theme",
			Desginer = true
		}}, {"AddTextbox", "__Designer.Textbox.WorkspaceName", filessection, {
			Name = "Workspace Name",
			Value = library.WorkspaceName or "Unnamed Workspace",
			Flag = "__Designer.Files.WorkspaceFile",
			Callback = function(n, o)
				persistoptions.Workspace = n or o
			end
		}}, {"AddPersistence", "__Designer.Persistence.WorkspaceProfile", filessection, persistoptions}, {"AddButton", "__Designer.Button.TerminateGUI", settingssection, {{
			Name = "Terminate GUI",
			Callback = library.unload
		}, {
			Name = "Reset GUI",
			Callback = resetall
		}}}, {"AddKeybind", "__Designer.Keybind.ShowHideKey", settingssection, {
			Name = "Show/Hide Key",
			Location = library.configuration,
			Flag = "__Designer.Settings.ShowHideKey",
			LocationFlag = "hideKeybind",
			Value = library.configuration.hideKeybind,
			Callback = function()
				lasthidebing = os.clock()
			end
		}}}
		if setclipboard and daaata[8] then
			local common_table = daaata[8][4]
			if common_table then
				common_table[1 + #common_table] = {
					Name = "Join Discord",
					Callback = function()
						local http = game:GetService('HttpService') 
						local req =  http_request or request or HttpPost or syn.request 
						if req then
							req({
								Url = 'http://127.0.0.1:6463/rpc?v=1',
								Method = 'POST',
								Headers = {
									['Content-Type'] = 'application/json',
									Origin = 'https://discord.com'
								},
								Body = http:JSONEncode({
									cmd = 'INVITE_BROWSER',
									nonce = http:GenerateGUID(false),
									args = {code = 'uNQRZs6gzm'}
								})
							})
						end
					end
				}
				common_table = nil
			end
		end
		if options.Info then
			local typ = type(options.Info)
			if typ == "string" then
				daaata[1 + #daaata] = {"AddLabel", "__Designer.Label.Creator", detailssection, {
					Text = options.Info
				}}
			elseif typ == "table" and #options.Info > 0 then
				for _, v in next, options.Info do
					daaata[1 + #daaata] = {"AddLabel", "__Designer.Label.Creator", detailssection, {
						Text = tostring(v)
					}}
				end
			end
		end
		for _, v in next, daaata do
			designerelements[v[2]] = v[3][v[1]](v[3], v[4])
		end
		designerelements["__Designer.Textbox.WorkspaceName"]:Set(library.WorkspaceName or "Unnamed Workspace")
		for k, v in next, elements do
			if v and k and string.sub(k, 1, 11) == "__Designer." and v.Type and v.Type ~= "Persistence" then
				flags[1 + #flags] = k
			end
		end
		if library.Backdrop then
			library.Backdrop.Image = resolveid(library_flags["__Designer.Background.ImageAssetID"], "__Designer.Background.ImageAssetID") or ""
			library.Backdrop.Visible = not not library_flags["__Designer.Background.UseBackgroundImage"]
			library.Backdrop.ImageTransparency = (library_flags["__Designer.Background.ImageTransparency"] or 95) / 100
			library.Backdrop.ImageColor3 = library_flags["__Designer.Background.ImageColor"] or Color3.new(1, 1, 1)
		end
		local function setbackground(t, Asset, Transparency, Visible)
			if Visible == nil and t ~= nil and type(t) ~= "table" then
				Asset, Transparency, Visible = t, Transparency, Visible
			end
			if Visible == 0 or ((Asset == 0 or Asset == false) and Visible == nil and Transparency == nil) then
				Visible = false
			elseif Visible == 1 or ((Asset == 1 or Asset == true) and Visible == nil and Transparency == nil) then
				Visible = true
			elseif Asset == nil and Transparency == nil and Visible == nil then
				Visible = not library_flags["__Designer.Background.UseBackgroundImage"]
			end
			local temp = Asset and type(Asset)
			if Transparency == nil and Visible == nil and temp == "number" and ((Asset ~= 1 and Asset ~= 0) or (Asset > 0 and Asset <= 100)) then
				Transparency, Asset, temp = Asset, nil
			end
			if temp and ((temp == "number" and Asset > 1) or temp == "string") then
				designerelements["__Designer.Textbox.ImageAssetID"]:Set(Asset)
			end
			temp = tonumber(Transparency)
			if temp then
				designerelements["__Designer.Slider.ImageTransparency"]:Set(temp)
			end
			if Visible ~= nil then
				designerelements["__Designer.Toggle.UseBackgroundImage"]:Set(not not Visible)
			end
			return Asset, Transparency, Visible
		end
		local bk = options.Background or options.Backdrop or options.Grahpic
		if bk then
			if type(bk) == "table" then
				setbackground(bk.Asset or bk[1], bk.Transparency or bk[2], bk.Visible or bk[3])
			else
				setbackground(bk, 0, 1)
			end
		end
		library.Designer = {
			Options = options,
			Parent = windowFunctions,
			Name = "Designer",
			Flag = "Designer",
			Type = "Designer",
			Instance = designer,
			SetBackground = setbackground
		}
		local savestuff = library.elements["__Designer.Background.WorkspaceProfile"]
		if savestuff then
			library.LoadFile = savestuff.LoadFile
			library.LoadFileRaw = savestuff.LoadFileRaw
			library.LoadJSON = savestuff.LoadJSON
			library.LoadJSONRaw = savestuff.LoadJSONRaw
			library.SaveFile = savestuff.SaveFile
			library.GetJSON = savestuff.GetJSON
		end
		spawn(updatecolorsnotween)
		return library.Designer
	end
	windowFunctions.AddDesigner = windowFunctions.CreateDesigner
	windowFunctions.NewDesigner = windowFunctions.CreateDesigner
	windowFunctions.Designer = windowFunctions.CreateDesigner
	windowFunctions.D = windowFunctions.CreateDesigner
	function windowFunctions:UpdateAll()
		local target = self or windowFunctions
		if target and type(target) == "table" and target.Flags then
			for _, e in next, target.Flags do
				if e and type(e) == "table" and e.Update then
					pcall(e.Update)
				end
			end
			pcall(function()
				if library.Backdrop then
					library.Backdrop.Visible = not not library_flags["__Designer.Background.UseBackgroundImage"]
					library.Backdrop.Image = resolveid(library_flags["__Designer.Background.ImageAssetID"], "__Designer.Background.ImageAssetID") or ""
					library.Backdrop.ImageColor3 = library_flags["__Designer.Background.ImageColor"] or Color3.new(1, 1, 1)
					library.Backdrop.ImageTransparency = (library_flags["__Designer.Background.ImageTransparency"] or 95) / 100
				end
			end)
		end
	end
	library.UpdateAll = windowFunctions.UpdateAll
	if options.Themeable or options.DefaultTheme or options.Theme then
		spawn(function()
			local os_clock = os.clock
			local starttime = os_clock()
			while os_clock() - starttime < 12 do
				if homepage then
					windowFunctions.GoHome = homepage
					local x, e = pcall(homepage)
					if not x and e then
						warn("Error going to Homepage:", e)
					end
					x, e = nil
					break
				end
				task.wait()
			end
			local whatDoILookLike = options.Themeable or options.DefaultTheme or options.Theme
			windowFunctions:CreateDesigner((type(whatDoILookLike) == "table" and whatDoILookLike) or nil)
			if options.DefaultTheme or options.Theme then
				spawn(function()
					local content = options.DefaultTheme or options.Theme or options.JSON or options.ThemeJSON
					if content and type(content) == "string" and #content > 1 then
						local good, jcontent = JSONDecode(content)
						if good and jcontent then
							for cflag, val in next, jcontent do
								local data = elements[cflag]
								if data and data.Type ~= "Persistence" then
									if data.Set then
										data:Set(val)
									elseif data.RawSet then
										data:RawSet(val)
									else
										library.flags[cflag] = val
									end
								end
							end
						end
					end
				end)
			end
			os_clock, starttime = nil
		end)
	end
	return windowFunctions
end
library.NewWindow = library.CreateWindow
library.AddWindow = library.CreateWindow
library.Window = library.CreateWindow
library.W = library.CreateWindow

local Wait = library.subs.Wait

local PepsiUi = library:CreateWindow({
    Name = "Nagi Hub",
    Theme = {
        Image = "rbxassetid://7483871523",
        Info = "Info",
        Background = {
            Asset = "rbxassetid://5553946656"
        }
    }
})

local Page = PepsiUi:CreateTab({
    Name = "[General]"
})

local Page2 = PepsiUi:CreateTab({
    Name = "[PvP]"
})

local Page3 = PepsiUi:CreateTab({
    Name = "[Shop/Dungeon]"
})

local Page4 = PepsiUi:CreateTab({
    Name = "[Misc]"
})

local Main = Page:CreateSection({
    Name = "AutoFarm", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})

WeaponList = {}

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do  
    if v:IsA("Tool") then
        table.insert(WeaponList ,v.Name)
    end
end

Main:AddDropdown({
     Name = "Select Weapon",
     Flag = "Select Weapon",
     List = WeaponList,
     Value = _G.Settings.Select_Weapon,
     Callback = function(value)
     	 _G.Select_Weapon = value
          _G.Settings.Select_Weapon = value
          saveSettings()
      end
})

Main:AddButton({
    Name = "Refresh Weapon",
    Callback = function()
        table.clear(WeaponList)
        for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
            if v:IsA("Tool") then
                table.insert(WeaponList ,v.Name)
            end
        end
    end
})

local AutoFarm = Main:AddLabel({ Name = "❌ : AutoFarm" })
Main:AddToggle({
    Name = "AutoFarm",
	Value = _G.Settings.autofarmlevel, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Settings.autofarmlevel = value
        _G.AutoFarmLv = value
        _G.Settings.AutoFarm = value
     	if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
       saveSettings()
    end
})

spawn(function()
  while task.wait() do
	  pcall(function()
		if _G.Settings.autofarmlevel == true then
			AutoFarm:Set("✅ : AutoFarm")
		elseif _G.Settings.autofarmlevel == false then
			AutoFarm:Set("❌ : AutoFarm")
		end
	  end)
   end
end)

Main:AddToggle({
    Name = "AutoFarmFast",
	Value = _G.Settings.AutoFarmFast, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoFarmFast = value
        _G.Settings.AutoFarmFast = value
     	if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
     	saveSettings()
    end
})
Main:AddToggle({
	Name = "AutoBuy Abilities",
	Callback = function()
        while wait() do
	

            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
        
        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
        
        
        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
        
        
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
     end
end
})
spawn(function()  
    while task.wait() do --นี้
        pcall(function()
        if _G.Settings.autofarmlevel then
			local MyLevel = game.Players.LocalPlayer.Data.Level.Value
			local QuestC = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest
            if _G.AutoFarmFast and (MyLevel >= 30 and MyLevel <= 300) then
          	if MyLevel >= 30 and MyLevel <= 69 then
				CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
				BringMobFarm = false
                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                    if v.Name == "God's Guard [Lv. 450]" then
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            repeat task.wait()
                                EquipWeapon(_G.Select_Weapon)
								getgenv().noclip = true
                                _G.AutoFarmLv = false
                                v.HumanoidRootPart.CanCollide = false
                                v.Humanoid.WalkSpeed = 0
                                v.Head.CanCollide = false
								BringMobFarm = true
								PosMon = v.HumanoidRootPart.CFrame
								v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                v.HumanoidRootPart.Transparency = 1
                                getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            until not _G.Settings.autofarmlevel  or not v.Parent or v.Humanoid.Health <= 0
                        end
                    end
                end
                for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                    if v.Name == "God's Guard [Lv. 450]" then
                        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                     else
                     	_G.AutoFarmLv = false
                     	BringMobFarm = false
                     	UnEquipWeapon(_G.Select_Weapon)
						 getgenv().noclip = false
						CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
						getgenv().ToTarget(CFrameMon)
						if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
							end
						end
                   end
   			elseif MyLevel >= 70 and MyLevel <= 310 then
   			if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
           	    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
            	end
   			if QuestC.Visible == false then
   			CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
				BringMobFarm = false
                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                    if v.Name == "God's Guard [Lv. 450]" then
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            repeat task.wait()
                                EquipWeapon(_G.Select_Weapon)
								getgenv().noclip = true
                                _G.AutoFarmLv = true
                                v.HumanoidRootPart.CanCollide = false
                                v.Humanoid.WalkSpeed = 0
                                v.Head.CanCollide = false
                                v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                v.HumanoidRootPart.Transparency = 1
								BringMobFarm = true
								PosMon = v.HumanoidRootPart.CFrame
						        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            until not _G.Settings.autofarmlevel  or not v.Parent or v.Humanoid.Health <= 0
                        end
                    end
                end
                for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                    if v.Name == "God's Guard [Lv. 450]" then
                        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                     else
                     	_G.AutoFarmLv = true
                     	BringMobFarm = false
						 getgenv().noclip = false
                     	UnEquipWeapon(_G.Select_Weapon)
						CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.92542, -0.93441087, -6.77488776e-09, -0.356197298, 1.12145182e-08, 1, -4.84390199e-08, 0.356197298, -4.92565206e-08, -0.93441087)
						getgenv().ToTarget(CFrameMon)
						if _G.Settings.autofarmlevel and (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 3000 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
							end
						end
                   end
              elseif QuestC.Visible == true then
                local quest = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
  			  local Player = string.split(quest," ")[2]
     			getgenv().SelectPly = string.split(quest," ")[2]
     			if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
           		 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
            		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
           	 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
            		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
           	 	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
            		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
   		     end
     			if string.find(quest,"Defeat") then
     	 		  repeat task.wait()
        	  	    if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
            	 		   game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
        	    		end
						game:GetService("Players").LocalPlayer.PlayerGui.Main.InCombat.Visible = false
                        game:GetService("Players").LocalPlayer.PlayerGui.Main.SafeZone.Visible = false
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.PvpDisabled.Visible == true then
                           game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EnablePvp")
                       end
						 EquipWeapon(_G.Select_Weapon)
             		    TPPlayer(game:GetService("Players")[getgenv().SelectPly].Character.HumanoidRootPart.CFrame*CFrame.new(0,0,5))
             		    game:GetService("VirtualUser"):CaptureController()
            	   	  game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
     	  		      game.Players:FindFirstChild(Player).Character.HumanoidRootPart.Size = Vector3.new(120,120,120)
             			game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
						 game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
      			  until game.Players:FindFirstChild(Player).Character.Humanoid.Health <= 0 or not game.Players:FindFirstChild(Player) or not FastFarm()
        				if not game.Players:FindFirstChild(Player) then
         		  		 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
        				end   
     			  else
     					UnEquipWeapon(_G.Select_Weapon)
            			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("PlayerHunter")
     			end
		   end
				elseif MyLevel >= 300 and MyLevel <= 2400 then
			 if QuestC.Visible == false then
				_G.AutoFarmLv = true
			else
					_G.AutoFarmLv = true
					end
			 else
				_G.AutoFarmLv = true
           	end
     	 end
		 if _G.AutoFarmLv then
                CheckQuest()
                if QuestC.Visible == false then
                    CheckQuest()
                    repeat wait() getgenv().ToTarget(CFrameMon) until (CFrameMon.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30000 or not _G.Settings.autofarmlevel
                    if (CFrameMon.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 30000 then
						wait(.2)
						BringMobFarm = false
						getgenv().noclip = false
                        wait(.2)
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NameQuest,LevelQuest)
                        wait(0.5)
                        getgenv().ToTarget(CFrameMon)
                    end
                elseif QuestC.Visible == true then
                    CheckQuest()
                    if game:GetService("Workspace").Enemies:FindFirstChild(Mon) then
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                                if v.Name == Mon then
                                    if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                                        repeat game.RunService.Heartbeat:wait()
                                            EquipWeapon(_G.Select_Weapon)
											getgenv().noclip = true
                                            getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                            v.HumanoidRootPart.CanCollide = false
                                            PosMon = v.HumanoidRootPart.CFrame
                                            v.Humanoid.WalkSpeed = 20
                                            v.Head.CanCollide = false
											BringMobFarm = true
                                            v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                               			 v.HumanoidRootPart.Transparency = 1
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                        until not _G.Settings.autofarmlevel or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
                                    else
										CheckQuest()
                                        getgenv().ToTarget(CFrameMon)
                                    end
                                end
                                if not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
                   				 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
               				 end
                            end
                        end
                    else
                        BringMobFarm = false
						getgenv().noclip = false
                        if game:GetService("ReplicatedStorage"):FindFirstChild(Mon) then
                            getgenv().ToTarget(game:GetService("ReplicatedStorage"):FindFirstChild(Mon).HumanoidRootPart.CFrame * CFrame.new(5,10,7))
                               else
                                     getgenv().ToTarget(CFrameMon)
                                     UnEquipWeapon(_G.Select_Weapon)
									 getgenv().noclip = false
                                    end
                     	      end
                	      end
         		    end
				end
           end)
     end
 end)
 spawn(function()
    while task.wait() do
    if _G.Settings.autofarmlevel then
    function UseCode(Text)
                game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
            end
        UseCode("Enyo_is_Pro")
        UseCode("Magicbus")
        UseCode("JCWK")
        UseCode("Starcodeheo")
        UseCode("Bluxxy")
        UseCode("fudd10_v2")
        UseCode("3BVISITS")
        UseCode("UPD16")
        UseCode("FUDD10")
        UseCode("BIGNEWS")
        UseCode("Sub2OfficialNoobie")
        UseCode("SUB2GAMERROBOT_EXP1")
        UseCode("StrawHatMaine")
        UseCode("SUB2NOOBMASTER123")
        UseCode("Sub2Daigrock")
        UseCode("Axiore")
        UseCode("TantaiGaming")
        UseCode("STRAWHATMAINE")
        UseCode("kittgaming")
        UseCode("Magicbus")
        UseCode("JCWK")
        UseCode("Starcodeheo")
        UseCode("Bluxxy")
        UseCode("fudd10_v2")
        UseCode("Enyu_is_Pro")
        UseCode("Sub2Fer999")
        UseCode("THEGREATACE")
        UseCode("SUB2GAMERROBOT_EXP1")
        UseCode("Sub2OfficialNoobie")
        UseCode("StrawHatMaine")
        UseCode("SUB2NOOBMASTER123")
        UseCode("Sub2Daigrock")
        UseCode("Axiore")
        UseCode("TantaiGaming")
        UseCode("STRAWHATMAINE")
        UseCode("JCWK")
        UseCode("Sub2Fer999")
        UseCode("Magicbus")
        UseCode("Starcodeheo")
        UseCode("Bluxxy")
        UseCode("Sub2Fer999")
        UseCode("GAMERROBOT_YT")
            end
        end
    end)

 Main:AddLabel({
     Name = "The World",
     Flag = "The World"
 })
 Main:AddToggle({
    Name = "Auto New World",
	Value = _G.Settings.Auto_New_World, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_New_World = value
        _G.Settings.Auto_New_World = value
     	if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
     	saveSettings()
    end
})

		spawn(function()
				while wait() do
					pcall(function()
						if _G.Auto_New_World then
							if game.Players.LocalPlayer.Data.Level.Value >= 700 then
								if _G.Settings.autofarmlevel then
									_G.Setting.Config["AutoFarmLv"] = false
								end
								if game.Workspace.Map.Ice.Door.CanCollide == true and game.Workspace.Map.Ice.Door.Transparency == 0 then
									wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
									EquipWeapon("Key")
									repeat wait() getgenv().ToTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488)) until (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Settings.Main["Auto New World"]
									wait(3)
								elseif game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 then
									if game:GetService("Workspace").Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") then
										for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
											if v.Name == "Ice Admiral [Lv. 700] [Boss]" and v.Humanoid.Health > 0 then
												repeat wait()
													EquipWeapon(Weapon)
													getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
													v.HumanoidRootPart.Size = Vector3.new(60,60,60)
													v.HumanoidRootPart.Transparency = 1
													v.Humanoid.JumpPower = 0
													v.Humanoid.WalkSpeed = 0
													v.HumanoidRootPart.CanCollide = false
													v.Humanoid:ChangeState(11)
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
												until v.Humanoid.Health <= 0 or not v.Parent
												game:GetService("ReplicatedStorage"):InvokeServer("TravelDressrosa")
											end
										end
									else
										getgenv().ToTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488))
									end
								else
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
								end
							end
						end
					end)
				end
			end)
			
Main:AddToggle({
    Name = "Auto Third World",
	Value = _G.Settings.Auto_Third_World, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Third_World = value
        _G.Settings.Auto_Third_World = value
     	if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
     	saveSettings()
    end
})

    spawn(function()
        while wait() do
            if _G.Auto_Third_World then
                pcall(function()
                    if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1500 and World2 then
                        _G.AutoFarmLv = false
                        if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 0 then
                            getgenv().ToTarget(CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016))
                            if (CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
                                wait(1.5)
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
                            end
                            wait(1.8)
                            if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
                                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if v.Name == "rip_indra [Lv. 1500] [Boss]" then
                                        repeat wait()
                                            EquipWeapon(_G.Select_Weapon)
                                            v.HumanoidRootPart.Size = Vector3.new(50,50,50)
                                            v.HumanoidRootPart.CanCollide = false
                                            v.Humanoid.WalkSpeed = 0
                                            getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,_G.Select_Distance,0))
                                            game:GetService'VirtualUser':CaptureController()
                                            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                                            sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                        until _G.Auto_Third_World == false or v.Humanoid.Health <= 0 or not v.Parent
                                    end
                                end
                            elseif not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") and (CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
                                getgenv().ToTarget(CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016))
                            end
                        end
                    end
                end)
            end
        end
    end)
 
 local Settings = Page:CreateSection({
    Name = "Settings", -- ชื่อ
    Side = "Right" -- ตำแหน่ง Left/Right
})

Settings:AddToggle({
    Name = "BringMonster",
	Value = _G.Settings.BringMonster, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.BringMonster = value
        _G.Settings.BringMonster = value
        saveSettings()
    end
})

spawn(function()
	while true do wait()
		if setscriptable then
			setscriptable(game.Players.LocalPlayer, "SimulationRadius", true)
		end
		if sethiddenproperty then
			sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
		end
	end
end)
   spawn(function()
      while task.wait() do
            pcall(function()
                if _G.BringMonster and BringMobFarm then
                   for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                       if not string.find(v.Name,"Boss") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 500 then
                           if InMyNetWork(v.HumanoidRootPart) then
                               v.HumanoidRootPart.CFrame = PosMon
                               v.Humanoid.JumpPower = 0
                               v.Humanoid.WalkSpeed = 0
                               v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                               v.HumanoidRootPart.Transparency = 1
                               v.HumanoidRootPart.CanCollide = false
                               v.Head.CanCollide = false
                               if v.Humanoid:FindFirstChild("Animator") then
                                   v.Humanoid.Animator:Destroy()
                               end
                                  v.Humanoid:ChangeState(11)
                                  v.Humanoid:ChangeState(14)
                              end
                          end
                      end
                 end
            end)
       end
 end)
                
function InMyNetWork(object)
	if isnetworkowner then
		return isnetworkowner(object)
	else
		if (object.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 200 then 
			return true
		end
		return false
	end
end

Settings:AddDropdown({
     Name = "Select Fast Attack",
     Flag = "Normal",
     List = {"Normal" , "Fast", "Slow"},
     Value = _G.Settings.Select_Fast_Attack,
     Callback = function(value)
     	 _G.Select_Fast_Attack = value
          _G.Settings.Select_Fast_Attack = value
          saveSettings()
      end
})

if _G.Select_Fast_Attack == nil then
	_G.Select_Fast_Attack = "Normal" 
end

Settings:AddToggle({
    Name = "FastAttack",
	Value = _G.Settings.FastAttack, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.FastAttack = value
        _G.Settings.FastAttack = value
        saveSettings()
    end
})

coroutine.wrap(function()
	while task.wait(.1) do
		local ac = CombatFrameworkR.activeController
		if ac and ac.equipped then
			if _G.FastAttack then
				AttackFunction()
				if _G.Select_Fast_Attack == "Normal" then
					if tick() - cooldownfastattack > .9 then wait(.1) cooldownfastattack = tick() end
				elseif _G.Select_Fast_Attack == "Fast" then
					if tick() - cooldownfastattack > 1.5 then wait(.01) cooldownfastattack = tick() end
				elseif _G.Select_Fast_Attack == "Slow" then
					if tick() - cooldownfastattack > .3 then wait(.7) cooldownfastattack = tick() end
				end
			elseif _G.FastAttack == false then
				if ac.hitboxMagnitude ~= 55 then
					ac.hitboxMagnitude = 55
				end
				ac:attack()
			end
		end
	end
end)()

Settings:AddToggle({
    Name = "FastAttackGoot",
	Value = _G.Settings.FastAttackDev, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.FastAttackDev = value
        _G.Settings.FastAttackDev = value
        saveSettings()
    end
})

local Module = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
local CombatFramework = debug.getupvalues(Module)[2]
local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
spawn(function()
while true do
	if _G.FastAttackDev then
		pcall(function()
			CameraShakerR:Stop()
			CombatFramework.activeController.attacking = false
			CombatFramework.activeController.timeToNextAttack = 0 --0
			CombatFramework.activeController.increment = 3  --3
			CombatFramework.activeController.hitboxMagnitude = 150
			CombatFramework.activeController.blocking = false
			CombatFramework.activeController.timeToNextBlock = 0 --0
			CombatFramework.activeController.focusStart = 0
			CombatFramework.activeController.humanoid.AutoRotate = true
		end)
	end
	task.wait()
end
end)

spawn(function()
  while wait() do
  if _G.FastAttackDev then
	for i, v in pairs(game.Workspace["_WorldOrigin"]:GetChildren()) do
		if v.Name == "CurvedRing" or v.Name == "SlashHit" or v.Name == "DamageCounter" or v.Name == "SwordSlash" or v.Name == "SlashTail" or v.Name == "Sounds" then
			v:Destroy() 
		end
	end
end
end
end) 
getgenv().A = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib).wrapAttackAnimationAsync
getgenv().B = require(game.Players.LocalPlayer.PlayerScripts.CombatFramework.Particle).play
spawn(function()
while wait() do
  if _G.FastAttackDev then
		pcall(function()
			require(game:GetService("ReplicatedStorage").CombatFramework.RigLib).wrapAttackAnimationAsync =function(a1,a2,a3,a4,a5)
				local GetBladeHits = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib).getBladeHits(a2,a3,a4)
				if GetBladeHits then
					 require(game:GetService("ReplicatedStorage").CombatFramework.RigLib).play = function() end
					a1:Play(0.2, 0.2, 0.2)
					a5(GetBladeHits)
					 require(game:GetService("ReplicatedStorage").CombatFramework.RigLib).play = getgenv().B 
					wait(.5)
					a1:Stop()
				end
			end
		end)
	 end
end
end)

_G.Settings.Auto_Buso = true
Settings:AddToggle({
    Name = "AutoBuso",
	Value = _G.Settings.Auto_Buso, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Buso = value
        _G.Settings.Auto_Buso = value
        saveSettings()
    end
})

spawn(function()
    while wait(1) do
		pcall(function()
			if _G.Auto_Buso then
				if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
				else
					wait(3)
				end
			end
		end)
    end
end)

_G.Settings.DeleteDamageFx = true
Settings:AddToggle({
    Name = "DeleteDamageFx",
	Value = _G.Settings.DeleteDamageFx, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.DeleteDamageFx = value
        _G.Settings.DeleteDamageFx = value
   if _G.DeleteDamageFx == true then
	while _G.DeleteDamageFx do wait()
		for i, v in pairs(game.Workspace["_WorldOrigin"]:GetChildren()) do
			if v.Name == "CurvedRing" or v.Name == "DamageCounter" or v.Name == "SwordSlash" or v.Name == "Damage" or v.Name == "Sounds" then
				v:Destroy() 
			end
		end
	end
	end
        saveSettings()
    end
})
Settings:AddToggle({
    Name = "AutoSetSpawnPoint",
	Value = _G.Settings.AutoSetSpawnPoint, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoSetSpawnPoint = value
        _G.Settings.AutoSetSpawnPoint = value
        while _G.AutoSetSpawnPoint do wait()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("SetSpawnPoint")
        end
        saveSettings()
    end
})


Settings:AddButton({
    Name = "BoostFPS",
    Callback = function(t)
        table.clear(WeaponList)
        _G.BoostFPS = t
		local decalsyeeted = true
		local g = game
		local w = g.Workspace
		local l = g.Lighting
		local t = w.Terrain
		t.WaterWaveSize = 0
		t.WaterWaveSpeed = 0
		t.WaterReflectance = 0
		t.WaterTransparency = 0
		l.GlobalShadows = false
		l.FogEnd = 9e9
		l.Brightness = 0
		settings().Rendering.QualityLevel = "Level01"
		for i, v in pairs(g:GetDescendants()) do
			if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then 
				v.Material = "Plastic"
				v.Reflectance = 0
			elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
				v.Transparency = 1
			elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
				v.Lifetime = NumberRange.new(0)
			elseif v:IsA("Explosion") then
				v.BlastPressure = 1
				v.BlastRadius = 1
			elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
				v.Enabled = false
			elseif v:IsA("MeshPart") then
				v.Material = "Plastic"
				v.Reflectance = 0
				v.TextureID = 10385902758728957
			end
		end
		for i, e in pairs(l:GetChildren()) do
			if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
				e.Enabled = false
			end
		end
	if _G.BoostFPS then
		local decalsyeeted = true
		local g = game
		local w = g.Workspace
		local l = g.Lighting
		local t = w.Terrain
		t.WaterWaveSize = 0
		t.WaterWaveSpeed = 0
		t.WaterReflectance = 0
		t.WaterTransparency = 0
		l.GlobalShadows = false
		l.FogEnd = 9e9
		l.Brightness = 0
		settings().Rendering.QualityLevel = "Level01"
		for i, v in pairs(g:GetDescendants()) do
			if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then 
				v.Material = "Plastic"
				v.Reflectance = 0
			elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
				v.Transparency = 1
			elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
				v.Lifetime = NumberRange.new(0)
			elseif v:IsA("Explosion") then
				v.BlastPressure = 1
				v.BlastRadius = 1
			elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
				v.Enabled = false
			elseif v:IsA("MeshPart") then
				v.Material = "Plastic"
				v.Reflectance = 0
				v.TextureID = 10385902758728957
			end
		end
		for i, e in pairs(l:GetChildren()) do
			if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
				e.Enabled = false
			end
		end
	end
    end
})

Settings:AddLabel({
     Name = "Webhook",
     Flag = "Webhook"
 })

Settings:AddTextbox({
    Name = "Webhook link",
	Value = "link",
    Callback = function(x)
		Webhooklink = x
    end
})

Settings:AddButton({
    Name = "Send Webhook",
    Callback = function(t)
    	WebHookLog:WebHookKaiTanSend(Webhooklink)
    end
})

Settings:AddTextbox({
    Name = "BaseShee link",
	Value = "link",
    Callback = function(x)
		WebHookLog:SheetBestLogSend(Baselink)
    	_G.SendWebHookPing = x
    end
})

Settings:AddButton({
    Name = "Send BaseShee",
    Callback = function(t)
		Baselink = x
		_G.SendWebHookPing = x
    end
})

 local AutoStats = Page:CreateSection({
    Name = "Auto Stats", -- ชื่อ
    Side = "Right" -- ตำแหน่ง Left/Right
})

AutoStats:AddToggle({
    Name = "Auto_Kaitun",
	Value = _G.Settings.Auto_Kaitun, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Kaitun = value
        _G.Settings.Auto_Kaitun = value
        saveSettings()
    end
})

AutoStats:AddToggle({
    Name = "Auto_Melee",
	Value = _G.Settings.Auto_Melee, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Melee = value
        _G.Settings.Auto_Melee = value
        saveSettings()
    end
})

AutoStats:AddToggle({
    Name = "Auto_Defense",
	Value = _G.Settings.Auto_Defense, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Defense = value
        _G.Settings.Auto_Defense = value
        saveSettings()
    end
})

AutoStats:AddToggle({
    Name = "Auto_Sword",
	Value = _G.Settings.Auto_Sword, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Sword = value
        _G.Settings.Auto_Sword = value
        saveSettings()
    end
})

AutoStats:AddToggle({
    Name = "Auto_Gun",
	Value = _G.Settings.Auto_Gun, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Gun = value
        _G.Settings.Auto_Gun = value
        saveSettings()
    end
})

AutoStats:AddToggle({
    Name = "Auto_Demon_Fruit",
	Value = _G.Settings.Auto_Demon_Fruit, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Auto_Demon_Fruit = value
        _G.Settings.Auto_Demon_Fruit = value
        saveSettings()
    end
})

   AutoStats:AddSlider({
        Name = "Select Point",
        Flag = "Select_Point",
        Value = _G.Settings.Point,
        Min = 1,
        Max = 100,
        Textbox = true,
        Format = function(value)
            _G.Point = value
            _G.Settings.Point = value
            saveSettings()
            return "Point : " .. tostring(value)
        end
    })
    

spawn(function()
	while wait(.1) do
		if _G.Auto_Kaitun then
			if game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value >= 2400 then
				if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Defense",_G.PointStats)
				end
				else
				if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
				end
			end
		end
	end
end)

spawn(function()
    while wait() do
        pcall(function()
            if _G.Auto_Melee then
            	if _G.Auto_Kaitun == true then
            		if game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value >= 2400 then
               		 if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
                    		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
                		end
                	   else
                		if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
						end
                	end
                	else
                	if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
					end
                end
            end
        end)
    end
end)


spawn(function()
    while wait() do
        pcall(function()
            if _G.Auto_Defense then
            	if _G.Auto_Kaitun == true then
            		if game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value >= 2400 then
               		 if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
                    		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
                		end
                	   else
                		if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Defense",_G.PointStats)
						end
                	end
                	else
                	if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Defense",_G.PointStats)
					end
                end
            end
        end)
    end
end)

spawn(function()
    while wait() do
        pcall(function()
            if _G.Auto_Sword then
            	if _G.Auto_Kaitun == true then
            		if game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value >= 2400 then
               		 if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
                    		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
                		end
                	   else
                		if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Sword",_G.PointStats)
						end
                	end
                	else
                	if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Sword",_G.PointStats)
					end
                end
            end
        end)
    end
end)


spawn(function()
    while wait() do
        pcall(function()
            if _G.Auto_Gun then
            	if _G.Auto_Kaitun == true then
            		if game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value >= 2400 then
               		 if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
                    		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
                		end
                	   else
                		if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Gun",_G.PointStats)
						end
                	end
                	else
                	if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Gun",_G.PointStats)
					end
                end
            end
        end)
    end
end)

spawn(function()
    while wait() do
        pcall(function()
            if _G.Auto_Demon_Fruit then
            	if _G.Auto_Kaitun == true then
            		if game:GetService("Players")["LocalPlayer"].Data.Stats.Melee.Level.Value >= 2400 then
               		 if game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
                    		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Melee",_G.PointStats)
                		end
                	   else
                		if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Demon Fruit",_G.PointStats)
						end
                	end
                	else
                	if  game:GetService("Players")["LocalPlayer"].Data.Points.Value ~= 0 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint","Demon Fruit",_G.PointStats)
					end
                end
            end
        end)
    end
end)

local AutoFighting = Page:CreateSection({
    Name = "Auto Fighting", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})

AutoFighting:AddToggle({
    Name = "AutoFullyGodhuman",
	Value = _G.Settings.AutoFullyGodhuman, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoFullyGodhuman = value
        _G.Settings.AutoFullyGodhuman = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
       	 BringMobFarm = false
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
	while wait() do
		if _G.AutoFullyGodhuman then
			pcall(function()
			if game.Players.LocalPlayer.Character:FindFirstChild("Godhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Godhuman") then
				_G.Select_Weapon = "Godhuman"
				else
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step").Level.Value <= 399 and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value <= 399 and  game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value <= 399 and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon").Level.Value <= 399 then
					if not W3 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
					elseif W3 then
					if CheckMaterial("Fish Tail") <= 20 and W3 then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                  	  	if v.Name == "Fishman Raider [Lv. 1775]" or v.Name == "Fishman Captain [Lv. 1800]" then
                        		if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                           	 	repeat task.wait()
                               	 	EquipWeapon(_G.Select_Weapon)
                              		  v.HumanoidRootPart.CanCollide = false
                               	 	v.Humanoid.WalkSpeed = 0
                                		v.Head.CanCollide = false
										PosMon = v.HumanoidRootPart.CFrame
										BringMobFarm = true
                                		v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                		v.HumanoidRootPart.Transparency = 1
                                		getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                		game:GetService'VirtualUser':CaptureController()
                                		game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            		until not _G.AutoFullyGodhuman or not v.Parent or v.Humanoid.Health <= 0
                        		end
                  				else
									  BringMobFarm = false
                 					 getgenv().ToTarget(CFrame.new( -10993,332, -8940))
                   	 		end
              		  	end
						elseif CheckMaterial("Dragon Scale") <= 10 and W3 then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                  	  	if v.Name == "Fishman Raider [Lv. 1775]" or v.Name == "Fishman Captain [Lv. 1800]" then
                        		if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                           	 	repeat task.wait()
                               	 	EquipWeapon(_G.Select_Weapon)
                              		  v.HumanoidRootPart.CanCollide = false
                               	 	v.Humanoid.WalkSpeed = 0
                                		v.Head.CanCollide = false
										PosMon = v.HumanoidRootPart.CFrame
										BringMobFarm = true
                                		v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                		v.HumanoidRootPart.Transparency = 1
                                		getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                		game:GetService'VirtualUser':CaptureController()
                                		game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            		until not _G.AutoFullyGodhuman or not v.Parent or v.Humanoid.Health <= 0
                        		end
								else
									BringMobFarm = false
									getgenv().ToTarget(CFram.new(6594,383,139))
              		  		end
							end
							if CheckMaterial("Dragon Scale") >= 10 and CheckMaterial("Fish Tail") >= 20 then
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
							end
						end
						elseif not W2 then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
						elseif W2 then
						if CheckMaterial("Magma Ore") <= 20 and W2 then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                  	  	if v.Name == "Magma Ninja [Lv. 1175]" then
                        		if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                           	 	repeat task.wait()
                               	 	EquipWeapon(_G.Select_Weapon)
                              		  v.HumanoidRootPart.CanCollide = false
                               	 	v.Humanoid.WalkSpeed = 0
                                		v.Head.CanCollide = false
										PosMon = v.HumanoidRootPart.CFrame
										BringMobFarm = true
                                		v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                		v.HumanoidRootPart.Transparency = 1
                                		getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                		game:GetService'VirtualUser':CaptureController()
                                		game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            		until not _G.AutoFullyGodhuman or not v.Parent or v.Humanoid.Health <= 0
                        		end
									else
										BringMobFarm = false
										getgenv().ToTarget(CFrame.new( -5428,78, -5959))
              		  			end
								end
						elseif CheckMaterial("Mystic Droplet") <= 10 and W2 then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                  	  	if v.Name == "Water Fighter [Lv. 1450]" then
                        		if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                           	 	repeat task.wait()
                               	 	EquipWeapon(_G.Select_Weapon)
                              		  v.HumanoidRootPart.CanCollide = false
                               	 	v.Humanoid.WalkSpeed = 0
                                		v.Head.CanCollide = false
										PosMon = v.HumanoidRootPart.CFrame
										BringMobFarm = true
                                		v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                		v.HumanoidRootPart.Transparency = 1
                                		getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                		game:GetService'VirtualUser':CaptureController()
                                		game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            		until not _G.AutoFullyGodhuman or not v.Parent or v.Humanoid.Health <= 0
                        		end
									else
										BringMobFarm = false
										getgenv().ToTarget(CFrame.new( -3385,239, -10542))
              		  			end
								end
								if not W3 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
								elseif W3 then
									if CheckMaterial("Mystic Droplet") >= 10 and CheckMaterial("Magma Ore") >= 20 and CheckMaterial("Dragon Scale") >= 10 and CheckMaterial("Fish Tail") >= 20 then
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
									wait(.3)
									_G.AutoFarmLv = true
									print("Succeed")
									end
								end
							end
						end
						else 
						if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") and game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Death Step") and game.Players.LocalPlayer.Character:FindFirstChild("Death Step").Level.Value >= 400 then
                       	 game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                   	 end
                    	if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Electric Claw").Level.Value >= 400 then
                        	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                    	end
                    	if game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Sharkman Karate").Level.Value >= 400 or game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate").Level.Value >= 400 then
                        	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
                  	  end 
        			end
				end
			end)
		end
 	end
end)

AutoFighting:AddToggle({
    Name = "AutoFullySuperhuman",
	Value = _G.Settings.AutoFullySuperhuman, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoFullySuperhuman = value
        _G.Settings.AutoFullySuperhuman = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})
spawn(function()
    pcall(function()
        while task.wait() do 
            if _G.Settings.AutoFullySuperhuman then
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 150000 then
                    UnEquipWeapon("Combat")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
                end   
                if game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") then
                    _G.Select_Weapon = "Superhuman"
                end  
                if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") or game.Players.LocalPlayer.Character:FindFirstChild("Electro") or game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299 then
                        _G.Select_Weapon = "Black Leg"
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 299 then
                        _G.Select_Weapon = "Electro"
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299 then
                        _G.Select_Weapon = "Fishman Karate"
                    end
                    if game.Players.LocalPlayer.BackpacUnEquipWeaponk:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 299 then
                        _G.Select_Weapon = "Dragon Claw"
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 300000 then
                        UnEquipWeapon("Black Leg")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
                    end
                    if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 300000 then
                        UnEquipWeapon("Black Leg")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 750000 then
                        UnEquipWeapon("Electro")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
                    end
                    if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 750000 then
                        UnEquipWeapon("Electro")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300 and game:GetService("Players")["Localplayer"].Data.Fragments.Value >= 1500 then
                        UnEquipWeapon("Fishman Karate")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2") 
                    end
                    if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300 and game:GetService("Players")["Localplayer"].Data.Fragments.Value >= 1500 then
                        UnEquipWeapon("Fishman Karate")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
                    else
                        local Fragment = game:GetService("Players")["Localplayer"].Data.Fragments.Value
                        if Fragment <=1499 then
                            _G.Setting.Config["AutoFullySuperhuman"] = true 
                        else
                            _G.Setting.Config["AutoFullySuperhuman"] = false
                        end
                    end
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 3000000 then
                        UnEquipWeapon("Dragon Claw")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
                    end
                    if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300 and game:GetService("Players")["LocalPlayer"].Data.Beli.Value >= 3000000 then
                        UnEquipWeapon("Dragon Claw")
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
                    end 
                end
            end
        end
    end)
end)

AutoFighting:AddToggle({
    Name = "AutoDeathStep",
	Value = _G.Settings.AutoFullySuperhuman, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoDeathStep = value
        _G.Settings.AutoDeathStep = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    while wait() do wait()
        if _G.AutoDeathStep then 
            if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Death Step") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Death Step") then
                if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 450 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
                    _G.Select_Weapon = "Death Step"
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") then 
						local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") 
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
					end
                end  
                if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 450 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
                    _G.Select_Weapon = "Death Step"
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") then 
						local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Death Step") 
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
					end
                end  
                if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 449 then
                    _G.Select_Weapon = "Black Leg"
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") then 
						local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") 
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
					end
                end 
            else 
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
            end
        end
    end
end)

AutoFighting:AddToggle({
    Name = "AutoSharkman",
	Value = _G.Settings.AutoFullySuperhuman, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoSharkman = value
        _G.Settings.AutoSharkman = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    pcall(function()
        while wait() do
            if _G.AutoSharkman then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
                if string.find(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate"), "keys") then  
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Water Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Water Key") then
                        getgenv().ToTarget(CFrame.new(-2604.6958, 239.432526, -10315.1982, 0.0425701365, 0, -0.999093413, 0, 1, 0, 0.999093413, 0, 0.0425701365))
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 400 then
                    else 
                        Ms = "Tide Keeper [Lv. 1475] [Boss]"
                        if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then   
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == Ms then    
                                    OldCFrameShark = v.HumanoidRootPart.CFrame
                                    repeat task.wait()
                                        AutoHaki()
                                        EquipWeapon(_G.Select_Weapon)
                                        v.Head.CanCollide = false
                                        v.Humanoid.WalkSpeed = 0
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.CFrame = OldCFrameShark
                                        getgenv().ToTarget(v.HumanoidRootPart.CFrame*CFrame.new(0,35,0))
                                        game:GetService("VirtualUser"):CaptureController()
                                        game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 670))
                                        sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                                    until not v.Parent or v.Humanoid.Health <= 0 or _G.AutoSharkman == false or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Water Key") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Water Key")
                                end
                            end
                        else
                            getgenv().ToTarget(CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202))
                            wait(3)
                        end
                    end
                else 
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate")
                end
            end
        end
    end)
end)

AutoFighting:AddToggle({
    Name = "AutoElectricClaw",
	Value = _G.Settings.AutoFullySuperhuman, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoElectricClaw = value
        _G.Settings.AutoElectricClaw = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    pcall(function()
        while wait() do 
            if _G.AutoElectricClaw then
                if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electric Claw") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electric Claw") then
                    if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") then 
							local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") 
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
						end
                    end  
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") then 
							local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") 
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
						end
                    end  
                    if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 399 then
                        wait(.5)
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") then 
							local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") 
							game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
						end
                    end 
                else
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
                end
            end
            if _G.AutoElectricClaw then
                if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") then
                    if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
                        if AutoFarm == false then
                            getgenv().ToTarget(CFrame.new(-10371.4717, 330.764496, -10131.4199))           
                            wait(1.1)                
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start")
                            wait(.5)
                            getgenv().ToTarget(CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438))                            
                            wait(.5)
                            getgenv().ToTarget(CFrame.new(-10371.4717, 330.764496, -10131.4199))                           
                            wait(1.1)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                        elseif _G.Settings.autofarmlevel == true then
                            _G.Settings.autofarmlevel = false
                            wait(.5)
                            getgenv().ToTarget(CFrame.new(-10371.4717, 330.764496, -10131.4199))           
                            wait(1.1)                
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw","Start")
                            wait(.5)
                            getgenv().ToTarget(CFrame.new(-12550.532226563, 336.22631835938, -7510.4233398438))                            
                            wait(.5)
                            getgenv().ToTarget(CFrame.new(-10371.4717, 330.764496, -10131.4199))                           
                            wait(1.1)
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
                            wait(.5)
                            if game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") then 
								local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Electric Claw") 
								game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
							end
                            _G.Settings.autofarmlevel = true
                        end
                    end
                end
            end
        end
    end)    
end)

AutoFighting:AddToggle({
    Name = "AutoDragonTalon",
	Value = _G.Settings.AutoDragonTalon, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoDragonTalon = value
        _G.Settings.AutoDragonTalon = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    while wait() do
        if _G.AutoDragonTalon then
            if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Talon") or game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Talon") then
                if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 400 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") then 
					local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") 
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
					end
                end  
                if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw") and game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") then 
					local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Talon") 
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
					end
                end  
                if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 399 then
                    if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") then 
					local ToolHumanoid = game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") 
						game.Players.LocalPlayer.Character.Humanoid:EquipTool(ToolHumanoid) 
					end
                end 
            else 
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
            end
        end
    end
end)

 local AutoItem = Page:CreateSection({
    Name = "Auto Item", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})

if W1 then
AutoItem:AddLabel({
     Name = "AutoSaber",
     Flag = "AutoSaber"
 })

AutoItem:AddToggle({
    Name = "AutoSaber",
	Value = _G.Settings.AutoSaber, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoSaber = value
        _G.Settings.AutoSaber = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

AutoItem:AddToggle({
    Name = "AutoSaberHop",
	Value = _G.Settings.AutoSaber, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoSaberHop = value
        _G.Settings.AutoSaberHop = value
        saveSettings()
    end
})

	spawn(function()
		    while wait() do
					pcall(function()
						if _G.AutoSaber and game.Players.LocalPlayer.Data.Level.Value >= 200 and not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Saber") and not game.Players.LocalPlayer.Character:FindFirstChild("Saber") then
							if game:GetService("Workspace").Map.Jungle.Final.Part.Transparency == 0 then
								if game:GetService("Workspace").Map.Jungle.QuestPlates.Door.Transparency == 0 then
									if (CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 100 then
										getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
										wait(1)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate1.Button.CFrame
										wait(1)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate2.Button.CFrame
										wait(1)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate3.Button.CFrame
										wait(1)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate4.Button.CFrame
										wait(1)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Jungle.QuestPlates.Plate5.Button.CFrame
										wait(1) 
									else
										getgenv().ToTarget(CFrame.new(-1612.55884, 36.9774132, 148.719543, 0.37091279, 3.0717151e-09, -0.928667724, 3.97099491e-08, 1, 1.91679348e-08, 0.928667724, -4.39869794e-08, 0.37091279))
									end
								else
									if game:GetService("Workspace").Map.Desert.Burn.Part.Transparency == 0 then
										if game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Torch") then
											EquipWeapon("Torch")
											getgenv().ToTarget(CFrame.new(1114.61475, 5.04679728, 4350.22803, -0.648466587, -1.28799094e-09, 0.761243105, -5.70652914e-10, 1, 1.20584542e-09, -0.761243105, 3.47544882e-10, -0.648466587))
										else
											getgenv().ToTarget(CFrame.new(-1610.00757, 11.5049858, 164.001587, 0.984807551, -0.167722285, -0.0449818149, 0.17364943, 0.951244235, 0.254912198, 3.42372805e-05, -0.258850515, 0.965917408))                 
										end
									else
										if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","GetCup")
											wait(0.5)
											EquipWeapon("Cup")
											wait(0.5)
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","FillCup",game:GetService("Players").LocalPlayer.Character.Cup)
											wait(0)
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") 
										else
											if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == nil then
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
											elseif  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
												if game:GetService("Workspace").Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
													    for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                    										if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                      										  if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            											repeat task.wait()
                               											 EquipWeapon(_G.Select_Weapon)
                                											v.HumanoidRootPart.CanCollide = false
                               											 v.Humanoid.WalkSpeed = 0
                                											v.Head.CanCollide = false
                                											getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                											game:GetService'VirtualUser':CaptureController()
                                											game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            										until v.Humanoid.Health <= 0 or _G.Settings.Main["Auto Saber"] == false
                        										end
                    										end
															for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                   								   		 if v.Name == "Mob Leader [Lv. 120] [Boss]" then
                   							    	    		getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
															   end
                   						      		end
												    end
              							    end
											elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon")
												wait(0.5)
												EquipWeapon("Relic")
												wait(0.5)
												getgenv().ToTarget(CFrame.new(-1404.91504, 29.9773273, 3.80598116, 0.876514494, 5.66906877e-09, 0.481375456, 2.53851997e-08, 1, -5.79995607e-08, -0.481375456, 6.30572643e-08, 0.876514494))
											end
										end
									end
									if _G.AutoSaberHop then
										Hop()
									end
								end
							else
								if game:GetService("Workspace").Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") or game:GetService("ReplicatedStorage"):FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
									for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
										if v.Name == "Saber Expert [Lv. 200] [Boss]" then
											repeat wait()
												EquipWeapon(_G.Select_Weapon)
                                    			getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,30,5))
                                  		      game:GetService'VirtualUser':CaptureController()
                                    			game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
											until v.Humanoid.Health <= 0 or _G.Settings.Main["Auto Saber"] == false
											if v.Humanoid.Health <= 0 then
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","PlaceRelic")
											end
										end
									end
									if _G.AutoSaberHop then
										Hop()
									end
								end
							end
						end
					end)
				end
			end)

AutoItem:AddLabel({
     Name = "Auto Pole",
     Flag = "Auto Pole"
 })

AutoItem:AddToggle({
    Name = "Auto Pole",
	Value = _G.Settings.AutoPole, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoPole = value
        _G.Settings.AutoPole = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

AutoItem:AddToggle({
    Name = "Auto PoleHop",
	Value = _G.Settings.AutoPoleHop, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoPoleHop = value
        _G.Settings.AutoPoleHop = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    while task.wait() do
        if _G.AutoPole then
            pcall(function()
                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                    if v.Name == "Thunder God [Lv. 575] [Boss]" then
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            repeat task.wait()
                                EquipWeapon(_G.Select_Weapon)
                                v.HumanoidRootPart.CanCollide = false
                                v.Humanoid.WalkSpeed = 0
                                v.Head.CanCollide = false
                                v.HumanoidRootPart.Size = Vector3.new(100,100,100)
                                v.HumanoidRootPart.Transparency = 1
                                getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            until not _G.AutoPole or not v.Parent or v.Humanoid.Health <= 0
                        end
                    end
                end
                for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                    if v.Name == "Thunder God [Lv. 575] [Boss]"  then
                        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                       end
                       if _G.AutoPoleHop then
                          	Hop()
                          end
                    end
            end)
        end
    end
end)
end

AutoItem:AddLabel({
     Name = "AutoBoss",
     Flag = "AutoBoss"
 })
 
 local Boss = {}

for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
    if string.find(v.Name, "Boss") then
        if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
            else
            table.insert(Boss, v.Name)
        end
    end
end

if _G.Settings.Select_Boss == nil then
	_G.Settings.Select_Boss = ""
end

local BossName = AutoItem:AddDropdown({
     Name = "Select Boss",
     List = Boss,
     Value = _G.Settings.Select_Boss,
     Callback = function(value)
     	 Select_Boss = value
          _G.Settings.Select_Boss = value
          saveSettings()
      end
})

AutoItem:AddButton({
    Name = "Refresh Weapon",
    Callback = function()
        BossName:Clear()
        for i, v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do
        if string.find(v.Name, "Boss") then
            BossName:Add(v.Name) 
        end
    end
end
})

AutoItem:AddToggle({
    Name = "AutoFarmBoss",
	Value = _G.Settings.AutoFarmBoss, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoFarmBoss = value
        _G.Settings.AutoFarmBoss = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    while task.wait() do
        if _G.AutoFarmBoss then
            pcall(function()
                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                    if v.Name == Select_Boss then
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            repeat task.wait()
                                EquipWeapon(_G.Select_Weapon)
                                v.HumanoidRootPart.CanCollide = false
                                v.Humanoid.WalkSpeed = 0
                                v.Head.CanCollide = false
                                getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            until not _G.AutoFarmBoss or not v.Parent or v.Humanoid.Health <= 0
                        end
                    end
                end
                for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                    if v.Name == Select_Boss then
                        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
						end
                    end
            end)
        end
    end
end)

AutoItem:AddToggle({
    Name = "AutoFarmBossAll",
	Value = _G.Settings.AutoFarmBossAll, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.AutoFarmBossAll = value
        _G.Settings.AutoFarmBossAll = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

spawn(function()
    while task.wait() do
        if _G.AutoFarmBossAll then
            pcall(function()
                for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                    if string.find(v.Name,"Boss") then
                        if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                            repeat task.wait()
                                EquipWeapon(_G.Select_Weapon)
                                v.HumanoidRootPart.CanCollide = false
                                v.Humanoid.WalkSpeed = 0
                                v.Head.CanCollide = false
                                getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
                                game:GetService'VirtualUser':CaptureController()
                                game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
                            until not _G.AutoFarmBossAll or not v.Parent or v.Humanoid.Health <= 0
                        end
                    end
                end
                for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                    if string.find(v.Name,"Boss") then
                        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,35,5))
						end
                    end
            end)
        end
    end
end)

 local Combat = Page2:CreateSection({
    Name = "Combat", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})

Combat:AddLabel({
     Name = "Combat",
     Flag = "Combat"
 })
 
 Combat:AddToggle({
    Name = "Show Fov",
	Value = _G.Settings.ShowFov, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.ShowFov = value
        _G.Settings.ShowFov = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})
 
    local lp = game:GetService('Players').LocalPlayer
    local mouse = lp:GetMouse()
    spawn(function()
        while wait() do
            if _G.Aimbot_Skill then
                pcall(function()
                       local MaxDist, Closest = math.huge
                       for i,v in pairs(game:GetService("Players"):GetChildren()) do 
                        local Head = v.Character:FindFirstChild("HumanoidRootPart")
                        local Pos, Vis = game.Workspace.CurrentCamera.WorldToScreenPoint(game.Workspace.CurrentCamera, Head.Position)
                        local MousePos, TheirPos = Vector2.new(mouse.X, mouse.Y), Vector2.new(Pos.X, Pos.Y)
                        local Dist = (TheirPos - MousePos).Magnitude
                        if Dist < MaxDist and Dist <= _G.Select_Size_Fov and v.Name ~= game.Players.LocalPlayer.Name then
                            MaxDist = Dist
                            _G.Aim_Players = v
                        end
                    end
                end)
            end
        end
    end)
    local Circle = Drawing.new("Circle")
    Circle.Color =  Color3.fromRGB(52, 190, 255)
    Circle.Thickness = 1
    Circle.Radius = 250
    Circle.NumSides = 460
    Circle.Filled = false
    Circle.Transparency = 0.5
    
    game:GetService("RunService").Stepped:Connect(function()
        Circle.Radius = _G.Select_Size_Fov
        Circle.Thickness = 1
        Circle.NumSides = 460
        Circle.Position = game:GetService('UserInputService'):GetMouseLocation()
        if _G.ShowFov then
            Circle.Visible = true
        else
            Circle.Visible = false
        end
    end)
  _G.Select_Size_Fov = 20
  Combat:AddSlider({
        Name = "Select Size Fov",
        Flag = "Select_Size_Fov",
        Value = _G.Settings.Select_Size_Fov,
        Min = 1,
        Max = 1000,
        Textbox = true,
        Format = function(value)
            _G.Select_Size_Fov = value
            _G.Settings.Select_Size_Fov = value
            saveSettings()
        return "Size Fov : " .. tostring(value)
        end
    })
    
Combat:AddToggle({
    Name = "Aimbot Skill",
	Value = _G.Settings.Aimbot_Skill, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Aimbot_Skill = value
        _G.Settings.Aimbot_Skill = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})
    
    spawn(function()
        local gg = getrawmetatable(game)
        local old = gg.__namecall
        setreadonly(gg,false)
        gg.__namecall = newcclosure(function(...)
            local method = getnamecallmethod()
            local args = {...}
            if tostring(method) == "FireServer" then
                if tostring(args[1]) == "RemoteEvent" then
                    if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
                        if _G.Aimbot_Skill then
                            args[2] = _G.Aim_Players.Character.HumanoidRootPart.Position
                            return old(unpack(args))
                        end
                    end
                end
            end
            return old(...)
        end)
    end)
	task.spawn(function()
	while wait() do
		if _G.Aimbot_Skill then
			if game.Players:FindFirstChild(SelectPlayer) and game.Players:FindFirstChild(SelectPlayer).Character:FindFirstChild("HumanoidRootPart") and game.Players:FindFirstChild(SelectPlayer).Character:FindFirstChild("Humanoid") and game.Players:FindFirstChild(SelectPlayer).Character.Humanoid.Health > 0 then
				AimBotSkillPosition = game.Players:FindFirstChild(SelectPlayer).Character:FindFirstChild("HumanoidRootPart").Position
			end
		end
	end
end)

Combat:AddToggle({
    Name = "Aimbot Gun",
	Value = _G.Settings.Aimbot_Gun, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Aimbot_Gun = value
        _G.Settings.Aimbot_Gun = value
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})
spawn(function()
	while wait() do
		for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
			if v:IsA("Tool") then
				if v:FindFirstChild("RemoteFunctionShoot") then 
					SelectToolWeaponGun = v.Name
				end
			end
		end
		for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
			if v:IsA("Tool") then
				if v:FindFirstChild("RemoteFunctionShoot") then 
					SelectToolWeaponGun = v.Name
				end
			end
		end
	end
end)

local lp = game:GetService('Players').LocalPlayer
local mouse = lp:GetMouse()
mouse.Button1Down:Connect(function()
	if _G.Aimbot_Gun and game.Players.LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) and game:GetService("Players"):FindFirstChild(SelectPlayer) then
		tool = game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun]
		v17 = workspace:FindPartOnRayWithIgnoreList(Ray.new(tool.Handle.CFrame.p, (game:GetService("Players"):FindFirstChild(SelectPlayer).Character.HumanoidRootPart.Position - tool.Handle.CFrame.p).unit * 100), { game.Players.LocalPlayer.Character, workspace._WorldOrigin });
		game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(game:GetService("Players"):FindFirstChild(SelectPlayer).Character.HumanoidRootPart.Position, (require(game.ReplicatedStorage.Util).Other.hrpFromPart(v17)));
	end 
end)


local TP = Page2:CreateSection({
    Name = "TP", -- ชื่อ
    Side = "Right" -- ตำแหน่ง Left/Right
})

TP:AddLabel({
     Name = "TP",
     Flag = "TP"
 })

TP:AddButton({
    Name = "Teleport To Old World",
    Callback = function()
    	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
end
})

TP:AddButton({
    Name = "Teleport To Second Sea",
    Callback = function()
    	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
end
})

TP:AddButton({
    Name = "Teleport To Third Sea",
    Callback = function()
    	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
end
})

TP:AddLabel({
     Name = "TP lsland",
     Flag = "TP lsland"
 })

if game.PlaceId == 2753915549 then
	IW1 = {
		"WindMill",
        "Marine",
        "Middle Town",
        "Jungle",
        "Pirate Village",
        "Desert",
        "Snow Island",
        "MarineFord",
        "Colosseum",
        "Sky Island 1",
        "Sky Island 2",
        "Sky Island 3",
        "Prison",
        "Magma Village",
        "Under Water Island",
        "Fountain City",
        "Shank Room",
        "Mob Island"
	}
TP:AddLabel({
     Name = "Game ID 2753915549",
     Flag = "W1"
 })
 
TP:AddDropdown({
     Name = "Select lsland",
     Flag = "Select lsland",
     List = IW1,
     Value = _G.Settings.Select_lsland,
     Callback = function(value)
     	 _G.Select_lsland = value
          _G.Settings.Select_lsland = value
          saveSettings()
      end
})
end

if game.PlaceId == 4442272183 then
	
TP:AddLabel({
     Name = "Game ID 4442272183",
     Flag = "W2"
 })
	
 	LW2 = {
    	"The Cafe",
        "Frist Spot",
        "Dark Area",
        "Flamingo Mansion",
        "Flamingo Room",
        "Green Zone",
        "Factory",
        "Colossuim",
        "Zombie Island",
        "Two Snow Mountain",
        "Punk Hazard",
        "Cursed Ship",
        "Ice Castle",
        "Forgotten Island",
        "Ussop Island",
        "Mini Sky Island"
	}

TP:AddDropdown({
     Name = "Select lsland",
     Flag = "Select lsland",
     List = LW2,
     Value = _G.Settings.Select_lsland,
     Callback = function(value)
     	 _G.Select_lsland = value
          _G.Settings.Select_lsland = value
          saveSettings()
      end
})
end

if game.PlaceId == 7449423635 then
	LW3 = {
        "Mansion",
        "Port Town",
        "Great Tree",
        "Castle On The Sea",
        "MiniSky", 
        "Hydra Island",
        "Floating Turtle",
        "Haunted Castle",
        "Ice Cream Island",
        "Peanut Island",
        "Cake Island",
        "Noname Island(New)"
	}
	
TP:AddLabel({
     Name = "Game ID 7449423635",
     Flag = "W3"
 })
	
TP:AddDropdown({
     Name = "Select lsland",
     Flag = "Select lsland",
     List = LW3,
     Value = _G.Settings.Select_lsland,
     Callback = function(value)
     	 _G.Select_lsland = value
          _G.Settings.Select_lsland = value
          saveSettings()
      end
})
end

if _G.Settings.Select_lsland == nil then
	_G.Settings.Select_lsland = ""
end

TP:AddToggle({
    Name = "Teleport",
	Value = _G.Settings.Teleport, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
        _G.Teleport = value
        _G.Settings.Teleport = value
        if _G.Teleport == true then
    while _G.Teleport do wait()
        repeat wait()
            if _G.Select_lsland == "WindMill" then
                ByPass(CFrame.new(979.79895019531, 16.516613006592, 1429.0466308594))
            elseif _G.Select_lsland == "Marine" then
                ByPass(CFrame.new(-2566.4296875, 6.8556680679321, 2045.2561035156))
            elseif _G.Select_lsland == "Middle Town" then
                ByPass(CFrame.new(-690.33081054688, 15.09425163269, 1582.2380371094))
            elseif _G.Select_lsland == "Jungle" then
                ByPass(CFrame.new(-1612.7957763672, 36.852081298828, 149.12843322754))
            elseif _G.Select_lsland == "Pirate Village" then
                ByPass(CFrame.new(-1181.3093261719, 4.7514905929565, 3803.5456542969))
            elseif _G.Select_lsland == "Desert" then
                ByPass(CFrame.new(944.15789794922, 20.919729232788, 4373.3002929688))
            elseif _G.Select_lsland == "Snow Island" then
                ByPass(CFrame.new(1347.8067626953, 104.66806030273, -1319.7370605469))
            elseif _G.Select_lsland == "MarineFord" then
                ByPass(CFrame.new(-4914.8212890625, 50.963626861572, 4281.0278320313))
            elseif _G.Select_lsland == "Colosseum" then
                ByPass( CFrame.new(-1427.6203613281, 7.2881078720093, -2792.7722167969))
            elseif _G.Select_lsland == "Sky Island 1" then
                ByPass(CFrame.new(-4869.1025390625, 733.46051025391, -2667.0180664063))
            elseif _G.Select_lsland == "Sky Island 2" then  
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
            elseif _G.Select_lsland == "Sky Island 3" then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
            elseif _G.Select_lsland == "Prison" then
                ByPass( CFrame.new(4875.330078125, 5.6519818305969, 734.85021972656))
            elseif _G.Select_lsland == "Magma Village" then
                ByPass(CFrame.new(-5247.7163085938, 12.883934020996, 8504.96875))
            elseif _G.Select_lsland == "Under Water Island" then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
            elseif _G.Select_lsland == "Fountain City" then
                ByPass(CFrame.new(5127.1284179688, 59.501365661621, 4105.4458007813))
            elseif _G.Select_lsland == "Shank Room" then
				ByPass(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
				wait(.1)
                getgenv().ToTarget(CFrame.new(-1442.16553, 29.8788261, -28.3547478))
            elseif _G.Select_lsland == "Mob Island" then
                getgenv().ToTarget(CFrame.new(-2850.20068, 7.39224768, 5354.99268))
            elseif _G.Select_lsland == "The Cafe" then
                ByPass(CFrame.new(-380.47927856445, 77.220390319824, 255.82550048828))
            elseif _G.Select_lsland == "Frist Spot" then
                getgenv().ToTarget(CFrame.new(-11.311455726624, 29.276733398438, 2771.5224609375))
            elseif _G.Select_lsland == "Dark Area" then
                getgenv().ToTarget(CFrame.new(3780.0302734375, 22.652164459229, -3498.5859375))
            elseif _G.Select_lsland == "Flamingo Mansion" then
                getgenv().ToTarget(CFrame.new(-483.73370361328, 332.0383605957, 595.32708740234))
            elseif _G.Select_lsland == "Flamingo Room" then
                getgenv().ToTarget(CFrame.new(2284.4140625, 15.152037620544, 875.72534179688))
            elseif _G.Select_lsland == "Green Zone" then
                ByPass( CFrame.new(-2448.5300292969, 73.016105651855, -3210.6306152344))
            elseif _G.Select_lsland == "Factory" then
                getgenv().ToTarget(CFrame.new(424.12698364258, 211.16171264648, -427.54049682617))
            elseif _G.Select_lsland == "Colossuim" then
                getgenv().ToTarget( CFrame.new(-1503.6224365234, 219.7956237793, 1369.3101806641))
            elseif _G.Select_lsland == "Zombie Island" then
                ByPass(CFrame.new(-5622.033203125, 492.19604492188, -781.78552246094))
            elseif _G.Select_lsland == "Two Snow Mountain" then
                getgenv().ToTarget(CFrame.new(753.14288330078, 408.23559570313, -5274.6147460938))
            elseif _G.Select_lsland == "Punk Hazard" then
                ByPass(CFrame.new(-6127.654296875, 15.951762199402, -5040.2861328125))
            elseif _G.Select_lsland == "Cursed Ship" then
                getgenv().ToTarget(CFrame.new(923.40197753906, 125.05712890625, 32885.875))
            elseif _G.Select_lsland == "Ice Castle" then
                ByPass(CFrame.new(6148.4116210938, 294.38687133789, -6741.1166992188))
            elseif _G.Select_lsland == "Forgotten Island" then
                ByPass(CFrame.new(-3032.7641601563, 317.89672851563, -10075.373046875))
            elseif _G.Select_lsland == "Ussop Island" then
                ByPass(CFrame.new(4816.8618164063, 8.4599885940552, 2863.8195800781))
            elseif _G.Select_lsland == "Mini Sky Island" then
                getgenv().ToTarget(CFrame.new(-288.74060058594, 49326.31640625, -35248.59375))
            elseif _G.Select_lsland == "Great Tree" then
                ByPass(CFrame.new(2681.2736816406, 1682.8092041016, -7190.9853515625))
            elseif _G.Select_lsland == "Castle On The Sea" then
                ByPass(CFrame.new(-5074.45556640625, 314.5155334472656, -2991.054443359375))
            elseif _G.Select_lsland == "MiniSky" then
                getgenv().ToTarget(CFrame.new(-260.65557861328, 49325.8046875, -35253.5703125))
            elseif _G.Select_lsland == "Port Town" then
                ByPass(CFrame.new(-290.7376708984375, 6.729952812194824, 5343.5537109375))
            elseif _G.Select_lsland == "Hydra Island" then
                ByPass(CFrame.new(5228.8842773438, 604.23400878906, 345.0400390625))
            elseif _G.Select_lsland == "Floating Turtle" then
                ByPass(CFrame.new(-13274.528320313, 531.82073974609, -7579.22265625))
            elseif _G.Select_lsland == "Mansion" then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12471.169921875, 374.94024658203, -7551.677734375))
            elseif _G.Select_lsland == "Haunted Castle" then
                ByPass(CFrame.new(-9515.3720703125, 164.00624084473, 5786.0610351562))
            elseif _G.Select_lsland == "Ice Cream Island" then
                ByPass(CFrame.new(-902.56817626953, 79.93204498291, -10988.84765625))
            elseif _G.Select_lsland == "Peanut Island" then
                ByPass(CFrame.new(-2062.7475585938, 50.473892211914, -10232.568359375))
            elseif _G.Select_lsland == "Cake Island" then
                ByPass(CFrame.new(-1884.7747802734375, 19.327526092529297, -11666.8974609375))
             elseif _G.Select_lsland == "Chocolate Island" then
                ByPass(CFrame.new(53.0000267, 58.6640739, -12851.6777, -0.203585744, 0, 0.979057133, 0, 1, 0, -0.979057133, 0, -0.203585744))
            end
        until not _G.TeleportIsland
    end
    StopTween(_G.TeleportIsland)
 end
		if value == false then
			wait()
       	 getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
        	wait()
     	end
        saveSettings()
    end
})

TP:AddToggle({
    Name = "Teleport to Sea Beast",
	Value = _G.Settings.Teleport_to_Sea_Beast, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
    _G.Teleport_to_Sea_Beast  = value
	_G.Settings.Teleport_to_Sea_Beast = value
end
})
		task.spawn(function()
                while wait() do
                    pcall(function()
                        if _G.Teleport_to_Sea_Beast then
                            for i,v in pairs(game.Workspace.SeaBeasts:GetChildren()) do
                                if v:FindFirstChild("HumanoidRootPart") then
                                    toTarget(v.HumanoidRootPart.CFrame * CFrame.new(1,500,1))
                                end
                            end
                        end
                    end)
                end
            end)

local Shop = Page3:CreateSection({
    Name = "Shop", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})

Shop:AddLabel({
     Name = "AutoBuy",
     Flag = "Shop"
 })

Shop:AddToggle({
    Name = "Auto Buy Enchanment Haki",
	Value = _G.AutoBuyEnchanmentHaki, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
   _G.AutoBuyEnchanmentHaki = value
while _G.AutoBuyEnchanmentHaki do wait(.1)
	local args = {
		[1] = "ColorsDealer",
		[2] = "2"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end
end
})

Shop:AddToggle({
    Name = "AutoBuyLegendarySword",
	Value = _G.AutoBuyLegendarySword, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
   _G.AutoBuyLegendarySword = value
while _G.AutoBuyLegendarySword do wait(.1)
	local args = {
		[1] = "LegendarySwordDealer",
		[2] = "1"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	local args = {
		[1] = "LegendarySwordDealer",
		[2] = "2"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	local args = {
		[1] = "LegendarySwordDealer",
		[2] = "3"
	}
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end 
end
})

Shop:AddLabel({
     Name = "Fighting",
     Flag = "Shop"
 })
	
	
Shop:AddDropdown({
     Name = "Select Buy",
     Flag = "Select Buy",
     List = {"Black Leg","Electro","Fishman Karate","Dragon Claw","Superhuman","Death Step","Electric Claw","Sharkman Karate","Dragon Talon","Godhuman"},
     Value = _G.Settings.Select_Buy,
     Callback = function(value)
     	 _G.Select_Buy = value
          _G.Settings.Select_Buy = value
          saveSettings()
      end
})

if _G.Settings.Select_Buy == nil then
	_G.Settings.Select_Buy = ""
end

Shop:AddToggle({
    Name = "Buy",
	Value = _G.Buy, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
   _G.Buy = value
	if _G.Buy then
		if _G.Select_Buy == "Black Leg" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyBlackLeg")
		elseif _G.Select_Buy == "Electro" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectro")
		elseif _G.Select_Buy == "Fishman Karate" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
		elseif _G.Select_Buy == "Dragon Claw" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","1")
    		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","DragonClaw","2")
		elseif _G.Select_Buy == "Superhuman" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman")
		elseif _G.Select_Buy == "Death Step" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep")
		elseif _G.Select_Buy == "Electric Claw" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw")
		elseif _G.Select_Buy == "Sharkman Karate" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyFishmanKarate")
		elseif _G.Select_Buy == "Dragon Talon" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon")
		elseif _G.Select_Buy == "Godhuman" then
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman")
		end
	end
end
})

Shop:AddLabel({
     Name = "Fragment",
     Flag = "Shop"
 })
 
 Shop:AddButton({
    Name = "Refund Stat",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Refund","2")
end
})

Shop:AddButton({
    Name = "Reroll Race",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Reroll","2")
end
})

Shop:AddLabel({
     Name = "Buy Abilities",
     Flag = "Shop"
 })
 
 Shop:AddButton({
    Name = "Buy Haki",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Buso")
end
})

Shop:AddButton({
    Name = "Buy Geppo",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Geppo")
end
})

Shop:AddButton({
    Name = "Buy Soru",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyHaki","Soru")
end
})

Shop:AddButton({
    Name = "Buy Ken",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("KenTalk","Buy")
end
})

Shop:AddLabel({
     Name = "Buy Swords",
     Flag = "Shop"
 })

Shop:AddButton({
    Name = "Buy Katana",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Katana")
end
})

Shop:AddButton({
    Name = "Buy Cutlass",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Cutlass")
end
})

Shop:AddButton({
    Name = "Buy Duel Katana",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Duel Katana")
end
})

Shop:AddButton({
    Name = "Buy Iron Mace",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Iron Mace")
end
})

Shop:AddButton({
    Name = "Buy Pipe",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Pipe")
end
})

Shop:AddButton({
    Name = "Buy Triple Katana",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Triple Katana")
end
})

Shop:AddButton({
    Name = "Buy Dual-Headed Blade",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Dual-Headed Blade")
end
})

Shop:AddButton({
    Name = "Buy Bisento",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Bisento")
end
})

Shop:AddButton({
    Name = "Buy Soul Cane",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Soul Cane")
end
})

Shop:AddLabel({
     Name = "Buy Gun",
     Flag = "Shop"
 })

Shop:AddButton({
    Name = "Buy Slingshot",
    Callback = function()
    	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Slingshot")
end
})

Shop:AddButton({
    Name = "Buy Musket",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Musket")
end
})

Shop:AddButton({
    Name = "Buy Flintlock",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyItem","Flintlock")
end
})

Shop:AddButton({
    Name = "Buy Kabucha",
    Callback = function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","1")
	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BlackbeardReward","Slingshot","2")
end
})

local Dun = Page3:CreateSection({
    Name = "Dungeon", -- ชื่อ
    Side = "Right" -- ตำแหน่ง Left/Right
})

if game.PlaceId == 2753915549 then
Dun:AddLabel({
     Name = "Dungeon World2 - 3",
     Flag = "Dungeon"
 })
end
if game.PlaceId == 4442272183  or game.PlaceId == 7449423635 then
Dun:AddLabel({
     Name = "Welcome to Dungeon",
     Flag = "Dungeon"
 })

Dun:AddToggle({
    Name = "Kill Aura",
	Value = _G.Settings.Kill_Aura, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
    _G.Kill_Aura = value
    _G.Settings.Kill_Aura = value
	saveSettings()
end
})

task.spawn(function()
    while task.wait() do
        if _G.Kill_Aura  then
            for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
                if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                    pcall(function()
                        repeat task.wait()
                            sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                            v.Humanoid.Health = 0
                            v.HumanoidRootPart.CanCollide = false
                            v.HumanoidRootPart.Size = Vector3.new(500,500,500)
                            v.HumanoidRootPart.Transparency = 1
                        until not _G.Kill_Aura or v.Parent or v.Humanoid.Health <= 0
                    end)
                end
            end
        end
    end
end) 

Dun:AddToggle({
    Name = "Next Island",
	Value = _G.Settings.Next_Island, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
    _G.Next_Island = value
    _G.Settings.Next_Island = value
	saveSettings()
end
})

task.spawn(function()
        pcall(function()
            while task.wait() do
                if _G.Next_Island then
                    if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.Timer.Visible == true then
                        if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
                            getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame*CFrame.new(0,25,0))
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
                            getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame*CFrame.new(0,25,0))
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
                            getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame*CFrame.new(0,25,0))
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
                            getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame*CFrame.new(0,25,0))
                        elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
                            getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame*CFrame.new(0,25,0))
                        end
                    end
                end
            end
        end)
    end)
    
Dun:AddToggle({
    Name = "Auto Awakener",
	Value = _G.Settings.Auto_Awakener, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
    _G.Auto_Awakener = value
    _G.Settings.Auto_Awakener = value
	saveSettings()
end
})
    
    spawn(function()
        pcall(function()
            while wait(.1) do
                if _G.Auto_Awakener then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Check")
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Awakener","Awaken")
                end
            end
        end)
    end)

Dun:AddDropdown({
     Name = "Select Chips",
     Flag = "Select Chips",
     List = {"Flame","Ice","Quake","Light","Dark","String","Rumble","Magma","Human: Buddha","Sand","Bird: Phoenix"},
     Value = _G.Settings.Select_Buy,
     Callback = function(value)
     	 _G.Select_Chips = value
          _G.Settings.Select_Chips = value
          saveSettings()
      end
})

Dun:AddToggle({
    Name = "AutoSelectDungeon",
	Value = _G.Settings.AutoSelectDungeon, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
    _G.AutoSelectDungeon = value
    _G.Settings.AutoSelectDungeon = value
	saveSettings()
end
})

if _G.Settings.AutoSelectDungeon == nil then
	_G.Settings.AutoSelectDungeon = ""
end

	spawn(function()
        while wait() do
            if _G.AutoSelectDungeon then
                pcall(function()
                    if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flame-Flame") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flame-Flame") then
                        _G.SelectChip = "Flame"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Ice-Ice") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Ice-Ice") then
                        _G.SelectChip = "Ice"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Quake-Quake") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Quake-Quake") then
                        _G.SelectChip = "Quake"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Light-Light") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Light-Light") then
                        _G.SelectChip = "Light"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dark-Dark") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Dark-Dark") then
                        _G.SelectChip = "Dark"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("String-String") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("String-String") then
                        _G.SelectChip = "String"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Rumble-Rumble") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Rumble-Rumble") then
                        _G.SelectChip = "Rumble"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Magma-Magma") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Magma-Magma") then
                        _G.SelectChip = "Magma"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha Fruit") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Human-Human: Buddha Fruit") then
                        _G.SelectChip = "Human: Buddha"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Sand-Sand") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Sand-Sand") then
                        _G.SelectChip = "Sand"
                    elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Bird-Bird: Phoenix") or game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Bird-Bird: Phoenix") then
                        _G.SelectChip = "Bird: Phoenix"
                    else
                        _G.SelectChip = "Flame"
                    end
                end)
            end
        end
    end)

Dun:AddToggle({
    Name = "Auto StartDungeon",
	Value = _G.Settings.StartDungeon, -- ปรับค่าToggle true/false or Config
    Callback = function(value)
   _G.StartDungeon = value
	_G.Settings.StartDungeon = value
 while _G.StartDungeon do wait()
    if game.PlaceId == 4442272183 then
      fireclickdetector(game:GetService("Workspace").Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
   elseif game.PlaceId == 7449423635 then
       fireclickdetector(game:GetService("Workspace").Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
    end
end
saveSettings()
end
})
end

local EspSection = Page4:CreateSection({
    Name = "Misc", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})

    EspSection:AddToggle{
        Name = "No Clip",
        Flag = "No_clip",
        Value = _G.Settings.No_clip,
        Callback  = function(value)
            _G.No_clip = value
            _G.Settings.No_clip = value
            saveSettings()
        end
    }
    
    spawn(function()
        pcall(function()
            game:GetService("RunService").Stepped:Connect(function()
                if _G.No_clip then
                    for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                        if v:IsA("BasePart") then
                            v.CanCollide = false    
                        end
                    end
                end
            end)
        end)
    end)
    
    EspSection:AddToggle{
        Name = "Infinit Energy",
        Flag = "Infinit_Energy",
        Value = _G.Settings.Infinit_Energy,
        Callback  = function(value)
            _G.Infinit_Energy = value
            _G.Settings.Infinit_Energy = value
            saveSettings()
            InfinitEnergy()
        end
    }
    
    EspSection:AddToggle{
        Name = "Dodge No CoolDown",
        Flag = "Dodge_No_CoolDown",
        Value = _G.Settings.Dodge_No_CoolDown,
        Callback  = function(value)
            _G.Dodge_No_CoolDown = value
            _G.Settings.Dodge_No_CoolDown = value
            saveSettings()
            DodgeNoCoolDown()
        end
    }
    
    EspSection:AddToggle{
        Name = "Infinit Ability",
        Flag = "Infinit_Ability",
        Value = _G.Settings.Infinit_Ability,
        Callback  = function(value)
            _G.Infinit_Ability = value
            _G.Settings.Infinit_Ability = value
            saveSettings()
        end
    }
    
    spawn(function()
        while wait() do
            if _G.Infinit_Ability then
                InfAbility()
            end
        end
    end)
    
    EspSection:AddToggle{
        Name = "Infinit Sky Jump",
        Flag = "Infinit_SkyJump",
        Value = _G.Settings.Infinit_SkyJump,
        Callback  = function(value)
            _G.Infinit_SkyJump = value
            _G.Settings.Infinit_SkyJump = value
            saveSettings()
            SkyJumpNoCoolDown()
        end
    }
    
    EspSection:AddToggle{
        Name = "Infinit Soru",
        Flag = "Infinit_Soru",
        Value = _G.Settings.Infinit_Soru,
        Callback  = function(value)
            _G.Infinit_Soru = value
            _G.Settings.Infinit_Soru = value
            saveSettings()
            SoruNoCoolDown()
        end
    }
    
    EspSection:AddToggle{
        Name = "Infinit Range Observation Haki",
        Flag = "Infinit_Range_Observation_Haki",
        Value = _G.Settings.Infinit_Range_Observation_Haki,
        Callback  = function(value)
            _G.Infinit_Range_Observation_Haki = value
            _G.Settings.Infinit_Range_Observation_Haki = value
            saveSettings()
        end
    }
    
    spawn(function()
        while wait() do
            if _G.Infinit_Range_Observation_Haki then
                game.Players.LocalPlayer.VisionRadius.Value = math.huge
            end
        end
    end)
local Misc2 = Page4:CreateSection({
    Name = "Misc2", -- ชื่อ
    Side = "Right" -- ตำแหน่ง Left/Right
})

Misc2:AddLabel({
     Name = "UI",
 })

    Misc2:AddButton({
        Name = "Inventory",
        Callback = function()
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")
            game.Players.localPlayer.PlayerGui.Main.Inventory.Visible = true
        end
    })
    
    Misc2:AddButton({
        Name = "Devil Fruit Inventory",
        Callback = function()
            local args = {
                [1] = "getInventoryFruits"
            }
            
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryFruits")
            game:GetService("Players").LocalPlayer.PlayerGui.Main.FruitInventory.Visible = true
        end
    })
    
    Misc2:AddButton({
        Name = "Devil Fruit Shop",
        Callback = function()
            local args = {
                [1] = "GetFruits"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
        end
    })
    
    Misc2:AddButton({
        Name = "Title Name",
        Callback = function()
            local args = {
                [1] = "getTitles"
            }
            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
            game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
        end
    })
    
    Misc2:AddButton({
        Name = "Color Haki",
        Callback = function()
            game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
        end
    })
    
    Misc2:AddLabel({
     Name = "MainMiscSection",
 })
    
    Misc2:AddToggle({
        Name = "White Screen",
        Flag = "White_Screen",
        Value = _G.Settings.White_Screen,
        Callback = function(value)
            _G.White_Screen = value
            _G.Settings.White_Screen = value
            saveSettings()
            if _G.White_Screen then
                game:GetService("RunService"):Set3dRenderingEnabled(false)
            else
                game:GetService("RunService"):Set3dRenderingEnabled(true)
            end
        end
    })
    
    Misc2:AddToggle({
        Name = "Remove Fog",
        Flag = "Remove_Fog",
        Value = false,
        Callback = function(value)
            _G.Remove_Fog = value
            if not _G.Remove_Fog then return end
            while _G.Remove_Fog do wait()
                game.Lighting.FogEnd = 9e9
                if not _G.Remove_Fog then
                    game.Lighting.FogEnd = 2500
                end
            end
        end
    })

local Items = Page4:CreateSection({
    Name = "Items", -- ชื่อ
    Side = "Left" -- ตำแหน่ง Left/Right
})
if W1 then
Items:AddLabel({ Name = "World : 1" })
end

if W2 then
Items:AddLabel({ Name = "World : 2" })
end

if W3 then
Items:AddLabel({ Name = "World : 3" })
end

Items:AddLabel({ Name = "Race : "..game:GetService("Players").LocalPlayer.Data.Race.Value })

Items:AddLabel({ Name = "Fruit : "..game.Players.LocalPlayer.Data.DevilFruit.Value})

Items:AddLabel({ Name = "Level : "..game.Players.localPlayer.Data.Level.Value})

Items:AddLabel({ Name = "Bounty : "..game:GetService("Players").LocalPlayer.leaderstats["Bounty/Honor"].Value})

Items:AddLabel({ Name = "Melee" })

local Superhuman = Items:AddLabel({ Name = "❌ : Superhuman" })
local Death_Step = Items:AddLabel({ Name = "❌ : Death Step" })
local Sharkman_Karate = Items:AddLabel({ Name = "❌ : Sharkman Karate" })
local Electric_Claw = Items:AddLabel({ Name = "❌ : Electric Claw" })
local Dragon_Talon = Items:AddLabel({ Name = "❌ : Dragon Talon" })
local God_Human = Items:AddLabel({ Name = "❌ : God Human" })

spawn(function()
while task.wait() do
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySuperhuman",true) == 1 then
		Superhuman:Set("✅ : Superhuman")
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDeathStep",true) == 1 then
		Death_Step:Set("✅ : Death Step")
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuySharkmanKarate",true) == 1 then
		Sharkman_Karate:Set("✅ : Sharkman Karate")
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyElectricClaw",true) == 1 then
		Electric_Claw:Set("✅ : Electric Claw")
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyDragonTalon",true) == 1 then
		Dragon_Talon:Set("✅ : Dragon Talon")
	end
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BuyGodhuman",true) == 1 then
		God_Human:Set("✅ : GodHuman")
	end
end
end)

Items:AddLabel({ Name = "Gun" })

local Kabu_cha = Items:AddLabel({ Name = "❌ : Kabucha" })
local Bizarre_Rifle = Items:AddLabel({ Name = "❌ : Bizarre Rifle" })
local Acidum_Rifle = Items:AddLabel({ Name = "❌ : Acidum Rifle" })

spawn(function()
while task.wait() do
	pcall(function()
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
			if v.Name == "Kabucha" then
				Kabu_cha:Set("✅ : Kabucha")
			end
			if v.Name == "Acidum Rifle" then
				Acidum_Rifle:Set("✅ : Acidum Rifle")
			end
			if v.Name == "Bizarre Rifle" then
				Bizarre_Rifle:Set("✅ : Bizarre Rifle")
			end
		end
	end)
end
end)

Items:AddLabel({ Name = "Quest" })

local Kill_Don_Swan = Items:AddLabel({ Name = "❌ : Kill Don Swan" })
local Bartilo_Quest = Items:AddLabel({ Name = "❌ : Bartilo Quest" })
local Don_Swan_Quest = Items:AddLabel({ Name = "❌ : Don Swan Quest" })

spawn(function()
while task.wait() do
	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
		Bartilo_Quest:Set("✅ : Bartilo Quest")
	end

	if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess == nil then
		--Nothing
	else
		Don_Swan_Quest:Set("✅ : Don Swan Quest")
	end

	if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("ZQuestProgress", "Check") == 1 then
		Kill_Don_Swan:Set("✅ : Kill Don Swan")
	end
end
end)

local Items2 = Page4:CreateSection({
    Name = "Items2", -- ชื่อ
    Side = "Right" -- ตำแหน่ง Left/Right
})

Items2:AddLabel({ Name = "Sword" })

local Saber = Items2:AddLabel({ Name = "❌ : Saber" })
local Rengoku = Items2:AddLabel({ Name = "❌ : Rengoku" })
local Midnight_Blade = Items2:AddLabel({ Name = "❌ : Midnight_Blade" })
local Dragon_Trident = Items2:AddLabel({ Name = "❌ : Dragon_Trident" })
local Yama = Items2:AddLabel({ Name = "❌ : Yama" })
local Buddy_Sword = Items2:AddLabel({ Name = "❌ : Buddy_Sword" })
local Canvander = Items2:AddLabel({ Name = "❌ : Canvander" })
local Twin_Hooks = Items2:AddLabel({ Name = "❌ : Twin_Hooks" })
local Spikey_Trident = Items2:AddLabel({ Name = "❌ : Spikey_Trident" })
local Hallow_Scythe = Items2:AddLabel({ Name = "❌ : Hallow_Scythe" })
local Dark_Dagger = Items2:AddLabel({ Name = "❌ : Dark_Dagger" })
local Tushita = Items2:AddLabel({ Name = "❌ : Tushita" })
local Cursed_Dual_Katana = Items2:AddLabel({ Name = "❌ : Cursed_Dual_Katana" })

spawn(function()
while task.wait() do
	pcall(function()
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
			if v.Name == "Saber" then
				Saber:Set("✅ : Saber")
			end
			if v.Name == "Rengoku" then
				Rengoku:Set("✅ : Rengoku")
			end
			if v.Name == "Midnight Blade" then
				Midnight_Blade:Set("✅ : Midnight Blade")
			end
			if v.Name == "Dragon Trident" then
				Dragon_Trident:Set("✅ : Dragon Trident")
			end
			if v.Name == "Yama" then
				Yama:Set("✅ : Yama")
			end
			if v.Name == "Buddy Sword" then
				Buddy_Sword:Set("✅ : Buddy Sword")
			end
			if v.Name == "Canvander" then
				Canvander:Set("✅ : Canvander")
			end
			if v.Name == "Twin Hooks" then
				Twin_Hooks:Set("✅ : Twin Hooks")
			end
			if v.Name == "Spikey Trident" then
				Spikey_Trident:Set("✅ : Spikey Trident")
			end
			if v.Name == "Hallow Scythe" then
				Hallow_Scythe:Set("✅ : Hallow Scythe")
			end
			if v.Name == "Dark Dagger" then
				Dark_Dagger:Set("✅ : Dark Dagger")
			end
			if v.Name == "Tushita" then
				Tushita:Set("✅ : Tushita")
			 end
			 if v.Name == "Cursed Dual Katana" then
				 Cursed_Dual_Katana.Set("✅ : Cursed Dual Katana")
			  end
			end
		end)
	end
end)

Items2:AddLabel({ Name = "Sword Legendary" })

local Shisui = Items2:AddLabel({ Name = "❌ : Shisui" })
local Saddi = Items2:AddLabel({ Name = "❌ : Saddi" })
local Wando = Items2:AddLabel({ Name = "❌ : Wando" })
local True_Triple_Katana = Items2:AddLabel({ Name = "❌ : True Triple Katana" })

spawn(function()
while task.wait() do
	pcall(function()
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
			if v.Name == "Shisui" then
				Shisui:Set("✅ : Shisui")
			end
			if v.Name == "Saddi" then
				Saddi:Set("✅ : Saddi")
			end
			if v.Name == "Wando" then
				Wando:Set("✅ : Wando")
			end
			if v.Name == "True Triple Katana" then
				True_Triple_Katana:Set("✅ : True Triple Katana")
			end
		end
	end)
end
end)

Items2:AddLabel({ Name = "Accessory" })

local Dark_Coat = Items2:AddLabel({ Name = "❌ : Dark Coat" })
local Ghoul_Mask = Items2:AddLabel({ Name = "❌ : Ghoul Mask" })
local Swan_Glass = Items2:AddLabel({ Name = "❌ : Swan Glass" })
local Pale_Scarf = Items2:AddLabel({ Name = "❌ : Pale Scarf" })
local Valkyrie_Helm = Items2:AddLabel({ Name = "❌ : Valkyrie Helm" })

spawn(function()
while task.wait() do
	pcall(function()
		for i,v in pairs(game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("getInventoryWeapons")) do
			if v.Name == "Dark Coat" then
				Dark_Coat:Set("✅ : Dark Coat")
			end
			if v.Name == "Ghoul Mask" then
				Ghoul_Mask:Set("✅ : Ghoul Mask")
			end
			if v.Name == "Swan Glasses" then
				Swan_Glass:Set("✅ : Swan Glass")
			end
			if v.Name == "Pale Scarf" then
				Pale_Scarf:Set("✅ : Pale Scarf")
			end
			if v.Name == "Valkyrie Helmet" then
				Valkyrie_Helm:Set("✅ : Valkyrie Helmet")
			end
		end
	end)
end
end)

local SuperFastMode = true -- เปลี่ยนเป็นจริงถ้าคุณต้องการโจมตี Super Super Super Fast (เช่นการฆ่าทันที) แต่จะทำให้เกมเตะคุณมากกว่าโหมดปกติ
             _G.FastAttack = true

local plr = game.Players.LocalPlayer

local CbFw = debug.getupvalues(require(plr.PlayerScripts.CombatFramework))
local CbFw2 = CbFw[2]

function GetCurrentBlade() 
    local p13 = CbFw2.activeController
    local ret = p13.blades[1]
    if not ret then return end
    while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
    return ret
end
function AttackNoCD() 
        local AC = CbFw2.activeController
        for i = 1, 1 do 
            local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
                plr.Character,
                {plr.Character.HumanoidRootPart},
                60
            )
            local cac = {}
            local hash = {}
            for k, v in pairs(bladehit) do
                if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                    table.insert(cac, v.Parent.HumanoidRootPart)
                    hash[v.Parent] = true
                end
            end
            bladehit = cac
            if #bladehit > 0 then
				
                local u8 = debug.getupvalue(AC.attack, 4.8)
				
                local u9 = debug.getupvalue(AC.attack, 5.8)
				
                local u7 = debug.getupvalue(AC.attack, 3.8)
				
                local u10 = debug.getupvalue(AC.attack, 6.8)
				
                local u12 = (u8 * 798405 + u7 * 727595) % u9
				
                local u13 = u7 * 798405
				    
				(function()
                    u12 = (u12 * u9 + u13) % 1099511627776
                    u8 = math.floor(u12 / u9)
                    u7 = u12 - u8 * u9
                end)()
                u10 = u10 - 0.01  --/ 1.2
                debug.setupvalue(AC.attack, 4.8, u8)
				
                debug.setupvalue(AC.attack, 5.8, u9)
				
                debug.setupvalue(AC.attack, 3.8, u7)
				
                debug.setupvalue(AC.attack, 6.8, u10)
				
                pcall(function()
                    for k, v in pairs(AC.animator.anims.basic) do
                        v:Play()
                    end                  
                end)
                if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then 
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                    game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                    game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "") 
                end
            end
        end
    end 
local cac
if SuperFastMode then 
	cac=task.wait
else
	cac=wait
end
print("Yes")
while cac() do 
	AttackNoCD()
end    
-------------------------------------------------------

if getgenv().noclip then
	local a = Instance.new('Part',workspace)
	--
	local a = Instance.new("Part")
	a.Name = "epicbingus"
	a.Parent = game.Workspace
	a.Anchored = true 
	a.Transparency = 1
	a.Size = Vector3.new(10,0.5,10) 
end
---
game:GetService("RunService").Heartbeat:Connect(function()
   pcall(function()
   if not game:GetService("Workspace"):FindFirstChild("epicbingus") and getgenv().noclip then
	local a = Instance.new("Part")
	a.Name = "epicbingus"
	a.Parent = game.Workspace
	a.Anchored = true 
	a.Transparency = 1
	a.Size = Vector3.new(40,0.5,40)
		end
   end)
end)

function changestate()
   game.Workspace["epicbingus"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,-4,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
end

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			if getgenv().noclip then
				if game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Y < 0 then
					changestate()
				end
			end
		end)
	end)
end)



  

spawn(function()------body velocity
	game:GetService("RunService").Stepped:Connect(function()
		if _G.Settings.autofarmlevel then
			if not game.Players.localPlayer.Character.HumanoidRootPart:FindFirstChild('bv') then
				local bv = Instance.new("BodyVelocity",game.Players.LocalPlayer.Character.HumanoidRootPart)
				bv.Name = 'bv'
				bv.MaxForce = Vector3.new(100000,100000,100000)
				bv.Velocity = Vector3.new(0,0,0)
			end
		else
			if game.Players.localPlayer.Character.HumanoidRootPart:FindFirstChild('bv') then
				game.Players.localPlayer.Character.HumanoidRootPart:FindFirstChild('bv'):Destroy()
			end
		 end
	end)
end)

_groupMon = false

spawn(function()
	game:GetService("RunService").Heartbeat:Connect(function()
		pcall(function()
			if _G.Settings.autofarmlevel  then
				checklevel()
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if v.Name ~= "Ice Admiral [Lv. 700] [Boss]" and v.Name ~= "Don Swan [Lv. 3000] [Boss]" and v.Name ~= "Saber Expert [Lv. 200] [Boss]" and v.Name ~= "Longma [Lv. 2000] [Boss]" and (v.HumanoidRootPart.Position-PosMon.Position).magnitude <= magbring then
						if syn then
						v.HumanoidRootPart.CFrame = PosMon
						v.Humanoid.JumpPower = 0
						v.Humanoid.WalkSpeed = 0
						v.Humanoid.Sit = true
						v.HumanoidRootPart.CanCollide = false
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						v.Humanoid:ChangeState(14)
						v.Humanoid:ChangeState(11)
					else
						v.HumanoidRootPart.CFrame = PosMon
						v.Humanoid.JumpPower = 0
						v.Humanoid.WalkSpeed = 0
						v.Humanoid.Sit = true
						v.HumanoidRootPart.CanCollide = false
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
						v.Humanoid:ChangeState(14)
						v.Humanoid:ChangeState(11)
						end
					end
				end
			end
		end)
	end)
end)

spawn(function()--critical damage
	local backup = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework)
	local Crit = getupvalues(backup)[2]
	local CombatFrameworkR = getupvalues(backup)[2]
	local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
	function maxincrement()
		return #Crit.activeController.anims.basic
	end
	spawn(function()
		local old
		old = hookmetamethod(game, "__namecall",function(self,...)
			local method = getnamecallmethod() local args = {...}
	
			if method:lower() == "fireserver" then
				if args[1] == "hit" then
					args[3] = maxincrement()
					return old(self,unpack(args))
				end end
			return old(self,...)
		end) 
	end)
end)

game:GetService("RunService").Heartbeat:Connect(function()
	pcall(function()
		if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
			if getgenv().noclip then 
				setfflag("HumanoidParallelRemoveNoPhysics", "False")
				setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
				game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
			end
		end
	end)
end)
  ---------------------------------                                    
return library, library_flags, library.subs
            
        else
            counter = counter +1
        end
    end
end
