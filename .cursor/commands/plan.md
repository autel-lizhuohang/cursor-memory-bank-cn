# PLAN 命令 - 任务规划

此命令根据 VAN 模式中确定的复杂度级别创建详细的实施计划。

## 记忆库集成

读取来源:
- `memory-bank/tasks.md` - 任务需求和复杂度级别
- `memory-bank/activeContext.md` - 当前项目上下文
- `memory-bank/projectbrief.md` - 项目基础（如存在）

更新:
- `memory-bank/tasks.md` - 添加详细的实施计划

## 渐进式规则加载

### 步骤 1: 加载核心规则
```
Load: .cursor/rules/isolation_rules/main.mdc
Load: .cursor/rules/isolation_rules/Core/memory-bank-paths.mdc
```

### 步骤 2: 加载 PLAN 模式映射
```
Load: .cursor/rules/isolation_rules/visual-maps/plan-mode-map.mdc
```

### 步骤 3: 根据复杂度加载特定规划规则
基于 `memory-bank/tasks.md` 中的复杂度级别:

**级别 2:**
```
Load: .cursor/rules/isolation_rules/Level2/task-tracking-basic.mdc
Load: .cursor/rules/isolation_rules/Level2/workflow-level2.mdc
```

**级别 3:**
```
Load: .cursor/rules/isolation_rules/Level3/task-tracking-intermediate.mdc
Load: .cursor/rules/isolation_rules/Level3/planning-comprehensive.mdc
Load: .cursor/rules/isolation_rules/Level3/workflow-level3.mdc
```

**级别 4:**
```
Load: .cursor/rules/isolation_rules/Level4/task-tracking-advanced.mdc
Load: .cursor/rules/isolation_rules/Level4/architectural-planning.mdc
Load: .cursor/rules/isolation_rules/Level4/workflow-level4.mdc
```

## 工作流程

1. **读取任务上下文**
   - 读取 `memory-bank/tasks.md` 获取复杂度级别
   - 读取 `memory-bank/activeContext.md` 获取当前上下文
   - 审查代码库结构

2. **创建实施计划**
   - **级别 2:** 记录计划的更改、要修改的文件、实施步骤
   - **级别 3:** 创建包含组件、依赖项、挑战的全面计划
   - **级别 4:** 创建带有架构考虑的分阶段实施计划

3. **技术验证** (级别 2-4)
   - 记录技术栈选择
   - 如需要则创建概念验证
   - 验证依赖项和构建配置

4. **识别创意阶段**
   - 标记需要设计决策的组件
   - 记录哪些组件需要创意探索

5. **更新记忆库**
   - 在 `memory-bank/tasks.md` 中更新完整计划
   - 标记规划阶段为完成

## 使用方法

输入 `/plan` 基于 `memory-bank/tasks.md` 中的任务开始规划。

## 后续步骤

- **如识别到创意阶段:** 使用 `/creative` 命令
- **如无创意阶段:** 进入 `/build` 命令
