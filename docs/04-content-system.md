# 04｜内容系统与配置结构

## 为什么必须配置化

Tiny Harvest Town 后续要支持年级包、学科包、主题季。如果题目、NPC 对话、任务奖励和知识点都写死在游戏代码里，后期维护成本会非常高。

MVP 阶段就应该让内容尽量用 JSON/CSV 配置。

## 内容对象

### knowledge_point

知识点。

字段建议：

- id
- grade
- subject
- name
- description
- difficulty_level
- scene_tags
- prerequisite_ids

### task

任务。

字段建议：

- id
- title
- type
- scene
- npc_id
- knowledge_point_ids
- prompt
- answer_type
- correct_answer
- options
- hint
- wrong_feedback
- correct_feedback
- rewards
- unlock_conditions
- next_task_ids

### reward

奖励。

字段建议：

- type: item / gold / relationship / building_progress / unlock
- target_id
- amount

### npc

角色。

字段建议：

- id
- name
- role
- description
- default_location
- dialogue_style

### item

物品。

字段建议：

- id
- name
- category
- description
- buy_price
- sell_price
- stackable
- usable_in_tasks

## 内容包结构

```text
data/content/
  knowledge_points/
    grade3_math.json
  tasks/
    sample_math_tasks.json
  npcs/
    npcs.json
  items/
    items.json
```

## 任务配置样例

```json
{
  "id": "task_bakery_001",
  "title": "帮面包店准备草莓篮",
  "type": "main_story",
  "scene": "workshop",
  "npc_id": "amu",
  "knowledge_point_ids": ["g3_math_division_equal_share"],
  "prompt": "面包店需要把 36 个草莓平均装进 4 个篮子，每个篮子要放几个？",
  "answer_type": "number",
  "correct_answer": 9,
  "hint": "平均分就是每个篮子一样多。可以想一想 4 × 几 = 36。",
  "wrong_feedback": "篮子看起来有的多、有的少。我们再分一次，让每个篮子一样多。",
  "correct_feedback": "太好了，4 个篮子都装得刚刚好。面包店的准备进度增加了。",
  "rewards": [
    {"type": "building_progress", "target_id": "bakery", "amount": 10},
    {"type": "item", "target_id": "strawberry_basket", "amount": 4}
  ]
}
```

## 内容编辑器需求

MVP 后台至少支持：

- 新增/编辑知识点。
- 新增/编辑任务。
- 新增/编辑题目。
- 绑定 NPC、场景和奖励。
- 预览题目在游戏中的显示。
- 导出 JSON。
- 查看学习记录。

不建议第一版就做复杂权限、复杂审核流、多人协同编辑。可以先做单管理员版本。
