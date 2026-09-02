# BepisPluginSuper

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Upstream](https://img.shields.io/badge/Upstream-IllusionMods%2FBepisPlugins-orange)](https://github.com/IllusionMods/BepisPlugins)

> **BepisPlugins 增强版** — 在保留原版全部功能的基础上，新增 **动态加载** 与 **快捷键热重载** 能力，Mod 修改无需重启游戏，即刷即用。

---

## 核心新增功能

| **功能**             | **原版** | **本 fork** | **说明**                                                     |
| -------------------- | -------- | ----------- | ------------------------------------------------------------ |
| **动态加载**         | **❌**    | **✅**       | **游戏运行时自热重载新增的 `.zip` Mod 包**                   |
| **快捷键热重载**     | **❌**    | **✅**       | **按下默认快捷键Ctrl+D组合快捷键快捷键即可刷新并加载最新 Mod，无需退出游戏** |
| **零重启迭代**       | **❌**    | **✅**       | **修改、添加或替换 Mod 后，刷新一下即可生效**                |
| **添加默认侧载目录** | ❌        | ✅           | 游戏过根目录添加modsOne，在我们从网络，拿到一个新mod时，放入这个隔离modsOne目录，避免mod有问题，影响我们的游戏本体和冲问题，等验证稳定无问题时，移动到默认mods目录 |
| Sideloader           | ✅        | ✅           | 原版全部功能保留                                             |
| ExtensibleSaveFormat | ✅        | ✅           | 原版全部功能保留                                             |
| 其他插件             | ✅        | ✅           | 所有原版插件完整兼容                                         |

### 热重载使用方式

1. 将新的 Mod 文件（`.zip`，.zipmod）拖入游戏目录的 `Mods` 文件夹
2. 在游戏中按下 **热重载快捷键**（默认 `Ctrl+D`，可在 `BepInEx\config` 中修改）
3. 插件自动扫描变更 → 动态加载新增 Mod → 即时生效
4. 无需保存退出、无需重启游戏

> **提示**：热重载仅对支持动态加载的 Mod 类型生效（如服装、贴图、道具等）。涉及底层资源替换或脚本注入的 Mod 仍建议重启以确保稳定性。

---

## 适用游戏

与原 [BepisPlugins](https://github.com/IllusionMods/BepisPlugins) 完全一致：

- Koikatu / Koikatsu Party
- EmotionCreators
- AI-Shoujo / AI-Girl
- HoneySelect2
- HoneyCome
- SamabakeScramble / Summer Vacation Scramble
- 其他 Illusion / Illgames 系游戏

---

## 安装方法

### 前置条件
1. 安装 [BepInEx](https://github.com/BepInEx/BepInEx)
   - HoneySelect2 及更早游戏 → BepInEx 5
   - RoomGirl / HoneyCome 及更新游戏 → BepInEx 6 (nightly build 668+)
2. 安装 [ConfigurationManager](https://github.com/BepInEx/BepInEx.ConfigurationManager)

### 安装本插件
1. 前往 [Releases](../../releases) 下载对应游戏前缀的压缩包（如 `AI` 代表 AI-Girl）
2. 解压到游戏根目录（与游戏 `.exe` 和 `BepInEx` 文件夹同级）
3. 插件记得备份，覆盖旧文件（如有提示）
4. 启动游戏，按 `F1` 打开 ConfigurationManager 确认插件已加载

---

## 配置项

安装后首次启动游戏，会在 `BepInEx\config` 目录生成配置文件：

| 配置项              | 默认值   | 说明             |
| ------------------- | -------- | ---------------- |
| `HotReloadKey`      | `Ctrl+D` | 热重载快捷键     |
| `EnableDynamicLoad` | `true`   | 是否启用动态加载 |

> 修改配置后无需重启游戏，ConfigurationManager 内修改即时生效。

---

## 与原版的关系

本项目是 [IllusionMods/BepisPlugins](https://github.com/IllusionMods/BepisPlugins) 的 **Fork & 功能增强** 版本。

- **原版**：Mod 加载仅在游戏启动时执行一次，新增/修改 Mod 必须重启游戏才能生效
- **本版**：在保留原版全部插件功能与兼容性的前提下，通过新增动态加载模块，实现了运行时的 Mod 热插拔

---

## 构建

```bash
# 克隆仓库
git clone https://github.com/andyyang120/BepisPluginSuper.git
cd BepisPluginSuper

# 还原 NuGet 包
nuget restore

# 构建 Release
msbuild BepisPlugins.sln /p:Configuration=Release
```
## 开源协议

本项目基于上游 [IllusionMods/BepisPlugins](https://github.com/IllusionMods/BepisPlugins) 的 **MIT 协议** 进行分发。

- 原版代码版权归属 [IllusionMods](https://github.com/IllusionMods) 及其贡献者
- 新增功能（动态加载、热重载模块）版权归属本项目维护者

详见 [LICENSE](https://www.kimi.com/chat/LICENSE) 文件。

------

## 致谢

- [IllusionMods](https://github.com/IllusionMods) — 原版 BepisPlugins 的创建者与维护者
- [BepInEx](https://github.com/BepInEx/BepInEx) — 强大的 Unity / IL2CPP 插件框架
- 所有为社区贡献 Mod 的作者

------

> **免责声明**：本插件仅供学习与技术交流使用。使用本插件产生的任何后果由使用者自行承担。

plain

```
---

LICENSE

​```text
MIT License

Copyright (c) 2024 andyyang120 (BepisPluginSuper modifications)
Copyright (c) 2018-2024 IllusionMods (Original BepisPlugins)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

NOTICE: This project is a fork of https://github.com/IllusionMods/BepisPlugins
The original work is copyright IllusionMods and licensed under MIT.
Modifications (dynamic loading, hot-reload functionality) are copyright
andyyang120 and also licensed under MIT.
```
