## Claude 如何记住你的项目

## Skill

```
my-skill/
└── SKILL.md
```

`SKILL.md` 的结构很简单——上半部分告诉 AI"什么时候用我"，下半部分告诉 AI"具体怎么做"：

```
---
name: my-skill                    # ← 上半部分：元数据
description: >-                   #    AI 靠这里决定要不要激活这个技能
  当用户需要做某件事时，使用这个技能。
---

下半部分：操作指令                   # ← AI 激活技能后才会读到这里
按照以下步骤执行...
```

上半部分叫 **frontmatter**（`---` 之间的 YAML），包含 `name` 和 `description` 两个字段。AI 在**每次对话**开始时都会扫描所有已安装技能的 frontmatter，靠 description 来判断"这个技能和当前请求相关吗"——这是技能被触发的**唯一依据**。