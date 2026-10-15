# engineering-han

`engineering-han` 是一套可跨项目复用的个人工程化 Agent Skill。它强调先理解项目、按风险控制流程重量、基于证据开发与调试，并在完成前执行与改动面匹配的验证。

它不是完整 SDD 框架，也不会为每个改动强制生成 proposal、spec、design 和 tasks。项目的具体架构、命令和兼容性要求继续由项目内的 `AGENTS.md` 或同类说明提供。

## 包含的工作模式

- 陌生项目定向与影响面分析
- 功能开发、行为修改和重构
- 系统化问题诊断
- 证据优先的代码审查
- 完成前验证
- 有选择地沉淀项目知识

这些模式统一通过 `$engineering-han` 触发，Skill 会按当前任务只读取需要的参考流程。

## 安装

通过 Skills CLI 全局安装：

```sh
npx skills add aDreamyWind/engineering-han -g -y
```

也可以直接把仓库克隆到 Codex 的 Skills 目录：

```sh
git clone git@github.com:aDreamyWind/engineering-han.git ~/.codex/skills/engineering-han
```

## 使用

显式调用：

```text
使用 $engineering-han 在这个项目中实现用户登录功能。
```

```text
使用 $engineering-han 定位这个并发测试偶发失败的根因并修复。
```

```text
使用 $engineering-han 审查当前分支相对 main 的改动。
```

Skill 默认仅允许显式调用，避免与其他开发流程 Skill 自动重叠；项目自己的指令和用户当前请求始终优先。

## 项目适配

每个项目只需要维护自己的 `AGENTS.md`，说明：

- 项目结构和必读架构文档；
- 构建、测试、lint 和文档命令；
- 项目特有的扩展点、迁移和兼容性规则；
- 不同改动面需要提供的验证证据。

详细建议见 [`references/project-adapter.md`](references/project-adapter.md)。

## 设计原则

- 小改动不强制写计划。
- 中高风险改动才使用简短 Change Brief。
- 项目事实留在项目内，跨项目方法才进入本 Skill。
- 可机械检查的规则应落到测试、类型、lint 或 CI，而不是只写成提示词。
- 只报告实际执行过的验证，不把“未运行”描述为“通过”。
