## Full list of modifications to the server:

### Java Differences
- Withers are easier to fight
- Redstone is different (use different tutorials)
- Java combat is used (attack cooldown, sweeping edge)
- Character Creator skins don't show up to Java players
- Emotes don't work: instead they swap items in offhand
- Glowing effect (raids/spectral arrows) doesn't show up
- Deepslate generates 16 blocks higher (Deepslate coal is possible)
- Snow doesn't fall or stack up by default
- Furnace Minecarts exist

### Mechanics
- Double doors both open at the same time
- Only one player has to sleep to skip night
- Spectral arrows place a torch where they land
- Items are placed into a barrel after death (temporarily)
- A chat message will appear when your tool is about to break
- You can view coords, rotation, by typing `/trigger ch_toggle`
- You can plan nether portal locations by typing `trigger np_[inOverworld/inNether]` depending on your current location
- All statistics are saved as a scoreboard
- Cobblestone generators create Deepslate below Y=0
- Pistons can push block entities like in Bedrock
- Chains stick together like Slime Blocks, but only on the vertical axis
- Glass breaks faster using a Pickaxe

### Mob Behaviour
- Villagers follow emerald blocks (mostly)
- Parrots stay on your shoulder unless you take damage
- Withers keep their focus after reload
- Shulkers can drop double shells
- Guardians struck by lightning become Elder Guardians
- Phantoms grow larger the longer you stay awake
- Mobs drop their heads upon death
- Wandering traders sell miniblock heads
- Name a mob `silence me` to disable sounds

Note: Mob heads don't show up in inventory/when worn due to Bedrock limitations


### Crafting
 (All recipes can be viewed by default from the menu)
- Packed ice can be turned back into Ice
- Coral Plants can be used to make Coral Blocks
- Charcoal can be used to make Black Dye
- Blackstone and Gravel have recipes
- All Cobblestone recipes can be made with Blackstone
- Droppers can be crafted into Dispensers
- Concrete Powder can be smelted into Stained Glass
- Dispensers can be made with sticks and string instead of a bow
- Items such as Concrete, Wool, can be re-dyed
- Items such as Bread, Shulker Boxes, can be made without a table

### Performance
- World render distance will adjust based on player count/CPU load
- Redstone is slightly different, but shouldn't affect majority of contraptions
- Chunks may flicker every few minutes due to distance changes
- Chunks have been pregenerated to reduce CPU load (worldgen tweaks in 1.18.1 won't count)
