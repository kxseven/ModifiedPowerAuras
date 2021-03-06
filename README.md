# ModifiedPowerAurasContinued

This is continuation of this work:

https://github.com/Geigerkind/ModifiedPowerAuras

from @Geigerkind

Many thanks to original developer of Power Auras as well as the creator of Modified Power Auras.

ModifedPowerAuras (Mpowa) is a great vanilla World of Warcraft (WoW) addon, intended to show icons and auras
on screen when certain conditions are met, IE buff or debuff present, ability is on cooldown and so on, 
but it falls short in one important aspect: showing aura when action or spell is available, in range 
and ready to be casted/performed.

Consider the case of the Judgement spell, we are tanking or DPS-ing and we want to have an aura show us 
when the spell is ready to be casted (we have active Seal and it's not on cooldown), target is in range 
and target is an enemy. Original Mpowa will have only one check: if spell is on a cooldown. It means that 
(Inverted On Cooldown) aura will be shown even if you don't have a Seal active, you are not targeting 
anything or targeting friendly or dead target or targeting an enemy out of range. Instead of performing 
check on the spell book only, we have to do additional checks, some of them on the Action Bar slots. In 
order to identify which Action Bar slot we are interested in we compare textures from the spell book with 
textures on the Action Bar until we find a match. For this reason, spell you are interested in must be placed on 
one of the Action bars. Checks for spells can be performed on every update which is preferred option 
as you can move spells freely on the Action Bars and Mpowa will find it, or if you have performance 
problems you can choose to uncheck Auto Update but then you have to reset UI by issuing RESETUI command
every time you move or create another aura that tracks if spell is available, or check Auto Update 
briefly and then uncheck it again. I don't see any performance hit on my computer from using Auto Update
feature, but your millage may vary.

~~I have tried to preserve most of previous functionality so instead of having Action Available button you
have to check two boxes, "Ability not ready" which is original "On cooldown" checkbox with additional 
functionality like range clipping and making sure that other cast requirements are met (in case of Judgement
that you have Seal active) and you also need to check "Invert" button to show when Ability is ready as 
opposed to not ready.~~

I also made some changes in UI inconsistencies, like need to do double negative (Invert and On cooldown) to 
show when ability is ready to be performed, which is now simply an "Ability available" checkbox. There is also 
a checkbox "Enemy only", which will ensure that you are targeting an enemy in order to cast harmful spells, 
or you can uncheck this if you are using Mpowa for beneficial spells, like Power Word: Shield for example. The
last addition is "Auto Update" check box, which will be checked automatically when you check "Ability available" 
box. If you prefer to do spell finding manually, you can uncheck this box but then if you move your spell to a 
new slot or create a new aura that requires spell tracking functionality you will have to reset UI.