	================================================================================
	IF there are questions, help needed or anything, please use the FiveM FORUM
	topic to discuss and help each other.
	================================================================================


	Based on/inspired by: 
	Blumlaut (FiveM Community) / Bluethefurry (Github)
	Original Post:	 https://forum.fivem.net/t/release-trains/28841
	Original Script: https://github.com/Bluethefurry/FiveM-Trains/releases
	Reworked by VenomXNL: https://forum.cfx.re/t/release-fivem-freight-train-ai-and-enterable-trams-as-passenger-suited-for-roleplay-to/

	(Re-) Worked by: Nickoos
	License: Use it as you please but do have decency and respect by crediting the original creators :)
	
	What is it?: A very extensive Train and (well mostely) Metro Addon for FiveM
	
	Basic Functionality list:
	  - Spawns a 'synced' (and working/driving) Freight train on the railroad tracks of Los Santos
	  - Spawns (1 or 2) Metro carts which can be entered as passenger by the players ("no passenger limit!")
	  - Players can WALK AROUND in the moving Metro! :)
	  - Players HAVE to buy a Metro Ticket to be able to enter (With (ATM) animated Ticket machine handling)
	  - Ticket will 'invalidate' when they have entered so they will have to buy a new one
	  - Wanted level handling (refuse passengers from entering when wanted)
	  - 'terrorist detection', which means if players shoot while on the train they will get a 4 star wanted level
	  - Easily configurable with basic variables
	  - Different Bank Messages (for Maze Bank, Bank of Liberty or Fleeca bank)
	  - Metro's, Freight Train and their drivers are 'invincible' (to prevent others 'ruining' the game/RP)
	  - Players can only EXIT the Metro at the stations (by Pressing [E] by default)
	  - Players COULD enter the Metro ANYWHERE (if they have a Ticket Of course), by making it stop (stand in front of it)
	  
	Known 'bugs' or 'issues':
	  - When you enter the Metro as passenger the doors 'will dissapear', why? I don't know, but you can NOT walk through it!
		NOTE: They CAN still be used as cover though (the bottom part), which means the 'collision info' will remain active though.
	  - The ticket machines above ground (the green/old ones) DO NOT WORK, I tried for several hours to find them in the archives but
		with no luck. I however did find one that looks like it, but that one doesn't respond at all.
		I MIGHT update that when someone can tell me the model of that ticket machine object, however for now I have left it at that.
		Also because the original game-texture says: "Sorry, this machine will NEVER work", so i thought: lets keep it in lore :P (nice excuse huh? haha)
	  - When a player puts a vehicle (which doesn't automatically despawns) infront of the Metro, the Metro will wait there till the
		vehicle is removed for eternity.

	General adivce (applies to ALL uploading coders):
	If this script/addon doesn't do what you wanted it to do, if you think it's "sh*tty" etc, that's all fine, but
	just keep that to yourself and find another one that suits your needs (or even better: Make it yourself) ;)
	Keep in mind that people upload code to help/provide others in resources and learning matterial, and that doing so
	costs (extra) time. Time they took to provide you (and many others) with resources, code, samples and addons.
	Contribute, help, share and evolve together, that's the power of a community :)
	(Ofcourse doesn't mean that constructive critisim isn't welcome or desired (since we all will always have points of
	improvement :) )
	  
	=================================== Money Handling Information ===================================
	 If the rest if TL;DR, fine, your problem ;) :P (Don't nag either if you can't figure it out haha)
	 But ATLEAST do read this piece for setup! and IF you have questions, or if want to Adapt or
	 re-publish/upload it: Don't be stubborn, respect other peoples work, and DO read the above ;)
	===================================================================================================
	IMPORTANT NOTE: Bellow 'somewhere' in the code you will find these two lines:
	BankAmount = 10000    --StatGetInt("BANK_BALANCE",-1)
	PlayerCashAm = 10000  --StatGetInt("MP0_WALLET_BALANCE",-1)
	
	Make sure that you adapt them to YOUR OWN SERVER, since like stated there (in the script to),
	many servers use a different money management system, and thus it's not quite possible to make
	one that is 'general in use' for all. We use one that doesn't uses the game stats at all (since thats
	to easy to influence with cheat programs for example). To make sure that people could test/try this
	script i have set the INTERNAL SCRIPT money values to very high (those DO NOT affect the player itself though!)

	This also means that there is no money being taken from the player when he/she buy's a ticket
	
	To make sure that money is taken from the player when buying a ticked you will need to find the following code part:
		if PayWithBank == 1 then
			-- Put YOUR code to deduct the amount from the players BANK account here
			-- 'Basic Example':  PlayerBankMoney = PlayerBankMoney - TicketPrice
		else
			-- Put YOUR code to deduct the amount from the players CASH money account here
			-- 'Basic Example':  PlayerCash = PlayerCash - TicketPrice
		end
	
	And add your OWN SERVER money handling/taking code here
	
	I hope this code/addon is usefull for some people or that they might learn from it by using parts of it :)
	
	Greets,
	VenomXNL & Nickoos
