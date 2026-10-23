# 锂离子电池状态估计论文英文写作风格指南

## 1. 语料与使用原则

本指南依据原工作区 `lithium_batteries_state_estimation` 中的 48 篇论文编写；PDF 原件不随本技能副本打包，第 12 节改用论文出版页面链接。原语料已核对全部文件名，并确认 48 篇 PDF 均可提取文本，约含 42 万个可提取的英文词（包含正文之外的可提取内容）。复核时逐篇查看了摘要与引言，并检索了正文中的方法、验证、结果和讨论表达；以下归纳侧重这些部分的写作功能，而不是复制原句。

| 期刊 | 篇数 |
|---|---:|
| *Nature Communications* | 11 |
| *Applied Energy* | 14 |
| *Energy* | 14 |
| *Energy Storage Materials* | 5 |
| *Nature Energy*、*Joule*、*Energy Conversion and Management*、*Reliability Engineering and System Safety* | 各 1 |

这些是**特定论文的语言习惯**，不是任何期刊的官方写作规则。单篇期刊只能提供论文级示例。以清晰、准确、证据约束的英语为默认风格；目标期刊明确时，应先核对该期刊**当前的作者指南及文章类型要求**，再调整摘要、正文和图注的信息密度。目标期刊的具体要求优先于本指南的跨期刊建议。语料中偶见的冗长模块清单、重复自评、模糊比较或过强结论不作为范本。本指南是语言与论证表达的辅助依据，不代替投稿清单。

## 2. 术语与任务边界

| 概念 | 推荐英文及使用边界 |
|---|---|
| 荷电状态 | *state of charge (SOC)*；表示剩余电量相关状态，不与健康状态互换。 |
| 健康状态 | *state of health (SOH)*；首次使用时说明采用的定义，如容量或内阻指标。 |
| 容量 | *capacity*, *available capacity*, *usable capacity*, *reference capacity*, *nominal capacity*, *discharge capacity*；说明采用哪一定义、测试条件与单位，不能把容量误差直接称为 SOH 误差。 |
| 衰退 | *capacity fade*, *capacity degradation*, *degradation trajectory*；区分已观测衰退与未来轨迹预测。 |
| 剩余寿命 | *remaining useful life (RUL)*；给出寿命终点或失效阈值的定义，区分剩余循环数与日历时间。 |
| 任务动词 | *Estimate* 常用于由观测推断当前或已发生的潜在状态；*predict* 也可指留出样本的状态预测，*forecast* 更明确指向未来时点或轨迹；*diagnose* 指识别健康问题。选词时同时交代目标量、预测时点和时域，不单凭动词判断是否在预测未来。 |
| 性能概念 | *Accuracy* 须由与任务匹配的具体指标支撑（回归误差、分类准确率等不可混用）；*robustness* 需有相应扰动或工况测试；*generalization* 需有与所声称范围匹配的独立测试证据；*uncertainty* 需说明所报告不确定性的定义与计算方法，若声称预测区间或概率已校准，还需相应校准证据。*Adaptation* 允许对目标域进行调整，不能直接写成零样本泛化。 |
| 对象层级 | *cell*, *module*, *pack*, *battery system* 按实际样本层级使用；单电芯结果不能直接表述为电池包验证。 |

常见专业搭配包括 *partial charging profile*, *voltage relaxation*, *electrochemical impedance spectroscopy (EIS)*, *differential voltage analysis*, *incremental capacity analysis*, *health indicator*, *cell-to-cell variability*, *operating conditions*, *distribution shift*, *target-domain labels*, *sensor noise* 和 *inference latency*。这些词只在研究实际使用相应信号、方法或测试时出现。正文中的必要缩写通常在首次出现时定义，并在全文保持一个概念对应一个名称；摘要和每条图注是否使用或重新定义缩写，分别按目标期刊要求处理。例如，下文所引 *Nature Communications* 格式说明要求摘要不使用缩写，并在各图注中定义缩写。*Open-circuit voltage (OCV)*、*voltage plateau*、*state of energy (SOE)*、*end of life (EOL)* 和 *capacity retention* 也不能与 SOC、SOH 或容量随意替换。

## 3. 论文章节的叙述任务

### 摘要

建议顺序是“任务及具体障碍 → 核心方法思想 → 测试对象和条件 → 决定性结果 → 有边界的意义”。方法部分应呈现解决问题的关键设计，而不是连续罗列模块名称。语料中的 *Nature Communications* 论文常较快进入研究动作或核心发现；所选 *Applied Energy* 与 *Energy* 论文有时会多给一层工程实现和多工况指标。这些是语料观察，不替代目标期刊的摘要要求。摘要中的数值要说明指标、数据或条件，不孤立地写“误差降低”。

### 引言

段落由实际任务出发，指出现有路线依赖的前提，再解释这个前提为何在目标场景失效，最后提出本文要回答的问题。例如缺口可以是目标域标签不足、LFP 电压平台导致可观测性降低、使用历史不完整或现场数据与实验室数据分布不同；不要仅以 *few studies have investigated...* 代替真正的知识缺口。语料中有些文章从全球变暖、能源转型或电动车增长开篇；若这些事实不直接导向研究问题，应从状态估计的具体障碍切入。

### 方法

先说明输入、输出和系统边界，再交代框架、各模块操作及其作用。多模块段落采用“要解决的问题 → 模块接收什么 → 做了什么 → 为后续环节提供什么”的顺序。

### 结果

一个比较结果尽量包含以下信息槽：

`测试对象/数据集 + 工况或划分 + 指标 + 本文值 + 同条件基线值 + 图表位置`。

先写观察，再写有证据支撑的局部解释。比较前核对是否使用同一数据划分、指标、单位和操作条件。消融实验要明确移除了什么、在哪些条件下测量、指标如何变化；误差变化只能支持该组件在测试设置中的贡献，不能自动证明电化学机制或模块“协同”。若论文把 Results 和 Discussion 合为一节，仍要在句子层面区分“观察”与“解释”。具体英文信息槽见第 10 节。

### 讨论

讨论从“发现了什么”转向“发现意味着什么、与已有认识如何相连、在哪些条件下可能不成立”。机制解释应指出对应的测量或干预证据。

### 结论

结论凝练贡献、关键证据、适用范围与仍待验证的问题，不逐图重复结果，也不提出正文未支持的新用途。

## 4. 按研究类型组织摘要与结尾

这批论文显示，**研究类型比期刊名称更能决定叙述顺序**。一篇论文可能同时属于几类；后续改写应以原稿的主要研究问题为准。

| 研究类型 | 摘要中优先交代 | 结尾应回到 |
|---|---|---|
| 状态估计算法 | 输入信号、目标状态、核心建模选择、验证条件与误差。 | 算法在哪些电芯和工况下有效，以及哪些条件仍未测试。 |
| 新测量信号或快速诊断 | 信号为何能用于状态估计、测量协议及其时间/硬件负担。 | 测量可行性与模型误差各自的边界。 |
| 迁移学习或领域适配 | 源域、目标域、目标标签量和适配步骤。 | 迁移后表现，而非笼统宣称“通用”。 |
| 退役与二次利用预测 | 退役时可获取的数据、未知历史或 SOC、预测时域。 | 二次利用条件变化对预测的限制。 |
| 现场监测或数据资源 | 现场系统数量、跟踪时间、参考测量和数据开放范围。 | 现场观察的价值及其与实验室估计的差异。 |
| 多任务或系统级联合估计 | 每项任务的目标量、共享信息、对应指标和系统层级。 | 各任务的独立证据；不把某一指标提升为全系统结论。 |

一些论文的结尾重新罗列了全部模块或重复使用 *novel/superior/remarkable*。这种写法可以帮助识别作者希望强调的组件，但后续改写宜压缩成“主要发现 → 决定性证据 → 适用条件 → 未解决限制”。若正文只有误差比较，结尾不应升级为已证实机制。若全文没有独立的 Discussion 章节，也应在合并章节或结尾中交代主要限制。

## 5. 词汇、主语与句式

### 5.1 动词选择

| 写作动作 | 自然、精确的动词 | 判断标准 |
|---|---|---|
| 交代问题 | *remain challenging, be limited by, rely on, be sensitive to, require* | 限制后面必须有具体条件或原因。 |
| 说明方法 | *derive, extract, select, fuse, integrate, constrain, regularize, adapt, fine-tune, update* | 动词要与算法实际操作对应。*Fuse* 不等于简单并列输入。 |
| 交代验证 | *evaluate on, compare with, benchmark against, validate against, assess across* | 普通测试可用 *evaluate*；*validate* 要有明确的验证依据或设计。 |
| 报告结果 | *achieve, reduce, increase, decrease, retain, converge, exhibit* | 紧跟指标、数值、比较对象和测试范围。 |
| 作出解释 | *indicate, suggest, support, be consistent with, be associated with, may reflect* | 从观测走向解释时保留适当不确定性。 |
| 讨论用途 | *enable, facilitate, support, offer a route to* | 限定部署所需条件；不把实验室性能写成已落地应用。 |

优先写具体结果，少用无锚点的 *novel, superior, remarkable, significant, robust*。*Statistically significant* 或可能被理解为统计显著的 *significant/significantly*，应有相应统计分析支撑；若仅指幅度较大，优先报告数值，并选用不会暗示统计检验的措辞。

### 5.2 逻辑连接

| 逻辑关系 | 可选表达 | 使用要求 |
|---|---|---|
| 转折、限制 | *however, although, whereas, despite* | 前后命题须有真实的对立或限制。 |
| 从缺口进入研究动作 | *to address this limitation, to test whether, to quantify the effect of* | 后面接实际方法或实验。 |
| 增加证据 | *in addition, further, beyond this comparison* | 下一句应加入新信息，而不是改写同一结论。 |
| 明确范围 | *under, across, within, for, in the absence of* | 限定语紧邻被限定的结果。 |
| 比较 | *compared with, relative to, whereas, by contrast* | 比较对象及其测试条件一致。 |
| 受限推论 | *these findings suggest, the results indicate, taken together* | 语气与证据强度一致。 |

### 5.3 主语与语态

全篇贡献句可用 *This paper presents/proposes...*、*This study develops...* 或 *Here we show...*；不同论文确有不同主语习惯，不必统一替换为 *This paper*。具体步骤不宜反复以 *This paper uses...* 开头。方法、分析或结果作主语若更清楚，也可使用主动语态。施事者不重要时自然使用被动语态。避免为显得“客观”而连续使用被动句，也避免每句都以 *We* 或 *This paper* 开头。

一般“使用”优先用简洁的 *use*。只有当 *utilize* 在具体句子中确实表达了不同含义时才使用，不把它当作更学术的 *use*。

### 5.4 长句、模块和公式

48 篇论文并非每一句都值得模仿。部分工程类摘要将多个算法、连接词、测试条件和性能主张放在同一句或连续数句中，且使用较多 *novel*, *superior*, *significantly*。改写时提取其信息关系，避免复现这些句子的冗长和自评。

1. **保留因果或条件关系**：先找主句结论，再找支持它的测试条件、比较对象与数据；若一个长句跨越“缺口 → 三个模块 → 多项结果”，按功能拆分。
2. **模块列表改为功能链**：写清每一模块解决的具体问题、接收的输入和传给下一步的信息；*First/Next/Finally* 只在顺序影响理解或复现时使用。
3. **控制公式说明的长度**：把行间公式视为所在句子的一部分，按句法加标点，并在符号首次出现处清楚定义。若紧接公式定义少量符号，可用 *where* 承接；是否同句、另句或另段取决于清晰度及目标期刊格式，不强制使用一种句式。模型假设、推导理由或物理解释通常另起句，避免全部塞进符号定义。

## 6. 各部分的时态

对这 48 篇论文的相关段落再次核对后，最重要的发现是：**同一章节经常同时使用过去时和现在时**。作者可以用过去时报告某次实验，再用现在时说明图表、方法的当前功能或这组结果所支持的结论。部分论文在 Results 中用现在时带读者走过分析流程；因此“Results 全部改为过去时”不是这批语料的真实规律。以下为改写时可执行的默认判断，而非投稿期刊的硬性规定。

| 论文部分 | 主要在说什么 | 常用时态及判断 |
|---|---|---|
| 标题与小标题 | 命名问题、方法或发现。 | 多用名词结构或现在时陈述持续成立的核心结论；通常无需为了统一时态而改写。 |
| 摘要 | 背景、知识缺口、研究动作、关键结果和意义同时出现。 | 背景与未解决问题常用**一般现在时**；*Here we present/show...*、*This study proposes...* 等论文贡献句也常用现在时。特定实验如何完成可用**一般过去时**；结果句可用过去时或现在时，取决于强调“该次测得”还是“本文结果表明”。摘要内部保持逻辑清楚比统一时态更重要；目标期刊若对摘要句式、缩写或结尾时态有具体规定，则先遵守该规定。 |
| 引言 | 通行知识、已有研究、当前缺口和本文研究问题。 | 公认定义及尚存问题用**一般现在时**；某篇前人论文实施了什么可用**一般过去时**；一个研究方向迄今积累了什么可用**现在完成时**。本文段落可用现在时介绍论文动作，但不把尚未验证的结果写成领域常识。 |
| 材料与方法 | 既有实际操作，也有可复现的算法、变量和方程定义。 | 已完成的采样、循环测试、训练集划分、测量与模型拟合多用**一般过去时**；模型结构、算法步骤、公式关系和符号定义常用**一般现在时**。按作者是在回顾一次实验，还是说明读者现在可以如何理解或复现方法来选。 |
| 结果 | 数据、比较、图表与局部解释。 | 特定样本在指定条件下的变化和实测比较通常优先用**一般过去时**；*Figure/Table ... shows/compares* 及对图中关系的说明常用**一般现在时**。若现在时清楚地用于引导读者查看图表或概括当前可见的关系，也可使用；不要为统一章节时态而机械切换，更不能把一次性观察升级为普遍规律。 |
| 讨论 | 回看本研究发现，联系已有知识，解释机制并限定外推。 | 回顾“我们测到了什么”可用**一般过去时**；“这些结果现在支持什么解释”及仍成立的研究含义可用**一般现在时**。推测和边界靠 *may, could, suggests, is consistent with* 等语气表达，而不靠时态伪装成确定因果。 |
| 结论 | 总结完成的工作、目前可支持的贡献与未解决问题。 | 完成的实验和观察可用**一般过去时**；方法的定义、本文贡献或现有结果支持的结论可用**一般现在时**。两者在同段出现正常，但平行列举的同类发现应保持时态协调。未完成的验证宜写 *remains to be evaluated*，不把未来计划写成已验证能力。 |
| 图题、图注、表注 | 指认图中面板、曲线、数据来源和制备过程。 | 图表“现在展示什么”多用**一般现在时**；样品如何制备、数据如何采集、实验如何执行多用**一般过去时**。图注内切换时态通常反映句子功能切换。 |

### 6.1 逐句选择时态

改写每个谓语前依次判断：

1. **是否在陈述本研究中已发生的事件？** 若是，优先过去时，并保留样本、条件和指标。
2. **是否在定义概念、描述公式/模型结构，或指向读者眼前的图表？** 若是，优先现在时。
3. **是否在概括截至目前的研究进展？** 可用现在完成时；若指明某位作者在某一年完成的具体研究，通常用过去时。不要为了显得学术而机械加入 *has/have*。
4. **是否在解释观察或预示应用？** 根据证据控制 *suggests/may/could*，并把范围限定在实际测试条件内；语气强度与时态是两个独立决定。
5. **相邻句是否谈同一时间层级？** 同一组实验观察的平行句保持协调；从“观察”转到“图表说明”或“当前解释”时，合理切换时态。

下面的例句是为说明判断而新写的句架，方括号并非语料原文：

> The cells were cycled under [condition]. Figure [n] shows the resulting capacity trajectories. Together, these observations suggest [interpretation within the tested range].

第一句回顾已实施的实验，第二句描述图目前展示的内容，第三句给出证据限定的当前解释。若第三句中的机制未被独立测量，应保留 *suggest* 或更弱表达，不改成 *demonstrate*。

本节的规则服从科学含义和目标期刊的实际文体。若原稿目前没有提供清楚的时间线、研究对象或验证条件，应先标出待核实信息，再决定时态；不能用时态选择掩盖事实不明。

## 7. 结果与数值表述

相同的 *MAE*、*RMSE* 或 *MAPE* 在语料中对应不同目标量、单位和汇总方式。写结果句时先核对“估计对象 → 指标定义 → 数值 → 汇总方式 → 数据范围”。

| 语料中常见写法 | 实际含义 | 改写时的限制 |
|---|---|---|
| *an MAE of [x]* | 某条件下的平均绝对误差。 | 说明对象与单位；SOC 的百分比点误差、容量 Ah 误差和 RUL 循环数不可混写。 |
| *as low as [x]* / *a minimum of [x]* | 最佳或最低值。 | 不改写成所有测试的平均表现。 |
| *up to [x]% reduction* | 最大相对降幅。 | 不改写成每个数据集都下降该幅度。 |
| *on average* / *across [n] datasets* | 指定集合的汇总值。 | 说明汇总范围；必要时保留数据集间差异。 |
| *within ±[x] percentage points* | 相对参考值的误差范围。 | 与百分比变化区分；说明适用测试条件及覆盖范围：全部样本、指定分位数，还是有明确定义的区间。未经证实，不写成所有误差均落在该范围内。 |
| *below [x]* / *less than [x]* | 上界或阈值。 | 不擅自替换为精确测量值。 |
| *an inference time of [x]* | 指定平台上的计算耗时。 | 与采集一段电压/电流数据所需时间、诊断流程总时间分开。 |

当报告相对误差改善时，至少知道原方法误差、本文误差及分母。例如 `RMSE decreased from [baseline] to [proposed]` 与 `RMSE was reduced by [relative amount]` 不应在没有原始数值时互相改写。对 *RUL* 给出 *cycles* 或时间单位；对 *SOH* 明确其容量、内阻或其他定义。报告 *R²* 时说明其定义和计算所用数据集；它不能替代有单位的误差指标。

若原稿报告跨电芯或跨工况的汇总性能，应核对独立样本的单位（电芯、电池包或其他对象）与数量、汇总方式以及离散程度或区间的含义。循环数和切出的时间窗口数不自动等于独立电芯数。涉及 *significant*、置信区间或误差条时，还须保留原稿中的统计方法与定义；缺失时标记待作者核实，不补造检验结果。

## 8. 验证范围与证据强度

### 8.1 验证场景决定措辞

这些论文常用“跨条件”描述验证，但条件的种类并不等价。后续改写先填清验证对象，再决定能否使用 *robust*, *generalizable*, *transferable*, *real-world* 等词。

| 需要分开的验证维度 | 写作时必须交代的内容 | 不应顺手扩大为 |
|---|---|---|
| 同一电芯内的随机样本划分与留出电芯 | 训练集、测试集是否共享电芯；是否按循环或样本切分。 | 跨电芯泛化。 |
| 跨温度、跨工况与跨老化阶段 | 训练和测试各包含哪些温度、负载谱、SOC 区间与寿命阶段。 | 跨化学体系或现场部署。 |
| 跨制造商、化学体系、外形尺寸或容量规格 | 目标域是否在训练中出现；有多少目标域样本和标签。 | 不需适配的普遍泛化。 |
| 电芯到电池包迁移 | 包级标签比例、包内不一致性、测试包是否独立。 | 单电芯精度直接适用于包级系统。 |
| 实验室到现场 | 现场样本、运行时长、参考容量获取方式和现场数据质量。 | 只凭动态实验室工况宣称实际车辆验证。 |
| 噪声、缺失值、异常值 | 扰动类型、强度、施加位置和有无异常识别。 | 未经测试的所有“复杂工况”稳健性。 |
| 在线与实时 | 测量/数据获取时间、模型运行平台、单次推理延迟和是否在目标硬件上测试。 | 仅凭 GPU 延迟宣称 BMS 嵌入式实时部署。 |

在跨域研究中，*unlabeled target domain* 只表示目标域无标签，不表示整个训练过程无标签。*Fine-tuning with limited target labels* 应写明标签比例或数量；*without target labels*、*without historical data* 和 *without diagnostic tests* 是三种不同的数据约束。*Extrapolation* 仅用于测试确实超出训练范围的情况，普通留出集预测可用 *prediction* 或 *evaluation*。

### 8.2 数据驱动研究的可复现表述

对机器学习或数据驱动论文，方法与结果的措辞还取决于以下事实是否写清：数据来源及预处理、训练/验证/测试集的用途、按电芯/循环/时间窗口划分的方式、测试对象是否独立、调参是否使用测试集、基线与消融的比较条件，以及计算平台和耗时的定义。特别注意同一电芯的相邻窗口或循环进入训练集和测试集时，不能把样本级留出结果写成跨电芯泛化；预处理或特征选择若利用了测试集信息，也需核查信息泄漏。独立外部数据集、简单基线和硬件成本不是每篇论文都必须具备的实验，但缺少这些证据时应相应收窄主张。以上是**改写前的信息核对项**，不是允许润色者添加原稿没有的实验或结果。

### 8.3 从观测到机制的证据阶梯

1. **观测**：报告测量值、模型输出、误差变化及其条件。
2. **支持的解释**：消融、特征归因或一致性测试可以支持“某组件有贡献”或“结果与某解释一致”。
3. **机制或因果**：使用 *drives, is attributable to, demonstrates the mechanism* 前，应有能隔离该机制的独立测量、干预或强控制设计。相关性、注意力权重、SHAP 或潜变量的可解释性本身不足以证明电化学机制。

## 9. 期刊表达侧重点

| 语料类型 | 值得借鉴的叙述重点 | 不应直接推断 |
|---|---|---|
| *Nature Communications*（11 篇） | 快速呈现障碍、研究动作、核心发现及其边界；压缩模块清单。 | 不能强制所有文章使用 *Here we show*。 |
| *Nature Energy*（1 篇，单篇示例） | 该论文强调现场系统、长期测量、样本与数据资源价值。 | 不可把该单篇的现场研究框架套到普通模型论文。 |
| *Joule*（1 篇，单篇示例） | 该论文将模型解释、验证和应用场景连成一条证据链。 | 可解释潜变量不等于已证实物理机制。 |
| *Energy Storage Materials*（5 篇） | 解释传感信号或材料特征与估计任务的联系。 | 成本优势、跨材料适用性须有测试。 |
| *Applied Energy*（14 篇） | 工程工况、基线、消融、误差和计算成本。 | 不照搬冗长算法清单或未经限定的自评。 |
| *Energy*（14 篇） | 联合估计、温度与工况变化、模型组合和跨域边界。 | 不把某一数据集的精度写成普遍稳健性。 |
| *Energy Conversion and Management*、*Reliability Engineering and System Safety*（各 1 篇，单篇示例） | 所选论文涉及系统耦合、实时性和可靠性问题。 | 合成或实验室配置不等于现场部署。 |

## 10. 可复用的信息槽

下面是本指南原创的**信息槽**，不是论文原句，也不是需要逐字套用的模板。方括号只能由原稿已有证据填充。

| 功能 | 信息槽 |
|---|---|
| 明确缺口 | `Although [existing approach] can [supported strength], its performance under [specific condition] remains uncertain because [specific reason].` |
| 说明方法 | `To address [problem], [method] combines [actual inputs/operations] to estimate [defined target].` |
| 描述迁移 | `After training on [source domain] and adapting with [amount of target data], [model] was evaluated on [independent target set].` |
| 量化结果 | `Under [test condition], [method] achieved [metric and value], compared with [same-condition baseline and value].` |
| 报告消融 | `Removing [component] changed [metric] from [value] to [value] on [test set], supporting its contribution to [bounded function].` |
| 讨论解释 | `[Observation] is consistent with [plausible interpretation]; however, [unmeasured mechanism or alternative explanation] remains unresolved.` |
| 明确部署边界 | `The measured [latency/accuracy] supports [tested capability], while [field or hardware condition] remains to be evaluated.` |

改写时应先判断原稿是否真的包含这些信息。缺少基线、目标域标签量、独立测试或机制证据时，不为凑句式而补造事实。

## 11. 后续改写流程

收到中文或英文初稿后，先确定章节、目标期刊（如有）、研究对象、术语定义和段落任务；再按本指南重排信息、润色英文。最终逐项检查：

- 科学含义、因果方向、证据强度和适用范围是否保留；
- 数字、单位、指标、误差方向、数据集、工况、基线与引文位置是否保留；
- SOC、SOH、容量、衰退轨迹和 RUL 是否被准确区分；
- 结果、解释、机制与部署主张是否停留在原有证据允许的层级；
- 是否避免直接复制语料原句或重复使用固定句架。
- 若目标期刊已确定，是否另行核对其当前作者指南、文章类型与必要声明；本指南不以语料习惯覆盖期刊要求。

默认交付自然、克制的英文改写；仅在确有实质性修改或原稿含科学歧义时附简短说明。缺少必要信息时标明待作者核实，不补造实验、数值、引用或机制。

## 12. 语料锚点

下表标出本次复核中直接支持上述写作判断的代表性论文。表中的“可借鉴之处”是对**写作功能**的概括，不是可复制的英文原句；未列出的论文也参与了术语与表达复核。

| 论文 PDF | 可借鉴的写作功能 | 改写时的边界 |
|---|---|---|
| [2020 年 EIS 预测研究](https://doi.org/10.1038/s41467-020-15235-7) | 把测量方式、数据规模和模型输出按证据链组织。 | “可解释特征”不自动等于已证明退化机制。 |
| [2022 年不均匀使用条件预测研究](https://doi.org/10.1038/s41467-022-32422-w) | 说明未知历史、未来使用协议和校准不确定度各自的作用。 | 预测区间须有校准证据。 |
| [2023 年无目标标签 SOH 研究](https://doi.org/10.1038/s41467-023-38458-w) | 准确区分“目标电池无标签”与其他训练数据。 | 不写成完全无监督或零数据学习。 |
| [2024 年退役电池生成式研究](https://doi.org/10.1038/s41467-024-54454-0) | 把退役条件、SOC 范围与测试误差放在同一结论范围内。 | 经济与排放预测须保留情景假设。 |
| [2025 年现场 EV 数据研究](https://doi.org/10.1038/s41467-025-56485-7) | 用真实车辆样本和运行年限解释实验室与现场数据差异。 | 现场数据开放与现场算法验证是不同主张。 |
| [2026 年二次利用轨迹预测研究](https://doi.org/10.1038/s41467-026-69369-1) | 把使用模式、预测跨度、精度和计算时间配套说明。 | 推理时间不能代替完整诊断时间。 |
| [家用储能长期现场测量研究](https://doi.org/10.1038/s41560-024-01620-9) | 区分现场实测、参考容量测试、年容量变化及共享数据。 | 每年“百分点”损失不能写成每年“百分比”下降。 |
| [Joule 车载健康评估研究](https://www.sciencedirect.com/science/article/pii/S2542435125001916) | 把输入信号、机制约束、健康诊断与未来预测按任务分开。 | 物理可解释潜空间不能直接写成独立电化学机制证据。 |
| [应力与电信号联合估计研究](https://www.sciencedirect.com/science/article/pii/S0360544225027057) | 分清两条估计支路、融合顺序和最终 SOC/SOH 指标。 | “融合”要有实际组合过程。 |
| [电芯到电池包迁移研究](https://www.sciencedirect.com/science/article/pii/S0360544225039702) | 明示少量目标包级标签的比例和包级测试范围。 | 少标签微调不等于零样本泛化。 |
| [跨化学体系与尺度研究](https://www.sciencedirect.com/science/article/pii/S0360544226011849) | 将跨化学体系、跨尺度、噪声/缺失值测试分别报告。 | 三种验证不能合成一个泛泛的“稳健”。 |
| [短时特征微调研究](https://www.sciencedirect.com/science/article/pii/S2405829725004222) | 对齐短时信号长度、目标标签量和同域基线。 | *Direct transfer* 与 *fine-tuning* 不是同一测试条件。 |
| [快速二次利用诊断研究](https://www.sciencedirect.com/science/article/pii/S2405829726001935) | 区分诊断流程耗时、分类准确率和 SOH 回归误差。 | “无需预设条件”不等于没有测量协议。 |
| [多电芯联合估计研究](https://www.sciencedirect.com/science/article/pii/S0196890426004929) | 明示合成多电芯配置、SOC/SOH 误差与推理延迟。 | 实验室配置和实际现场部署分开表述。 |

### 12.1 时态用法的论文例证

- [阻抗谱预测论文](https://doi.org/10.1038/s41467-020-15235-7)在 Results 中用现在时讲解训练与测试流程，并用现在时引导读者看图；这说明 **Results 主要报告已完成研究**不等于**每个谓语必须用过去时**。
- [不均匀使用条件研究](https://doi.org/10.1038/s41467-022-32422-w)在讨论中混合回顾性过去时和描述模型当前能力的现在时；改写时应保留“已验证的实验”与“可支持的能力”之间的界线。
- [长期现场测量论文](https://doi.org/10.1038/s41560-024-01620-9)用现在时介绍研究贡献与图表，同时报告已经积累的多年现场数据；时态切换服务于“当前可用的数据资源”与“过去完成的测量”两种信息。
- [车载健康评估论文](https://www.sciencedirect.com/science/article/pii/S2542435125001916)在 Results 和 Discussion 中同时使用方法/能力的现在时与数据生成的过去时；结论语气还应受诊断测试范围约束。
- [LFP 滤波估计论文](https://www.sciencedirect.com/science/article/pii/S0306261925014850)在结尾以现在时概括方法如何工作，也回顾其测试；不要因为标题是 Conclusions 就统一转换成过去时。

## 13. 官方指南与使用边界

以下官方资料用于核对本指南的**一般表达原则和报告边界**，不是把某一家期刊的规定套用到所有期刊。投稿时仍须查看目标期刊当期的作者指南与文章类型要求。

- [Nature Portfolio：How to write your paper](https://www.nature.com/nature-portfolio/for-authors/write)：强调清晰直接的句子、必要时定义术语与缩写，并以目标期刊作者指南为准。
- [Nature Communications：How to submit](https://www.nature.com/ncomms/submit/how-to-submit)：强调跨领域读者可理解的标题、摘要和正文，以及足以解释和复现结果的方法。
- [Nature Communications：格式要求](https://www.nature.com/documents/ncomms-formatting-instructions.pdf)：所引 PDF 标注修订于 2021 年；其中对摘要缩写、结尾句及图注缩写有具体要求，也列出公式与符号格式。投稿前核对该刊当时生效的最新版，不能把此文件当作其他期刊的通用规则。
- [Nature Communications：计算工具研究的可复现性指南](https://www.nature.com/documents/Computational_tools_reporting_guidelines.pdf)：对数据预处理、数据划分、独立验证和基线比较提出报告建议。
- [Nature Portfolio：Machine Learning Checklist](https://www.nature.com/documents/ML-reporting-summary.pdf)：提供数据来源、信息泄漏、模型训练、评估和计算资源的核对项；表中问题不等于所有研究都必须完成每一种实验。
- [Nature Communications：Policy Guide](https://www.nature.com/ncomms/submit/policy)及 [Nature Energy：Content Types](https://www.nature.com/nenergy/content)：展示数据/代码声明与不同文章类型的具体要求，不能直接泛化为所有期刊的统一格式。
