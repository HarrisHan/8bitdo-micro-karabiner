# 8BitDo Micro × Karabiner — Mac AI 生产力手柄

> 把一颗 30 克重的 8BitDo Micro 游戏手柄，变成 Mac 上的「**AI 工作流硬件控制器**」。
>
> Push-to-talk 语音输入 / Claude Code 一键 Approve / Ghostty 终端切 split / 切 tab / 唤起 Raycast — 全部脱离键盘。

<p align="center">
  <img src="images/hero.jpg" alt="8BitDo Micro held in front of a Mac running Claude Code" width="600" />
</p>

---

## ✨ 它能做什么

- 🎙️ **Push-to-talk 语音输入** — 按住 L 肩键说话，松开停止（macOS Dictation / Typeless / Whisper 都能用）
- ✅ **Claude Code 单手 Approve** — A 键 = Enter 确认，B 键 = Esc 中断，方向键选选项
- 🪟 **Ghostty 终端导航** — 按住 R + 方向键切 split，按住 R2 + ←/→ 切 tab
- 🚀 **全局 AI 入口** — Start 键召唤 Raycast/Spotlight，Select 键召唤 Ghostty Quick Terminal
- 🧭 **应用切换** — L2 键 = Cmd+Tab，Home 键 = Mission Control
- 🛡️ **零冲突** — 规则只绑定 8BitDo 设备 ID，不影响其他键盘正常输入

整套规则在 macOS 全局生效，Claude Code、Cursor、Ghostty、浏览器…通通适用。

---

## 🗺️ 完整按键映射

<p align="center">
  <img src="images/product.jpg" alt="8BitDo Micro overview with original packaging" width="500" />
  <br/>
  <em>8BitDo Micro 绿色版 — 仅 30g，可单手握持</em>
</p>

<p align="center">
  <img src="images/keymap.svg" alt="Full keymap diagram" width="100%" />
</p>

### 默认层（不按 modifier）

| 物理按键 | 映射 | 用途 |
|---|---|---|
| **L** 肩键 | `Fn` | 🎙️ Push-to-talk 语音输入（按住说话，松开停止） |
| **L2** 扳机 | `Cmd+Tab` | 切应用 |
| **R** 肩键 | *Modifier 层 1（split）* | 单按无动作，按住进 split 切换层 |
| **R2** 扳机 | *Modifier 层 2（tab）* | 单按无动作，按住进 tab 切换层 |
| **A** | `Enter` | ✅ 确认 / Approve |
| **B** | `Esc` | ❌ 取消 / 中断 Claude / 关弹窗 |
| **X** | `Tab` | 自动补全 / 接受 ghost text |
| **Y** | `Shift+Tab` | Claude Code 模式切换（Plan / Auto-Edit / Normal） |
| **↑↓←→** D-pad | 方向键 | 在选项 / 菜单 / vim / less 里导航 |
| **Select (-)** | `Cmd+\`` | 召唤 Ghostty Quick Terminal（全局） |
| **Start (+)** | `Cmd+Space` | 召唤 Raycast / Spotlight |
| **Home ⌂** | `Ctrl+↑` | Mission Control（全窗口概览） |
| **Star ⭐** | — | 8BitDo Micro 在 Keyboard 模式下此键不发码（死键） |

### Modifier 层（按住 R 或 R2）

| 组合 | 映射 | 用途 |
|---|---|---|
| **R + ↑** | `Cmd+Opt+↑` | Ghostty 切上方 split |
| **R + ↓** | `Cmd+Opt+↓` | Ghostty 切下方 split |
| **R + ←** | `Cmd+Opt+←` | Ghostty 切左侧 split |
| **R + →** | `Cmd+Opt+→` | Ghostty 切右侧 split |
| **R2 + ←** | `Cmd+Shift+←` | Ghostty 切上一个 tab |
| **R2 + →** | `Cmd+Shift+→` | Ghostty 切下一个 tab |

> 💡 **设计逻辑**：R / R2 都是右手键，方向键是左手键 → modifier 用一只手，目标键用另一只手，**双手不抢同一个手指位置**。这是为什么不用 L2 当 modifier 的关键考虑。

---

## 🚀 30 秒安装

### 前置依赖

| 工具 | 版本 | 装法 |
|---|---|---|
| [Karabiner-Elements](https://karabiner-elements.pqrs.org/) | 14+ | `brew install --cask karabiner-elements` |
| 8BitDo Micro 手柄 | 任意 | [官网](https://www.8bitdo.com/micro/) / 各电商平台 |

### 步骤 1：把 8BitDo 切到 Keyboard 模式

8BitDo Micro **底部边缘有一个三档物理拨动开关**，标着 `s` / `d` / `k` 三个档位 — **拨到 `k` 档**就是 Keyboard 模式，手柄会被 macOS 识别为蓝牙键盘。

| 档位 | 模式 | 用途 |
|---|---|---|
| `s` | **S**witch | Nintendo Switch 主机 |
| `d` | **D**-input | Android / Windows 通用 gamepad |
| **`k`** | **K**eyboard ⭐ | **Mac / iOS 当作蓝牙键盘 — 本仓库需要这档** |

> 💡 不需要任何按键组合，也不需要重启手柄，拨过去立刻生效。Keyboard 模式下手柄发出标准 HID 键盘事件，Karabiner 才能拦截。

### 步骤 2：和 Mac 配对

设置 → 蓝牙 → 找到 "8BitDo Micro gamepad" → 配对。

### 步骤 3：导入 Karabiner 规则（任选其一）

#### 方法 A：URL 直接导入（推荐）

把下面这串 URL 粘贴到浏览器地址栏并回车，Karabiner 会自动弹出导入对话框：

```
karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/HarrisHan/8bitdo-micro-karabiner/main/config/8bitdo-micro-rule.json
```

点击「Import」→「Enable All」即生效。

#### 方法 B：手动复制 JSON

1. 打开 Karabiner-Elements → `Complex Modifications` 标签页 → `Add predefined rule`
2. 把 [`config/8bitdo-micro-rule.json`](config/8bitdo-micro-rule.json) 的内容复制到：
   ```
   ~/.config/karabiner/assets/complex_modifications/8bitdo-micro-rule.json
   ```
3. 在 Karabiner UI 里点 `Enable All`

#### 方法 C：直接替换整个 karabiner.json

⚠️ 会覆盖你所有现有规则。**仅在全新安装时使用**。

```bash
cp ~/.config/karabiner/karabiner.json ~/.config/karabiner/karabiner.json.bak
curl -L https://raw.githubusercontent.com/HarrisHan/8bitdo-micro-karabiner/main/config/karabiner.json \
  -o ~/.config/karabiner/karabiner.json
```

### 步骤 4：测试

打开任意文本输入框：

- 按 8BitDo 的 **A 键** → 应该是回车
- 按 **B 键** → 应该是 Esc
- **方向键** → 上下左右
- **按住 R + 方向键** → 应该输出 Cmd+Opt+方向键（在 Ghostty 多 split 时切焦点）

---

## 💡 推荐使用场景

### 场景 1：Claude Code 边走边对话

> 单手拿手柄走来走去，靠它一个 push-to-talk + Approve 就把 AI 工作流跑起来。

1. 按住 **L** 说话 → 系统 Dictation / Typeless 转写到 Claude Code 输入框
2. 松开 **L** → 录音停止
3. 按 **A** → 提交（Enter）
4. Claude 给方案，按 **方向键** 选 Approve / Reject 选项
5. 按 **A** → 确认 / 按 **B** → 取消
6. Claude 跑偏想停，按 **B** → Esc 中断

### 场景 2：Ghostty 多 split 4 屏布局开发

> 一个 Ghostty 窗口分 4 个 split，一只手在键盘上敲代码，另一只手拿手柄切焦点。

```
┌─────────────┬─────────────┐
│  Claude     │  pnpm dev   │  ← R+→ 切到这
│  Code       │  watch      │
├─────────────┼─────────────┤
│  git        │  log tail   │
│  status     │             │
└─────────────┴─────────────┘
```

- **R + 方向键** = 切 split
- **R2 + ←/→** = 切顶部 tab（多个项目并行时）

### 场景 3：会议 / 演讲时的"暗手"操作

> 演讲时手不离开，靠手柄暗操作 Mac：
> - **Start** 召唤 Raycast 搜任何东西
> - **Select** 召唤 Quick Terminal 临时跑命令
> - **Home** 看全窗口概览快速跳转
> - **L2** Cmd+Tab 切 app

---

## 🛠️ 自定义修改

整套规则在 [`config/8bitdo-micro-rule.json`](config/8bitdo-micro-rule.json)。每个 manipulator 是一条独立规则，结构简单：

```jsonc
{
    "type": "basic",
    "conditions": [
        {
            "type": "device_if",
            "identifiers": [{
                "vendor_id": 11720,        // 8BitDo Micro
                "product_id": 36897,        //
                "is_keyboard": true
            }]
        }
    ],
    "from": { "key_code": "g" },           // 手柄 A 键发出的 keycode
    "to": [{ "key_code": "return_or_enter" }] // 改成 Enter
}
```

### 改某个键的功能

1. 用 Karabiner-EventViewer 抓你想改的键发出什么 keycode（详见下面 FAQ）
2. 在 `config/8bitdo-micro-rule.json` 找到对应 manipulator，改 `to` 字段

### 加一个 modifier 组合

照着 R / R2 的模式：

```jsonc
// 1) 让 X 键当 modifier
{
    "from": { "key_code": "h" },           // X 键发出的 keycode
    "to": [{ "set_variable": { "name": "x_layer", "value": 1 }}],
    "to_after_key_up": [{ "set_variable": { "name": "x_layer", "value": 0 }}]
},
// 2) X + ↑ 触发自定义动作
{
    "conditions": [{ "type": "variable_if", "name": "x_layer", "value": 1 }],
    "from": { "key_code": "c" },           // ↑ 键发出的 keycode
    "to": [{ "key_code": "p", "modifiers": ["left_command", "left_shift"] }]  // Cmd+Shift+P
}
```

---

## 🐛 FAQ / 排错

### Q: 8BitDo 没反应

确认下 5 件事：
1. 手柄是不是在 **Keyboard 模式**（紫色 LED） — 不是的话按 `Start+B` 切
2. macOS 蓝牙里手柄状态是 **Connected**
3. Karabiner-Elements 主界面顶部 Status 是绿色（无错误）
4. `Complex Modifications` 标签页里规则是 **Enabled**
5. 按你电脑上的 **Magic Keyboard 上的 g 键**，输入应该正常 — 如果 g 也变成 Enter 了，说明 device_if 没起作用，检查 `vendor_id` / `product_id`

### Q: 我的 8BitDo 按 A 键发出来的不是 g？

每代 8BitDo Micro 固件可能不同。**抓你自己手柄的 keycode** 流程：

1. 打开 `/Applications/Karabiner-EventViewer.app`
2. 切到 `Main` 标签页
3. 按 8BitDo 上的每个键，记录窗口里出现的 `key_code` 字段
4. 同时切到 `Devices` 标签页，记录手柄的 `vendor_id` 和 `product_id`
5. 把 [`config/8bitdo-micro-rule.json`](config/8bitdo-micro-rule.json) 里所有的 `from.key_code` 和 `vendor_id` / `product_id` 改成你的实际值

或者用命令行直接列设备：

```bash
"/Library/Application Support/org.pqrs/Karabiner-Elements/bin/karabiner_cli" --list-connected-devices
```

### Q: L 键按住不能 push-to-talk

`L` 键会发出 `fn`，但是否真的触发录音取决于你装了什么：

- **macOS 系统 Dictation** — 系统设置 → 键盘 → 听写 → 快捷键改成 `按下 Fn 键` (Hold)
- **Typeless / Whisper / SuperWhisper** — 按软件自己的快捷键设置走
- 如果你的工具是 toggle 模式（按一下开，再按一下关），那 push-to-talk 体验会变成"按一下开 + 松手关" — 可以接受

### Q: 普通键盘上按 g/h/i/j/k 也变成 Enter/Tab/Shift-Tab/Esc/Fn 了！

`device_if` 没匹配到 — 可能你的 `vendor_id` 和我的不同。运行：

```bash
"/Library/Application Support/org.pqrs/Karabiner-Elements/bin/karabiner_cli" --list-connected-devices | grep -A 5 -i 8bitdo
```

把里面真实的 `vendor_id` / `product_id` 替换到 JSON 中。

### Q: R / R2 单按时有 0.5 秒延迟感

正常 — Karabiner 在等是否会接「R + 其他键」的组合。如果想消除延迟，可以把 R 改成 `to_if_alone` 模式（单按发某个键），但那样 R 就不能再当纯 modifier 了。

### Q: 我的截屏功能没有了

原方案中 R2 是 `Cmd+Shift+5`（截屏面板），后改为 modifier 让位给 tab 切换。如果想找回截屏：

- macOS 自带快捷键：`Cmd+Shift+4` 区域截屏 / `Cmd+Shift+5` 截屏录屏面板（直接键盘按）
- 或者在 8BitDo Ultimate Software 里把 **Star ⭐** 键映射成发某个 keycode，然后在本规则里加新 manipulator

---

## 🗂️ 仓库结构

```
.
├── README.md
├── LICENSE
├── config/
│   ├── 8bitdo-micro-rule.json     # ⭐ Karabiner Complex Modification（推荐用这个 import）
│   └── karabiner.json             # 完整 karabiner.json 参考
└── images/
    ├── hero.jpg                   # 工作场景图
    ├── keymap.png                 # 全键位映射图
    └── mode-switch.png            # 8BitDo 模式切换说明图
```

---

## 🤝 贡献

欢迎 PR！

- 改进文档 / 翻译 / 加示例图
- 适配其他型号（8BitDo Zero 2 / Lite 2 / Pro 2 …）
- 增加更多 modifier 层组合（截屏 → AI、命令面板、tmux 整合…）

如果你做了适配自己工作流的 fork，在 issue 里贴个链接，我会汇总到 README。

---

## 📜 License

MIT — 随意 fork、修改、商用。

---

## 🙏 Credits

- [Karabiner-Elements](https://karabiner-elements.pqrs.org/) by Takayama Fumihiko
- [8BitDo Micro](https://www.8bitdo.com/micro/) by 8BitDo
- [Ghostty](https://ghostty.org/) by Mitchell Hashimoto
- 灵感来自 vibecoding / 单手 AI 工作流的探索

如果这个仓库对你有帮助，**Star ⭐ 一下**就是最好的反馈。

---

<p align="center">
  Made with 🎮 + ⌨️ + 🤖 by <a href="https://github.com/HarrisHan">@HarrisHan</a>
</p>
