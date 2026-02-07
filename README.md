# RapidAISkill

本仓库用于存放与 **RapidAI** 相关的 **Skill**（技能），供各类 AI 助手或平台在参与 RapidAI 生态项目开发时复用。Skill 不限于 Cursor：凡是以可复用指引形式、约定 AI 在特定场景下如何完成任务的，均可在本仓库中收纳（如 Cursor Agent Skill、其他 IDE/助手的规则或技能等）。

## 什么是 Skill？

Skill 是一段**可复用的指引**（常见形式如 `SKILL.md` 或各平台自有的规则文件），描述在特定场景下 AI 应如何完成任务、遵循哪些结构与约定。将 Skill 集中放在本仓库中，便于在多个 RapidAI 相关项目中统一引用，保证文档与流程的一致性。本仓库中的 Skill 可能采用某一平台的格式（例如 Cursor 的 Agent Skill），但语义上适用于所有能理解并执行该指引的 AI 工具。

## 仓库结构

```text
RapidAISkill/
├── .cursor/
│   └── skills/           # 所有 Skill 按子目录存放
│       └── <skill-name>/
│           └── SKILL.md   # 技能说明与指引
├── README.md
├── LICENSE
└── .gitignore
```

每个 Skill 以独立子目录形式存放。当前约定放在 `.cursor/skills/` 下（便于 Cursor 直接识别），目录名即技能标识；目录内通常包含 `SKILL.md` 或该平台所需的技能说明文件及可选辅助文件。若为其他平台提供的 Skill，可沿用相同目录结构或注明其适用平台与路径约定。

## 已有 Skill

| Skill | 说明 |
|-------|------|
| [rapid-contributing-guide](.cursor/skills/rapid-contributing-guide/) | 为 RapidAI 风格项目创建或优化贡献指南（`docs/contributing.md`），对齐 RapidOCRDocs 的贡献流程（前置要求、一至八步骤、约定式提交、流程小结等）。 |

## 如何使用

1. **在 Cursor 中引用**
   将本仓库克隆到本地，或在 Cursor 的 Skill 配置中指向本仓库 `.cursor/skills/` 下对应子目录。具体配置方式请参考 Cursor 官方文档中关于 Agent Skills 的说明。

2. **在其他 AI 助手/平台中使用**
   将本仓库克隆或拉取后，根据该平台的规则配置方式，把对应 Skill 目录或文件加入其“技能/规则”路径即可。各平台配置方式请查阅其官方文档。

3. **在项目里使用**
   当你在编写或修改 RapidAI 相关项目的文档、代码时，若触发了某 Skill 的描述场景（例如“编写贡献指南”），AI 会按该 Skill 的指引执行，保证输出符合 RapidAI 的约定。

## 贡献新 Skill

欢迎为 RapidAI 生态补充新的 Skill（例如：Issue/PR 模板、代码规范、发布流程等）。Skill 可以是 Cursor 格式，也可以是其他 AI 平台/助手的规则或技能格式：

1. 在 `.cursor/skills/` 下新建子目录（或按目标平台约定放置），如 `your-skill-name/`。
2. 在该目录中编写技能说明文件（如 `SKILL.md` 或该平台要求的文件名），建议包含：
   - 适用平台（Cursor / 其他）及何时使用、做什么；
   - 若为 Cursor 格式：前置 YAML（`name`、`description`）+ 正文步骤与注意事项；
   - 若为其他平台：按该平台规范编写，并在 README 或本仓库说明中注明。
3. 向本仓库提交 Pull Request，并简要说明该 Skill 的用途、适用场景与适用平台。

编写时可参考 [Cursor 官方 Skill 文档](https://docs.cursor.com) 或本仓库中已有的 `rapid-contributing-guide`；其他平台请参考各自文档。

## 许可证

本项目采用 [Apache License 2.0](LICENSE) 许可。

## 相关链接

- [RapidAI](https://github.com/RapidAI) 组织与相关项目
- Cursor [Agent Skills](https://docs.cursor.com) 文档（以官方最新为准，适用于 Cursor 格式 Skill）
