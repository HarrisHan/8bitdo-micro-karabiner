# Images

| 文件名 | 状态 | 内容 |
|---|---|---|
| `hero.jpg` | ✅ 已就位 | 8BitDo Micro 在 Mac 屏幕前的工作场景照（背景是 Claude Code 终端） |
| `product.jpg` | ✅ 已就位 | 8BitDo Micro 实物 + 原包装盒 |
| `keymap.svg` | ✅ 已就位 | 17 键全映射示意图（SVG 矢量图，GitHub 直接渲染） |
| `mode-switch.svg` | ✅ 已就位 | 4 种模式切换组合键示意图 |
| `split-demo.gif` | ⭐ 可选 | Ghostty 多 split 下按 R+方向键切焦点的录屏（< 5MB） |
| `tab-demo.gif` | ⭐ 可选 | Ghostty 多 tab 下按 R2+左右切 tab 的录屏 |
| `claude-code-demo.gif` | ⭐ 可选 | Claude Code 里用方向键 + A 键 Approve 的演示 |

## 拍摄 / 制作建议

- **hero.jpg**: 自然光，干净桌面，手柄边上一台 Mac，屏幕里隐约可见 Claude Code / Ghostty。横版构图便于在 GitHub README 全宽展示。
- **keymap.png**: 用 8BitDo Micro 的官方产品图作底图，用 Figma 在每个按键旁画 callout 标注功能名（Enter / Esc / Fn / Modifier 等）。导出 1400×900 PNG。
- **mode-switch.png**: 简单图表即可，4 行表示 4 种模式 + 对应组合键 + LED 颜色色块。

## 提交方式

把图片放到本目录（`images/`）下，然后：

```bash
cd ~/work/8bitdo-micro-karabiner
git add images/*.{png,jpg,gif}
git commit -m "docs: add visual assets for README"
git push
```

GitHub 会自动渲染 README 里的 `<img>` 标签。
