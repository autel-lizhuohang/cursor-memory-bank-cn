# CREATIVE 命令 - 设计决策

此命令对规划过程中标记的组件执行结构化的设计探索。

## 记忆库集成

读取来源:
- `memory-bank/tasks.md` - 需要创意阶段的组件
- `memory-bank/activeContext.md` - 当前项目上下文

创建:
- `memory-bank/creative/creative-[feature_name].md` - 设计决策文档

更新:
- `memory-bank/tasks.md` - 记录设计决策

## 渐进式规则加载

### 步骤 1: 加载核心规则
```
Load: .cursor/rules/isolation_rules/main.mdc
Load: .cursor/rules/isolation_rules/Core/memory-bank-paths.mdc
```

### 步骤 2: 加载 CREATIVE 模式映射
```
Load: .cursor/rules/isolation_rules/visual-maps/creative-mode-map.mdc
```

### 步骤 3: 加载创意阶段强制规则
```
Load: .cursor/rules/isolation_rules/Core/creative-phase-enforcement.mdc
Load: .cursor/rules/isolation_rules/Core/creative-phase-metrics.mdc
```

### 步骤 4: 加载专业创意规则 (延迟加载)
仅在需要特定创意阶段类型时加载:

**架构设计:**
```
Load: .cursor/rules/isolation_rules/Phases/CreativePhase/creative-phase-architecture.mdc
```

**UI/UX 设计:**
```
Load: .cursor/rules/isolation_rules/Phases/CreativePhase/creative-phase-uiux.mdc
```

**算法设计:**
```
Load: .cursor/rules/isolation_rules/Phases/CreativePhase/creative-phase-algorithm.mdc
```

## 工作流程

1. **验证规划完成**
   - 检查 `memory-bank/tasks.md` 中的规划完成情况
   - 验证创意阶段已被识别
   - 如未完成，返回 `/plan` 命令

2. **识别创意阶段**
   - 从 `memory-bank/tasks.md` 读取标记为创意工作的组件
   - 优先排序设计探索的组件

3. **执行创意阶段**
   对于每个组件:
   - **🎨🎨🎨 进入创意阶段: [类型]**
   - 定义需求和约束
   - 生成 2-4 个设计选项
   - 分析每个选项的优缺点
   - 选择并论证推荐的方法
   - 记录实施指南
   - 验证解决方案符合需求
   - **🎨🎨🎨 退出创意阶段**

4. **记录决策**
   - 创建 `memory-bank/creative/creative-[feature_name].md`
   - 在 `memory-bank/tasks.md` 中更新设计决策

5. **验证完成**
   - 确保所有标记的组件都已完成创意阶段
   - 在 `memory-bank/tasks.md` 中标记创意阶段为完成

## 使用方法

输入 `/creative` 开始对计划中标记的组件进行创意设计工作。

## 后续步骤

所有创意阶段完成后，进入 `/build` 命令进行实施。
