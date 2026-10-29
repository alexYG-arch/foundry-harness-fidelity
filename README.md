# Foundry Harness Fidelity

用于 **Foundry 的 Harness 搭建合同**：从原始 Spec/Plan 出发，核对合同、任务、实现和验收是否保持一致，避免交付一个符合缩小后合同、却缺少原定能力的 Harness。

当前 Skill 版本为 **1.1.2**。本仓库提供语义核对规则、开发对照场景，以及与 Foundry 配合使用的合同说明。具体项目的状态、冻结、批准、预算和执行仍由选定版本的 Foundry 原生流程管理。

## 用于什么合同

这里的“合同”指工程中的搭建与验收约定：根据什么需求、交付哪些 Harness 能力、由谁实现或复用、允许做什么、用什么证据验收。Foundry 的版本化搭建文档及其 Requirement/Plan 承载相应内容，具体执行范围另由真实运行批准绑定；本 Skill 核对这些内容与原始目标是否一致。

**先阅读 [Foundry 合同说明](docs/FOUNDRY_CONTRACT.md)**。其中写明了职责、必需的项目绑定信息、范围与授权边界、交付和验收口径，并给出可以并入现有合同的片段。

适用任务包括：

- 将 Spec/Plan 接入 Foundry，搭建或升级 Harness。
- 审查搭建合同是否遗漏要求、弱化约束或引入无依据的额外要求。
- 检查执行适配、日志、结果解析及下游交接能否支持约定用途。
- 在明确授权下，根据实际结果维护此 Skill。

普通产品文案修改、单纯查询运行状态，不需要展开本 Skill 的流程。

## 使用

将 [foundry-harness-fidelity](foundry-harness-fidelity) 目录放入当前宿主支持的 Skill 目录。下载包只包含该 Skill 的 5 个文件；仓库的合同说明和验证记录单独维护。

审查示例：

```text
使用 $foundry-harness-fidelity，核对当前任务中 Spec/Plan 到 Harness
搭建合同、任务、实现和验收的需求覆盖、范围一致性和实际可用性。
沿用当前有效的阶段决定和授权，报告具体差距、证据及未验证项。
```

搭建示例：

```text
使用 $foundry-harness-fidelity，按我选定的 Spec/Plan 和 Foundry 版本搭建 Harness。
先核对现有合同能否复用，保留完整目标及本阶段边界，按当前有效授权持续推进。
将搭建自测、下游实际可用性和产品执行验收分别报告。
```

将具体来源、版本、阶段、工具、目录和预算绑定在项目现有记录中。没有这些绑定时，通用合同说明本身不能作为某个项目已经批准或可以执行的依据。

## 版本与校验

1.1.2 收紧默认提示词，区分首次接入与增量阅读，明确证据复用条件，并补充真实使用评估的观察方式。原有核心约束及 A–N 共 14 个场景正文保留，新增 O–Q 共 3 个合成对照场景。

- [下载 1.1.2 ZIP](dist/foundry-harness-fidelity-1.1.2.zip)
- [1.1.2 变更与校验说明](docs/VALIDATION_1.1.2.txt)
- [Skill 正文](foundry-harness-fidelity/SKILL.md)

已完成结构、引用、UI 元数据、压缩包完整性及解压内容一致性检查，以及针对性静态复核。17 个场景是已公开答案的开发材料；本版尚未取得独立行为评估或真实任务效率收益的验证结果。

本次发布保持已交付的 1.1.2 Skill 与 ZIP 内容不变，新增的仓库文档用于说明如何接入 Foundry。Foundry 的具体接口与流程以任务选定版本为准，不能由 Skill 的版本号推断兼容性认证。

## 相关项目

[Harness Foundry](https://github.com/alexYG-arch/Harness_Foundry) 提供相应的工程流程与控制机制。使用时核对所选版本的实际接口和约束。
