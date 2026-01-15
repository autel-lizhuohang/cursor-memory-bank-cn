# VAN 命令 - 初始化与入口点

此命令初始化memory bank系统，执行平台检测，确定任务复杂度，并路由到适当的工作流程。

## memory bank集成

**关键:** 所有memory bank文件位于 `memory-bank/` 目录:
- `memory-bank/tasks.md` - 任务跟踪的真实来源
- `memory-bank/activeContext.md` - 当前焦点
- `memory-bank/progress.md` - 实施状态
- `memory-bank/projectbrief.md` - 项目基础

## 渐进式规则加载

此命令渐进式加载规则以优化上下文使用:

### 步骤 1: 加载核心规则 (始终需要)
```
Load: .cursor/rules/isolation_rules/main.mdc
Load: .cursor/rules/isolation_rules/Core/memory-bank-paths.mdc
Load: .cursor/rules/isolation_rules/Core/platform-awareness.mdc
Load: .cursor/rules/isolation_rules/Core/file-verification.mdc
```

### 步骤 2: 加载 VAN 模式映射
```
Load: .cursor/rules/isolation_rules/visual-maps/van_mode_split/van-mode-map.mdc
```

### 步骤 3: 根据任务分析加载复杂度特定规则
确定复杂度级别后，加载:
- **级别 1:** `.cursor/rules/isolation_rules/Level1/workflow-level1.mdc`
- **级别 2-4:** 加载计划模式规则 (转换到 PLAN 命令)

## 工作流程

1. **平台检测**
   - 检测操作系统
   - 根据平台调整命令
   - 设置路径分隔符

2. **memory bank验证**
   - 检查 `memory-bank/` 目录是否存在
   - 如不存在，创建memory bank结构
   - 验证必要文件存在

3. **任务分析**
   - 如存在则读取 `memory-bank/tasks.md`
   - 分析任务需求
   - 确定复杂度级别 (1-4)

4. **基于复杂度路由**
   - **级别 1:** 继续在 VAN 模式，进入实施
   - **级别 2-4:** 转换到 `/plan` 命令

5. **更新memory bank**
   - 在 `memory-bank/tasks.md` 中更新复杂度确定
   - 在 `memory-bank/activeContext.md` 中更新当前焦点

## 使用方法

输入 `/van` 后跟任务描述或初始化请求。

示例:
```
/van 初始化项目以添加用户认证功能
```

## 后续步骤

- **级别 1 任务:** 直接进入 `/build` 命令
- **级别 2-4 任务:** 使用 `/plan` 命令进行详细规划
