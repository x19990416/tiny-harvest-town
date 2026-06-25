# 06｜技术架构建议

## 技术路线判断

Stardew Valley 最早采用 C# + XNA，后续迁移到 C# + MonoGame。这条路线自由度高，但需要开发者自研大量底层系统。

Tiny Harvest Town 不建议第一版直接模仿这条路线。项目同时需要学习内容、题库、配置后台、家长端和数据记录，应优先选择开发效率和内容迭代效率更高的方案。

## 推荐架构

游戏客户端：Godot 4.x  
游戏脚本：GDScript 或 C#  
内容配置：JSON  
内容后台：Vue / React + Spring Boot 或 FastAPI  
数据库：PostgreSQL 或 MySQL  
部署：Web 后台优先，游戏客户端先做 PC/Web Demo，再考虑移动端。

## 客户端模块

- SceneManager：场景切换。
- PlayerController：玩家移动与交互。
- DialogueSystem：NPC 对话。
- TaskSystem：任务读取、状态推进。
- ExerciseSystem：题目展示、答题、校验。
- InventorySystem：物品与材料。
- BuildingProgressSystem：建筑修复。
- SaveSystem：本地存档。
- ContentLoader：读取 JSON 内容。
- ReportCollector：记录学习行为。

## 服务端模块

MVP 可以先本地 JSON，后续再接服务端。

服务端建议模块：

- Account：家长账号/儿童账号。
- Content：知识点、任务、题目、奖励配置。
- Progress：游戏进度。
- LearningRecord：答题记录、知识点熟练度。
- Report：家长端成长报告。
- Package：成长包、主题季、学科包。

## 数据流

1. 游戏启动读取内容包。
2. 玩家进入场景并接任务。
3. TaskSystem 根据任务触发 ExerciseSystem。
4. ExerciseSystem 校验答案并返回结果。
5. 结果写入 Progress 与 LearningRecord。
6. RewardSystem 发放材料/建筑进度。
7. ReportCollector 汇总为小镇日记/家长报告。

## MVP 开发顺序

1. Godot 小地图与玩家移动。
2. NPC 对话。
3. JSON 内容读取。
4. 单个任务触发。
5. 数学题 UI 与答案校验。
6. 奖励发放与背包。
7. 建筑修复进度。
8. 本地存档。
9. 简单学习报告。
10. 内容后台原型。

## 不建议第一版做的技术

- 复杂联机。
- 开放聊天。
- 完整账号体系。
- 实时云同步。
- 大规模内容商城。
- 复杂 AI 生成题目自动上线。

AI 可以后续辅助出题，但必须有教研审核和难度控制，不建议第一版让 AI 直接面向孩子动态出题。
