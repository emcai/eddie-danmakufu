To use the power system, go to the file for the shot you want to use it with.

The file is one of these:
Reimu_A.txt
Reimu_B.txt
Reimu_C.txt

In @Initialize, you should see this:
	
	LoadPlayerShotData(GetCurrentScriptDirectory ~ "ShotData.txt");
	ObjPlayer_AddIntersectionCircleA1(playerObject, 0, 0, 2, 20);
	
	SetPlayerAutoItemCollectLine(160);
	SetPlayerSpeed(4, 2);
	
>>> powerEnabled = false;
	shotType = 1;
	
	LoadSounds;
	
	DrawSprite;
	DrawHitbox;
	
	CreateShots;
	CreateOptions;

Change "powerEnabled = false" to "powerEnabled = true".
	
	LoadPlayerShotData(GetCurrentScriptDirectory ~ "ShotData.txt");
	ObjPlayer_AddIntersectionCircleA1(playerObject, 0, 0, 2, 20);
	
	SetPlayerAutoItemCollectLine(160);
	SetPlayerSpeed(4, 2);
	
>>> powerEnabled = true;
	shotType = 1;
	
	LoadSounds;
	
	DrawSprite;
	DrawHitbox;
	
	CreateShots;
	CreateOptions;

The power system is now enabled on that shot type. You can also copy the entire file and change that in the copy,
so you can have both power enabled and disabled players on the selection screen in-game.

If you want to disable the power system, change "powerEnabled" back to false.


Homing Bullets

The homing bullets on Reimu A's unfocused shot and Reimu B's unfocused shot have special tracking systems.
The center two options will focus on the closest enemy to them, while the other two focus on the farthest
enemy. These distances are based on the options' positions. If the enemy an amulet is tracking is killed,
the amulet selects a new enemy to track based on what option it was fired from.


Fantasy Heaven

The timer on Fantasy Heaven is 15 seconds. Each orb takes 200 shot hits to light. The spell activates when all
orbs are lit, equivalent to 1400 shots. Once activated, damage dealt is exponentially lowered as the spell
progresses.