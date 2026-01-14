# ARCHIVE 命令 - 任务归档

此命令创建全面的归档文档并更新记忆库以供将来参考。

## 记忆库集成

读取来源:
- `memory-bank/tasks.md` - 完整的任务详情和检查清单
- `memory-bank/reflection/reflection-[task_id].md` - 反思文档
- `memory-bank/progress.md` - 实施状态
- `memory-bank/creative/creative-*.md` - 创意阶段文档 (级别 3-4)

创建:
- `memory-bank/archive/archive-[task_id].md` - 归档文档

更新:
- `memory-bank/tasks.md` - 标记任务为完成
- `memory-bank/progress.md` - 添加归档引用
- `memory-bank/activeContext.md` - 为下一个任务重置

## 渐进式规则加载

### 步骤 1: 加载核心规则
```
Load: .cursor/rules/isolation_rules/main.mdc
Load: .cursor/rules/isolation_rules/Core/memory-bank-paths.mdc
```

### 步骤 2: 加载 ARCHIVE 模式映射
```
Load: .cursor/rules/isolation_rules/visual-maps/archive-mode-map.mdc
```

### 步骤 3: 根据复杂度加载特定归档规则
基于 `memory-bank/tasks.md` 中的复杂度级别:

**级别 1:**
```
Load: .cursor/rules/isolation_rules/Level1/quick-documentation.mdc
```

**级别 2:**
```
Load: .cursor/rules/isolation_rules/Level2/archive-basic.mdc
```

**级别 3:**
```
Load: .cursor/rules/isolation_rules/Level3/archive-intermediate.mdc
```

**级别 4:**
```
Load: .cursor/rules/isolation_rules/Level4/archive-comprehensive.mdc
```

## 工作流程

1. **验证反思完成**
   - 检查 `memory-bank/reflection/reflection-[task_id].md` 是否存在
   - 验证反思是否完成
   - 如未完成，返回 `/reflect` 命令

2. **创建归档文档**

   **级别 1:**
   - 创建快速摘要
   - 更新 `memory-bank/tasks.md` 标记任务完成

   **级别 2:**
   - 创建基础归档文档
   - 记录所做的更改
   - 更新 `memory-bank/tasks.md` 和 `memory-bank/progress.md`

   **级别 3-4:**
   - 创建全面的归档文档
   - 包含: 元数据、摘要、需求、实施细节、测试、经验教训、参考资料
   - 归档创意阶段文档
   - 记录代码更改
   - 记录测试方法
   - 总结经验教训
   - 更新所有记忆库文件

3. **归档文档结构**
   ```
   # 任务归档: [任务名称]

   ## 元数据
   - 任务 ID、日期、复杂度级别

   ## 摘要
   任务的简要概述

   ## 需求
   任务需要完成的内容

   ## 实施
   任务是如何实施的

   ## 测试
   如何验证解决方案

   ## 经验教训
   任务的关键收获

   ## 参考资料
   相关文档链接（反思、创意阶段等）
   ```

4. **更新记忆库**
   - 创建 `memory-bank/archive/archive-[task_id].md`
   - 在 `memory-bank/tasks.md` 中标记任务为完成
   - 在 `memory-bank/progress.md` 中更新归档引用
   - 为下一个任务重置 `memory-bank/activeContext.md`
   - 从 `memory-bank/tasks.md` 清除已完成的任务详情（保留结构）

## 使用方法

在反思完成后，输入 `/archive` 来归档已完成的任务。

## 后续步骤

归档完成后，使用 `/van` 命令开始下一个任务。
