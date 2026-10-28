# 风格锁定 · 视觉分析

一个用于 Codex 的视觉风格分析 Skill。它从场景参考图提取风格特征，划分严格保持、受控变化和自由变化，并提供语义替换边界与风格偏移检查标准。

它只负责分析与约束：不设计新场景、不编写最终生图提示词、不生成图片，也不验证商品像素级保真。多张场景图默认分别分析；商品图作为商品外观依据，不用于提取场景风格。

## 下载并安装 Skill

1. 在 GitHub 仓库页面点击 **Code → Download ZIP**，解压下载的文件。
2. 将解压后仓库里的 `skills/style-lock` 整个文件夹复制到 Codex 的用户 Skill 目录中，确保最终路径是：
   - Windows：`%USERPROFILE%\.codex\skills\style-lock\SKILL.md`
   - macOS / Linux：`~/.codex/skills/style-lock/SKILL.md`
3. 保留 `agents` 和 `references` 子文件夹。如果目标位置已有同名 Skill，请先核对并备份，不要直接覆盖。
4. 重启 Codex，然后在新对话中使用 `$style-lock` 并提供场景参考图。

## 示例

> 使用 $style-lock 分析这张场景参考图，提取核心风格、变化权限和风格偏移检查标准。

## 文件说明

- `skills/style-lock/SKILL.md`：Skill 指令。
- `skills/style-lock/references/output-format.md`：分析结果的输出格式。
- `skills/style-lock/agents/openai.yaml`：Codex 的显示信息与默认提示。
- `plugin.json` 和 `assets/icon.svg`：原插件元数据和图标。本说明仅保证上述手动安装 Skill 的文件结构，不代表已验证各平台的插件安装流程。

版本：0.1.0。公开仓库并不自动授予特定开源许可证；使用和再分发条款以仓库所有者明确声明的许可证为准。
