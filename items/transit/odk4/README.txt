--[[
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░
░██░░░░░░░░██░░░░░██░██░░░░░░░░██░███████████░██░░░░░██░░░░░░░██░░░░░░██████████░░░███████░░░░████░░░░░░
░██░░░░░░░░██░░░░░██░██░░░░░░░░██░░░░░██░░░░░░███░░░░██░░░░░░████░░░░░░░░░██░░░░░███░░░░░███░░██░████░░░
░██░░░░░░░░██░░░░░██░███░░░░░░███░░░░░██░░░░░░████░░░██░░░░░██░░█░░░░░░░░░██░░░░░██░░░░░░░██░░██░░░░██░░
░██░░░░░░░░██░░░░░██░█░██░░░░██░█░░░░░██░░░░░░██░██░░██░░░░██░░░██░░░░░░░░██░░░░░██░░░░░░░██░░██░░░░██░░
░██░░░░░░░░██░░░░░██░█░░██░░██░░█░░░░░██░░░░░░██░░█░░██░░░░███████░░░░░░░░██░░░░░██░░░░░░░██░░███████░░░
░██░░░░░░░░██░░░░░██░█░░░█░░█░░░█░░░░░██░░░░░░██░░░█░██░░░██░░░░░██░░░░░░░██░░░░░██░░░░░░░██░░██░██░░░░░
░██░░░░░░░░██░░░░░██░█░░░████░░░█░░░░░██░░░░░░██░░░████░░██░░░░░░░██░░░░░░██░░░░░███░░░░░███░░██░░███░░░
░█████████░░███████░░█░░░░██░░░░█░███████████░██░░░░███░███░░░░░░░███░░░░░██░░░░░░░███████░░░░██░░░░███░
░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ 

**Anykine Studios is not affiliated with Luminator.

// -- ODK (Operators Display Keypad) 4 -- //

Thank you for Using an Anykine Studios Group Product.
This README File Contains All Information Of This Product, and the Manual.

// PRODUCT INFORMATION -- // 
-- NAME: 
LUMINATOR ODK 4

-- VERSION:
v2.01.b (2024 Re-launch)

-- ORIGINAL RELEASE DATE:
3/22/23

-- RELAUNCH RELEASE DATE:
TBD

-- LAST UPDATE DATE:
8/25/24

-- DISTRIBUTOR:
ANYKINE STUDIOS GROUP (@ASWDGSAGDB)

-- PROGRAMMERS: 
@aswdgsagdb (Mattt)

-- CONTRIBUTORS: 
@EdDude107 - Provided Information on ODK System and Specifications, Tested ODK
@jar656 - Provided ODK 4 Physical Model

// -- ANYKINE STUDIOS USE: -- //

-- PRODUCT YEAR:
2024

-- PRODUCT SUPPORT:
ACTIVE

-- SUPPORT LOG:
NONE

]]


--[[ **START** MANUAL 

// -- PRODUCT MANUAL -- //

To quickly view parts of this manual, use CTRL + F (windows) or CMD + F (mac) and search with keywords.

// (PART 1) SETUP: --
	1. Place the entire "AnySystems" model in the Body of the Vehicle Chassis you are utilizing. 
		*!! If you already have past "AnySystems" installed, do not put this new "AnySystems" model, but take 
		the individual "ODK4System" model and put it in the existing "AnySystems" model inside Body.
		
	2. Open the "Control Unit" Model.
	
	3. Navigate to the "Data" Folder, then open it.
	
	4. (Skip this step **for now** if you don't have a Anykine Studios Database folder prepared):
		Insert your Codebase folder here, and remove the pre-installed codebase folder called "CODES".
		(there should only be ONE folder here. multiple codebase files are currently not supported)
		--> **IF YOU DON'T HAVE A CODE BASE FOLDER PREPARED: Naviagte to **Part 2** of this Manual.** <--
		
	5. Place "Control Unit" model at your desired PHYSICAL location in the vehicle.
		(reminder to NOT remove this model from its "ODK4System")
		
	6. Place the signboards provided (in "Signboards" --> "Boards") at your desired PHYSICAL locations on the vehicle.
		(reminder to NOT remove this model from its "ODK4System")
		 
	7. Set how your Unit will power on.
		Option 1: Set the PowerDetection ObjectValue to a BoolValue you would like it to listen to.
		Option 2: Use the "LuminatorOpener" Plugin for A-Chassis Vehicles. 
			Place "LuminatorOpener" that is in "SetupItems" directly in the Plugin folder for A-Chassis. 
			If you like to keep the unit purely accessable without the need to have the camera right in front of it
				,open the "LuminatorOpener" Frame, then make the Visibility Property of the "OpenPanel" button to false.
		Option 3: Manually script the Bool value to On or Off. 
			ServerScripts: The Bool Value is accessable via "Control Unit" --> "Handlers" --> "Values" --> "UnitOn"
			LocalScripts: Utilize UnitPowerToggle Event; Accessable via "Control Unit" --> "Handlers" --> "Events" --> "UnitPowerToggle"
							To use "UnitPowerToggle", :FireServer("On" or "Off")
		
		7.b **If you have skipped step #4 of this setup, go back to it now before continuing**
		
	8. Test your ODK 4 Unit! Ensure it powers on properly. 
	
	9. Configure your ODK 4 further with **Part 3** of this Manual.
	
	--> *DO NOT MANUALLY DELETE THE "SETUPITEMS" FOLDER, SYSTEM WILL AUTO-CLEAN ON GAME START.* <--



// (PART 2) MAKING AN ODK DATABASE: -- 
	1. Navigate to the "Data" Folder, then open it.
	2. Use the Folder Named: "CODES" - You can change this name to whatever you like!
	3. There will be 2 folders inside this folder: "Dests" and "Routes"
	
		- // To Add New Dests or PublicRelations:
			1. Open the Dests Folder
			
			2. Choose And Open Your Desired Dest Folder (DestA, DestB or PublicRelations).
			
			3. Duplicate and Use "00" - This can be changed to whatever code you want to register it as! (1-9, A-F)
			
				- Configuring a Code:
					1. Open the "CodeInfo" Folder Inside the Named Code. 
					2. Set "Dest Name" and "Dest Number" String Values to your likings. 
					
				- Adding Decal Signs to a Code:
					1. Open your desired signboard folder you want to add a sign to (Front, Rear, Side).
					2. Create or Duplicate a "Decal" Instacce, and insert the AssetID for the Image you want. 
					3. Name the Decal Instace in the Order you want it to be appeared on the board, starting from 1.
						Repeat the Above Steps for as much slides you want.
						
					**do NOT touch the "Selected" value and WaitTime NumValue. This is utilized by the system itself**
					Repeat the Above Steps as much times as needed for a new Dest or PR.
						
		- // To Add New Routes:
			1. Open the Routes Folder
			
			2. Duplicate and Use "00" - This can be changed to whatever code you want to register it as! (1-9, A-F)
			
				- Configuring a Route Code:
					1. Open the "CodeInfo" Folder Inside the Named Code. 
					2. Set "Route Name" and "Route Number" String Values to your likings.
				- Adding Dests to a Route Code:
					1. There will be 2 StringValues inside, DestA and DestB
					2. Set the value in DestA to a DestA code. 
					3. Set the value in DestB to a DestB code. 
				
	After those steps:		
	4. You have Successfully Created a Database for the ODK! 
		This Database is Universal for all Systems for Transit made by Anykine Studios.

	--> **For People That Need Assistance In Databases, Anykine Studios Offers A Free Service That Will Make A Code Database Folder Made 
		And Personallized For You Or Your Group. Contact Anykine Studios Via Our Social Links For More Information. 



// (PART 3) CONFIGURATION: --

	Unit Configuration ("Control Unit" --> "Configuration" --> "Unit")
		- ClearCode: The Specifc Code you want the selected Dest to clear. (1-9, A-F) - Default: 00
		- Cooldown: Cooldown for pressing the Enter button (NOT recommended to edit, changing this WILL lead to problems) - Default: 3
		- FlashOverOnCodeEntry: If you would like the Dests to "FlashOver" when a code is entered. - Default: false
		- MaxDigits: The Maximum amount of digits allowed to be entered for codes. - Default: 5
		- RouteEnabled: If Route Codes can be used on this system. - Default: true
		- RunEnabled: If Run/Block is used on this system. ) - Default: true
		- SwitchSpeed: The speed at which the signs switch between dests. (in seconds) - Default: 2
		- USBEnabled: If the USB Importing system is allowed to be used. - Default: false
			-----> (CAUTION: This allows users to insert assets in-game, use with trust) <----- 
		- UseTextDisplay: For a text preview on the DestinationPreview frame on the main screen. - Default: false
		
	Signbaord Configuration ("Control Unit" --> "Configuration" --> "Boards")
		- BacklitColor: The Color3 of the Backlit on the Signboards. - Default: Color3.fromRGB(52,52,52)
		- DestBackLit: If you like to have the Signboards be BackLit. - Default: false
		- FilledBackground: If the Background of the Signboard is filled when there is no text showing. - Default: true
		- InvalidCodeFlash: When an inputted code is invalid, flash a message on the Front Signboard - Default: false
			Refer to #3 to set an invalid code sign. (unit does not come with an image for it)
		- RunBoxColor: The Color3 of the Run/Block text on the Run/Block box. - Default: Color3.fromRGB(255,255,255)
		The following will have to be done by hand:
		1. To make the signboard parts Transparent, select the "Case" part in each signboard and manually set the "Transparency" to 1.
		2. To make the Runbox parts Transparent, select the "Box" part in the "RunBox" model and manually set the "Transparency" to 1.
		3. To set an Invalid code sign, select the "InvalidCode" decal in the "FrontSignboard" and set the Image accordingly.
		4. To set a SignOff image, select the "SignOff" decal in all the signboards and set the Images accordingly.
		5. To set a FlashOver image, select the "FlashOver" decal in all the signboards and set the Images accordingly.
		
	Options Configuration ("Control Unit" --> "Configuration" --> "Options")
		- CommercialUse: When using this system for fleets, makes configuration all centeralized to singular "ODKCommercial" folder in ServerStorage. - Default: false
			For more information on how to use "CommercialUse", refer to **Part 4** of this manual.
		- **DEPRECIATED** OptionsModule: Used when CommercialUse is enabled, optional to edit. - Default: **NOT IN USE**
		- PowerDetection: The Bool Value listed to when to Power on the ODK Unit. - Default: UnitOn

// (PART 4) COMMERCIAL USE: --
	1. Ensure "CommercialUse" is set to true in the "Options" folder. (refer to Part 3, Options Configuration)
	
	2. (**If you already have a "ODKCommercial" folder configurated inside of "ServerStorage" SKIP THIS AND STEP #3.**)
		In the "SetupItems" folder, move the "ODKCommercial" folder DIRECTLY to "ServerStorage".
	3. Open the "ODKCommercial" folder.
	
		- // To Configure Fleet Configurations
			1. Open the "FLEET_CONFIG" folder.
			2. Add Codebook folders inside the "Codebooks" folder. 
			3. Add Configuration folders inside the "Configurations" folder. 
				To get configuration folders: 
					- Make config changes to a ODK Control Unit "Configuration" Folder.
					- Duplicate that "Configuration" folder.
					- Rename that folder to anything to define that folder .
			
		-- // To Configure Fleet Assignments
			1. Open the "FLEET_ASSIGN" folder.
			2. Add/Duplicate/Edit the ConfigurationInstances. 
				To add/edit/make ConfigurationInstances:
					- Duplicate the Template ConfigurationInstance "FLEETNAME"
					- Edit the ConfigurationInstance Name Property
					- Edit the "Attributes" of the ConfigurationInstance in the Properties Window
						- codebook_folder: The name of the Codebook folder made in "FLEET_CONFIG" you would want this Fleet to use.
						- config_folder: The name of the Configuration folder made in "FLEET_CONFIG" you want this Fleet to use.
				Repeat the Above Steps as much times as needed for a new Fleet.
		
	4. Inside the "CommercialUse" BoolValue, there is a "Fleet" StringValue.
	
	5. Edit the StringValue of "Fleet" to the Fleet Name you made in "FLEET_CONFIG" want to assign this ODK to.
	
	--> **For any other Units that will be utilizing this "Commercial" mode, repeat above steps for those units,
		disregarding the need for Steps 2 and 3.
	





- // You have reached the end of this manual. // -
	Thanks for using Anykine Studios Products.
	
	
-- // FINAL DISCLAIMERS: // --

- WHEN USING THE LUMINATOROPENER PLUGIN FOR A-CHASSIS, IT IS EXPECTED THE VEHICLE IS AT A COMPLETE STOP.
- DO NOT MANUALLY DELETE THE SETUPITEMS FOLDER, SYSTEM WILL AUTO-CLEAN ON GAME START.
- DO NOT CHANGE OR EDIT ANY SCRIPTS, UNLESS YOU KNOW WHAT YOU ARE DOING
- DO NOT RENAME ANY MODELS, EXCEPT SIGN DECALS, DEST FOLDERS, ROUTE FOLDERS, ETC. (Ask for Support)
- DO NOT REPUBLISH WITH ANY CHANGES MADE. 
- REMOVING ANYKINE STUDIOS GROUP LABELS WILL VOID ANY FURTHER SUPPORT.

**END** MANUAL --]] 


-- Anykine Studios Group, 2024.
-- CC-BY-NC-ND.
