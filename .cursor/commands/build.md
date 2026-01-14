# BUILD 命令 - 代码实施

此命令按照实施计划和创意阶段决策实施计划的更改。它强制执行测试驱动的方法，即为所有成功标准编写测试，并且在完成每个阶段之前测试必须通过。

## 记忆库集成

读取来源:
- `memory-bank/tasks.md` - 实施计划和检查清单
- `memory-bank/creative/creative-*.md` - 设计决策 (级别 3-4)
- `memory-bank/activeContext.md` - 当前项目上下文

更新:
- `memory-bank/tasks.md` - 实施进度、测试结果和状态
- `memory-bank/progress.md` - 构建状态、测试结果和观察

## 渐进式规则加载

### 步骤 1: 加载核心规则
```
Load: .cursor/rules/isolation_rules/main.mdc
Load: .cursor/rules/isolation_rules/Core/memory-bank-paths.mdc
Load: .cursor/rules/isolation_rules/Core/command-execution.mdc
```

### 步骤 2: 加载 BUILD 模式映射
```
Load: .cursor/rules/isolation_rules/visual-maps/build-mode-map.mdc
```

### 步骤 3: 根据复杂度加载特定实施规则
基于 `memory-bank/tasks.md` 中的复杂度级别:

**级别 1:**
```
Load: .cursor/rules/isolation_rules/Level1/workflow-level1.mdc
Load: .cursor/rules/isolation_rules/Level1/optimized-workflow-level1.mdc
```

**级别 2:**
```
Load: .cursor/rules/isolation_rules/Level2/workflow-level2.mdc
```

**级别 3-4:**
```
Load: .cursor/rules/isolation_rules/Level3/implementation-intermediate.mdc
Load: .cursor/rules/isolation_rules/Level4/phased-implementation.mdc
```

## 工作流程

1. **验证前置条件**
   - 检查 `memory-bank/tasks.md` 中的规划完成情况
   - 对于级别 3-4: 验证创意阶段文档是否存在
   - 审查实施计划

2. **确定复杂度级别**
   - 从 `memory-bank/tasks.md` 读取复杂度级别
   - 加载适当的工作流规则

3. **执行实施**

   **级别 1 (快速错误修复):**
   - 审查错误报告
   - 检查相关代码
   - 实施针对性修复
   - 编写验证修复的测试
   - 运行测试并确保通过
   - 更新 `memory-bank/tasks.md`

   **级别 2 (简单增强):**
   - 审查构建计划
   - 检查相关代码区域
   - 按顺序实施更改
   - 为每个成功标准编写测试
   - 运行所有测试并确保通过
   - 更新 `memory-bank/tasks.md`

   **级别 3-4 (功能/系统):**
   - 审查计划和创意决策
   - 创建目录结构
   - 按计划阶段构建
   - **每个阶段:**
     - 为所有阶段成功标准编写测试
     - 运行测试并确保通过
     - 在所有测试通过之前不要进入下一阶段
   - 集成测试
   - 记录实施
   - 更新 `memory-bank/tasks.md` 和 `memory-bank/progress.md`

4. **测试驱动的阶段完成**
   - 从 `memory-bank/tasks.md` 中提取当前阶段的成功标准
   - 编写覆盖每个成功标准的测试用例
   - 执行所有测试
   - **门槛:** 所有测试必须通过才能完成阶段
   - 在 `memory-bank/tasks.md` 中记录测试结果
   - 如果测试失败: 修复实施，重新运行测试，重复直到全部通过

5. **命令执行**
   - 记录所有执行的命令
   - 记录结果和观察
   - 遵循特定平台的命令指南

6. **验证**
   - 验证所有构建步骤已完成
   - 验证所有成功标准测试通过
   - 验证更改符合需求
   - 在 `memory-bank/tasks.md` 中更新完成状态

## 使用方法

输入 `/build` 基于 `memory-bank/tasks.md` 中的计划开始实施。

## 后续步骤

实施完成后，进入 `/reflect` 命令进行任务审查。
