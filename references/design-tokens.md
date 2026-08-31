# 预置设计 Token（默认值）

> 这是本 skill 内置的**默认设计 token**。**用户可以在每次使用技能时上传自己的设计 token 覆盖**（优先级：用户 token > 预置）。
> 用户提供 token 的三种方式：① 直接粘贴值 ② 上传 token 文件（JSON/YAML/DESIGN.md/图片） ③ 提供品牌官网让 agent 提取配色。

## 颜色

| Token | 值 | 用途 |
|---|---|---|
| primary | `#1A5A3F` | 品牌主色，CTA、选中态、品牌元素 |
| primary-hover / pressed | `#145038` / `#0F3F2C` | 按钮状态递进 |
| primary-strong | `#14482F` | 浅底上的主色文字（WCAG AA） |
| primary-soft | `#E6EEE8` | 选中卡片填充、ghost 按钮 |
| accent | `#C8872A` | 唯一信号色（琥珀），只用于需要注意力处 |
| accent-strong | `#8A5A1E` | 信号色系文字（AA） |
| accent-soft | `#F7EDDC` | 信号色标签背景 |
| bg / surface | `#FAF9F6` / `#FFFFFF` | 页面背景 / 卡片表面 |
| ink / ink-2 / ink-3 | `#1E2B25` / `#5E6B64` / `#8A948E` | 正文 / 次级文字 / 占位禁用 |
| border | `#E4E1DA` | 1px 细边框（whisper） |
| success / warning / error | `#2E7D4F` / `#B9791E` / `#B3402F` | 语义状态色 |
| dark-bg / dark-surface | `#121613` / `#1A201C` | 深色模式 |
| dark-text / dark-primary | `#F1F4F0` / `#58A97C` | 深色模式文字 / 提亮主色 |

## 字体

- 栈：系统原生（iOS SF Pro / Android Roboto），不加 web 字体
- 阶梯：34/28/22/20/17/16/15/13/12/11px；标题负字距，正文 0；字重 400-700

## 间距（大留白）

- 基准 4pt 栅格；页边距 ≥24pt；卡片内边距 20pt；卡片间距 16-24pt；区块间距 ≥56pt；触控目标 ≥44pt

## 圆角

- sm 8 / md 12 / lg 16 / xl 24 / pill 999；按钮与输入 12，卡片 16，弹窗 24，chip pill

## 阴影（染色，禁纯黑）

- 卡：`0 4px 20px rgba(26,60,45,.08)`；弹窗：`0 16px 48px rgba(18,40,30,.16)`；多数表面无阴影

## 组件状态（全生命周期）

- 按钮：default / hover / pressed / disabled（禁用用 `#C4CDC6` 底 `#F4F6F4` 字，不用纯 opacity）
- 卡片：default / selected（主色 soft 填充 + 主色边框）
- 输入：default / focus（2pt 主色描边 + soft 光环）/ error（红字 + 红边框）
- 反馈：Toast（ink 底白字，2.2s 自动消失）；操作后 100ms 内可见变化

## 替换规则

1. 每次使用技能，第一步询问：**「你有自己的设计 token 吗？」**（无默认选项）
2. 用户给了 → 解析并**全量替换**预置值（颜色/字体/间距/圆角）
3. 用户没给 → 使用本预置 token 并在交付中注明「默认 token」
4. 换 token 时保证：主色与文字对比度 ≥ WCAG AA（4.5:1），深浅双主题都校验
