# 智能体客户端与接管入口

资料核对日期：2026-10-06。本页是官方文档调查与试用要求，**不是制作包兼容认证**。尚未有这一版制作包的客户整链验收记录。

## 先区分模型和客户端

GPT、Claude、Grok 可以指模型；实际读取项目说明、访问文件、执行命令的能力由客户端、版本、权限与工具共同决定。不要根据模型自称的品牌选择规则文件，也不要让客户从零编写接管说明。

本支持库以 AGENTS.md 为共同入口，CLAUDE.md 引用它；CODEBUDDY.md 指向同一入口。正式制作包也应预置入口，核心说明只维护一份。无需把同一制作流程复制成多套。

| 客户端 | 官方说明中的入口 | 本项目目前状态 |
|---|---|---|
| Codex 本地客户端 | AGENTS.md | 当前优先内测客户端；Mac 开发机离线检查已做，陌生客户整链仍待实测 |
| Claude Code | CLAUDE.md；可用 `@AGENTS.md` 导入，直接读取 AGENTS.md 受版本和设置影响 | 已提供本支持库的导入入口；完整制作链未测 |
| WorkBuddy | 官方项目文档列出 AGENTS.md / CODEBUDDY.md / .codebuddy 配置兼容 | 已提供本支持库的指引入口；客户端版本、工作空间、执行和看图需实测 |
| Grok Build | 官方文档列出 AGENTS.md 及 Claude 指令文件兼容 | 可评估共用入口；完整制作链未测；不等同于普通 Grok 聊天界面 |
| 豆包工作及其他产品 | 本轮未充分核实相应版本的项目说明加载机制 | 未确认，不能标成兼容，也不等于判定不可用 |

## 开始前实际检查

记录客户端名称/版本、使用的模型（可见时）、操作系统、制作包版本和权限。仅说“我是某模型，我能做”不算通过。

- 能读取当前制作包说明和项目目录。
- 能在指定项目目录写入并读回一个测试文件。
- 能执行包要求的本地工具；缺依赖时明确指出，不绕过权限。
- 能实际查看一张测试图片并描述内容；解析到文件名不算看图。
- 能为用户生成并打开审阅 HTML；用户能播放音频和视频。智能体不必具备浏览器自动操控能力。
- 生图要确认实际可用工具，或明确采用用户外部生图后导入的路径；看图能力不等于生图能力。
- 费用授权、已有任务编号和恢复进度按制作包规则检查，不能在能力检查中自动付费生成。

官方说明支持读取规则，不代表这些检查都能通过；单步检查通过也不代表完整作品已通过用户审阅。

## 使用状态怎样标注

分别记录：文档入口已核实、当前环境检查通过、离线示例通过、真实短片通过、换聊天恢复通过、用户采用。不可将任意前一项写成“全面支持”。

入口根本打不开或智能体接管不了时，允许用户直接反馈截图，不要求先让失效的智能体生成完整报告。其他技术问题按 [问题反馈模板](.github/ISSUE_TEMPLATE/problem.md) 整理，未知项写“未知”。

## 官方资料

- [Codex：AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Claude Code：项目记忆与共享 AGENTS.md](https://code.claude.com/docs/en/memory)
- [WorkBuddy：产品与本地文件能力](https://cloud.tencent.com/product/workbuddy)
- [WorkBuddy：项目级配置与兼容入口](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Project)
- [Grok Build：产品入口](https://docs.x.ai/build/overview)
- [Grok Build：Skills 与指令文件兼容](https://docs.x.ai/build/features/skills-plugins-marketplaces)

产品文档可能更新；客户实际版本与上述入口不一致时，应先核实差异，不自动改写本机全局设置。
