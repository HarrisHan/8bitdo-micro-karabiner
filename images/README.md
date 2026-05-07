# Images placeholder

放置以下 6 张图片：

| 文件名 | 内容 | 优先级 |
|---|---|---|
| `hero.jpg` | 8BitDo Micro 放在 Mac 旁边的工作场景照片（建议 1600x900 横版，展示"小手柄 + 大屏幕"的对比） | ⭐⭐⭐ 必须 |
| `keymap.png` | 标注了所有 17 个键映射后功能的全景示意图（可以用 Figma / Excalidraw / Photoshop 在产品图上画 callout 标注） | ⭐⭐⭐ 必须 |
| `mode-switch.png` | 8BitDo 4 种模式切换组合键的示意图（Start+B → Keyboard / Start+Y → Switch / Start+X → Android / Start+A → iOS） | ⭐⭐ 推荐 |
| `split-demo.gif` | Ghostty 4 split 布局下，按 R+方向键切焦点的录屏（gif < 5MB） | ⭐ 可选 |
| `tab-demo.gif` | Ghostty 多 tab 下按 R2+左右切 tab 的录屏 | ⭐ 可选 |
| `claude-code-demo.gif` | Claude Code 里用方向键 + A 键 Approve 的演示 | ⭐ 可选 |

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
