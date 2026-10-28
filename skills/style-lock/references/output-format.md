# style-lock 输出格式｜仅风格分析

每张场景参考图一份独立档案。若用户指定了已有的风格档案名称/ID，沿用该名称；否则可用 `style-S1`、`style-S2` 作为本次回答中的临时标识（不代表已保存文件）。

## 一、核心风格及可见依据

用一小段话概述辨识度最高的风格身份。表格：`维度｜观察事实｜可见依据｜判断置信度`。

另外单列：`核心风格` 与 `可选生活方式点缀`。区分明确可见的信息与有限推测，不臆测品牌、房型、镜头焦距等不可验证事项。

## 二、三层变化权限

表格：`特征或关系｜严格保持/受控变化/自由变化｜可见依据｜分级理由｜允许范围`。

“严格保持”的对象可以是视觉关系，不必是具体物件。允许变化不等于必须变化。

## 三、同类替换边界与关系约束

表格：`元素及语义类别｜可接受的替换类别｜必须保持的材质/比例/色彩/布局关系｜禁区`。

只定义边界，不指定具体替换后的产品、餐具、背景、菜品、家具、摆位和数量；不写新的场景搭配方案。

## 四、风格偏移检查

表格：`检查项｜通过特征｜偏移表现｜判断依据`。

明确区分：光线方向、曝光、白平衡、冷暖、对比度、饱和度、明暗层次、拍摄透视、空间语义、材质关系、画面密度/遮挡、随拍感与适度精致度。

## 五、结构化风格摘要

下面是可供其他执行环节读取的字段结构；**示例值是占位文字，不是当前参考图分析结论**。只填确实已得到的信息；不确定值设为 `null` 或加入 `uncertainties`。如果用户未指定，不要自动生成融合档案。

```json
{
  "style_id": "style-S1",
  "reference_roles": {
    "scene_references": ["S1"],
    "product_references": ["P1"],
    "other_references": [],
    "merged_scene_styles": false
  },
  "core_style": {
    "summary": "<以图中可见特征总结>",
    "photography": ["<距离与视角等>"],
    "space_semantics": ["<空间类别与生活氛围>"],
    "composition": ["<主体比例、布局密度与层次>"],
    "materials_and_relationships": ["<材质和协调关系>"],
    "optional_lifestyle_accents": []
  },
  "lighting_color": {
    "exposure": "<观察到的曝光程度>",
    "white_balance": "<观察到的白平衡>",
    "warm_cool_bias": "<冷暖倾向>",
    "contrast": "<对比度与层次>",
    "saturation": "<饱和度>",
    "light_direction_and_softness": "<光线方向与柔和程度>"
  },
  "scene_semantics_and_relationships": [],
  "change_permissions": {
    "strict_keep": [],
    "controlled_change": [],
    "free_change": []
  },
  "product_protection_boundary": {
    "appearance_source": "P1 等用户商品原图；若没有商品图则为 null",
    "scene_reference_must_not_override_product": true,
    "product_authenticity_verified_by_this_skill": false
  },
  "style_drift_checks": [],
  "uncertainties": []
}
```

如任务只有场景图而没有商品图，`product_references` 使用空数组，`appearance_source` 为 `null`。`change_permissions` 中每项至少应保留 `feature`、`evidence`、`reason`、`boundary` 字段。
