# DoL 战斗动作扩展 CombatActionsExt

《Degrees of Lewdity》**ModLoader 模组**：在战斗动作列表里增加性行为动作与脱衣动作。
**不修改任何游戏文件**，全部通过 ModLoader 的段落替换（TweeReplacer）与脚本注入实现。

> 适配版本：**DoL 0.5.12.13**（0.5.11.9 的补丁锚点同样兼容）
> 语言：中文 · 许可：MIT（代码）
> ⚠️ **NSFW**：本模组包含成人向文本内容，仅限成年玩家使用。

## 功能

| 动作 | 部位 | 出现条件 |
|---|---|---|
| 咬 | 敌人（人类/野兽） | 嘴自由且没被捂住/塞住 |
| 脱掉上衣 / 脱掉下衣 | 对方衣物 | 同原版 Undress：`chest/penis/vagina is "clothed"` |
| 揉捏胸部 | 对方胸部 | 上身裸露 |
| 插入小穴 → 继续指奸 → 拳交 → 继续拳交 | 对方小穴 | 小穴已露且空着 |
| 手指插入 → 继续指奸 → 拳交 → 继续拳交 | 对方肛门 | 下衣已脱；入口未占用 |
| 脚揉胸部 → 继续揉胸 | 对方胸部 | 赤脚 + 上身裸露 |
| 脚趾插入 → 继续踩弄 | 对方肛门 | 赤脚 + 下衣已脱 |
| 继续缠着 / 结束战斗 | — | 敌人高潮后出现（本 mod 动作使对方高潮时） |

- 插入状态、入口占用判定、被挤出来/换动作自动退出，全部按原版语义
- 脱衣使用原版 `npcUndressText` / `npcRevealText` / `npcGenitalReaction` / `namedNpcReaction` 与衣物耐久判定
- 动作分类：咬=反抗(def)、脱衣=brat、性行为=sub（写入原版 `combatActionColours`）
- 自检探针：控制台执行 `CombatActionsExtProbe()` 检查加载与 7 条补丁

## 安装

1. ModLoader → 添加 zip → 选 `CombatActionsExt_v0.8.0.zip`
2. 刷新页面
3. 前置：ModLoader + TweeReplacer

## 构建

```powershell
Set-ExecutionPolicy -Scope Process Bypass -Force
pwsh -File .\build-actions.ps1
# 指定游戏目录：
pwsh -File .\build-actions.ps1 -GameDirOverride '<游戏目录>' -OutDir '<输出目录>'
```

## 目录

```
CombatActionsExt/
  boot.json
  twee/CombatActionsExt.tw
  dist/js/probe.js           加载/补丁自检探针
  dist/js/actionColours.js   动作分类着色
build-actions.ps1            构建脚本（7 条 TweeReplacer 补丁）
```

## 声明

- 非官方模组，《Degrees of Lewdity》版权归 **Vrelnir** 所有，请支持正版
- 本 mod 只含自写代码与文本，不含任何游戏资源；免费发布、禁止商用