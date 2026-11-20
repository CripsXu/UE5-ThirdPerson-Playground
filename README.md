# UE5-ThirdPerson-Playground · 第三人称动作练习场

这是一份用纯蓝图实现的动作玩法练习。玩家可以翻越矮墙、接续近战攻击，并对目标发起双人处决。项目使用增强输入（Enhanced Input）接收操作，用动画通知控制攻击时机，用运动扭曲（Motion Warping）将角色动作对齐到场景目标。

[观看或下载 45 秒实机演示](docs/gameplay-demo.mp4)

## 对照录像阅读蓝图

| 录像时间 | 画面 | 源码入口 |
|---|---|---|
| 00:19–00:24 | 玩家撑过白色矮墙，落在墙的另一侧 | 在 [角色蓝图](Content/ThirdPerson/Blueprints/BP_ThirdPersonCharacter.uasset) 中查看越障目标，再对照 [翻越蒙太奇](Content/Characters/RPG_Characters/Animations/Vaulting/VaultOver_Montage.uasset) 中的 `VaultStart`、`VaultMiddle` 和 `VaultLand`。 |
| 00:28–00:33 | 玩家连续出招，目标受到近战攻击 | 从 [攻击组件](Content/ThirdPerson/Blueprints/BPC_AttackSystem.uasset) 查看连段与命中检测，再打开 [第一段攻击蒙太奇](Content/Characters/RPG_Characters/Animations/SwordAttack/Attack1_Montage.uasset) 查看接续与结束通知。 |
| 00:34–00:39 | 玩家与目标进入配对动作，目标倒地 | 对照 [处决接口](Content/BluePoints/BPI_Assasination.uasset) 和 [目标角色蓝图](Content/BluePoints/BP_Danny.uasset)，查看交互提示以及受方动画的播放入口。 |

## 本地运行

1. 安装 Git LFS，克隆仓库后在仓库根目录运行 `git lfs pull`，下载蓝图、关卡、动画资源和录像。
2. 使用 **虚幻引擎 5.8** 打开 [threepreson.uproject](threepreson.uproject)。
3. 在编辑器中打开 [第三人称演示关卡](Content/ThirdPerson/Lvl_ThirdPerson.umap)，点击工具栏的「运行」。可在 [输入映射](Content/Input/IMC_Default.uasset) 中查看按键绑定。

## 工程目录

- [角色与战斗蓝图](Content/ThirdPerson/Blueprints) 包含玩家角色、控制器、攻击组件和攻击通知。
- [交互与状态](Content/BluePoints) 包含目标角色、处决接口和玩家状态组件。
- [角色动画](Content/Characters/RPG_Characters/Animations) 包含动画蓝图、攻击、受击、翻越和处决蒙太奇。
- [界面](Content/UI) 包含状态显示和交互提示。
