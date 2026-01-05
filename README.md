# Plamemo_plot_fact_datasets
《可塑性记忆》的剧情数据集，结合动漫和游戏构建，存在差异的情节以游戏为准，可用于角色扮演中的RAG作为上下文事实补充

# 字段说明
## 必需字段
1. **fact_id**: 唯一标识符,格式为 "plot_{i_p}_fact_{序号}"
2. **fact_type**: 事实类型,从以下选择:
   - "event": 事件(角色做了什么)
   - "relationship": 角色关系变化
   - "character_state": 角色状态/情感变化
   - "dialogue": 关键对话内容
   - "scene": 场景描述

3. **subject**: 事实的主体(通常是角色名)
4. **predicate**: 谓词(动作、关系或状态)
5. **object**: 客体(动作的对象、目标或属性值)

## 上下文字段
1. **temporal_context**: 
```json
   {
     "chapter": "章节名称",
     "plot_index": 情节索引,
     "conversation_index": 对话索引(如适用)
   }
```

2. **spatial_context**: 场景描述(从conversation.scenario提取)
3. **participants**: 参与该事实的所有角色列表

## 增强字段
1. **narrative_text**: 用自然语言完整描述该事实(用于语义检索)
2. **metadata**:
```json
    {
      "prominence": 继承自plot的prominence,
      "emotional_tone": "情感基调(如:紧张、温馨、悲伤等)",
      "plot_function": "叙事功能(如:转折点、伏笔、高潮等)"
    }
```
