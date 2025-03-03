local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
	Name = "Mango Hub ðŸ¥­",
	Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
	LoadingTitle = "Mango Hub ðŸ¥­",
	LoadingSubtitle = "By acceleration.roblox on Discord",
	Theme = "AmberGlow", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
	DisableRayfieldPrompts = true,
	DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
	ConfigurationSaving = {
	   Enabled = false,
	   FolderName = nil, -- Create a custom folder for your hub/game
	   FileName = "Big Hub"
	},
 
	Discord = {
	   Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
	   Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
	   RememberJoins = true -- Set this to false to make them join the discord every time they load it up
	},
 
	KeySystem = true, -- Set this to true to use our key system
	KeySettings = {
	   Title = "Mango Hub ðŸ¥­",
	   Subtitle = "Key System",
	   Note = "Go to https://rekonise.com/mango-hub-key-o99qe and do the tasks to get the key", -- Use this to tell the user how to get a key
	   FileName = "skibidi12223232345", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
	   SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
	   GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
	   Key = {"M#a#Z@QP"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
	}
 })

 local SaitamaTab = Window:CreateTab("Saitama Movesets") -- Title, Image
 local JJKSaitamaSection = SaitamaTab:CreateSection("JJK Movesets")

 local Button = SaitamaTab:CreateButton({
	Name = "JJS Gojo",
	Callback = function()
		loadstring(game:HttpGet("https://gist.githubusercontent.com/JcBoomin/a63e9ac3e90cef03ecf37e997fd21632/raw/98b567b81f61bb30042e0078b78f3fb24685fb8d/Gojo",true))()
		Rayfield:Notify({
			Title = "JJS Gojo executed!",
			Content = "âŸ¦Let's get... A little crazy.âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

  local Button = SaitamaTab:CreateButton({
	Name = "Isagi",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/CensoredScripts/Scripts/refs/heads/main/Script"))()
		Rayfield:Notify({
			Title = "Be Careful With Final Shot! 🗣️",
			Content = " I WILL become the best..",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Gojo",
	Callback = function()
		getgenv().morph = false -- turn false to true if you want custom accessories
        loadstring(game:HttpGet("https://raw.githubusercontent.com/skibiditoiletfan2007/BaldyToSorcerer/refs/heads/main/LatestV2.lua"))()
		Rayfield:Notify({
			Title = "Gojo executed!",
			Content = "âŸ¦Nah, I'd win.âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

  local Button = SaitamaTab:CreateButton({
	Name = "Custom Moveset",
	Callback = function()
		loadstring(game:HttpGet("loadstring(game:HttpGet("https:/ /pastebin.com/raw/V4Ptawxz",true))()"))()
		Rayfield:Notify({
			Title = "Not inspired from anything",
			Content = "but it's still pretty cool",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Hakari",
	Callback = function()
		loadstring(game:HttpGet("https://pastebin.com/raw/eEDYWj8p"))()
		Rayfield:Notify({
			Title = "Hakari executed!",
			Content = "âŸ¦A life of gambling always comes... with risk.âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Kashimo",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/damir512/Kashimo/main/Protected_7491278457865044.txt"))()
		Rayfield:Notify({
			Title = "Kashimo executed!",
			Content = "âŸ¦TURN UP THE VOLUME, THIS IS A FUNERAL FOR THE LIVING!!âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Todo",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/Nova2ezz/Todo-moveset/refs/heads/main/Todo"))()
		Rayfield:Notify({
			Title = "Todo executed!",
			Content = "âŸ¦The CPU in my 540,000 IQ brain has come to a single conclusion... VICTORY!!âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Yuji [Sukuna in ult]",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/Onihub-sigma/Onihub-Itadori/refs/heads/main/Itadori%20Onihub%20Public.txt"))()
		Rayfield:Notify({
			Title = "Yuji executed!",
			Content = "âŸ¦BLACK FLASH!!âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Mahito",
	Callback = function()
		loadstring(game:HttpGet('https://raw.githubusercontent.com/Kenjihin69/Kenjihin69/refs/heads/main/Mahitotsbupdate'))()
		Rayfield:Notify({
			Title = "Mahito executed!",
			Content = "âŸ¦I truly am... A CURSE!!âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "JJS Mahito [If you start flying just sidedash]",
	Callback = function()
		loadstring(game:HttpGet('https://pastebin.com/raw/2HJnbJPM'))()
		Rayfield:Notify({
			Title = "JJS Mahito executed!",
			Content = "âŸ¦Let's kick it up a notch!âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Heian Era Sukuna",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/damir512/sukunasaitamav1/main/thescript",true))()
		Rayfield:Notify({
			Title = "Heian Era Sukuna Executed!",
			Content = "âŸ¦Domain Expansion... Malevolant Shrine.âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })

 local Button = SaitamaTab:CreateButton({
	Name = "Sukuna",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/Nova2ezz/Sukuna/refs/heads/main/KenjakuTsbOnYt"))()
		Rayfield:Notify({
			Title = "Sukuna!",
			Content = "âŸ¦The king of curses!âŸ§",
			Duration = 6.5,
			Image = 0,
		 })
	end,
 })
 

