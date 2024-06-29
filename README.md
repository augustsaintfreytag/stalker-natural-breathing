(Artwork pending)

# STALKER Natural Breathing

A natural breathing sound system mod for STALKER Anomaly (Open X-Ray/Monolith engine). Gives your character the ability to breathe, even without a gas mask, and when not coughing and dying. The breathing reacts to context and environment, with different styles for everyday exploration, combat, underground spaces, and changes to sounds when having low health or stamina.

Compatible with Voiced Actor Framework by Ayykyu (https://www.moddb.com/members/ayykyu/addons). Primarily designed for War Nymph by Isthar (https://www.moddb.com/mods/stalker-anomaly/addons/war-nymph) and LASS (Ladies and Sister Stalkers) by Paint_Thinner (https://github.com/Paint-Thinner/Ladies-and-Sister-Stalkers-LASS).

> [!WARNING]
> This mod is in active development and not yet functional.
> You may install this mod for personal testing on your own risk.
> This warning will be removed once the mod is completed.

## Features

This mod includes the following features:

- Introduces a *reactive breathing system* for the player character
- Breathing system adopts existing logic for gas mask breathing (hooking into actor effects)
- Regular breathing (not wounded, not low on stamina) has three modes: default, distress, and fear
- Introduces a *fear factor* system to determine if the character is in a high stress environment
  - Assigns fear points for safe space, night time, underground, hostile NPCs nearby, in combat, emission imminent
  - The higher the calculated fear factor is, the more elevated the breathing becomes (3 stages)
- Introduces high quality custom-made female breathing sounds
  - New sounds cover calm (3 modes), low stamina/running (3 modes), and low health (2 modes)
- Implements a system for residual sounds where one state can persist for a while even if conditions change
  - Even if a character has restored stamina and could run again, their heartrate would still be elevated
  - Prevents odd single breaths, e.g. when hitting a stamina threshold, getting one exhausted sound, then a calm one again
- Significantly cleans up playback system, add types for modes, add reusable logic for cycles

## License

This mod was created by Saint for free use by the STALKER modding community with basic attribution. Scripts and configuration files included with this mod are licensed under the MIT license. Included sound effects use edited bases licensed from Soundstripe under a commercial license.
