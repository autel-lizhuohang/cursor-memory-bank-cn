# REFLECT 命令 - 任务反思

此命令促进对已完成实施的结构化反思，记录经验教训和流程改进。

## memory bank集成

读取来源:
- `memory-bank/tasks.md` - 已完成的实施详情
- `memory-bank/progress.md` - 实施状态和观察
- `memory-bank/creative/creative-*.md` - 设计决策 (级别 3-4)

创建:
- `memory-bank/reflection/reflection-[task_id].md` - 反思文档

更新:
- `memory-bank/tasks.md` - 反思状态

## 渐进式规则加载

### 步骤 1: 加载核心规则
```
Load: .cursor/rules/isolation_rules/main.mdc
Load: .cursor/rules/isolation_rules/Core/memory-bank-paths.mdc
```

### 步骤 2: 加载 REFLECT 模式映射
```
Load: .cursor/rules/isolation_rules/visual-maps/reflect-mode-map.mdc
```

### 步骤 3: 根据复杂度加载特定反思规则
基于 `memory-bank/tasks.md` 中的复杂度级别:

**级别 1:**
```
Load: .cursor/rules/isolation_rules/Level1/quick-documentation.mdc
```

**级别 2:**
```
Load: .cursor/rules/isolation_rules/Level2/reflection-basic.mdc
```

**级别 3:**
```
Load: .cursor/rules/isolation_rules/Level3/reflection-intermediate.mdc
```

**级别 4:**
```
Load: .cursor/rules/isolation_rules/Level4/reflection-comprehensive.mdc
```

## 工作流程

1. **验证实施完成**
   - 检查 `memory-bank/tasks.md` 中的实施完成情况
   - 如未完成，返回 `/build` 命令

2. **审查实施**
   - 将实施与原始计划进行比较
   - 审查创意阶段决策 (级别 3-4)
   - 审查代码更改和测试

3. **记录反思**

   **级别 1:**
   - 快速审查错误修复
   - 记录解决方案

   **级别 2:**
   - 审查增强功能
   - 记录进展顺利的方面
   - 记录挑战
   - 记录经验教训

   **级别 3-4:**
   - 全面审查实施
   - 与原始计划比较
   - 记录进展顺利的方面
   - 记录遇到的挑战
   - 记录经验教训
   - 记录流程改进
   - 记录技术改进

4. **创建反思文档**
   - 创建 `memory-bank/reflection/reflection-[task_id].md`
   - 结构: 摘要、进展顺利的方面、挑战、经验教训、流程改进、技术改进、后续步骤

5. **更新memory bank**
   - 在 `memory-bank/tasks.md` 中更新反思状态
   - 标记反思阶段为完成

## 使用方法

输入 `/reflect` 开始对已完成任务的反思。

## 后续步骤

反思完成后，进入 `/archive` 命令以完成任务文档归档。
