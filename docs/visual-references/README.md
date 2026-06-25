# Tiny Harvest Town｜视觉参考图 v0.1

本目录用于存放《Tiny Harvest Town｜小禾镇》的视觉参考图、风格样机图和后续美术方向参考。

## 当前文件

- `style-mockup-v0.1.png`

用途：  
作为《小禾镇》第一阶段像素美术风格锚点，用于统一后续 AI 生成资产、美术外包、Godot 场景搭建和 UI 风格。

## 使用原则

这张图不是最终游戏截图，也不是可直接拆分进 Godot 的精灵图。它的用途是：

1. 确定整体视觉气质。
2. 统一角色、建筑、农田、UI 的方向。
3. 作为后续生成 tileset、建筑、角色、UI 的参考图。
4. 给 AI 生图工具或美术作为风格基准。

## 后续资产生成顺序

建议从以下资产开始：

1. `game/assets/tiles/farm_tileset_v0.png`
2. `game/assets/buildings/building_bakery_broken.png`
3. `game/assets/buildings/building_bakery_repairing.png`
4. `game/assets/buildings/building_bakery_repaired.png`
5. `game/assets/buildings/building_mili_store.png`
6. `game/assets/buildings/building_amu_workshop.png`
7. `game/assets/characters/char_player_*`
8. `game/assets/ui/ui_quiz_panel.png`
9. `game/assets/ui/ui_dialogue_box.png`

## Git 提交建议

```bash
git add docs/visual-references/style-mockup-v0.1.png docs/visual-references/README.md
git commit -m "add visual style mockup reference"
git push
```
