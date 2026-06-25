# 项目结构说明

```text
tiny-harvest-town/
  README.md
  PROJECT_STRUCTURE.md
  docs/
    00-product-brief.md
    01-prd-mvp.md
    02-game-design.md
    03-knowledge-map-grade3-math.md
    04-content-system.md
    05-art-style-guide.md
    06-tech-architecture.md
    07-compliance-and-safety.md
    08-roadmap.md
  data/
    content/
      knowledge_points/
        grade3_math.json
      tasks/
        sample_math_tasks.json
      npcs/
        npcs.json
      items/
        items.json
  game/
    README.md
    project.godot
    scenes/
      Main.tscn
    scripts/
      Main.gd
  backend/
    README.md
  admin/
    README.md
  .github/
    ISSUE_TEMPLATE/
      feature.md
      content-task.md
```

## 当前定位

此仓库是 Tiny Harvest Town 的项目初始化仓库，重点是产品、策划、教研、内容配置和工程方向，不是完整可运行游戏。

## 后续建议分支

- main：稳定文档和可运行版本。
- develop：日常开发。
- feature/godot-prototype：Godot 原型。
- feature/content-admin：内容后台。
- feature/grade3-math-content：三年级数学内容包。
