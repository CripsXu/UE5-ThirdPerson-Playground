# UE5-ThirdPerson-Playground

A third-person action study implemented in Unreal Engine 5.8 using Blueprints, Enhanced Input, animation montages and Motion Warping.

[Watch or download the 45-second gameplay capture](docs/gameplay-demo.mp4)

| Recording | Feature | Start reading here |
|---|---|---|
| 19-24 s | Vault over a low wall | BP_ThirdPersonCharacter and VaultOver_Montage |
| 28-33 s | Melee attacks and hit reactions | BPC_AttackSystem, sword combo notifies and BP_Danny |
| 34-39 s | Paired close-range takedown | BPI_Assasination and the attacker/victim montages |

## Run locally

Install Git LFS, clone the repository and run `git lfs pull`. Open `threepreson.uproject` with Unreal Engine 5.8 and play `/Game/ThirdPerson/Lvl_ThirdPerson`. Input bindings live in `/Game/Input/IMC_Default`.

## Project layout

- [Character and combat Blueprints](Content/ThirdPerson/Blueprints)
- [Target, interface and player state](Content/BluePoints)
- [Animation Blueprint and montages](Content/Characters/RPG_Characters/Animations)
- [HUD and interaction prompt](Content/UI)

This private snapshot includes third-party animation and character assets. Check the applicable rights before redistributing the project or footage. The original play log recorded a divide-by-zero warning in ABP_RPGCharacter. The capture demonstrates gameplay; a packaged build is not included.
