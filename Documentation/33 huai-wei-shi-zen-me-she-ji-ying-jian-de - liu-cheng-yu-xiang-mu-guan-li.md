三十三 流程与项目管理
========================

原创 硬件十万个为什么 2020-03-16 21:19:26

最先将IPD付诸实践的是IBM公司，1992年IBM在激烈的市场竞争下，遭遇到了严重的财政困难，公司销售收入停止增长，利润急剧下降。经过分析，IBM发现他们在研发费用、研发损失费用和产品上市时间等几个方面远远落后于业界最佳。为了重新获得市场竞争优势，IBM提出了将产品上市时间压缩一半，在不影响产品开发结果的情况下，将研发费用减少一半的目标。为了达到这个目标，IBM公司率先应用了集成产品开发（IPD）的方法，在综合了许多业界最佳实践要素的框架指导下，从流程重整和产品重整两个方面来达到缩短产品上市时间、提高产品利润、有效地进行产品开发、为顾客和股东提供更大价值的目标。

  

IPD流程不是华为发明的，但是大家都认知到华为在引入IPD流程之后，业绩出现拐点，大家都认为IPD流程是非常经典的内容。其实，它每年都不会不断的变化，研发流程作为IPD流程的重要组成部分，每年都要发布一个版本，以保证流程的先进性与实用性。

  

在开始讲研发流程的版本管理之前，先科普几个跟研发流程密切相关的组织，便于理解流程版本管理的层级关系。

  

**研发流程改进委员会**：由各产品线研发部部长，研发流程部部长，研发流程部5级专家组成。主要负责研发流程变革项目的管理。一帮领导，思考和规划流程的战略变革方向，做流程改进的规划。

  

**研发流程CCB（研发流程变更控制管理委员会）**：由研发流程部部长，研发流程部5级专家，各产品线研发质量部部长组成。负责研发流程领域所有CR（change require 变更需求）的评审。

  

**各产品线研发质量部**：负责本产品线研发流程的适配和推行，验收。配合公司级研发流程的相关工作。研发流程部的流程管理专家会接口不同的产品线，就流程方面的工作进行交流和对接。

![华为是怎样开发硬件的  之三十三——流程与项目管理](http://p1.pstatp.com/large/pgc-image/5fc9ebd0f79445acb13a084af5eac990)

流程的产生、实施，在华为内部，也像项目一样，经历若干的阶段。

研发流程版本的生命周期大致分为这5个部分：规划、实施监控、发布、推行、验收。

  

**那么，一些中小公司的朋友，是不是会发问：“我们连流程都没有，谈什么流程变更？”**

其实我们不是没有流程，我们都有一些流程，只是没有书面化，或者是没有公司内部统一。

1、但是大家都是一样的做事情，每次做事情，犯过的错误，一直在错；

2、同事出过的错误，每个新员工都犯一遍错误；

3、做一件事情，每个同事犯不同的错误，每个人都有自己的经验，但是没有分享；技巧都不统一。都是凭着工程师的经验做事情。

  

那么每个公司，都应该在每个具体的细节上面，去反思总结，持续改进。把一些可以参考的动作，都整理出来；每个人犯的错误，都书面化描述出来，整理成规范、checklist、模板；在一些关键的节点，检查一些关键动作。

  

**由公司自上而下的，一个研发动作一个研发动作的去规范，时间久了，沉淀下来，就是一个完整的、适合自己的研发流程体系。你不一定要按照IPD流程来，但是可以学习其思想。**

  

**研发流程版本规划**一般在年底进行，由研发流程部部长和5级专家主导，研发流程各个领域的负责人参与。规划主要是根据目前业务的需求，流程的现状来规划研发流程变更项目或则研发流程领域一些探索性的业务（CR不在规划的范围）。研发流程变革项目是怎么规划来的呢？举个例子：研发外包是目前普遍的业务现状，但是流程里面缺少这一块的内容，那么最好就成立一个研发外包管理的流程变革项目，对业务进行梳理，并发布相应的流程。在做流程项目规划的时候，要考虑项目的范围和难易程度，项目是一期就能完成还是需要分期完成，项目由哪个产品线牵头比较合适，这些都是做规划的时候需要考虑的内容。

  

**研发流程版本的构成**由两大部分组成：除了变革项目外，最主要的来源是CR。如图所示：

![华为是怎样开发硬件的  之三十三——流程与项目管理](http://p1.pstatp.com/large/pgc-image/76ec5590625b443e90143f4a8d14ad42)

CR的来源主要又分为三个部分：日常CR，研发流程变革项目CR，其他流程变革项目CR。

日常CR：华为公司的任何员工发现流程文件中有问题的地方，或者与业务不相符的地方，都可以提交CR申请，提交改进建议。

研发流程变革项目：不是所有的变革项目都会发布新的流程，有一分部变革项 目是对现有流程的梳理和优化，涉及到流程修改的具体内容，都需要通过提交CR申请。

其他流程变革项目CR：非研发领域的流程项目，但涉及到研发流程配套修改的内容，也需要提交CR申请。

顺便来看一下CCB的运作：

![华为是怎样开发硬件的  之三十三——流程与项目管理](http://p1.pstatp.com/large/pgc-image/6a444afbe92d47b7b163437c9d912087)

经过CCB评审通过的CR内容，会由CCB秘书记录在CR清单中，在流程版本发布前，集中更改涉及到流程文件，并随版本发布。华为研发流程变更涉及到的流程文件的修改，每年都在上百条，所以说华为的流程从来都不是一成不变的。

  

**研发流程版本实施与监控**：研发流程版本实际上各个研发流程变革项目和CR的合集，所以研发流程版本的实施与监控，实际上就是各个研发流程变革项目和CR的实施与监控。CR的运作流程在上面一节已经讲过，现在主要来看看研发流程变革项目的管理。

研发流程变革项目的阶段和产品的版本管理其实没有大的差别，也经过需求收集分析，立项，团队组建，开发，等过程：

![华为是怎样开发硬件的  之三十三——流程与项目管理](http://p1.pstatp.com/large/pgc-image/097b03fac3ee4cc990c14a6edcfdf075)

每个决策点都需要到研发流程改进委员会汇报。根据项目的负责程度，决策点也可以进行裁剪合并。

研发流程变革项目成员一般会由流程专家和产品线业务、质量人员组成。流程专家会把握整个流程项目的进度节点，协调各产品线的意见，从流程的角度给建议以及流程文件的修改。产品线的业务人员和QA根据业务的现状和趋势，对于流程现状提出更改建议。最终项目组输出项目材料以及流程CR，再获得研发流程改进委员会和CCB的同意后，项目成果会跟随研发流程版本发布。

我觉得华为的研发流程变革项目有几个困难的地方：

1.  **不是所有产品线都重视流程，所以参与项目的人员的能力和责任性参差不齐。**
2.  **各产品线产品形态各异，要在中间找到平衡点，发布公司级的流程，是一个权衡和拉锯的过程。**
3.  **寻找合适的试点项目。华为的项目进度是出名的紧张，在大家都恨不得一天当做两天用的时候，能找到项目愿意在忙碌中试点新的流程，也不是容易的事。**

  

**研发流程版本发布**：每年的7,8月份是研发流程版本发布的时间。在正式发布之前的一个月左右，是集中修改流程文件的时候。文档需要审批上传，流程图活动图都要根据CR清单实施修改。等到所有变更都修改完毕后，研发流程部部长会汇集变更中的要点，到研发流程改进委员会和研发部部长会议上进行汇报，经过中央研发部部长同意后，研发流程正式发布。

如果有流程变革项目进度拖延了，没有赶上流程版本发布的节奏，就只能等到下一年。除非非常紧急的情况下，研发流程才会增发版本。

  

**研发流程推行：**我认为**研发流程的推行是非常重要的环节，也是整个流程管理中比较难的一个环节。**流程变革项目在运作的过程中虽然有试点项目，但试点项目毕竟是少数几个项目，不可能覆盖公司所有的项目类型，而推行，却是在整个公司的推行。那么推行的过程是怎样的呢？

在流程版本发布以后，与产品线接口的流程管理专家会到产品线IPMT，研发管理会议上汇报流程版本的重要变更点，以取得产品线领导的支持。同时，流程管理专家和产品线流程负责人会根据CR清单，逐条对变更进行适配。适配中最重要的两个文件，一个是流程活动，一个是交付件模板，这两个是关系到流程是否能够正确执行，产品交付是否合格最重要的内容。如果某个变更对某个产品来说确实不需要推行或则部分推行，都得在适配的时候提出来，并且给出适配的具体方案。

个人认为适配是推行环节中非常重要的一个前奏环节，适配做得好不好，关系到流程推行的难易程度，同时，适配也是对流程管理专家和产品线流程负责人一个非常重大的考验。必须对流程的变更和产品线产品非常熟悉，才能做出正确的适配。如果流程的推行过程，被认为一定是自上而下的，或则研发人员认为流程的变更对于业务没有帮助还必须推行，那我认为，这是推行的前期适配工作没有做好。

适配也分层级：首先是产品线一级的适配，然后是SPDT，PDT的适配，最后是产品项目的适配，在产品项目的质量策划中，就得明确相关的流程活动及交付件。这也为后续流程的验收打下基础。

  

**流程验收**：流程验收是在第二年的5月份左右。验收的过程我们也用一张图来进行说明。

![华为是怎样开发硬件的  之三十三——流程与项目管理](http://p1.pstatp.com/large/pgc-image/6cceb5bd89c8490ab8c590c1e4f39bbc)

研发流程的变更会涉及到产品的整个开发过程，所以验收的项目尽量选择进展时间长的，可以验收到更多的变更点。验收项目的多少也要根绝产品线和验收清单的覆盖点来确定。一般情况下一个产品线验收4，5个项目差不多。如果整体验收结果出来后，发现有一些变更点都没有验收到，可以再补抽查。

交付件的审查主要看新模板的使用情况以及交付件的归档，密集是否符合要求。目前对于有特殊市场要求的产品，会审查得更严格一些。

验收会议主要是对项目成员的访谈，包括项目经理，QA，研发人员，配置经理等各领域角色。验收会议的目的主要是对项目过程的规范性和流程遵从性做一个调查和了解，同时对流程变革的内容做一个了解，变革内容是否合适，产品在执行的过程中有没有遇到什么问题和困难，对于流程还有哪些建议，这些都是对流程的改进一个很好的输入。所以，如果你是产品线的研发人员，如果你的项目正在被验收，不要拒绝也不要应付了事，这是一个很好的机会，让流程能离你们更近。

验收报告也分几层：单个项目的验收报告，产品线的验收报告，以及整个研发流程的验收报告。整个研发流程的验收报告需要在研发流程改进委员会汇报，各个产品线的验收情况会拉通，所以哪个产品线对流程的执行度是什么情况就一目了然了。