# Blocks
This section describes available blocks and how to use them in your prompts. Blocks can be called by typing `[file pv/get/blockname]` into the prompt where you want the block content to appear. Blocks also have shorthands for convinience which usually come in the form of `[file pv/x]`.

## Character
Fetches a random character from the thesaurus. Character group can be specified to narrow down selection.

Shorthand: `[file pv/c]`.

Available groups: `mane6`, `cmc`, `support_cast`, `villan`, `background` and `eqg`.

Example usage:
```
[file pv/get/character] wearing a funny hat
[file pv/c g=mane6], solo, pony, looking back at you, derpibooru_p_95
```

Sample output:
```
rainbow dash
starlight glimmer
```

## Species
Generates species description. If `character` variable is set or passed, it will favor character's native species. Furthermore, if chosen species ends up being "pony", it will be decorated with pony kind (like "unicorn", for example).

Shorthand: `[file pv/sp]`.

Example usage:
```
rainbow dash, [file pv/get/species character="rainbow dash"], flying in the sky
[file pv/s], magenta body, cyan mane and tail, smiling at you
```

Sample output:
```
kirin
alicorn, pony
humanized
```

## Custom
This block is meant to be used in GUI only. It simply outputs whatever the "custom" variable contains.

## Pose
Generates character pose description. If `species` variable is set or passed, it will automatically choose either pony-specific or humanized/eqg-specific pose descriptions.

Shorthand: `[file pv/p]`.

Available groups: `sfw_only`, `allow_nsfw` and `nsfw_only`.

Example usage:
```
trixie, unicorn, solo, [file pv/get/pose], excited, looking at you
adagio dazzle, equestria girls, [file pv/p species="eqestria girls" g=nsfw_only]
```

Sample output:
```
sitting
walking
galloping
```

> **Warning**
>
> Selecting `sfw_only` doesn't guarantee you from seeing some lewdness in the outputs. It simply guarantees that the block won't generate anything spicy. But outputs can be affected by other factors, such as: artists, intrinsic model biases, other blocks and so on.

## Expression
Generates emotion or facial expression description. Expression group can be specified to narrow down selection. Supports repeat count.

Shorthand: `[file pv/e]`.

Available groups: `emotional` and `facial`.

Example usage:
```
princess luna, [file pv/get/expression], derpibooru_p_95
princess luna, [file pv/e g=facial n=2], derpibooru_p_95
```

Sample output:
```
looking back at you
happy
angry, lidded eyes
```

> **Note**
>
> When repeat count is greater than 1 and group is unspecified, the block will generate 1 emotional description and `n - 1` facial descriptions. This is done to reduce nonsensical outputs like `happy, angry`.

## Face
Generates a random facial feature description. Supports repeat count.

Shorthand: `[file pv/f]`.

Example usage:
```
pinkie pie prancing in a meadow, solo, [file pv/get/face]
fluttershy, [file pv/f n=3], cute
```

Sample output:
```
fluffy ears
fiery eyes, large ears
```
> **Note**
>
> This is meant to be more of a wacky/zany kind of block and it can produce some starange (but often funny) images.

## Body
Generates a random body feature description. If `species` variable is set or passed, it will automatically choose either pony-specific or humanized/eqg-specific body descriptions. Supports repeat count.

Shorthand: `[file pv/b]`.

Available groups: `sfw_only`, `allow_nsfw` and `nsfw_only`.

Example usage:
```
twilight sparkle trotting through the woods, solo, [file pv/get/body]
applejack, [file pv/get/body n=3], derpibooru_p_95
rarity, humanized, [file pv/b species=humanized g=allow_nsfw n=3]
```

Sample output:
```
beautiful hooves
large legs, glowing body, amazing plot
```
> **Note**
>
> This is meant to be more of a wacky/zany kind of block and it can produce some starange (but often funny) images.

> **Warning**
>
> Selecting `sfw_only` doesn't guarantee you from seeing some lewdness in the outputs. It simply guarantees that the block won't generate anything spicy. But outputs can be affected by other factors, such as: artists, intrinsic model biases, other blocks and so on.

## Attire
Generates description of a character's attire. If `species` variable is set or passed, it will automatically choose either pony-specific or humanized/eqg-specific attire descriptions. Attire group can be specified to narrow down selection. Supports repeat count.

Shorthand: `[file pv/a]`.

Available groups: `generic`, `headwear`, `outfits` and `sexy`.

Example usage:
```
scootaloo, pegasus, solo, [file get/pv/attire]
princess celestia, humanized, solo, [file pv/a n=3 g=sexy], derpibooru_p_95
```

Sample output:
```
wearing nun outfit
top hat, socks
wearing cool leather jacket, sunglasses, wearing beanie
```

## Generic
Generates generic description or "magical" buzzwords and phrases we all came to know and love. Supports repeat count.

Shorthand: `[file pv/g]`.

Example usage:
```
trixie trotting in the fields, unicorn, solo, [file pv/get/generic n=5], derpibooru_p_95
starlight glimmer, unicorn, solo, [file pv/g n=5], derpibooru_p_95
```

Sample output:
```
extremely detailed
astonishing details, vibrant cinematic lighting, trending on artstation, 4K, countershading
```

## Scenery
Generates scenery description. Scenery group can be specified to narrow down selection. Supports repeat count.

Shorthand: `[file pv/bg]`.

Available groups: `biome`, `nature`, `place`, `time` and `weather`.

Example usage:
```
apple bloom, pony, solo, [file pv/get/scenery n=2]
twilight sparkle walking in a park, [file pv/get/scenery g=weather], derpibooru_p_95
princess celestia, alicorn, pony, solo, prancing, ([file pv/bg n=2 g=nature]:0.4), trending on artstation
```

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

## Medium
Generates a random art medium description. Medium group can be specified to narrow down selection.

Shorthand: `[file pv/m]`.

Available groups: `painting`, `drawing`, `realistic` and `other`.

Example usage:
```
rainbow dash, pegasus, solo, [file pv/get/medium]
a beautiful [file pv/m g=painting] of happy princess cadance
```

Sample output:
```
pen and paper art
pencil sketch
3d render
acrylic painting
digital drawing
```

## Style
Generates art style description. Style group can be specified to narrow down selection. Supports repeat count.

Shorthand: `[file pv/s]`.

Available groups: `artist`, `art_movement` and `setting`.

Example usage:
```
fluttershy, pegasus, solo, smiling at you, blushing, [file pv/get/style]
princess luna flying in the night sky, [file pv/s n=3 g=artist]
```

Sample output:
```
cyberpunk
post-apocalyptic setting
by Greg Rutkowski
magic the gathering setting, hurufiyya, by Darwyn Cooke
```
