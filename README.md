# SRB2Kart: Neptune fork

[SRB2Kart](https://srb2.org/mods/) is a kart racing mod based on the 3D Sonic the Hedgehog fangame [Sonic Robo Blast 2](https://srb2.org/), based on a modified version of [Doom Legacy](http://doomlegacy.sourceforge.net/).

## Neptune Fork
A fork of a fork. This hardcodes many features that I personally enjoy using or I thought would be good customization.

## Features (Neptune)
- All stuff from Saturn
- 32 Players
- Existing lua features from other custom clients such as interpoints, mashstop, PlayerItemUse, KartHyudoro, KartStealBumper, MobjScaleChange and KartSneaker
- Sneaker Extension with mini-turbos (Choose between two types bs and zbl. Chainoffroad is also toggleable)
- Additive Mini-turbos
- Customizable mini-turbo boost time
- Colorized HUD(With the ability to choose its color or to use your own skin color)
- BoostStacking(This is a big one! It now also has effects!)
- Being able to change what speed battle is in
- Expert Speed
- CEP Item Odd system(based on conga calc)
- Customizable itemtable
- Fixed NetID conflicts
- 16-angle support for sprites
- 65534 skins limit (everything skin num releated was made UINT16)
- Title Screen Thinker and HUD Hook
- Colored sneakertrails
- Multi item icons for most items
- Hardcoded Namtags and Driftgauge
- SRB2 2.2 Resync system
- Followers from RR
- More to come!
- All added features are toggable via convars

## New CVARs
- sneakerextend Default value: On
- sneakerextendtype Default value: zbl
- additivemt Default value: Off
- bluesparktics Default value: 20
- redsparktics Default value: 50
- rainbowsparktics Default value: 125
- colorizedhud Default value: On
- colorizeditembox Default value: On
- darkitembox Default value: On
- stacking Default value:	On
- stackingdim Default value: On
- stackingdimval Default value: 1.25
- stackingbrakemod Default value: 1.25
- stacking_sneakerstack Default value: 5
- stacking_sneakerspeedeasy Default value: 0.8317
- stacking_sneakerspeednormal Default value: 0.5
- stacking_sneakerspeedhard Default value: 0.2756
- stacking_sneakerspeedexpert Default value: 0.2243
- stacking_sneakeraccel Default value: 8.0
- stacking_invincibilitypeed Default value: 0.375
- stacking_invincibilityaccel Default value: 3.0
- stacking_growspeed Default value: 0.3
- stacking_growaccel Default value: 0.5
- stacking_growmult Default value: -0.3
- stacking_drfitspeed Default value: 0.25
- stacking_drfitaccel Default value: 4.0
- stacking_startspeed Default value: 0.25
- stacking_startaccel Default value: 6.0
- stacking_hyuudorospeed Default value: 0.1
- stacking_hyuudoroaccel Default value: 0.5
- stacking_speedcap Default value: On
- stacking_speedcapval Default value: 128.0
- kartbattlespeed Default value: Normal
- customodds Default value: On
- itemoddsystem Default value: CEP
- lastserver Default value: ""
- pingicon Default value: On
- highresportait Default value: Off
- multisneakericon Default value: Off
- stacking_boostflamecolor Default value; On
- stacking_stackingeffect Default value: On
- stacking_stackingeffectscaling On
- sneakertrailcolor Default value: On
- alwaysshowitemstacks Default value: Off
- kartnametag Default value: On
- nametagtransparency Default value: Dynamic
- nametagfacerank Default value: Off
- nametagrestat Default value: Restat
- nametagdist Default value: 320
- nametagmaxplayers Default value:3
- nametagmaxlenght Default value: 12
- nametagshowown Default value: Off
- nametagsmall Default value: Off
- nametaghop Default value: On
- nametagscore Default value: Off
- nametaghealth Default value: On
- kartdriftgauge Default value: On
- driftgaugeoffset Default value: -20
- driftgaugetransparency Default value: On
- driftgaugestyle Default value: Default
- chainoffroad Default value: Both
- stacking_paneltimer Default value: Off
- stacking_panelsharestack Default value: On
- stacking_panelstack Default value: 2
- sneakerstacksound Default value: On
- hidefollowers Default value: On
- stacking_boostpowercompat Default value: Off

## Note about stacking_boostpowercompat
This recreates the inaccurate stacking behaviour from 2.2g and below.

Accleration will stack, grow speedboost will stack with other boosts and boostmult in general works differently.

If you are using this set stacking_growmult to 0.4 to have grow match how it was previously.

## Item odds customization
Please use the cfg script located at ServerScripts/itemodds.cfg if you are going to host a server that will use custom odds.

This makes this dramitcally easier then doing it all by hand.

## New kartstuff data
- k_sneakerstack Current number of active sneaker stacks. Modfifying this will effect stack value
- k_driftstack Cosmetic Stack number. Can be used to see if a specfic boost is active but modifying it won't change how it stacks
- k_startstack ^
- k_invincibilitystack ^
- k_ssstack  ^
- k_trickstack ^
- k_totalstacks Value of all current stacks coesmetic or not
- k_ssspeedboost Used to pass through slipstream speedboost to internal stacking system
- k_ssaccelboost Used to pass through slipstream accelboost to internal stacking system
- k_slopespeedboost Used to pass through slopeboost speedboost to internal stacking system
- k_slopeaccelboost Used to pass through slopeboost accelboost to internal stacking system
- k_trickspeedboost Used to pass through trickmod speedboost to internal stacking system
- k_trickaccelboost Used to pass through trickmod accelboost to internal stacking system
- k_realsneakertimer Used for when chainoffroad is disabled for sneakers
- k_hphealth Used to pass through hpmod health to internal nametags
- k_paneltimer Timer used for when panels are made separate from from sneakers
- k_realpaneltimer Used for when chainoffroad is disabled for panels
- k_panelstack Used when panels don't share sneaker stack count. Current number of active panel stacks. Modfifying this will effect stack value.

## New lua functions

These should be the same as how they are usually used in lua.
- os.clock
- os.time
- os.date
- os.difftime

- debug.gethook
- debug.getinfo
- debug.getlocal
- debug.getupvalue
- debug.sethook
- debug.traceback

## Dependencies
- SDL2 (Linux/OS X only)
- SDL2-Mixer (Linux/OS X only)
- libupnp (Linux/OS X only)
- libgme (Linux/OS X only)
- libopenmpt (Linux/OS X only)
- libbacktrace (Linux/OS X only)

## Compiling

See [SRB2 Wiki/Source code compiling](http://wiki.srb2.org/wiki/Source_code_compiling). The compiling process for SRB2Kart is largely identical to SRB2.

## Disclaimer
Kart Krew is in no way affiliated with SEGA or Sonic Team. We do not claim ownership of any of SEGA's intellectual property used in SRB2.
