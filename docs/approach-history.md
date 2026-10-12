# 方案历史

检索了仓库现有文档和 Git 历史，未找到专门的方案历史入口；此前未记录的尝试未知。

## S01 — 通用机器人技能与既有验证的发布（2026-10-12）

- 原理：按实际失效阶段路由；任务维数、模型、坐标、控制接口和故障动作从当前合同确定。通过共享执行与连续回放参考、标定可辨识性诊断，去除品牌、固定关节数和特定工程链路假设。
- 适用条件：[dex-robotics-engineering](../dex-robotics-engineering/SKILL.md)、[IK](../dex-ik-design-debug/SKILL.md)、[retargeting](../dex-retargeting-debug/SKILL.md) 和 [impedance](../impedance-gain-tuning/SKILL.md)。本次发布此前已验证的四项内容，保持调用名；其他技能不属本轮范围。
- 状态：技能通用化及一次离线行为评估已完成。本次复用既有结果并移植可审查证据；提交和推送状态以 Git 记录为准。
- 验收标准：发布的 19 个技能文件与受评候选 SHA-256 一致；资源链接可在仓库内解析；元数据与实际适用范围一致；八个虚构任务按预定 23 条标准评估。结构检查、分析行为和物理验证分别报告。
- 实际结果：候选文件 19/19 匹配；公开答复中的 18 个资源链接解析通过。已有独立 agent 在不含对话历史、不读取评分标准的条件下完成八案，随后逐案语义评分，8/8 案通过、23 条标准均检查通过。本次只归一化链接与候选路径、更新答复哈希，未重跑行为评估。单次分析样本不构成求解器性能测试、实机结果或未来行为的统计保证。
- 证据：[实际答复](validation/2026-10-12/forward-responses-001.md)、[评分](validation/2026-10-12/behavior-assessment-001.json)、[候选指纹](validation/2026-10-12/candidate-manifest-001.json)、[发布归一化与检查](validation/2026-10-12/publication-normalization.json)。[可复用案例、方法与评分入口](../dex-robotics-engineering/tests/forward-evaluation.md)留在技能内。
- 重试条件：仅在新增模型或接口合同、实际误路由、行为回归或候选内容改变时追加证据；针对受影响案例复验并关联本条，不以同条件重复测试替代新证据。打包修复与必要链接检查不算算法路线重试。
