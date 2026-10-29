# 研究依据与适用限制

本次查阅日期：2026-10-28。用于解释维护选择，不是每次使用 Skill 的必读步骤，也不授予工具权限。论文是特定评测条件下的研究；社区帖子是报告线索；本文提出的具体规则仍需本 Skill 的行为评估。没有将外部代码、性能数字或建议直接设为任务门槛。

## 官方实践

- [OpenAI：Testing Agent Skills Systematically with Evals](https://developers.openai.com/blog/eval-skills)（2026-01-22）。主张观察执行轨迹与成果，分别评估输出、过程及成本，并包含显式、隐式和不应触发的请求。本版据此区分选择、加载和遵循；不照搬示例的样本数、脚本、模型调用或权限。
- [OpenAI：Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra)（2026-09-11）。讨论描述过载、指令重叠与渐进加载。本版收紧描述，将维护评估细节留在引用文件。文章针对其产品背景，不证明本版已正确路由，也不要求切换模型。

## 研究论文

- [SkillsBench v4](https://arxiv.org/abs/2602.12670v4)（2026-06-14版）。使用配对的有/无 Skill 设置评估跨任务表现，观察到效果随模型与任务变化，聚焦的 Skill 组合较有优势。借鉴可比基线和精简指令；其总体结果不能证明本 Skill 的收益。固定引用v4，避免混用早期版本的任务数与结论。
- [SWE-Skills-Bench v2](https://arxiv.org/abs/2603.15401v2)（2026-10-27版）。在可复现工程任务及配对设置中发现，多数所测 Skill 没有显著提升；模板锚定和覆盖明确任务要求是负面案例的机制之一。支持保留真实用户决定、避免凭存在 Skill 宣称提升。预印本结果有样本与配置边界，不推导所有 Skill 无效。

## 工程依据

- [NASA Systems Engineering Handbook：Appendix](https://www.nasa.gov/reference/system-engineering-handbook-appendix/)。定义需求的双向追溯，并允许用现有表格、模型或其他方式承载。本版将其用于来源到实现/验收，以及实现/验收到来源的语义核对；这是对 Harness 的工程应用，不引入 NASA 的全套文档或审批制度。

## 社区讨论与一手报告

- [github/spec-kit #4383](https://github.com/github/spec-kit/issues/4383)（2026-09-01报告，Specify CLI 1.0.1、Claude Code、Windows 11）。报告者称两字段的200字符约束在任务生成中漏掉一处，最终实现选用500。借此构造约束值丢失的开发案例J。本次未取得原始项目或独立复现；自动评估评论也不能替代复现，不能据此判定所有版本都有同一缺陷。
- [openai/codex #23496](https://github.com/openai/codex/issues/23496)（2026-05起；含6月补充）。用户讨论 Skill 已加载却未按要求委派，并报告授权指令冲突。借此区分加载、执行和权限；社区提出的放宽策略不作为本 Skill 权限。不能据此断言当前客户端仍有该缺陷，更不能绕过当前会话禁止子代理的限制。

## 本版自己的评估设计

有效批准需要匹配范围、条件及撤销/到期状态，是对旧版文字歧义的修正。开发案例与未见评估分离、污染后转为开发材料，是防止本 Skill 自证改进的设计选择；上述文献没有直接验证这些文字在本项目中的效果。采用结果仍分别标记结构校验、静态复核、独立行为和真实使用。
