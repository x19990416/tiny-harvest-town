# Backend｜服务端与内容接口

MVP 可以先用本地 JSON 读取内容。进入内测后，建议增加服务端。

## 建议职责

- 家长账号与儿童账号。
- 内容包管理。
- 知识点、任务、题目、奖励配置。
- 学习记录。
- 游戏进度。
- 家长端成长报告。

## 技术选择

结合项目情况，可以选择：

- Spring Boot 3 + PostgreSQL/MySQL
- FastAPI + PostgreSQL/MySQL

如果团队中 Java/Spring 更熟悉，优先 Spring Boot；如果需要快速搭内容接口，FastAPI 也可以。

## 初始 API 方向

- GET /content/packages
- GET /content/tasks?package=grade3-math-farm
- GET /content/knowledge-points?grade=3&subject=math
- POST /learning-records
- GET /reports/child/{childId}/daily
