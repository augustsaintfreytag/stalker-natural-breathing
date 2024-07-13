![Artwork Natural Breathing 02](https://github.com/augustsaintfreytag/stalker-natural-breathing/assets/7656669/a9f3d8cc-d562-44e8-b920-1e194aaee69b)

# STALKER Natural Breathing

A natural breathing sound system mod for STALKER Anomaly (Open X-Ray/Monolith engine). Gives your character the ability to breathe, even without a gas mask, and when not coughing and dying. The breathing reacts to context and environment, with different styles for everyday exploration, combat, underground spaces, and changes to sounds when having low health or stamina.

Compatible with Voiced Actor Framework by Ayykyu (https://www.moddb.com/members/ayykyu/addons). Primarily designed for War Nymph by Isthar (https://www.moddb.com/mods/stalker-anomaly/addons/war-nymph) and LASS (Ladies and Sister Stalkers) by Paint_Thinner (https://github.com/Paint-Thinner/Ladies-and-Sister-Stalkers-LASS).

## Features

This mod includes the following features:

- Introduces a *reactive breathing system* for the player character.
- Breathing system adopts existing logic for gas mask breathing (hooking into actor effects).
- Regular breathing (not wounded, not low on stamina) has three modes: default, distress, and fear.
- Introduces a *fear factor* system to determine if the character is in a high stress environment.
  - Assigns fear points for safe space, night time, underground, hostile NPCs nearby, in combat, emission imminent.
  - The higher the calculated fear factor is, the more elevated the breathing becomes (3 stages).
- Introduces high quality custom-made female breathing sounds.
  - New sounds cover calm (3 modes), low stamina/running (3 modes), and low health (2 modes).
- Implements a system for residual sounds where one state can persist for a while even if conditions change.
  - Even if a character has restored stamina and could run again, their heartrate would still be elevated.
  - Prevents odd single breaths, e.g. when hitting a stamina threshold, getting one exhausted sound, then a calm one again.
- Significantly cleans up playback system, add types for modes, add reusable logic for cycles.

Notes for *mod developers*: This mod hooks into the Voiced Actor Framework (if present) to automatically detect actor voice lines and suspends breathing cycle until other vocalizations are finished. The mod also detects item usage and suspends to allow item sounds (e.g. eating, drinking, meds) to play that usually already include actor sounds.

To make your mod compatible with Natural Breathing, you can call the following functions from your mod.

#### Stop and Suspend

- Instantly stops any breathing or sweetener sounds.
- Waits at least until `cooldown` has expired to resume breathing cycle.
- Can be used for another actor voice, like a scream.

```lua
z_saint_actor_breathing and z_saint_actor_breathing.stop_and_suspend_breathing(cooldown)
```

#### Suspend Next

- Does not stop an ongoing breath or sweetener sound.
- Suspends breathing and prevents another sound until `cooldown` has expired.
- Can be used for item use sounds, like eating, drinking, or smoking.

```lua
z_saint_actor_breathing and z_saint_actor_breathing.suspend_next_breathing(cooldown)
```

## License

This mod was created by Saint for free use by the STALKER modding community with basic attribution. Scripts and configuration files included with this mod are licensed under the MIT license. Included sound effects use edited bases licensed from Soundstripe under a commercial license.
