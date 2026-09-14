# 武器施法联动 / Weapon Spell Cast

用武器施放 [Iron's Spellbooks](https://www.curseforge.com/minecraft/mc-mods/irons-spellbooks)（铁魔法书）里的咒语。

- modId：`weapon_spell_cast`
- 版本：`1.0.0`
- 环境：**Minecraft 1.20.1–1.21 / Forge 47+**
- 必需依赖：`irons_spellbooks` `[3.0,)`（在其后加载）
- 可选依赖：`tacz`（装了才有枪械施法；没装照样用近战/弓）
- 作者：2046820954@qq.com
- License：**MIT**

> 本仓库为「铁魔法武器施法」(`iron_magic_weapon_cast_mod`，近战/弓) 与「枪械法术联动」(`tacz_iron_spell_gun`) 两个旧 mod 的**合并版**，并补全了完整配置文件。

## 三种触发方式（均可单独开关）

| 触发 | 条件 | 关键可调项 |
|------|------|-----------|
| **近战** | 剑/可配置武器攻击命中 | 是否要求蓄力满、只认剑类、触发概率 |
| **远程** | 拉弓射出箭矢 | 只认弓类、最小蓄力、触发概率 |
| **枪械** | TaCZ 开枪 | 每 N 发施放一次、触发概率、枪械 ID 黑白名单 |

## 配置

配置文件：`config/weapon_spell_cast-common.toml`，保存即生效。每种触发方式都可调：

- 冷却倍率、法力消耗倍率、法力返还比例
- 触发概率
- 武器 / 咒语 白名单、黑名单

通用项还包括：总开关、是否只认法术书来源的咒语、是否广播 `SpellOnCastEvent`、是否调用 `onServerCastComplete`、是否检查咒语前置条件、创造模式无视法力/冷却、维度黑名单，以及**按单个咒语覆盖倍率**。

## 仓库内容说明

本次通过 GitHub API 提交的是文本资源：`mods.toml`、`MANIFEST.MF`、`pack.mcmeta`、中英文语言文件。

以下编译字节码未包含在本次 API 提交中（通道仅支持文本）：

- `cn/autoforged/weaponspellcast/**/*.class`（12 个 .class，实际施法/事件逻辑）

完整可运行的 `weapon_spell_cast-1.0.0.jar` 请通过 GitHub 网页「Add file → Upload files」拖拽上传，或在 Release 中发布。
