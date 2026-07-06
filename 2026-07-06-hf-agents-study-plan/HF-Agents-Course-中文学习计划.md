# Hugging Face AI Agents Course 中文学习计划

> 为文科背景、英语中级的学习者定制。免费,零成本,结业可拿免费证书。
> 课程官网:https://huggingface.co/learn/agents-course/zh-cn/unit0/introduction(官方中文版!)
> 英文原版:https://huggingface.co/learn/agents-course/en/unit0/introduction

---

## 先看三件事

**1. 这门课有官方中文翻译。** 建议:中文版为主,遇到关键术语切回英文版对照,顺便练英语。

**2. 官方节奏是每单元 1 周、每周 3–4 小时。** 你没有编程基础,我们放慢到约 8 周,前面加一个「第 0 周」补 Python。

**3. 证书完全免费,没有截止日期。**
- 完成 Unit 1 → 拿 *fundamentals(基础)* 证书
- 完成 Unit 1 + 一个用例作业 + 最终挑战 → 拿 *certificate of completion(结业)* 证书

---

## 课前准备(第 0 周,约 4 小时)

课程官方前置要求只有两条:会一点 Python、大致知道 LLM 是什么。你需要补的是 Python。

**目标不是「学会编程」,而是「看得懂代码在干嘛」。** 掌握这六个概念就够上路:

| 概念 | 一句话类比 |
|------|-----------|
| variable(变量) | 贴了标签的盒子,里面装数据 |
| function(函数) | 一台机器:放进原料,吐出成品 |
| if / else(条件) | 「如果下雨就带伞,否则不带」 |
| loop(循环) | 「把这件事重复做,直到做完为止」 |
| list / dict(列表/字典) | 购物清单 / 通讯录(名字→电话) |
| import(调库) | 借用别人写好的工具箱 |

**怎么补:** 随便找一个免费 Python 入门(如 [W3Schools Python](https://www.w3schools.com/python/)),只看以上六节,每节跟着敲一遍代码。不要贪多。

**自检:** 能说出下面代码在干嘛,就算过关:

```python
words = ["agent", "tool", "agent", "memory"]
count = {}
for w in words:
    count[w] = count.get(w, 0) + 1
print(count)   # 数每个单词出现几次
```

**账号准备(10 分钟):** 注册免费的 [Hugging Face 账号](https://hf.co/join)。课程的动手环节都在浏览器里的 Hugging Face Spaces 运行,**不用在自己电脑上装任何东西**——这是这门课对新手最友好的地方。

---

## 第 1 周:Unit 0 + Unit 1 上半(什么是 Agent)

**这周解决一个问题:Agent 到底是什么?**

先给你直觉锚点:LLM(大语言模型,如 ChatGPT)本身只会「说」;**Agent = 会说 + 会做**。就像一个只能口头咨询的顾问,和一个能替你打电话、查资料、订机票的助理——后者就是 agent。

学习内容:
- Unit 0:Onboarding(报到),按页面指引设置账号,可选加 Discord
- Unit 1 前半:Agent 的定义、LLM 是怎么「思考」的、messages(消息)和 chat templates(聊天模板)

关键术语(先混个脸熟):
- *Agent(智能体)*:能感知、思考、行动的 AI 程序
- *LLM(Large Language Model,大语言模型)*:agent 的「大脑」
- *Tool(工具)*:agent 能调用的外部功能,比如搜索、计算器

**本周自检:** 用自己的话向朋友解释「ChatGPT 和 AI Agent 有什么区别」,说不清就回去重看。

## 第 2 周:Unit 1 下半(Agent 怎么运作)+ 考基础证书

**这周解决:Agent 内部的一次完整循环是怎么跑的?**

核心是 **Thought → Action → Observation(思考 → 行动 → 观察)循环**:
1. *Thought*:「用户问天气,我需要查天气工具」
2. *Action*:调用天气 API
3. *Observation*:拿到「北京 32 度」
4. 回到 Thought:「信息够了,可以回答了」→ 输出答案

就像你查资料写论文:想清楚要查什么 → 去图书馆检索 → 看检索结果 → 决定是继续查还是动笔。

学习内容:
- Unit 1 后半:Tools、Thought-Action-Observation 循环、用 Python 函数做工具的最小例子
- 做完 Unit 1 的 quiz(小测),**通过即拿第一张证书** 🎉

**本周自检:** 画出「问 agent 今天该穿什么」这个请求的 Thought→Action→Observation 流程图。

## 第 3–4 周:Unit 2.1 smolagents(第一个框架,重点)

**这周开始动手。** *Framework(框架)* = 别人搭好的脚手架,你不用从零造轮子。

课程教三个框架,**对你来说 smolagents 最重要**——它是 Hugging Face 自家的,最简洁,几行代码就能跑起一个 agent。

学习方法(务必遵守):
1. 每段示例代码,**先猜**它在干嘛,再运行验证
2. 运行成功后,**改一个小地方**(比如换个问题、换个工具)再跑,看变化
3. 报错不要慌:读错误信息的**最后一行**,它通常直接告诉你问题在哪

给两周时间,因为这是第一次密集接触代码。**目标:跑通一个会用搜索工具回答问题的 agent。**

## 第 5 周:Unit 2.2 + 2.3 快速过(LlamaIndex 和 LangGraph)

这两个框架**只需了解,不必精通**:
- *LlamaIndex*:擅长让 agent 查阅你自己的文档资料
- *LangGraph*:擅长编排复杂的多步骤流程(像画流程图一样设计 agent)

策略:每个花 1–2 小时读概念部分,示例代码看懂即可,不强求全部跑通。知道「什么场景该用哪个」就达标。

## 第 6 周:Unit 3 Agentic RAG(用例)

*RAG(Retrieval-Augmented Generation,检索增强生成)*:让 agent 先去资料库里查相关内容,再基于查到的内容回答——开卷考试,而不是闭卷硬背。*Agentic RAG* 就是让 agent 自己决定查什么、查几轮。

这个单元是真实用例,也是**结业证书要求的用例作业**所在。跟着做,并完成作业。

## 第 7–8 周:Unit 4 最终项目 + 结业证书

构建一个 agent 参加课程的 benchmark(基准测试)挑战,提交到学生排行榜。完成后拿**结业证书**。

不用追求排名——能跑通、能提交,对文科背景的你已经是了不起的成就。

---

## 加餐单元(选修,拿完证书后再说)

- Bonus 1:Fine-tuning for Function-calling(微调模型学会调用工具)——偏技术,可跳过
- Bonus 2:Agent 的可观测性与评估——想认真做 agent 产品再看
- Bonus 3:用 Agent 打宝可梦对战——纯好玩,当奖励

## 坚持下去的三个建议

1. **固定时间。** 每周约 4 小时,拆成两次、每次 2 小时,比周末突击 4 小时有效。
2. **卡住超过 30 分钟就求助。** 问 AI(把报错信息整段贴给 Claude/ChatGPT)、查课程 [Discord](https://discord.gg/UrrTSsSyjb) 的 #agents-course-questions 频道。卡住不是你的问题,是所有学编程的人的日常。
3. **每周写 3 句话总结**:这周学了什么、哪里卡住了、下周计划。这比多学一小时更能帮你坚持。

## 里程碑一览

| 时间 | 目标 | 奖励 |
|------|------|------|
| 第 0 周 | 看懂六个 Python 概念 | 敢碰代码了 |
| 第 2 周末 | 完成 Unit 1 quiz | 🎓 基础证书 |
| 第 4 周末 | 跑通第一个 smolagents agent | 你写的程序会自己干活了 |
| 第 6 周末 | 完成用例作业 | 距结业一步之遥 |
| 第 8 周末 | 提交最终项目 | 🎓 结业证书 |
