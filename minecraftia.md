# Full list of modifications to the server:

## Java Differences
- Some Character Creator skins don't show up
- Redstone is different (use different tutorials)
- Java combat is used (attack cooldown, sweeping edge)
- You can crawl into 1-block spaces by useing a trapdoor
- The Wither isn't as difficult to fight (less health, armour enchants aren't ignored)
- Tridents only drop from Drowned that hold them (not any Drowned)
- Armor stands can't be posed by crouching like usual
- Emotes don't work: instead they swap items in offhand
- Glowing effect (raids/spectral arrows) doesn't show up
- Deepslate generates 16 blocks higher (Deepslate coal is possible)
- Bamboo collision is broken to Bedrock players due to different offset algorithms
- Snow doesn't fall or stack up by default
- Furnace Minecarts exist

## Mechanics
### Commands/Chat
- A private chat message will appear when your tool is about to break
- Many statistics are saved as a scoreboard, for use in games/competition
- You can view coords, orientation, and time by typing `/trigger ch_toggle`
- You can plan nether portal locations by typing `trigger np_[inOverworld/inNether]` depending on your current location
- Armor stands can be modified, but for Bedrock players have to type `/trigger as_trigger set [number]` depending on the wanted pose
- You can check your ping by typing `/ping`
### Redstone
- Cobblestone generators create Deepslate below Y=0
- Pistons can push block entities like in Bedrock
- Chains stick together like Slime Blocks, but only on the vertical axis
- Redstone Dust updates faster, which could affect redstone (minor)
- Dispensers can carve pumpkins, play jukeboxes, and empty cauldrons
- Hopper minecarts can send transfer items into all containers, not just other hoppers.
### Entities
- Villagers follow emerald blocks (mostly)
- Cleric villagers can farm Nether Warts
- All villagers can be converted into zombies
- Parrots stay on your shoulder unless you take damage
- Withers keep their focus after a chunk unloads
- Guardians struck by lightning become Elder Guardians
- Phantoms grow larger the longer you stay awake
- Mobs can be named `silence me` to disable sounds
- Beehives contain lore indicating their contents
### Miscellaneous
- Double doors both open at the same time
- Only one player has to sleep to skip night
- Spectral arrows place a torch where they land
- Blaze powder can grow Nether Warts like bone meal
- Items are placed into a barrel after death (temporarily)
- XP Bottles can be gained by right-clicking an enchant table with a bottle
- XP Bottles can be smelted in a furnace to return experience
- Lingering Weakness potions can convert bedrock into stone
- Flower pots with Wither Roses will keep a chunk loaded
- Chests can be accessed through signs/item frames
- Cakes can be picked up with Silk Touch
- Glass breaks faster using a Pickaxe

## Loot tables
 (All recipes can be viewed by default from the menu)
### Drops
- Shulkers can drop double shells
- Tridents are more likely to drop
- Mobs drop their heads upon death
- Wandering traders sell miniblock heads
- Players drop their own heads (can break for some skins)

Note: Mob heads don't show up in inventory/on armor stands to Bedrock limitations
### Quality of Life
- Items such as Concrete, Wool, can be re-dyed
- Items such as Bread, Shulker Boxes, can be made without a table
- Packed ice can be turned back into Ice
- Dispensers can be crafted in bulk using sticks + string
- Dispensers can be crafted using a Dropper
### Alternate Recipes
- Gravel can be crafted out of Flint
- Charcoal can be used to make Black Dye
- Blackstone can be crafted with Basalt and Coal
- All Cobblestone recipes can be made with Blackstone
- Concrete Powder can be smelted into Stained Glass
- Coral Plants can be used to make Coral Blocks
- 
## Performance
- World render/ticking distance will adjust based on server lag
- Redstone power state calculations are slightly different, but shouldn't affect majority of contraptions
- Chunks may flicker every few minutes due to distance changes (rate can be changed later)
- Some chunks have been pregenerated to reduce CPU load (any worldgen tweaks in 1.18.1 won't count)
