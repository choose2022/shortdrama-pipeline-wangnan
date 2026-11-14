# 短剧全流程 Skill 套件（shortdrama-pipeline）

同样的 00–07 八份模块，**两个版本**，差别只在「模型适配卡」这一处。两版技能名不同，**可以同时装、互不覆盖**。

| 版本 | 目录 | 技能名 / 安装文件夹 | 内容差异 | 适合谁 |
|---|---|---|---|---|
| **基础版** | [`basic/`](basic/) | `shortdrama-pipeline-basic` | 平台中立口径；04 模块第六节只留适配卡接口，按附录 I 自己填卡。**已含「依赖 skill 缺失时：自动安装引导」四步硬规则**（SKILL.md 整节 + 00-总控 §七 指针） | 用 Seedance / 可灵 / 即梦 / Veo 等非 H3 模型，或还没定模型的人 |
| **H3 版** | [`h3/`](h3/) | `shortdrama-pipeline` | 基础版全部内容 + 04 模块第六节末已填好的 **MiniMax H3 视频适配卡**（三栏/六段式、4–15 s、17n+5、图槽 ≤9/≤3/≤3/≤12、台词语法、写实皮肤锁、参考图接线、实测备注）；SKILL.md 硬纪律第 1 条同步指向该卡 | 本机跑 MiniMax H3（本地 ComfyUI / 导演台）的人 |

两版共有：七道前置锁、11 类请求路由表、冲突裁决链（用户指令 > 前置锁 > 规则级别 > 权威比较 > 交用户裁定）、跨环节契约（素材形态 M0/M1/M2 四铁律、参考图三态、台词零丢失 4-gram <0.5、连续性账本五本、付费四步闸门）、模块 00–07、附录 A–K。

## 安装

1. 选定版本（也可两版都装）；
2. 在技能根目录下建文件夹，**名字必须与 `SKILL.md` frontmatter 里的 `name` 一致**：装 `basic/` 就建 `shortdrama-pipeline-basic`，装 `h3/` 就建 `shortdrama-pipeline`；
3. 把该版本的 `SKILL.md` 与 `references/` 直接放进去：

```
<skills-root>/shortdrama-pipeline/          ← h3 版
├── SKILL.md
└── references/
    ├── 00-总控.md
    ├── 01-剧本链.md
    ├── 02-视觉资产.md
    ├── 03-导演与分镜.md
    ├── 04-生成提示词.md
    ├── 05-生产与剪辑.md
    ├── 06-质检与治理.md
    └── 07-附录.md

<skills-root>/shortdrama-pipeline-basic/    ← basic 版，结构完全相同
```

4. **别在外面再套一层目录**：正文里的链接写的是 `references/xx.md`，多套一层就会全部指空。

## 依赖 skill 与本机缺失时的处理

这套件不内置任何第三方正文，但会点名几个外部 skill（`h3-prompt-writing`、`h3-video-prompting`、质检权威 `short-drama-qc-standards-wangnan`）。本机没有时**不许只说"缺了"就停**，按 SKILL.md 的四步走：实测 → 能装就自动装（技能商店同名卡 / 本机打包件 / 仓库整包，均拷进技能根，不许逐份手抄正文）→ 复检 → 仍缺只降级不停链，该条结论写「未完成」不写「通过」。

## 归属与许可

- 整理成文：**wangnan**。方法论来自本机 104 个去重 skill（216 份 SKILL.md）的精读提炼，对账记录见任一版本 `references/00-总控.md` §九。
- 本仓库**不收录**任何第三方 `SKILL.md` 正文段落。文中出现的 skill 名仅作名称引用，正文与版权归各自作者；H3 版适配卡的参数摘自 `h3-prompt-writing/references/base-en.txt` 与 `h3-video-prompting/references/prompt-formats.md`，只摘参数与格式口径，不复制原文段落。
- 质检标准文本的权威版本在 [manju-qc-standards-wangnan](https://github.com/choose2022/manju-qc-standards-wangnan)。
- 许可：**CC BY-NC-SA 4.0**（署名—非商业性使用—相同方式共享），仅覆盖本仓库的原创整理部分；第三方名称与条款的版权归原作者。
