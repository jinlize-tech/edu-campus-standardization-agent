---
name: edu-campus-standardization-agent-core
display_name: '校区标准化体系建设核心助手'
display_name_en: 'Campus Standardization Agent Core Assistant'
description: '为校区标准化体系建设提供输入校验、结构化整理和成果模板支持'
description_zh: '校验校区目标、组织/流程/服务/教学标准、现状证据、问题和优先级的完整性，并整理为可交付结构'
description_en: 'Validate structured inputs and prepare an output-ready structure for the parent agent.'
examples_zh:
  - '检查我提交的输入字段是否完整'
  - '整理这份业务资料并标出冲突项'
examples_en:
  - 'Check whether my structured input is complete.'
  - 'Organize the supplied business information and flag conflicts.'
version: 1.0.1
author: '广州金励泽科技服务有限公司'
---

# 校区标准化体系建设核心助手

本Skill是Agent内部的结构化支持组件，不替代Agent的诊断、方案设计、人工确认和复盘职责。

## 产品契约

- 核心任务：校区标准化体系诊断与建设。
- 主要风险：照搬单一校区经验或形成过度管控
- 去重边界：与校长经营OS LITE区分：限定标准化体系诊断与建设；与单项巡检/审计工具相比是多步骤编排。

## 输入

- 校区目标
- 组织/流程/服务/教学标准
- 现状证据
- 问题和优先级

## 工作流程

1. 用户提供结构化JSON时，先执行 @scripts/validate_input.js。
2. 输入缺失时返回缺失字段，不要求Agent自行编造。
3. 输入冲突时返回确认项，暂停正式结论。
4. 安全检查通过后，按 @templates/OUTPUT_TEMPLATE.md 建立空结构。
5. 将结构交回Agent继续专业处理。

## 专属检查

- 先明确标准版本、适用校区、检查范围、证据来源和例外条件。
- 按流程节点核对责任人、输入、完成标准、输出和升级机制。
- 区分现状证据、标准要求、差距、影响、整改动作和复验标准。
- 不代替机构作出处罚、人事、财务或行政批准决定。

## 边界

不得代替机构作出处罚或人事决定，不得把检查结果等同于行政批准。

本Skill不产生最终业务结论，不调用外部收费API，不保存用户数据。
