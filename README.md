/opt/homebrew/Library/Homebrew/cmd/shellenv.sh: line 18: /bin/ps: Operation not permitted
# 医学中文写作 Skill

`write-medical-chinese` 是一套面向中文医学写作的 Codex Skill，适用于医学文本的撰写、改写、润色、压缩、扩写和审校。

当前稳定版本：`v1.0.0`

## 主要功能

- 在 `Journal` 与 `Grant` 两种模式间由用户选择；
- 保持医学事实、数据、引文、证据强度和适用范围；
- 校准相关性、因果关系、疗效、安全性和不同层级终点的措辞；
- 识别商业化、互联网化、宣传性和口号式表达；
- 改善段落衔接与叙事连续性，避免按文献逐条罗列；
- 根据论文、标书、综述、病例报告、指南解读、课件和学术汇报等体裁调整表达。

## 两种写作模式

| 模式 | 适用内容 | 表达重点 |
| --- | --- | --- |
| `Journal` | 毕业论文、期刊投稿、综述、病例报告、指南解读和研究报告 | 数据、证据边界、平实严谨的表达 |
| `Grant` | 医学基金标书、项目申请、立项依据、创新性和可行性论证 | 科学问题、研究意义、创新性、可行性和预期贡献 |

用户未明确选择时，Skill 会简要说明两种模式、给出推荐及理由，再由用户确认。

## 安装

### 从 GitHub Release 下载

1. 下载对应版本的 ZIP 文件并解压；
2. 将其中的 `write-medical-chinese` 文件夹复制到个人 Skills 目录：

```text
$HOME/.agents/skills/
```

3. 如果 Skill 没有立即出现在列表中，重启 Codex。

安装后的结构应为：

```text
$HOME/.agents/skills/write-medical-chinese/SKILL.md
```

### 从仓库安装

下载或克隆本仓库后，将仓库中的 `write-medical-chinese` 文件夹复制到 `$HOME/.agents/skills/`。不要只复制 `SKILL.md`，参考规范和界面元数据也必须保留。

## 调用

显式调用：

```text
使用 $write-medical-chinese 润色以下医学文本。
```

指定论文模式：

```text
使用 $write-medical-chinese，采用 Journal 模式，润色以下论文讨论。
```

指定标书模式：

```text
使用 $write-medical-chinese，采用 Grant 模式，改写以下立项依据。
```

## 设计原则

- 文风优化不得掩盖医学事实错误或证据外推；
- 词语、句式和研究设计列表均为非穷举示例，不执行机械替换；
- 先识别段落中心和句间关系，再补充必要的过渡词句；
- 标书可以强化论证，但不得提高既有证据强度；
- 论文可以说明研究意义，但不得扩大结论适用范围；
- Skill 只提供写作和审校流程，不替代临床判断、统计审查或独立事实核查。

## 仓库结构

```text
medical-chinese-writing/
├── README.md
├── CHANGELOG.md
├── VERSION
└── write-medical-chinese/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
```

## 更新

下载新版本后，用新版 `write-medical-chinese` 文件夹替换旧版。替换前如有个人修改，请先备份或合并差异。

## 许可

本仓库尚未指定开源许可证。公开发布前应由作者确认使用、修改和再分发条件。
