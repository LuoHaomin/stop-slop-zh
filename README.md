# Stop Slop 中文版

消除中文写作中的AI痕迹。

## 这是什么

AI写中文有明显的套路：开头"随着...的发展"，结尾"任重而道远"，中间堆四字成语、排比句、强调性废话。这个skill教Claude（或任何大模型）识别和去除这些AI写作痕迹。

受 [Hardik Pandya](https://hvpandya.com) 的 [stop-slop](https://github.com/hvpandya/stop-slop) 项目启发，针对中文AI写作特征从零重新设计。

## Skill 结构

```
stop-slop-zh/
├── SKILL.md              # 核心指令
├── references/
│   ├── phrases.md        # 需要去除的短语和套话
│   ├── structures.md     # 需要避免的结构模式
│   └── examples.md       # 修改前后对比示例
├── README.md
└── LICENSE
```

## 安装

通过 [`npx skills`](https://skills.sh) 一键安装（registry 就是 GitHub 本身）：

```bash
# 装到当前项目（.claude/skills/）
npx skills add LuoHaomin/stop-slop-zh

# 装到全局，并指定 Claude Code
npx skills add LuoHaomin/stop-slop-zh -g -a claude-code
```

兼容 Claude Code / Cursor / Codex / Copilot 等 70+ agent。

## 快速开始

**Claude Code：** 用上面的命令安装，或把这个文件夹添加为 skill。

**Claude Projects：** 把 `SKILL.md` 和参考文件上传到项目知识库。

**自定义指令：** 从 `SKILL.md` 复制核心规则。

**API 调用：** 把 `SKILL.md` 包含在系统提示中。参考文件按需加载。

## 能识别什么

**套话** — 开头废话（"随着...的发展"、"不可否认"）、强调性废话（"至关重要"、"意义深远"）、四字成语堆砌、填充副词（"非常"、"显然"、"确实"）、空泛总结（"注入新的活力"）、学术腔。参见 `references/phrases.md`。

**公式化结构** — "不仅...而且..."堆砌、排比句泛滥、假大空的对比、空泛的总结段落、被动句、无生命主语、居高临下的旁白。参见 `references/structures.md`。

**句级问题** — 开头铺垫、感叹号/省略号滥用、连续短句堆叠、偷懒的极端词（"所有"、"永远"）、主动语态缺失。

## 评分

每个维度打1-10分：

| 维度 | 问题 |
|------|------|
| 直接 | 是在陈述还是在宣布？ |
| 节奏 | 有变化还是像节拍器？ |
| 信任 | 尊重读者的智力吗？ |
| 真实 | 读起来像人写的吗？ |
| 密度 | 有什么可以删的？ |

低于35/50：修改。

## 致谢

- 灵感来源：[stop-slop](https://github.com/hvpandya/stop-slop) by [Hardik Pandya](https://hvpandya.com)
- 中文版针对中文AI写作特征从零重写了短语列表、结构模式和示例

## 许可

MIT。自由使用，欢迎分享。
