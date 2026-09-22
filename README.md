# zcode-palette-presets

ZCode 主色 × 底色调色盘的**静态预设主题市场**：48 个主题包（6 主色 × 8 底色，每个含浅色/深色两组 token，合计 96 组明暗配色），全部通过 WCAG AA 校验。色值与 [Soonkeira/ZCodeSoon](https://github.com/Soonkeira/ZCodeSoon) fork 内置调色盘同源。

## 安装（粘贴地址即可）

ZCode / ZCodeSoon 中打开 **设置 → 插件 → 添加插件市场**，粘贴：

```
https://github.com/Soonkeira/zcode-palette-presets
```

然后在市场列表安装 **palette-presets** 并启用，再到 **设置 → 外观 → 主题包** 选择任意预设（如「极光青绿 · 苔砂」「高对比 AAA · 暖砂」）。

> 需要「三排 chips 自由组合 96 组」的完整调色盘面板与图片壁纸功能，请使用 [ZCodeSoon fork](https://github.com/Soonkeira/ZCodeSoon)（README 有构建说明）；本市场是无需构建的静态配色分发通道。

## 目录结构

```
marketplace.json                       # 市场清单（必须在仓库根）
plugins/palette-presets/
├── .zcode-plugin/plugin.json          # 插件清单（themes: "themes"）
└── themes/<主色>-<底色>/theme.json    # 48 个主题包
```

## 重新生成

色值的唯一来源是 ZCodeSoon 仓库的 `packages/ui/src/lib/palette.ts`。改色后在该仓库根执行：

```bash
node --import tsx scripts/gen-palette-presets.ts
```

再把生成的 `docs/palette-presets-marketplace/` 内容同步到本仓库根。
