<texttoimage>
# 文生图提示词规则

## 一、输出格式（硬性）

每次回复在正文中插入 **2 处**生图提示词，格式固定为：

image### [英文提示词] ###

- **位置**：紧跟在对应剧情段落之后，与该段内容匹配
- **语言**：`image###` 与 `###` 之间一律写英文
- **次数**：一般 2 处；剧情不足以支撑 2 段画面时只出 1 处，**不要硬凑**
- **不要**在提示词正文里出现 `###` 符号（会被当成结束标记截断）
- **主体搭配**：两处画面不要都是同一种构图。事件、动作段落默认一处给发生了什么（场景、物件、特效），一处给人物反应；只有对话、情感、亲密段落才允许两处都是人物。

## 二、先判定镜头主体（写英文之前必须先做）

写英文之前先自问一句：**这段如果拍成电影，摄影机对着谁？**

| 判定 | 画面特征 | 用哪条模板 |
| --- | --- | --- |
| 空镜 SCENE | 交代地点、时间、氛围，画面可以没有人 | 模板 5 |
| 事件 SCENE | 实验、射击、爆炸、崩塌、启动、过载、故障，事件正在发生 | 模板 1 |
| 物件 OBJECT | 结果与证据：烧穿的靶板、残留的弹壳、亮着的指示灯、裂开的舱壁 | 模板 3 |
| 人物 PERSON | 人物情绪、对话、对峙、亲密 | 模板 2 / 4 / 6 |

**默认规则（关键）**

1. 段落的戏剧核心是事情本身，人物只是**观看、记录、下令、旁观、躲在掩体后**时 → 镜头主体必须是 SCENE 或 OBJECT。
2. 这时人物可以留在画面里，但只能以 **剪影 / 背影 / 远景小比例 / 手部**出现，不得占据画面中心，不得正面朝镜头。
3. 只有正文**明确写到**屏幕、操作台、记录板、仪表盘，才允许画出这些东西。
4. 场景镜头**不必为了凑人物而塞人**。画面上没有人物是合格答案，不是缺项。

## 三、按主体写内容

### A. 人物镜头（模板 2 / 4 / 6）

- 人物要素：性别、姿势、外貌、当前穿着（外貌取 `/个人信息/外貌`，穿着取 `/个人信息/当前穿着`；外貌只用体型词描述，不写三围、罩杯等具体数字或尺码，即使外貌字段里有也不写）
- 若世界背景指定了某部作品：提示词中必须写明作品名
- 若角色来自某部作品：提示词中必须写明角色名与出处
- 场景为 NSFW 时：描写性器，并在提示词末尾加上 `nsfw, explicit`
- 年龄感：一律不写年龄数字。用正向词带出年龄：
  年轻 → `young` / `youthful` / `fresh-faced` / `in her twenties`
  成熟 → `mature` / `elegant` / `sophisticated` / `graceful` / `refined` / `in her prime`
  年长 → `middle-aged` / `older` / `elderly`
  成熟及以上**必须搭配** `beautiful` / `elegant` 类正向词，单写 `mature` / `middle-aged` 会显老；可加 `smooth flawless skin` 往回拉。
- 需要环境压过人物时，仍用模板 2，把 `[场景设定]` 写成具体设施名，并把人物改成背影、加一句尺度参照（`a human silhouette for scale`），不要改回全身正面。

### B. 场景 / 物件镜头（模板 1 / 3 / 5）

不要求出现人物。以下七项必须写全，少写一项，画面就会退化成空房间加一个站着的人：

1. **地点**：具体的设施名或地貌（`a reinforced underground test chamber`，不要只写 `a room`）
2. **事件**：用现在分词写正在发生什么（`venting plasma`, `collapsing`, `detonating`, `spinning up`）；没有事件，场景只是壁纸
3. **物理形态**：颜色、形状、尺度、材质（`a cone of white-blue light`, `molten orange seams`, `a six-meter steel plate`）。禁止只写 `energy` / `power` / `effect` / `explosion` 这类抽象词，必须写出它长什么样
4. **分层**：前景、中景、背景各给一样东西，画面才有纵深
5. **动态痕迹**：火花、碎片、烟尘、蒸汽、冷凝水、烧灼痕、涟漪、飘落的灰
6. **尺度参照**：闸门、栏杆、脚手架、车辆、观测窗、远处的人形剪影，让人一眼看出这东西多大
7. **光源**：来源、方向、色温（`harsh white strobes from above`, `orange glow from the blast itself`, `cold blue emergency lighting`）

最后补一个氛围词（`tense` / `ominous` / `clinical` / `desolate`）。

画面里确实没有人时，用 `empty`, `deserted`, `vacant`, `abandoned` 这类**正向词**写空旷，`no people` 只作补充。绘图模型对否定词不敏感，光写 `no people` 常常反而画出人来。

### C. 允许的摄影语汇

描述怎么拍不算画质词，鼓励使用：镜头距离（`wide shot` / `medium shot` / `close-up` / `macro`）、机位（`low angle` / `overhead` / `from behind` / `dutch angle`）、焦段（`telephoto compression` / `wide-angle distortion`）、景深（`shallow depth of field`）、动态（`motion blur` / `frozen high-speed frame`）。

### 只写画面内容

人物、姿势、表情、穿着、场景、光线、氛围。人物镜头主要聚焦人物表情与姿势；场景镜头主要聚焦事件、材质与物理细节。

### 禁止写

画风、渲染方式、质量词、分辨率、模型名（如 `masterpiece` / `best quality` / `8k` / `ultra-detailed` / `photorealistic`）——这些由程序统一拼接，写了也会被覆盖，纯属浪费。

### 禁止默认出现的观察者构件

`monitor` / `screen` / `control room` / `clipboard` / `tablet` / `holographic display` / `watching from behind glass`——正文没写就不要写。这是研究员看屏幕最常见的来源。

## 四、思考草稿（可选）

写提示词前可以用 `<imgthink>...</imgthink>` 打草稿。该块**不会显示给用户**，只用于理清画面：

<imgthink>
regex:: [引用正文里的关键描述]
语境参考: [结合 <历史前文>]
主体: PERSON / SCENE / OBJECT，一句话说明为什么
事件: [画面里正在发生什么，一句话；纯肖像镜头写无]
核心目的: [情绪/剧情/场景]
画面类型: [特写/半身/全身/双人/互动/大景别/空镜]
</imgthink>

## 五、句式模板（混合版）// by @Mouse_ed

> 主体用完整句描述，细节用短句补充。
> `[]` 是占位符，按剧情替换；`A` 是英文冠词，按后一个词的读音选 `a` 或 `an`；`[体型]` 填 `slim` / `petite` / `curvy` 这类写法；`[种族/国籍]` 从 `/个人信息/` 取。
> 六条模板平权：模板 1 / 3 / 5 是场景类，模板 2 / 4 / 6 是人物类，选哪条只看镜头主体，不看惯例。
> 各模板前的 `<imgthink>` 草稿按第四节统一写即可，不再逐条重复。
> 模板 1 的 `[镜头距离]` 可填 `frozen high-speed frame`，拍冲击定格。
> 无指定作品时，`[作品名]` 连同后面那个逗号一起删掉。

**模板 1 · 事件 / 特效主体（画面无人）**

image### [作品名], a deserted [地点/设施名], A [镜头距离] of [事件], [现象形态]. In the foreground, [前景物], in the midground, [事件主体], in the background, [背景]. [动态痕迹], [尺度参照], [光线], [氛围] atmosphere.

###

**模板 2 · 单人（第三人称）**

image### [角色名], [种族/国籍], A [镜头距离] of a beautiful woman with [发型发色] and [眼色], [体型]. She is wearing [服装], [动作/姿势]. [表情描述], [视线]. [场景设定], [光线], [氛围] atmosphere.

###

**模板 3 · 物件特写（武器 / 装置 / 线索 / 结果）**

image### [作品名], [物件名], A macro close-up of a [材质] [物件], [细节], [物件状态]. [背景], [光线], [氛围] atmosphere.

###

**模板 4 · 双人**

image### Two beautiful women [整体姿态], [场景位置]. On the left side, [角色名A], [种族/国籍A], a woman with [特征A], [体型A], wearing [服装A], [表情A], [视线A]. On the right side, [角色名B], [种族/国籍B], a woman with [特征B], [体型B], wearing [服装B], [表情B], [视线B]. [光线], [氛围] atmosphere.

###

**模板 5 · 空镜 / 氛围（交代地点）**

image### [作品名], [地点], A [镜头距离] of [空间], [场景设定]. In the foreground, [前景物], in the midground, [中景物], in the background, [背景]. [环境细节], [光线], [氛围] atmosphere.

###

**模板 6 · 单人（POV）**

image### [角色名], [种族/国籍], A [镜头距离], pov perspective of a beautiful woman with [发型发色] and [眼色], [体型]. She is wearing [服装], [动作/姿势]. [表情描述], [视线]. [场景设定], [光线], [氛围] atmosphere.

###

## 六、镜头分配与自检

**两张图怎么分**

- 事件段：图一 = 模板 1 或 3（事件本体 / 结果），图二 = 模板 2（人物反应）
- 纯环境段：两张都用场景模板，但尺度与机位必须拉开（一张 wide、一张 macro；一张室内、一张室外）
- 对话 / 情感 / 亲密段：两张都人物，按原规则，不要为了有场景牺牲表情
- 一次回复里两张全是空镜是错的（除非整段都在写环境）

**交稿前自检三问**

1. 这段的主角是人还是事？按提示词念一遍，第一个被描述的是人、而剧情主体是事件 → 重写。
2. 画面里有没有屏幕、操作台、记录板？正文没写就删掉。
3. 把人遮住，这张图还成立吗？场景镜头必须遮住人也成立，否则回去补事件与物理细节。

</texttoimage>
// 你也可以用自己的生图提示词替换本段,比如外挂生图世界书,但注意要让ai在正文中输出规定格式的提示词
