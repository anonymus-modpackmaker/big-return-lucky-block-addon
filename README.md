# big-return-lucky-block-addon
#Lucky block addon pensato per Spjockey e per la sua community, un progetto per ricordare i vecchi luckyblock giganti.

#Vi ricordo che con questa licenza tutto quello che pubblicate e senza copyright e di pubblico dominio. agite di conseguenza.

#Versione 1.21.8 neoforge

#Richiede la mod originale dei lucky block per funzionare :https://www.curseforge.com/minecraft/mc-mods/lucky-block

#No, non faro una versione per la modern lucky block mod, dato che l'intera struttura dell'addon e molto diversa e gli oggetti come spada fortunata, arco fortunato e le pozioni fortunate non sono supportate.

La mod che uso a supporto verrà rilasciata a parte e probabilmente avrà una licenza diversa dato che la sviluppo con mccreator e con vari plugin che hanno varie licenze, inizio con un buona "base vanilla" e poi miglioro il tutto con drop custom.

per ora l'id del blocco è old_time_lucky_block ma forse lo cambierò in futuro, il formato delle texture sono in una versione più vecchia e quindi potrebbero non funzionare, li aggiornerò in questi giorni insieme ai drop "classici rivisitati", volevo darvi qualcosa da vedere senza farvi aspettare una quantità troppo lunga di tempo.

se volte fare un blocco che vi sputa oggetti con 0 effetti, dove aprite a raffica i blocchi, beh sappiate che io non sono di quell'idea, io penso che sia giusto mette anche oggetti a raffica, ma debba esserci anche qualche "effetto wow" altrimenti non c'è gusto nello spaccare i blocchi.

eccovi un po di esempi  (nota, molti di questi esempi non sono aggiornati ma servono solo per dare l'idea):


/ wither stuff
group(
    type=effect,ID=wither,range=8,duration=30;
    type=particle,ID=splashpotion,potion=weakness;
    type=item,ID=bone,posOffset=#circleOffset(0.0,2.0),amount=10;
    type=item,ID=bone_meal,posOffset=#circleOffset(0.0,2.0),amount=10;
    type=item,ID=skeleton_skull,posOffset=#circleOffset(0.0,2.0)
)@luck=-2


/ negative potions
group(
    type=entity,ID=potion,NBTTag=(
        Item=(id=splash_potion,tag=(Potion=#randList(
            slowness,harming,poison,weakness
        )),Count=1),
        Motion=#motionFromDirection(#rand(0,360),-70,0.4)
    ),amount=10
)@luck=-2


/unlucky other stuff
type=entity,ID=lucky:lucky_projectile,NBTTag=(
        Motion=#motionFromDirection(#rand(0,360),-50,0.4),
        item=(id=diamond_sword),
        damage=7.0)@luck=-1

        
/ auto-breaking block
group(type=command,ID="/setblock ~ ~ ~ minecraft:stone destroy";type=command,ID="/setblock ~ ~ ~ minecraft:diamond_ore destroy",delay=1;type=command,ID="/setblock ~ ~ ~ minecraft:emerald_block destroy",delay=1.5;type=command,ID="/setblock ~ ~ ~ minecraft:gold_block destroy",delay=2;type=command,ID="/setblock ~ ~ ~ minecraft:raw_iron destroy",delay=2.5;type=command,ID="/setblock ~ ~ ~ minecraft:netherite_block destroy",delay=3;type=command,ID="/setblock ~ ~ ~ minecraft:copper_block destroy",delay=2.9;type=command,ID="/setblock ~ ~ ~ minecraft:amethyst_block destroy",delay=1.6;type=command,ID="/setblock ~ ~ ~ lucky:lucky_block destroy",delay=1.3)@luck=2 


/Lucky sword (classic)
group(type=command,ID="/setblock ~ ~-1 ~ minecraft:glowstone destroy";type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~";type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20;\
type=command,ID="/setblock ~ ~-1 ~1 minecraft:raw_gold_block destroy",delay=1;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=1;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=1;\
type=command,ID="/setblock ~1 ~-1 ~1 minecraft:raw_gold_block destroy",delay=2;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=2;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=2;\
type=command,ID="/setblock ~1 ~-1 ~ minecraft:raw_gold_block destroy",delay=3;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=3;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=3;\
type=command,ID="/setblock ~1 ~-1 ~-1 minecraft:raw_gold_block destroy",delay=4;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=4;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=4;\
type=command,ID="/setblock ~ ~-1 ~-1 minecraft:raw_gold_block destroy",delay=5;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=5;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=5;\
type=command,ID="/setblock ~-1 ~-1 ~-1 minecraft:raw_gold_block destroy",delay=6;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=6;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=6;\
type=command,ID="/setblock ~-1 ~-1 ~ minecraft:raw_gold_block destroy",delay=7;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=7;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=7;\
type=command,ID="/setblock ~-1 ~-1 ~1 minecraft:raw_gold_block destroy",delay=8;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=8;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=8;\
type=item,ID=lucky:lucky_sword,NBTTag=(Enchantments=#luckySwordEnchantments,Luck=100,display=(Name=#jsonStr(text="Lucky Sword",color=yellow,bold=true)),Unbreakable=true),delay=13;type=entity,ID=LightningBolt,delay=9;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=18,delay=10;type=command,ID="/setblock ~ ~ ~ minecraft:air",delay=10;\
type=command,ID="/setblock ~ ~ ~1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~-1 ~ ~1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~-1 ~ ~ minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~-1 ~ ~-1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~ ~ ~-1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~1 ~ ~-1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~1 ~ ~ minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~1 ~ ~1 minecraft:air destroy",delay=11)@luck=1


/Lucky bow (classic)
group(type=command,ID="/setblock ~ ~-1 ~ minecraft:sea_lantern destroy";type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~";type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20;\
type=command,ID="/setblock ~ ~-1 ~1 minecraft:raw_gold_block destroy",delay=1;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=1;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=1;\
type=command,ID="/setblock ~1 ~-1 ~1 minecraft:raw_gold_block destroy",delay=2;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=2;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=2;\
type=command,ID="/setblock ~1 ~-1 ~ minecraft:raw_gold_block destroy",delay=3;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=3;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=3;\
type=command,ID="/setblock ~1 ~-1 ~-1 minecraft:raw_gold_block destroy",delay=4;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=4;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=4;\
type=command,ID="/setblock ~ ~-1 ~-1 minecraft:raw_gold_block destroy",delay=5;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=5;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=5;\
type=command,ID="/setblock ~-1 ~-1 ~-1 minecraft:raw_gold_block destroy",delay=6;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=6;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=6;\
type=command,ID="/setblock ~-1 ~-1 ~ minecraft:raw_gold_block destroy",delay=7;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=7;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=7;\
type=command,ID="/setblock ~-1 ~-1 ~1 minecraft:raw_gold_block destroy",delay=8;type=command,ID="/playsound minecraft:block.stone.break @a ~ ~ ~",delay=8;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=20,delay=8;\
type=item,ID=lucky:lucky_bow,NBTTag=(Enchantments=#luckyBowEnchantments,Luck=100,display=(Name=#jsonStr(text="Lucky Bow",color=yellow,bold=true)),Unbreakable=true),delay=13;type=entity,ID=LightningBolt,delay=9;type=particle,ID="cloud",size=(0.5,0.5,0.5),particleAmount=18,delay=10;type=command,ID="/setblock ~ ~ ~ minecraft:air",delay=10;\
type=command,ID="/setblock ~ ~ ~1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~-1 ~ ~1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~-1 ~ ~ minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~-1 ~ ~-1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~ ~ ~-1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~1 ~ ~-1 minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~1 ~ ~ minecraft:air destroy",delay=11; \
type=command,ID="/setblock ~1 ~ ~1 minecraft:air destroy",delay=11)@luck=1


non nego che tendo ad abusare dei blocchi in caduta, roba tipo questa:


/ falling blocks (iron, gold, diamond, emerald)
/ launched blocks
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=lucky:lucky_block),Motion=#randLaunchMotion),amount=10@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=lucky:lucky_block),Motion=#randLaunchMotion),amount=20@chance=0.4@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=bedrock),Motion=#randLaunchMotion),amount=15@chance=0.1@luck=-2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=diamond_block),Motion=#randLaunchMotion),amount=15@chance=0.3@luck=2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=dragon_egg),Motion=#randLaunchMotion),amount=15@chance=0.2@luck=2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=emerald_block),Motion=#randLaunchMotion),amount=15@chance=0.3@luck=2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=gold_block),Motion=#randLaunchMotion),amount=15@chance=0.4@luck=1
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=netherite_block),Motion=#randLaunchMotion),amount=15@chance=0.3@luck=3
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=iron_block),Motion=#randLaunchMotion),amount=15@chance=0.4@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=redstone_block),Motion=#randLaunchMotion),amount=15@chance=0.5@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=lapis_block),Motion=#randLaunchMotion),amount=15@chance=0.5@luck=1
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=copper_block),Motion=#randLaunchMotion),amount=15@chance=0.5@luck=1
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=amethyst_block),Motion=#randLaunchMotion),amount=15@chance=0.5@luck=1
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=end_portal_frame),Motion=#randLaunchMotion),amount=15@chance=0.2@luck=-2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=fire),Motion=#randLaunchMotion),amount=15@luck=-2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=soul_fire),Motion=#randLaunchMotion),amount=15@luck=-2
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=tnt),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=glowstone),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=obsidian),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=crying_obsidian),Motion=#randLaunchMotion),amount=15@luck=0
/type=entity,ID=falling_block,NBTTag=(BlockState=(Name=cherry_wood),Motion=#randLaunchMotion),amount=15@luck=0
/type=entity,ID=falling_block,NBTTag=(BlockState=(Name=bamboo_planks),Motion=#randLaunchMotion),amount=15@luck=0
/type=entity,ID=falling_block,NBTTag=(BlockState=(Name=bamboo_block),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=sculk),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=#randColor_concrete),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=#randColor_concrete_powder),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=#randColor_wool),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=#randColor_terracotta),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=#randColor_stained_glass),Motion=#randLaunchMotion),amount=15@luck=0
type=entity,ID=falling_block,NBTTag=(BlockState=(Name=#randColor_glazed_terracotta),Motion=#randLaunchMotion),amount=15@luck=0

group(type=fill,ID=air,size=(1,51,1);
    type=entity,ID=falling_block,NBTTag=(BlockState=(Name=redstone_block)),posY=#bPosY+5;
    group(posY=#bPosY+10;posY=#bPosY+15;posY=#bPosY+20;posY=#bPosY+25;posY=#bPosY+30;posY=#bPosY+35;posY=#bPosY+40;posY=#bPosY+45;posY=#bPosY+50),type=entity,ID=falling_block,NBTTag=(BlockState=(Name=lucky:lucky_block))
)@luck=2
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=lucky:lucky_block)),amount=350,posOffset=#circleOffset(5,100)@chance=0.5@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=netherite_block)),amount=350,posOffset=#circleOffset(5,100)@chance=0.1@luck=75
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=diamond_block)),amount=350,posOffset=#circleOffset(5,100)@chance=0.3@luck=50
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=dragon_egg)),amount=350,posOffset=#circleOffset(5,100)@chance=0.3@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=redstone_block)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=cobweb)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=tnt)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=fire)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=soul_fire)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=emerald_block)),amount=350,posOffset=#circleOffset(5,100)@chance=0.5@luck=2
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=gold_block)),amount=350,posOffset=#circleOffset(5,100)@chance=0.5@luck=20
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=bedrock)),amount=350,posOffset=#circleOffset(5,100)@chance=0.1@luck=-50
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=obdsidian)),amount=350,posOffset=#circleOffset(5,100)@luck=0
/type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=cherry_leaves)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_candle)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_wool)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_concrete_powder)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_concrete)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_terracotta)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_shulker_box)),amount=350,posOffset=#circleOffset(5,100)@luck=0
type=entity,ID=falling_block,posY=#bPosY+7,NBTTag=(BlockState=(Name=#randColor_glazed_terracotta)),amount=350,posOffset=#circleOffset(5,100)@luck=0





