
# Tiny Harvest Town｜小禾镇 像素美术资产生成规范 v0.1

本文档用于统一《Tiny Harvest Town｜小禾镇》的像素美术规格，方便后续使用 AI 生成角色、地图、建筑、作物、UI 等游戏资产。本文档优先服务于首发 MVP：三年级数学农场季 / 修复面包店主线。

## 1. 核心规格

基础 tile：16 × 16 px
内部逻辑分辨率：640 × 360
默认显示分辨率：1280 × 720
推荐显示倍率：2x 整数缩放
角色单帧尺寸：24 × 32 px
作物单格尺寸：16 × 16 px
中型建筑尺寸：96 × 80 px
小型道具尺寸：16 × 16 px
中型道具尺寸：32 × 32 px

采用 2D 俯视像素视角 / 类星露谷视角。不是纯正上帝视角，也不是 45 度等距视角。

## 2. 视觉定位

项目类型：儿童知识成长型像素生活游戏。

参考气质：类似《星露谷物语》的悠闲生活模拟，但更清爽、更儿童友好、更低压力。

核心视觉关键词：

温暖田园、低饱和、清晰可读、圆润可爱、轻松生活感、小镇成长感。

避免：赛博、阴暗、成人化、强写实、复杂 3D、霓虹色、废土感、恐怖感。

## 3. Godot 显示建议

建议后续将 `game/project.godot` 的显示配置调整为：

```ini
[display]
window/size/viewport_width=640
window/size/viewport_height=360
window/stretch/mode="canvas_items"
window/stretch/aspect="keep"
```

如果为了调试方便，也可以暂时保持 1280×720，但美术资产仍按 16×16 tile 体系制作。

## 4. 角色规范

默认角色单帧尺寸：24 × 32 px。

角色逻辑占地：1 tile 宽 × 1 tile 深。
视觉高度可以超过 1 tile。

角色需要四方向：

down / 正面
up / 背面
left / 左侧
right / 右侧

MVP 最小动画：

idle_down：1-2 帧
walk_down：4 帧
walk_up：4 帧
walk_left：4 帧
walk_right：4 帧

角色头身比偏 1.5-2 头身。头部略大，五官简洁，表情友好，轮廓清楚，不要复杂服装纹理，不要成人化身材比例。

## 5. 地图资产规范

地面 tile 统一为 16 × 16 px。

第一批必须包含：

grass_01：草地
grass_02：草地变化块
dirt_01：泥土地
farm_soil_dry：干农田
farm_soil_watered：浇水农田
stone_path：石子路
wood_path：木板路
water_edge：水边
fence：栅栏

## 6. 作物和道具规范

作物单格尺寸：16 × 16 px。

每种作物建议四个成长阶段：

stage_0_seed
stage_1_sprout
stage_2_growing
stage_3_mature

MVP 作物：

wheat / 小麦
strawberry / 草莓
pumpkin / 南瓜

MVP 道具：

coin / 金币
wheat_seed / 小麦种子
strawberry_basket / 草莓篮
wheat / 小麦
bread / 面包
wood_plank / 木板
repair_tool / 修理工具

## 7. 建筑规范

建筑必须贴合 16×16 tile 网格。

小型建筑推荐：64 × 64 px。
中型建筑推荐：96 × 80 px。

MVP 核心建筑：

bakery / 面包店
shop / 商店
workshop / 工坊

面包店必须有三个状态：

bakery_broken
bakery_repairing
bakery_repaired

修复前：屋顶轻微破损，招牌歪斜，墙面有灰尘，但不要阴森。
修复中：脚手架、木板、修补痕迹。
修复后：温暖灯光，干净招牌，门口有面包香气感的小装饰。

## 8. UI 规范

UI 必须优先保证孩子可读。

MVP UI 组件：

dialogue_box：对话框
quiz_panel：答题面板
task_card：任务卡片
reward_popup：奖励弹窗
progress_bar：建筑修复进度条
inventory_slot：背包格子
button_primary：主按钮
button_secondary：次按钮

UI 风格：

圆角像素边框、米白色或浅木色底、深棕色文字、低饱和绿色/黄色/蓝色点缀。不使用霓虹色、复杂渐变、玻璃拟态、成人化 HUD。

## 9. 命名规范

所有资产使用英文小写 + 下划线。

角色：

char_player_idle_down.png
char_player_walk_down.png
char_hehe_idle_down.png
char_mili_idle_down.png
char_amu_idle_down.png

建筑：

building_bakery_broken.png
building_bakery_repairing.png
building_bakery_repaired.png
building_shop.png
building_workshop.png

作物：

crop_wheat_stage_0.png
crop_wheat_stage_1.png
crop_wheat_stage_2.png
crop_wheat_stage_3.png

UI：

ui_dialogue_box.png
ui_quiz_panel.png
ui_task_card.png
ui_progress_bar_bakery.png
ui_button_primary.png

## 10. AI 生成通用提示词

中文模板：

为儿童像素生活模拟游戏《Tiny Harvest Town｜小禾镇》生成一个像素游戏资产。

风格要求：温暖田园、低饱和、清晰可读、圆润可爱、儿童友好、2D 俯视像素视角、类星露谷生活模拟气质。

技术要求：像素艺术，清晰硬边，不要抗锯齿，不要模糊，不要 3D，不要写实，不要强透视，不要复杂光影。资产需要适配 16×16 tile 网格，透明背景，适合 Godot 2D 游戏使用。

输出要求：单个独立资产，居中摆放，边缘干净，轮廓清楚，不包含文字，不包含水印。

英文模板：

Create a pixel art asset for a children-friendly cozy life simulation game called Tiny Harvest Town.

Style: warm rural town, low saturation, clean and readable shapes, rounded cute design, child-friendly, 2D top-down pixel art, cozy farming life simulation mood.

Technical requirements: pixel art, crisp hard edges, no anti-aliasing, no blur, no 3D render, no realistic lighting, no strong perspective, no text, no watermark. The asset must fit a 16x16 tile grid, transparent background, suitable for a Godot 2D game.

Output: single isolated game asset, centered, clean silhouette, transparent background.

## 11. 第一批 MVP 资产

P0 必做：

主角正面站立：24×32
主角四方向行走：24×32 × 4 帧
禾禾 NPC：24×32
米粒 NPC：24×32
阿木 NPC：24×32
草地 tile：16×16
泥土地 tile：16×16
农田干/湿 tile：16×16
石子路 tile：16×16
面包店三状态：96×80
商店：96×80
工坊：96×80
小麦四阶段：16×16
草莓四阶段：16×16
南瓜四阶段：16×16
对话框 UI
答题面板 UI
修复进度条 UI

P1 可后置：

季节变化 tile、更多村民、动物、室内地图、节日装饰、完整背包图标、表情动画、多套服装。

P2 暂不做：

大世界完整地图、四季全套资产、几十个 NPC、大量家具、战斗/怪物资产、联机社交装饰、复杂天气系统资产。

## 12. 质量检查标准

每次 AI 生成资产后，必须检查：

是否符合 16×16 tile 网格。
是否为真正像素风，而不是普通插画缩小。
是否边缘清晰，没有模糊和抗锯齿。
是否透明背景。
是否没有文字和水印。
是否和已有资产色彩一致。
是否儿童友好，没有阴暗、恐怖、成人化细节。
是否能在 2x 放大后仍然清楚。
是否适合 Godot 切图和导入。
是否服务于 MVP，而不是无关装饰。

## 13. 当前阶段结论

《Tiny Harvest Town｜小禾镇》第一阶段不应追求完整资产库，而应先建立：

风格规范 → 视觉样机 → MVP 最小资产集 → 可玩 Demo

第一批资产只服务于：

三年级数学农场季 + 修复面包店主线

后续所有 AI 生成资产，都应优先遵守本文档的尺寸、视角、色彩、命名和提示词规范。
:::
