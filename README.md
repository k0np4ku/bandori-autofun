# bandori-autofun
## Overview
Autopatcher for bandori, works for all version/region. The provided tool will automatically unpack the APK, then insert smali files and code which required to load the provided native library.

By using this tool and distributes the generated modified APK on the internet, you're helping me to kill android modders, even if by small percentage. Thank you.

### Features
Adjustable auto-play, manual-always-perfect, no damage, and score multiplier (which has been disabled for reasons).

### Longevity
The provided tool and native library will works even when the game is officially updated, unless there are major changes which affect entire functionality. So, this tool will probably works until the game dies or until another layer of security being added into the game.

### Device support
32-bit ARM and x86, at the moment.

## Requirements
- JRE/JDK 11.02 or newer

## Download
You can download it on [Releases](https://github.com/k0np4ku/bandori-autofun/releases) page.

## Usage
```
$ auto <apk-file>
```

## Configuration
You can find the configuration file on the application's data path.
- **English version:** Android/data/com.bushiroad.en.bangdreamgbp/files/koaConf.ini
- **Japan version:** Android/data/jp.co.craftegg.band/files/koaConf.ini
- **Taiwan version:** Android/data/net.gamon.bdTW/files/koaConf.ini
- **Chinese version:** Uh, idk

In case you fucked up, you can delete the existing koaConf.ini and then a new configuration will be generated, or you can copy the following text:
```
# Note
## Types
# - Boolean: Only accept true & false as its value, and true means enabled, while false means disabled
# - Float: Fractional value, e.g., 1.0, 10.0, 100.0
# - Int: Integrer, or in idiot's language, a number

[main]
# Boolean | Setting this to false will disables entire functionality
enabled=true

# Boolean
# true = autoplay
# false = manual & always perfect
autoplay=true

# Float | Set to 1.0 for no multiplier
# This option has been disabled for reasons
scoreMultiplier=1.0

[manual]
# Boolean
noDamage=true

[autoplay]
# Int | Probability of doing perfect combo
# If rng% is lower than perfectCombo%, then the game will do perfectCombo, otherwise do either greatCombo or goodCombo (if enabled)
perfectComboProbability=98

# Boolean | Enabling this means that when rng% is greater than perfectCombo%, the game will do either greatCombo or goodCombo
# Logic: if rng% is lower than perfectCombo%, do perfectCombo, otherwise -
#        if greatCombo% is greater than goodCombo%, then do greatCombo, otherwise do goodCombo
# Setting this to false means that when rng% is greater than perfectCombo%, the game will simply do greatCombo
doGoodCombo=false

# Int | Probability of doing miss combo
# Logic: if missCombo% is greater than perfectCombo%, then do missCombo, otherwise continue to the next logic (read above)
missComboProbability=0
```
