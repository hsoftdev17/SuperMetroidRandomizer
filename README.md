# Super Metroid Randomizer

### About

I can comfortably beat the unrandomized version of Super Metroid in less 
than 1.5 hours, so I'm not bad, but I am by no means at the play level 
of a speed runner.  A side effect of this skill level is that I have 
beaten the game dozens and dozens of times over the years and want to
play randomized versions of it.  Thus, I love playing randomized Super 
Metroid ROMs, but I find that other Super Metroid randomizers out there 
make assumptions about the "special skills" I have as a player.

To me, "special skills" are things that are outside the realm of a 
normal play through the game.  For example, you can wall jump, but only 
really do so in that vertical column where the animals teach you how.  
You can bounce up on bombs in a pinch, but you certainly don't use it 
as a means of travel.  The fancier tricks almost all involve glitches 
in the game, and you've watched videos about how they work and can't 
get them to happen when you are the one playing.

This is not to say that I don't love other randomizers, but I find that
I can only beat about 1 in every 3 or 4 randomized ROMs they produce.
That's obviously a bit frustrating.  My Super Metroid Randomizer project 
is designed to correct this problem by allowing you to tell it which
skills you have.  The more skills you have, the more flexibility the
randomizer will have in how it messes with the locations of things.

### Skills

There is a skills configuration file that is provided to the randomizer
to tell it which skills you have.  Don't worry, if you don't provide one
it assumes you have no special skills.  The file is in the Java properties
file format so it's easy to use.  Simply provide the property of the skill
from the table below, an equal sign, and then either "true" or "false".

```
DamageBoost=true
WallJump=true
AdvancedWallJump=false
BombJump=true
AdvancedBombJump=false
MockBall=false
QuickCharge=false
ShortCharge=false
GateGlitch=false
```

Skill | Symbol | Property | Description
------|:------:|----------|------------
Damage Boost | Db | DamageBoost | The player can reach things slightly out of normal reach by being thrown into them by taking damage. [Damage Boosting](http://deanyd.net/sm/index.php?title=Damage_boosting)
Wall Jump | Wj | WallJump | The player can do basic wall jumping pretty well. [Wall Jump](http://deanyd.net/sm/index.php?title=Walljump)
Advanced Wall Jump | W+ | AdvancedWallJump | The player can do wall jumping very well.  Including getting around overhangs and jumping off of oddly angled places. [Wall Jump](http://deanyd.net/sm/index.php?title=Walljump)
Bomb Jump | Bj | BombJump | The player can do basic bomb jumping.  This means vertical only and of reasonable height. [Bomb Jump](http://deanyd.net/sm/index.php?title=Bomb_Jump)
AdvancedBombJump | B+ | AdvancedBombJump | The player can do bomb jumping very well.  This means vertical bomb jumps of unlimited height and non-vertical travel of long distances. [Bomb Jump](http://deanyd.net/sm/index.php?title=Bomb_Jump)
Mock Ball | Mb | MockBall | The player can perform the mock ball technique that allows high speed travel in ball form. [Mock Ball](http://deanyd.net/sm/index.php?title=Mockball)
Quick Charge | Qc | QuickCharge | The player can charge a speed boost in less than the distance usually required. [Quick Charge](http://deanyd.net/sm/index.php?title=Quick_charge)
Short Charge | Q+ | ShortCharge | The player can charge a speed boost in extremely short distances that require frame perfect button presses. [Short Charge](http://deanyd.net/sm/index.php?title=Short_charge)
Gate Glitch | Gg | GateGlitch | The player can skip left facing super missile gates from the right side. [Gate Glitch](http://deanyd.net/sm/index.php?title=Gate_Glitch)

### Options

Options are essentially ROM patches that adjust the game in different ways.  These can be almost anything.  Ranging from
a patch that makes the game skip the introduction to more complex modifications.  These are provided in the same way
as the Skills, but in the options file instead of the skills file.  A list of the currently supported options is 
provided by the program when you use the command line arguements:  -help options

### Command Line

The program is driven from the command line by providing a series of "markers" and "values" to the randomizer.
If you need to use spaces in a value, simply enclose it in double quotes to keep from confusing the command line 
parser.

Syntax: `java com.monkeycoder.smr.SuperMetroidRandomizer <parameters>`

Marker | Required | Description
-------|:--------:|------------
&#8209;help&nbsp;\<marker> | No | Shows advanced help for a marker.  When specified no other normal processing will be done.
&#8209;rom&nbsp;\<filename> | Yes | The ROM file to modify.
&#8209;out&nbsp;\<filename> | Yes | The randomized output file. (Cannot be the same as ROM file!)
&#8209;seed&nbsp;\<number> | No | The random seed value to use. (Overrides -hexseed if both are used.)
&#8209;hexseed&nbsp;\<number> | No | The random seed value in hex to use.
&#8209;skills&nbsp;\<filename> | No | The available skills configuration file.
&#8209;options&nbsp;\<filename> | No | The options configuration file.

