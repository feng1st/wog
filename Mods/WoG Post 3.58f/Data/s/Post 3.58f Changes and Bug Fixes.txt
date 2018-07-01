Post 3.58f Changes and Bug Fixes  November 22, 2006

script00.erm (WoGify)
 - If "Some dwellings have upgraded creatures" and "Master of life" are enabled both, L1-Dwellings will always have upgraded creatures (exception: neutral town - halflings are not automatically upgraded to rogues).
 - Added $lastplayer$, $battlewinner$, and $battleloser$ macros for future scripting convenience.
 - Corrected a bug with the replacement function that was sometimes replacing quest hut artifacts when it wasn't supposed to.
 - Added a function to store the spells disabled in map specifications and restore them after a save, since it was found that they aren't saved in the save game by default yet some ERM scripts need to check their value.
 - Added a check for customization of artifacts and scrolls (e.g., custom text or guards) and cancels replacement if the artifact or scroll is customized in this way.
 - 4ByteVar Library routines added to allow compressed storage of values in standard 32 bit v or w variables.
 - Added auto-disabling of "Arrow Towers Gain Experience" option if a Network game is detected, because this hard-coded option is not yet compatible with Network games.
 - $bit$ "Library" Function updated to allow script writers to use either the old syntax (return value is stored in y-100) or the new Function variable return syntax where a second variable is supplied and the return value is stored in that (but value is still also returned in y-100). e.g., !!$FU$bit$:P12/?v1; [Convert 12 to a bit number and store in v1]
 - Now monster stacks won't be replaced if there's any customization of text, artifact, or resources (treasure) for the stack, or if there's only a single monster AND the stack is set to not grow, or if the monster is customized to always join or always fight. This should help to allow the monster replacement option to still be used on most custom made maps without causing problems.
 - If a scroll is customized by a mapmaker with custom text or guards it will no longer be replaced by WoGification.
Note: script00.ert is also updated.
 - Check for banning of Disguise in WoG Options added to $spell$ library function.
 - $GetBasicPrimaries$ library function added.
 - $LocalPlayer$ library function added.
 - $RandomStack$ library function added.
 - Power and Knowledge bugs fixed in $GetBasicPrim$ function.

script01.erm (Map Rules)
 - changed FU690: Option "All towns have Grail" -- works even if there are Confluxes on the map, if the script93 (enhanced Grail) active (because this scripts disables the standard conflux grail) [FUTURE COMPATIBILITY CHANGE]
 - FU717: Option "All towns have grail" - if town = Conflux or Tower the dummy Grail will be built instead of the usual grail if the Enhanced Grail / Disable usual Tower Grail is on. [FUTURE COMPATIBILITY CHANGE]
 - FU710 modified to work well with the unlimited-skill-rule (script94) [FUTURE COMPATIBILITY CHANGE]
 - Newly hired Commanders now receive 5000 XP if the "Heroes start at 5th level" rule is active (7500 for Paladins).

script02.erm (Artifact Boost)
 - Diplomats Ring: max. Bonus for L1-Units: unlimited for easy, 1000 for normal, 500 for hard, 250 for expert and 100 for impossible.
 - Emblem Of Cognizance: added gold limit (per emblem): unlimited for easy, 100,000 for normal, 50,000 for hard, 25,000 for expert and 10,000 for impossible.
 - Statesman's Medal: now if you wish to use it, click on the town hall. If there is nothing to build, the Medal will NOT be removed (because it can be used in the Diplo-Boost (script96) too).
 - Pendant Of Holiness - gives only spells, that are not disabled (Map-Options), or banned (Wog-Option to ban Resurrection).
 - Pendant Of Dispassion gives you +1 Defense instead of Knowledge if Magic Ban (script99) is active. [FUTURE COMPATIBILITY CHANGE]
 - Fixed bug that occurs if you try to immediately use Statesman's Medal to build on day 1 with a hero who starts with the artifact.

script03.erm (Secondary Skill Boost)
 - Eagle Eye won't remove itself now (after learning all spells) if Eagle Eye II boost is also active.
 - Script now uses the $spell$ function for increased compatibility with current and future spell banning. Some other internal changes also made. Resistance and Tactics boosts are updated to work correctly in MP games.
 - Replaced "you" with the hero's name in level-up Eagle Eye spell-learning messages.
Note: script03.ert also updated.

script04.erm (Arcane Tower)
 - Some incompatibilities with new WoG artifacts that grant stat bonuses have been fixed.
 - Minor spelling-related bug corrected.

script05.erm (Loan Bank)
 - The interest for borrowing resources is now a minimum of 1 instead of 0.
 - The maximum loan you can currently borrow will now also be shown in the input dialogue.
 - If you try to take out a loan and already have one outstanding, your current loan amount (including interest) will be shown.
 - Now you can also right-click on the town's gold icon to display your current outstanding loans (including interest).
 - The last main bank menu option used by each player and also the last player number option for transferring resources are saved.

script06.erm (Hourglass of Asmodeus)
 - Now uses GetBasicPrim function to check hero's true power.

script07.erm (Fishing Well)
 - Script graphic location moved to Data\p folder and graphics renamed.

script09.erm (Market of Time)
 - Script rewritten to use fewer variables and to work with the Unlimited Skills script in 3.59.

script10.erm (Magic Mushrooms)
 - If a hero forgets the temporary Magic Skill (using Market of Time or Advanced Witch Hut), they can no longer use this as a method to get more skills than normally allowed.
 - Some internal function and variable changes also made.

script12.erm (Living Skull)
 - Skull will no longer search for Warlord's Banner.
 - Skull will not bring artifacts with guards attached.
 - If "Heroes pick up double artifacts" is active, you will get two artifacts from the skull.
 - Minor variable changes made (v76-v77 no longer used).

script14.erm (Altar of Transformation)
 - Script graphic location moved to Data\p folder and graphics renamed.

script15.erm (Mysterious Creature Dwelling)
 - A minor typo bug is corrected. The bug doesn't produce a visible error but may affect certain calculations.

script16.erm (Battle Academy)
 - Now uses GetBasicPrim function to correct errors from certain artifacts (mostly Enhanced Commander Artifacts).

script17.erm (Potion Fountains)
 - Berserker potion will set mana after combat but will not add it so it should now be fully-compatible with the Quick Combat no spell points option.

script18.erm (Alms House)
 - Increased the maximum experience a visiting Hero could have in order to receive an experience bonus from the Alms House from 250 to 1000. The amount of experience received remains unchanged.

script19.erm (Masters of Life)
 - Error with upgrading command pertaining to stack experience fixed.

script20.erm (Week of Monsters)
 - A check has been added for Stack Experience enabled--if not enabled, Wandering Monsters will never have Warlord's Banners.
 - Maximum number of Wandering monsters now increased and map size dependent.
 - Increased weekly growth (map size/18 per map level).
 - Monster's aggression, escape ability, and chance of a Warlord's Banner are now dependent on chosen Game Difficulty.

script23.erm (Sorcery)
 - A 3.59 bug fix resulted in a problem with the script working so a minor change has been made to accommodate this for all versions. [FUTURE COMPATIBILITY CHANGE]
 - Minor change to avoid some issues with 3.58f hint text checking filling up the hint text map buffer and producing ERM errors.
 - Sorcery information should now work correctly in network games when its not your turn.

script24.erm (Enhanced Dwelling Hint Text)
 - The script will now give correct information in a network game for non-current players right-clicking.
 - Now using library function for checking local player.

script25.erm (Map Options)
 - When Cartographers replaced with Covers of Darkness had terrain in front of the right-hand square, the Cartographer wasn't deleted (although the CoD was placed)--this has been corrected.
 - Saved message disabling options weren't immediately loaded on map loading--now they are.
 - Buy All Creatures button -- added check for script96 (diplomacy boost).
 - Fixed a bug with the Buy All Button that caused a game freeze if there were more than 998 unbought creatures in the town when the button was clicked.
 - Another bug that erroneously moved a visiting hero's Warlord's Banners to the first stack has also been corrected.
 - Message Disabling option added for script48.erm (Enhanced Secondary Skills)'s pre-combat message of the artillery-boost, and also for the "AI can't flee" message in the (future) script94.erm.
 - Animate Dead and Resurrection are now added as spell-banning options.
 - Duplicate name checks added for Hero and Town Renaming so duplicates won't be possible.
 - If you have a hero with Boosted Mysticism specialization (from script39) and choose Quick Combat without spell points, the hero will only spend spell points added by boosted Mysticism and you won't lose all your spell points.
 - If your hero drinks a Berserker potion and you choose Quick Combat without spell points, it should now work correctly after the battle.
 - Bug with spell-banning function fixed (y-94 was not initialized to 0).
 - Bug with select neutral town types and change in Mage Guild levels and Tower Library corrected.
 - Newly hired Commanders on day 1 only get the same experience as the hiring hero if Choose Commander Class is enabled.
 - For the Buy All Creatures option (click on castle icon), players can now customize for every town the creature levels they don't wish to hire and the creature levels that they want to hire non-upgraded, by ctrl-clicking on the castle icon (the Buy All button).
 - Reading of signs by right-clicking on them (Rewritable Signs script) should now work correctly in network games when it's not your turn.
 - Checking of mana and movement points remaining should now work correctly in network games when it's not your turn.
 - Future Compatibility update: message disabling added for (future) Monster Resources script.
 - Additional checking code added to Buy All Creatures option to ensure no creatures can be bought if the dwelling isn't built, even if there are (phantom) troops present for some reason.

script26.erm (Artificer)
 - Bug with non correct artifact numbers fixed (connected with AI upgrading)
 - AI will never upgrades to artifacts which he already has
 - Still Eye of the Dragon => Pendant of Courage upgrade cost changed to 6000
 - Some get syntax changed with check syntax.
 - Internal ERM syntax corrections.
 - Switched to universal timer.
 - If you have both Diplomacy and Estate secondary skills then you will have reduced gold price according to the lowest skill level of these skills:
   0 (none): 100%
   1 (basic): 90%
   2 (advanced): 80%
   3 (expert): 70%
 - Diplomacy artifacts also decrease cost.
 - Gold price depends on day.
Note: script26.ert updated to fix a small error with the information about upgrading Endless Gold receptacles.

script28.erm (School of Wizardry)
 - Internal ERM syntax correction.
 - Now uses GetBasicPrim function to correct errors from certain artifacts (mostly Enhanced Commander Artifacts).
Note: script28.ert updated to fix some minor grammar and spelling errors.

script30.erm (Adventure Cave)
 - Now War Machines cannot gain extra retaliations in combat from one of the Hermits.

script31.erm (Treasure Chest 2)
 - You'll no longer get an error if there are NO mines on the map (owned or unowned) and a deed to an unowned mine result is generated.
 - Also, will work now correctly with Mithril Forge script [FUTURE COMPATIBILITY CHANGE].
 - Switched from TM28 to TM2 (Universal Timer) and eliminated use of Flag 409.
 - Increased the likelihood of getting a spell scroll of the appropriate level if a duplicate scroll is generated, rather than switching to one of a lower level.

script33.erm (Living Scrolls)
 - Now if you select a Quick Combat battle, you won't see a pre-battle message about Living Scrolls.
 - Checks if the target stack already has the spell active on it and selects another target if it does.
 - Now uses the new RandomStack library function and some internal code changes have also been made.
 - Added message for Teleport by Living Scroll.
Note: script33.ert also updated.

script34.erm (Cards of Prophecy)
 - Fixed compatibility with Berserker Potion -- always adds attack if Berserker Potion is in use to avoid getting extra spell points.

script36.erm (Mithril Enhancements)
 - IMPORTANT: The right-click interface for Mithril enhancements has been changed to a ctrl-click instead. In addition, you will now see information when you ctrl-click on an object if you don't meet the requirements (e.g., not adjacent, not owned, not enough Mithril, etc.)
 - Interface change for click on Kingdom overview:  right-click now displays amount of Mithril in a no-button msgbox while ctrl+K displays Mithril Price list (as hinted in above msgbox).
 - Script graphic location moved to Data\p folder and graphics renamed.
 - Players can now check their own Mithril in network games when it's not their turn.
 - removed extra exclamation mark to avoid problems with 3.59 parser check
 - moved update warning message into .ert file.
Note: The Mithril Price List graphic is also updated.
Note: script36.ert also updated.

script37.erm (Rebalanced Factions)
 - The reduction of Phoenix HP (if Enhanced Monsters was not active) became part of the Wyvern Monarch timer and reduced Phoenix hitpoints (as well as increasing Wyvern Monarch HP and Cost increase) on Day 15 and 22. This has been corrected  by putting the Phoenix HP reduction back in the Day 1 function that triggers when Rebalanced Creatures (option 37) is turned on and not in the additional Wyvern Monarch timer section.
 - (Additional z variables replaced with two others to avoid conflict with Feral Habitat script.)
 - Lizard Warriors now get Double Strike even when Enhanced Monsters is also active.

script38.erm (Karmic Battles)
 - AI experience bonus corrected. Instead of gaining 500 XP for each battle fought (Karmic or otherwise), it will now gain 50 XP x the number of Karmic Battles fought (and only from monster stack battles). This is much closer to the XP gained by human players.

script39.erm (Hero Specialization Boost)
 - If you have a hero with Boosted Mysticism specialization and choose Quick Combat without spell points (from script25), the hero will only spend spell points added by boosted Mysticism and you won't lose all your spell points.
 - Your hero won't get spell points if the Berserker potion is in use.
 - Changed FU804 so that it will now use FU$GetBasicPrim$ to get the correct basic primary skill.
 - Monster bonus will be refreshed before every battle.

script41.erm (Battle Extender)
 - Some internal variable and Function changes made.

script42.erm (Garrisons)
 - Extra check added for garrison being neutral before allowing troop growth there.

script44.erm (Emerald Tower)
 - Corrected bug that prevented Emerald Towers being revisited at the start of a new week.
 - Vampire Lords and Ghost will no longer be offered the "Attack All Adjacent" ability because giving them that ability removes their normal life-drain regenerate and life-drain grow abilities.
 - Added a maximum # of special "Mithril" abilities that may be bought per creature type. L7=1, L6=2, L5=3, L4=4, L3=5, L2=6, L1=7.
 - There was no default selection for the option boxes. Now the default selection is "No thanks, I changed my mind".
 - If you tried to upgrade a monster on a "week of", the wizard tells you that he can't this week, but following this, the dialogue box that asks if you want to leave the Emerald Tower only has an "OK" button and doesn't let you choose not to leave. This has been fixed.
 - Script graphic location moved to Data\p folder and graphics renamed.
 - Corrected a name change bug that occurred if the AI visits and was offered a special ability the creature couldn't get or already had.

script45.erm (Castle Upgrading)
 - Each type of additional upgrade at each town increases in cost after the first, so while there's still no real limit, the practical number of upgrades is limited to 3-5 in most cases.
 - The town dwelling upgrading dialogue box now shows the current bonus growth next to each dwelling option.
 - Now you can check (but not make) upgrades in your towns when it's not your turn in a network game.

script46.erm (Berserker Flies)
 - Chance of Berserker Flies casting Berserk reduced from 100% to 25%.

script48.erm (Enhanced Secondary Skills)
 - Message Disabling option added for pre-combat message of the artillery-boost.
 - Fixed bug with Enhanced ESTATES: now gives daily gold when Enhanced Estates is active (previously gave gold for Enhanced Learning active).
 - Fixed a multiplayer dialog display issue with the Scouting enhancement.
 - Added a check for Map Specifications spell-banning for the Scholar skill enhancement. Previously, only WoG option banning was checked for.
 - Added a check for banning of Animate Dead, Resurrection, and Disguise in WoG options for Enhanced Scholar skill.
 - Fixed First Aid Boost (no additional creatures by using the demon rush strategy)
 - Fixed a random (seldom occurring) crash with the Luck boost.
 - Simplified dialog boxes for most enhanced scouting events so there's only a single dialog instead of two.

script49.erm (Henchmen)
 - War Machine/First Aid healing bug fixed. Resurrection now works too.
 - AI heroes will now keep the same Henchman once they've chosen one. If their Henchman dies and they enter a town, they get free Resurrection.
 - The Henchman choice reminder dialog should now appear at the start of all battles for the attacker and also for the defending Human player, and should no longer appear when visiting creature banks or attacking monsters if a battle doesn't occur.

script51.erm (Enhanced Commanders)
 - Some internal changes made.

script54.erm (Enhanced War Machines I)
 - If you also selected the option to demolish towns, you were unable to click on the former-Blacksmith in most cases to recruit Ghosts and then rebuild the town. This has been fixed.
 - Ballistae reduce the speed to a minimum of half the basic speed of the creature. If a stack is slowed, the minimum Speed is 1/3 of the basic speed (before you could slow a stack down to 1).

script55.erm (Enhanced War Machines II)
 - The catapults were proving way too deadly versus commanders. Adjusted formula for Ballistics catapult "critical hit".  Chance = 5% per catapult + Hero level, capped at 50%. Chance for "critical hit" halved when targeting Commanders.

script56.erm (Metamorphs)
 - If a Metamorph transformed from a 1-hex creature into a 2-hex creature, it overlapped any creature stack directly in front of it, causing this creature to "vanish" from the combat grid (at least temporarily). This has been corrected.
 - You can now use your Metamorph's action to make an optional transformation instead of attacking: right-click on the Wait button to do this.
 - Higher rank Metamorphs now have a minimum level of creature they'll transform into (if possible): Rank 0-3 = No min., Rank 4-5 = Min. Lvl 2, Rank 6-7 = Min. Lvl 3, Rank 8-9 = Min. Lvl 4, Rank 10+ = Min. Lvl 5.

script57.erm (Neutral Units)
 - These four neutral units won't receive stat bonuses (attack, defence, health and bless), only ranks due to the strong nature of their special abilities: Mighty Gorgon (because of Death Stare), Ghost Behemoth (because of Ignores Defence), Nightmare (because of Death Stare), Werewolf (because of Lycanthropy).
 - Also, if the option for creature banks to increase guards and rewards is enabled, Emissary buildings will not increase the number of Emissaries given.
 - Now it does not touch (increase number or set to hostile) monsters that are set to always join, have the No Growth flag set, or have custom text set by the mapmaker.
 - Speed optimizations will save several seconds at game start.
 - Neutral creatures are no longer blessed if the HSB is enabled and they fight vs. Adrienne or a another Fire-Specialist, because their HST Boost is that all enemies are cursed at the start of the battle, and the curse was overwritten by the script57 Bless, so that Adrienne was only a poor witch.

script58.erm (Espionage)
 - Expanded explanation of script added to top of script file.

script60.erm (Forgotten Shrine)
 - script graphic location moved to Data\p folder and graphics renamed.

script62.erm (Split Decision)
 - The AI will no longer try to split a Berserked stack nor will it try to split if its chosen action is a melee attack or walk and attack.
 - If you split a stack that has more than one Warlord's Banner, the split stack gets one too so that both stacks get to keep the Banner bonuses. However, due to a current ERM limitation, it will still show the original stack as having the same number of Banners for the duration of the combat.
 - If you combine two stacks and one has a Banner and the other doesn't, the combined stack will always have a Banner now.
 - Remaining spell castings are now averaged for combined stacks, based on the number of creatures in each stack and rounding fractional values of 0.5 or higher up to 1 (and below 0.5 down to 0). It uses the formula: (N1*C1)+(N2*C2)/(N1+N2), where N1=number in the 1st stack, N2=number in the 2nd stack, C1=number of remaining spell castings for the 1st stack, and C2=number of remaining spell castings for the 2nd stack.
 - If a stack has already gotten morale this round and you split it, neither of the split stacks will be able to get morale again until next round.
 - Additional error-checking and debug display (in the event of an error) added.
 - First error checking debug message disabled for now.

script63.erm (Passable Terrain)
 - The AI no longer has any chance of encountering ambushes when moving through trees or landslides when moving through mountains but is still affected by the reduced movement.

script64.erm (Tobyn's Scripts)
 - FU2333 - LUCK FUNCTION: Get current luck of a hero. Includes check for Spirit Guardian and and sets luck to zero for Hourglass (even if negative).
 Transfer Ownership:
  - Now you can also use shift+left_click to initiate transfer.
  - Level 8 dwellings working in WoG mode now only transfer to ally [no renounce and no enemy allowed because if you can reconquer, you may buy one creature *every* time you reconquer].
  - Town transfer reenabled and tried to avoid multiple growth exploit [code included to disable town transfer on monday and only allow renounce then, but inactive because no problem in hotseat. Have to re-activate the two lines of code if there are problems in MP].
 Estates:
  - Now has auto-Mithril cycling if reaching Exp Est with lvl 10+.
  - Auto-msgbox when reaching lvl10 and Exp Est now only displays once. Can be accessed anytime thereafter by rejecting all resource choices (after left-clicking Expert Estates skill icon).
 First Aid Enhanced:
 - First Aid specialist gives three spells now and also checks for hero specialty when *removing* the 3 spells.
 - Text glitch corrected in Estates skill right-click information that could sometimes show text from another script.

script65.erm (Monolith Toll)
- The option number was being checked using the same variable that was used to trigger Rebalanced Creatures in the Rebalanced Factions script, so it was possible that when Monolith Toll was turned on, the Rebalanced Creatures considered itself on even when it was meant to be off. This has been corrected by changing the variable used to check whether Monolith Toll was on to an unused variable.

script67.erm (Conflux Neutral Town)
 - When active, original Conflux creatures are now set to "neutral" (no town owns them) so they can be combined with other neutral creatures at no morale penalty.
 - A bug which prevented the original Conflux creatures (now neutral) from being upgraded at a Hill Fort is now fixed.
 - Minor bug fixed.

script68.erm (New Battlefields)
 - Battlefield pictures are now read from Data\p and other internal changes have also been made.

script70.erm (Death Chamber)
 - Switched z850 with z848 so that z850-z859 can be reserved for map makers.
 - Internal ERM syntax correction.
Note 1: this change was listed but accidentally omitted from 3.58f.
Note 2: script70.ert is also updated with a minor typo correction.

script71.erm (Enhanced Artifacts)
 - The various pendants that gave spells at the start of combat would not cast them on any creatures with the Dragon flag set, this has been fixed.
 - Notification when Garb of the Forest Lord is assembled was garbled. Also now only displays when fourth artifact is picked up (previously could display if no Alabaster Helmet was present).
 - Commander Artifact changes: Bonus information is now saved in w24. You'll get the bonus from one artifact only once (e.g., if you equip two Slava's rings, you'll only get the bonus once). Even if you become Expert in a secondary skill, the bonus will not be permanent (if you unequip the artifact, you'll be only advanced as before). Before you level up, the bonuses (primary and secondary skills) will be removed. This prevents a player using the artifacts as a "launch pad" for
skills you want (e.g., to get Necromancy for your Knight :-)) and guarantees that you'll be able to master a secondary skill (since the Expert rank will no longer be permanent). Note: After a level up, you won't see the bonuses until you start a battle or click somewhere in the hero screen. It's not ideal but because there's no !$HL-trigger (or it fires to early), this was the only way possible for now.
 - Commander Artifact future compatibility: if you use the quick-transfering in the heroes meeting screen (Transfer All or Transfer Equipped), you'll see the bonuses from the artifacts in the statistic of the hero who had them originally, but the bonuses will be removed, if you click somewhere in the hero screen or start a battle (in the old version this bonus remains permanent, so you could get 100 attack at day one, if you use the transfer several times).

script72.erm (Random Hero)
 - Random heroes may be given a few spells (if their Wisdom allows) to make the battle more challenging.
 - Fixed bugs with spells from earlier update.

script73.erm (Enhanced War Machines III by Bonizag)
 - Fixed: correct number of ballistae / First Aid Tents, if Commander = Ogre Leader / Hierophant.
 - Corrected an incompatibility between script73 and script30 (Adventure Cave). The bug removed all War Machines permanently, if you had a fight in am Adventure Cave (because the Cave-Script removed all War Machines temporarily and the WM-Script permanently, if they weren't equipped in a battle).
 - War Machine Factories now accumulate War Machines too. A battle log bug when a catapult shoots is also fixed.
 - Ammo Carts increase the Damage of your Shooters instead of giving Spell points back.
 - Catapults have been added.
 - Fixed a recursive call that could cause a stack overflow (crash) if the AI had too much gold.
 - Rewritten routines to buy War Machines in towns / factories (much faster / easier now).

script77.erm (WoG Cheat Menu)
 - Added: Function to change the stack size of monsters on the map just before combats by right-clicking on "Attack Value" on the Adventure Screen (only when WoG Cheat Menu is active).
 - If you clicked on a hero in the hero list and chose to give or remove resources, it would apply to the red player rather than the hero's true owner. This is now fixed.
 - Fixed a bug with adding or deleting scrolls in the hero screen.
Note: the "WoG Cheat Menu" is primarily for Mapmakers and testers -- see "Mapmaker Tools.txt" in the Documentation folder for details of how to use this tool.
 - Fixed a bug with building all town dwellings -- if it wasn't a Rampart or Inferno it crashed the game.
 - Fixed a picture display error for variable dump.

