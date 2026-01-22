# 项目工作区

这是一个包含 Memory Bank 系统配置和示例项目的工作区。

## 项目内容

### 1. Memory Bank 系统

位于 `.cursor/` 目录，这是一个经过令牌优化的分层任务管理系统，使用 Cursor 2.0 命令实现高效的开发工作流程。

#### 可用命令

- `/van` - 初始化项目，检测平台，确定任务复杂度
- `/plan` - 根据复杂度级别创建详细的实现计划
- `/creative` - 为需要设计决策的组件探索设计选项
- `/build` - 系统性地实现已规划的更改
- `/reflect` - 复盘已完成的工作并记录经验教训
- `/archive` - 创建完整的文档并更新 Memory Bank

#### 工作流程

```
/van → /plan → /creative → /build → /reflect → /archive
```

### 2. 贪吃蛇游戏

位于 `snake-game/` 目录，这是一个使用纯 HTML/CSS/JavaScript 构建的经典贪吃蛇游戏。

#### 特性

- 现代化的 UI 设计，带有渐变背景和霓虹风格
- 支持键盘控制（方向键或 WASD）
- 支持移动端触摸控制和虚拟方向键
- 本地存储最高分记录
- 响应式设计，适配各种屏幕尺寸
- 游戏速度随得分增加而加快

#### 运行方式

直接在浏览器中打开 `snake-game/index.html` 即可开始游戏。

#### 游戏控制

- **桌面端**：使用方向键 ↑ ↓ ← → 或 WASD 控制蛇的移动
- **移动端**：使用屏幕上的虚拟方向键或在画布上滑动
- **空格键**：开始/重新开始游戏

## 目录结构

```
/workspace/
├── .cursor/
│   ├── commands/          # Cursor 2.0 命令文件
│   │   ├── van.md
│   │   ├── plan.md
│   │   ├── creative.md
│   │   ├── build.md
│   │   ├── reflect.md
│   │   └── archive.md
│   └── rules/
│       └── isolation_rules/   # 分层规则系统
│           ├── Core/          # 核心规则
│           ├── Level1/        # 第1级 - 快速修复
│           ├── Level2/        # 第2级 - 简单增强
│           ├── Level3/        # 第3级 - 中等功能
│           ├── Level4/        # 第4级 - 复杂系统
│           ├── Phases/        # 阶段规则
│           └── visual-maps/   # 可视化流程图
├── snake-game/
│   └── index.html         # 贪吃蛇游戏
└── README.md
```

## 快速开始

1. **使用 Memory Bank 系统**：在 Cursor 聊天中输入 `/van` 开始初始化项目
2. **玩贪吃蛇游戏**：打开 `snake-game/index.html`

## 许可证

本项目仅供学习和参考使用。

---

*此工作区用于演示 Memory Bank 系统的使用和简单的 Web 项目开发。最后更新：2026 年 1 月*
