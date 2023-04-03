## Blocks
This section describes available blocks and how to use them in your prompts. 

### Character
Fetches a random character from the thesaurus. Character group can be specified to narrow down selection.

Example usage:
```
[file pv/get/character] wearing a funny hat
[file pv/get/character g=mane6], solo, pony, looking back at you, derpibooru_p_95
```

Available groups: `mane6`, `cmc`, `support_cast`, `villan`, `background` and `eqg`.

Sample output:
```
rainbow dash
starlight glimmer
```

### Species
Generates species description. If "character" variable is set or passed, it will favor character's native species. Furthermore, if chosen species ends up being "pony", it will be decorated with pony kind (like "unicorn", for example).

Example usage:
```
rainbow dash, [file pv/get/species character="rainbow dash"], flying in the sky
[file pv/get/species], magenta body, cyan mane and tail, smiling at you
```

Sample output:
```
kirin
alicorn, pony
humanized
```

### Custom
This block is meant to be used in GUI only. It simply outputs whatever the "custom" variable contains.

### Pose
Generates character pose description.

Example usage:
```
trixie, unicorn, solo, [file pv/get/pose], excited, looking at you
```

Sample output:
```
sitting
walking
galloping
```

### Expression
Generates emotion or facial expression description.

Example usage:
```
princess luna, [file pv/get/expression], derpibooru_p_95
```

Sample output:
```
looking back at you
happy
```

### Face
Generates a random facial feature description. Supports repeat count.

Example usage:
```
pinkie pie prancing in a meadow, solo, [file pv/get/face]
fluttershy, [file pv/get/face n=3], cute
```

Sample output:
```
fluffy ears
fiery eyes, large ears
```
> **Note**
>
> This is meant to be more of a wacky/zany kind of block and it can produce some starange (but often funny) images.

### Body
Generates a random body feature description. Supports repeat count.

Example usage:
```
twilight sparkle trotting through the woods, solo, [file pv/get/body]
applejack, [file pv/get/body n=3], derpibooru_p_95
```

Sample output:
```
beautiful hooves
large legs, glowing body, amazing plot
```
> **Note**
>
> This is meant to be more of a wacky/zany kind of block and it can produce some starange (but often funny) images.

### Attire
Generates description of a character's attire. Attire group can be specified to narrow down selection. Supports repeat count.

Example usage:
```
scootaloo, pegasus, solo, [file get/pv/attire]
princess celestia, humanized, solo, [file pv/get/attire n=3 g=sexy], derpibooru_p_95
```

Available groups: `generic`, `headwear`, `outfits` and `sexy`.

Sample output:
```
wearing nun outfit
top hat, socks
wearing cool leather jacket, sunglasses, wearing beanie
```

### Generic
Generates generic description or "magical" buzzwords and phrases we all came to know and love. Supports repeat count.

Example usage:
```
trixie trotting in the fields, unicorn, solo, [file pv/get/generic n=5], derpibooru_p_95
```

Sample output:
```
extremely detailed
astonishing details, vibrant cinematic lighting, trending on artstation, 4K, countershading
```

### Scenery
Generates scenery description. Attire group can be specified to narrow down selection. Supports repeat count.

Example usage:
```
apple bloom, pony, solo, [file pv/get/scenery n=2]
twilight sparkle walking in a park, [file pv/get/scenery g=weather], derpibooru_p_95
princess celestia, alicorn, pony, solo, prancing, ([file pv/get/scenery n=2 g=nature]:0.4), trending on artstation
```

Available groups: `biome`, `nature`, `place`, `time` and `weather`.

Sample output:
```
desert background
forest background, rainy weather
beautiful sunset
big city at night
amazing background
```

> **Note**
>
> This block tends to take away too much attention from the character sometimes. It might be a good idea to lower its weight as shown in one of the examples.

### Medium
Generates a random art medium description. Medium group can be specified to narrow down selection.

Example usage:
```
rainbow dash, pegasus, solo, [file pv/get/medium]
a beautiful [file pv/get/medium g=painting] of happy princess cadance
```

Available groups: `painting`, `drawing`, `realistic` and `other`.

Sample output:
```
pen and paper art
pencil sketch
3d render
acrylic painting
digital drawing
```

### Style
Generates art style description. Style group can be specified to narrow down selection. Supports repeat count.

Example usage:
```
fluttershy, pegasus, solo, smiling at you, blushing, [file pv/get/style]
princess luna flying in the night sky, [file pv/get/style n=3 g=artist]
```

Available groups: `artist`, `art_movement` and `setting`.

Sample output:
```
cyberpunk
post-apocalyptic setting
by Greg Rutkowski
magic the gathering setting, hurufiyya, by Darwyn Cooke
```
