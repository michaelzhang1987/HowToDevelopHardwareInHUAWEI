27 可靠性设计
======================

原创 硬件十万个为什么 2020-03-16 21:00:49

产品可靠性是设计出来的

生产出来的，管理出来的

－钱学森

**一、电路是设计出来的。不要做个画图，要做个设计师。**

一个电解电容紧挨着散热片焊接的，与电解电容相关联的那部分电路参数容易漂，现象和结果就是机器参数不稳； 绿色发光二极管的色调不一致，外观看起来不美观，发光管都有个波长的要求，即使都是绿光，波长的细微差别也会导致色差，而设计文件上并没对发光管的波长做出规定； 某块电路工作不好，发现将PCB板信号线的一个电感换成磁珠就好了，于是就改了BOM单，电路板上趴着个磁珠大肆生产了。常规理解看来，磁珠似乎和电感的特性是相同的，但事实上磁珠表现的是一个随频率变化的电阻特性，是消耗性的，而电感是储能特性，是储存性的削峰填谷。即使从实际结果来看，似乎更换器件后没问题，但其实并没有搞通真正的器件机理。病虽然莫名其妙的好了，但病毒的隐患仍在。

![](http://p1.pstatp.com/large/pgc-image/fc68cf3f9dd54675a6cff5c5259b7062)

还有很多类似的问题，比如散热，似乎热设计只和机箱内温度有关，却忽视了一个致命的问题，温度系数，即使温度不够高到烫手的地步，温度的升高是否会导致温漂，温漂后的参数值是否会将器件的特征参数推到电路正常工作的边缘？

比如降额，几乎所有工程师都说“我们降额了，基本降了50%，余量是足够的，这个问题肯定没有”。那么降额时，所有该降额的参数都降到了安全范围吗？同一类功能的器件，换了不同封装形式或生产工艺的时候，一样的降额系数能降出一样的效果来吗？在特定位置、特定电路下的器件，明确哪个特定参数该降的更大一点吗？

还有电磁兼容、振动、可维修性、测试等等多方面的问题，知己知彼，百战不殆，在实际的考察中，发现既不知己、也不知彼的设计太多，不知己是不知道自己不知道什么，不知彼是不知道设计所面对的对象的诸多参数、条件、工艺、特性，而恰恰是由此引出了太多的技术问题。

**二、电子可靠性设计原则**

电子可靠性的设计原则包括：RAMS定义与评价指标、电子设备可靠性模型、系统失效率的影响要素、电子产品可靠性指标、工作环境条件的确定、系统设计与微观设计、过程审查与测试、设计规范与技术标准。

钱学森的水平和优势是什么？电子、机械、软件、测试、管理？

都不是，是系统方法论和工程计算。

当我们要决策一个电路的器件选型的时候，如果有一个基本公式，直接告诉了我们应该重视哪个指标，器件选型和电路设计就遵循规范，自然可以提升我们的可靠性设计了。

例如一个插座电缆，上面要通过10A的电流，是用2根8A的导线并联分流好呢？还是用一根14A的电缆好呢？通过可靠性模型可以轻松得到答案。

驱动一个发光管，是用三极管好呢，还是用运放好呢？

电子产品的可靠性设计需要注意以下基本准确：

1、产品结构和电路应尽量简便。

2、尽量选用成熟的结构和典型的电路。

3、结构要简单化、积木化、插件化。

4、如采用新电路,应注意标准化。

5、采用新技术要充分注意继承性。

6、尽量采用数字电路。

7、尽量采用集成电路。

8、逻辑电路要进行简化设计。

9、对性能指标、可靠性指标要综合考虑。

10、应尽量采用传统工艺和习惯的操作方法。

11、应不断采用新的可靠性设计技术。

12、在电子产品中,常采用的可靠性设计技术包括元器件的降额设计、冗余化设计、热设计、电磁兼容设计、维修性设计、漂移设计、容错设计与故障弱化设计等,有些还包括软件的可靠性设计。

**三、提高电路可靠性设计方法**

电路可靠性设计方法包括降额设计（降额参数和降额因子）、热设计（热设计计算、热设计测试、热器件选型）、电路安全性设计规范、EMC设计、PCB设计（布局布线、接地、阻抗匹配、加工工艺）、可用性设计（可用性要素、用户操作分析、设计准则）、可维修性设计（可维修性等级、评估内容、设计方法）

电路可靠性设计规范的一个核心思想是监控过程，而不是监控结果。

比如热设计，按照热功率密度、热流密度的计算确定下来的散热方法，您就不必担心散热不够了；按照热阻和结温的计算方法，选定了风扇和散热片，只要有足够的余量。

1、降额设计

所谓降额设计,就是使元器件运用于比额定值低的应力状态的一种设计技术。为了提高元器件的使用可靠性以及延长产品的寿命,必须有意识地降低施加在器件上的工作应力（如：电、热、机械应力等）,降额的条件及降额的量值必须综合确定,以保证电路既能可靠地工作,又能保持其所需的性能。降额的措施也随元器件类型的不同而有不同的规定,如电阻降额是降低其使用功率与额定功率之比;电容降额是使工作电压低于额定电压;半导体分立器件降额是使功耗低于额定值;接触元件则必须降低张力、扭力、温度和降低其它与特殊应用有关的限制。

电子元器件的降额,通常有一个最佳的降额范围,在这个范围内,元器件的工作应力的变化对其失效率有显著的影响,设计也易于实施,而且不需要设备的重量、体积、成本方面付出太大的代价。因此,应根据元器件的具体应用情况来确定适当的降额水平。因为若降额不够则元器件的失效率会比较大,不能达到可靠性要求;反之,降额过度,将使设备的设计发生困难,并将在设备的重量、体积、成本方面付出较大的代价,还可能使元器件数量产生不必要的增加,这样反而会使设备可靠性下降。

降额的等级分为三个等级,分别称为Ⅰ级降额、Ⅱ级降额和Ⅲ级降额。

Ⅰ级降额是最大降额,超过它的更大降额,元器件的可靠性增长有限,而且使设计难以实现。Ⅰ级降额适用于下述情况：设备的失效将严重危害人员的生命安全,可能造成重大的经济损失,导致工作任务的失败,失败后无法维修或维修在经济上不合算等。

Ⅱ级降额指元器件在该范围内降额时,设备的可靠性增长是急剧的,且设备设计较Ⅰ级降额易于实现。Ⅱ级降额适用于设备的换效会使工作水平降级或需支付不合理的维修费用等场合。

Ⅲ级降额指元器件在该范围内降额时设备的可靠性增长效益最大,且在设备设计上实现困难最小,它适用于设备的失效对工作任务的完成影响小、不危及工作任务的完成或可迅速修复的情况。

2、 热设计

由于现代电子设备所用的电子元器件的密度越来越高,这将使元器件之间通过传导、辐射和对流产生热耦合。因此,热应力已经成为影响电子元器件失效率的一个最重要的因素。对于某些电路来说,可靠性几乎完全取决于热环境。所以,为了达到预期的可靠性目的,必须将元器件的温度降低到实际可以达到的最低水平。有资料表明：环境温度每提高10℃,元器件寿命约降低1/2。这就是有名的“10℃法则”。热设计包括散

热、加装散热器和制冷三类技术,这里笔者主要谈一谈散热技术。应用中常采用的方法：

第一种是传导散热方法,可选用导热系数大的材料来制造传热元件,或减小接触热阻并尽量缩短传热路径。

第二种是对流散热方式,对流散热方式有自然对流散热和强迫对流散热两种方法。自然对流散热应注意以下几点：

设计印制板和元器件时必须留出多余空间;

安排元器件时,应注意温度场的合理分布;

充分重视应用烟囱拨风原理;

加大与对流介质的接触面积。

强迫对流散热方式可采用风机（如计算机上的风扇）或双输入口推拉方式（如带换热器的推拉方式）。

第三种是利用热辐射特性方式,可以采用加大发热体表面的粗糙度、加大辐射体周围的环境温差或加大辐射体表面的面积等方法。

在热设计中,最常采用的方法是加散热器,其目的是控制半导体的温度,尤其是结温Tj,使其低于半导体器件的最大结温TjMAX,从而提高半导体器件的可靠性。半导体器件和散热器安装在一起工作时的等效热路图如图2所示。图中各参数的含义如下：

RTj—半导体器件内热阻,℃/W;

Tj—半导体器件结温,℃;

Tc—半导体器件壳温,℃;

Tf—散热器温度,℃;

Ta—环境温度,℃;

Pc—半导体器件使用功率,W。

根据图2,散热器的热阻RTf应为：

RTf=(RTj-Ta)/Pc-RTj-RTc

散热器热阻RTf是选择散热器的主要依据。Tj、RTj是半导体器件提供的参,Pc是设计要求的参数,RTc可以从热设计专业书籍中查到。下面介绍一下散热器的选择。

（1）自然冷却散热器的选择

首先按以下式子计算总热阻RT和散热器的热阻RTf,即：

RT=(Tjmax-Ta)/Pc

RTf=RT-RTj-RT。

算出RT和RTf之后,可根据RTf和Pc来选择散热器。选择时,根据所选散热RTf和Pc曲线,在横坐标上查出已知Pc,再查出与Pc对应的散热器的热阻R'Tf。

按照R'Tf≤RTf的原则选择合理的散热器即可。

（2）强迫风冷散热器的选择

强迫风冷散热器在选择时应根据散热器的热阻RTf和风速υ来选择合适的散热器和风速。

3、 冗余设计

冗余设计是用一台或多台相同单元（系统）构成并联形式,当其中一台发生故障时,其它单元仍能使系统正常工作的设计技术。冗余按特点分为热冗余储备和冷冗余储备;按冗余程度分,有两重冗余、三重冗余、多重冗余;安冗余范围分,有元器件冗余、部件冗余、子系统冗余和系统冗余。这种设计技术通常应用在比较重要,而且对安全性及经济性要求较高的场合,如锅炉的控制系统、程控交换系统、飞行器的控制系统等。

4、电磁兼容性设计

电磁兼容性设计也就是耐环境设计。首先要明白什么是电磁兼容性问题,电磁兼容性问题可以分为两类：一类是电子电路、设备、系统在工作时由于相互干扰或受到外界的干扰使其达不到预期的技术指标;另一类电磁兼容性问题就是设备虽然没有直接受到干扰的影响,但不能通过国家的电磁兼容标准,如计算机设备产生超过电磁发射标准规定的极限值,或在电磁敏感度、静电敏感度上达不到要求。为了使设备或系统达到电磁兼容状态,通常采用印制电路板设计、屏蔽机箱、电源线滤波、信号线滤波、接地、电缆设计等技术。印制电路板在设计布置时,应注意以下几点：

各级电路连接应尽量缩短,尽可能减少寄生耦合,高频电路尤其要注意;

高频线路应尽量避免平行排列导线以减少寄生耦合,更不能象低频电路那样连线扎成一束;

设计各级电路应尽量按原理图顺序排列布置,避免各级电路交叉排列;

每级电路的元器件应尽量靠近各级电路的晶体管和电子管,不应分布得太远,应尽量使各级电路自成回路;

各级均应采用一点接地或就近接地,以防止地电流回路造成干扰,应将大电流地线和沁电流回路的地线分开设置,以防止大电流流进公共地线产生较强的耦合干扰;

对于会产生较强电磁场的元件和对电磁场感应较灵敏的元件,应垂直布置、远离或加以屏蔽以防止和减小互感耦合;

处于强磁场中的地线不应构成闭合回路,以避免出现地环路电流而产生干扰;

电源供电线应靠近（电源的）地线并平行排列以增加电源滤波效果。

5、 漂移设计技术

产生漂移的原因主要是元器件的参数标准值与实际数值存在公差、环境条件变化对元器件性能产生影响或是使用在恶劣环境而导致元件性能退化等因素。

如果元器件参数值发生的漂移超出其设计参数范围,就会使设备或系统不能完成规定的功能。漂移设计是通过在设计阶段根据线路原理写出特性方程,然后通过收集元器件的分布参数来计算它们的漂移范围以使漂移结果处在设计范围内来保证设备正常使用的一种设计方法。

6 、互连可靠性设计

由于在大部分电子产品中都有接插件,为了降低这些连接部分的故障率,因此有必要进行互连可靠性设计,常采用的方法有：

注意接插件的选型,印制电路板应尽量采用大板或多层板,以减少接插点：

尽量减少可拔插点,以提高其可靠性,重要部件可采用冗余设计;

两个插头同时相对时,应采用将其中一个固定,另一个浮动的方式,来保证对准和拔插;

采用机械固定方式;

对于常插拔的部件,最好设计成单面走线;

连接空间应选择有序分割;

馈线和地线应隐蔽安装。

此外,在电子产品在可靠性设计中,有时还采用维修性设计技术、软件可靠性设计技术、机械零件可靠性设计技术、故障安全设计技术以及一些新的可靠性设计技术等。

**四、可靠性工程**

**可靠性工程是在产品全寿命过程中同故障作斗争的工程技术，是研究产品故障的发生、发展，故障发生后的处理，修理、保障，以及如何预防故障发生、直到消灭故障的工程技术。**

![](http://p1.pstatp.com/large/pgc-image/5b845711227346969229064127b79b4d)

提高系统（或产品或元器件）在整个寿命周期内可靠性的一门有关设计、分析、试验的工程技术。系统可靠性是指在规定的时间内和规定条件（如使用环境和维修条件等）下能有效地实现规定功能的能力。系统可靠性不仅取决于规定的使用条件等因素，还与设计技术有关。有组织地进行可靠性工程研究，是20世纪50年代初从美国对电子设备可靠性研究开始的。到了60年代才陆续由电子设备的可靠性技术推广到机械、建筑等各个行业。后来，又相继发展了故障物理学、可靠性试验学、可靠性管理学等分支，使可靠性工程有了比较完善的理论基础。

产品的可靠性是设计出来的，生产出来的，管理出来的。可靠性工程是为了达到系统可靠性要求而进行的有关设计、管理、试验和生产一系列工作的总和，它与系统整个寿命周期内的全部可靠性活动有关。可靠性工程是产品工程化的重要组成部分，同时也是实现产品工程化的有力工具。利用可靠性的工程技术手段能够快速、准确地确定产品的薄弱环节，并给出改进措施和改进后对系统可靠性的影响。可靠性工程具体如下图1所示。

产品在需求分析阶段、设计阶段、工程研制阶段和生产制造阶段都需开展一定的可靠性设计分析、管理、试验工作。

按照产品的层次结构，产品的系统层次、装置层次、部件层次和零件层次都分别有相应的可靠性工作内容，即产品不同层次的可靠性影响因素和薄弱环节各有特点，需要分别开展相应的可靠性设计、管理、试验工作项目解决。系统设计师和项目管理者需要在产品的工程化角度把握可靠性工程的开展和实施。影响器件可靠性的主要因素包括器件的种类和数量、器件的额定工作电参数和电应力、额定工作温度和环境温度、元器件的质量等级和品质保证等级，器件的降额特性和热敏感特性，器件的储存可靠性；影响部件可靠性的主要因素包括器件本身的可靠性与器件相互影响，主要需要考虑的因素为热分析、电磁兼容、耐环境、信号完整性、潜通路和工艺工装；影响装置可靠性的主要因素包括部件之间的相互影响和结构、工艺、连接；影响系统可靠性的主要因素包括冗余设计、人机工程和系统可靠性设计。

建立可靠性工程体系，开展和实施可靠性工程是产品高可靠性的必要条件，可靠性设计分析是可靠性工程的基础，可靠性设计水平差的产品可靠性必然低；可靠性的设计需要可靠性管理，可靠性管理是开展可靠性设计的技术管理保证和组织结构保证；设计出的产品在生产阶段难免引入“瑕疵”，需要可靠性试验“暴露”。

![](http://p1.pstatp.com/large/pgc-image/d4ff1dea642b410e841b721dd4638861)

按照鼓掌原因的统计，分析主要故障原因。针对主要矛盾，有针对性的制定措施，实现快速的可靠性提升。

可靠性工程，是将可靠性测试和设计，融入到设计过程中。

![](http://p1.pstatp.com/large/pgc-image/45874af985bc4d3dafaa3815d411bc23)

在概念阶段，汇总所有可靠性需求；在计划阶段，从设备组网、架构设计、冗余设计、FMEA设计等方面，对可靠性哦啊进行考虑。

在开发阶段，对计划的可靠性设计进行落实；在验证阶段对可靠性需求进行验证和测试。

**五、可靠性测试**

从硬件角度出发，可靠性测试分为两类：

　　以行业标准或者国家标准为基础的可靠性测试。比如电磁兼容试验、气候类环境试验、机械类环境试验和安规试验等。

　　企业自身根据其产品特点和对质量的认识所开发的测试项目。比如一些故障模拟测试、电压拉偏测试、快速上下电测试等。

　　下面分别介绍这两类可靠性测试。

　　1 基于行业标准、国家标准的可靠性测试方法

　　产品在生命周期内必然承受很多外界应力，常见的应力有业务负荷、温度、湿度、粉尘、气压、机械应力等。各种行业标准、国家标准制定者给出了某类产品在何种应用环境下会存在多大的应力等级，而标准使用者要根据产品的应用环境和对质量的要求选定相应的测试条件即应力等级，这个选定的应力等级实质上就是产品测试规格。

　　在产品的测试阶段，我们必须在实验室环境下对足够的测试样本一一施加相应的应力类型和应力等级，考察产品的工作稳定性。对于通信设备而言，常见的测试项目至少包括电磁兼容试验、安规试验、气候类环境试验和机械环境试验，而上述四类测试项目还包含很多测试子项，比如气候类环境试验还包括高温工作试验、低温工作试验、湿热试验、温度循环试验等。此类测试项目还有很多，这里就不做详细介绍。总的而言，所有的测试项目都属于规格符合性测试（即PASS或者FAIL测试），试验的目的都是模拟产品在生命周期内承受应力类型和应力等级，考察其工作稳定性。

　　2 企业设计的可靠性测试方法

　　由于网络产品的功能千差万别，应用场合可能是各种各样的，而与可靠性测试相关的行业标准、国家标准，一般情况下只给出了某类产品的测试应力条件，并没有指明被测设备在何种工作状态或配置组合下接受测试，因此在测试设计时可能会遗漏某些测试组合。比如机框式产品，线卡种类、线卡安装位置、报文类型、系统电源配置均可灵活搭配，这涉及到的测试组合会较多，这测试组合中必然会存在比较极端的测试组合。再如验证该机框的系统散热性能，最差的测试组合是在散热条件机框上满配最大功率的线卡板；如果考虑其某线卡板低温工作性能，比较极端的组合时是在散热条件最好的机框上配置最少的单板且配置的单板功耗最小，并且把单板放置在散热最好的槽位上。

　　总之，在做测试设计时，需要跳出传统测试规格和测试标准的限制，以产品应用的角度进行测试设计，保证产品的典型应用组合、满配置组合或者极端测试组合下的每一个硬件特性、硬件功能都充分暴露在各种测试应力下，这个环节的测试保证了，产品的可靠性才得到保证。

　　以下举两个例子来说明如何根据产品特点设计出可靠性测试方法。

　　2.1实例一：包处理器外挂缓存（Buffer）的并行总线测试

　　为了应对网络的突发流量和进行流量管理，网络设备内部的包处理器通常都外挂了各种随机访问存储器（即RAM）用来缓存包。由于包处理和RAM之间通过高速并行总线互连，一般该并行总线的工作时钟频率可能高达800Mhz，并且信号数量众多，拓扑结构复杂，在产品器件密度越来越高的情况下，产品很可能遇到串扰、开关同步噪音（SSN）等严重的信号质量问题，针对上述可能遇到的问题，我们需进行仔细的业务设计，让相应硬件电路的充分暴露在不利的物理条件下，看其工作是否稳定。

　　串扰，简单的来说是一种干扰，由于ASIC内部、外部走线的原因，一根信号线上的跳动会对其他信号产生不期望的电压噪声干扰。为了提高电路工作速率和减少低功耗，信号的幅度往往很低，一个很小的信号干扰可能导致数字0或者1电平识别错误，这会对系统的可靠性带来很大影响。在测试设计时，需要对被测设备施加一种特殊的业务负荷，让被测试总线出现大量的特定的信号跳变，即让总线暴露在尽可能大的串扰条件下，并用示波器观察个总线信号质量是否可接受、监控业务是否正常。以16位并行总线为例，为了将这种串扰影响极端化，设计测试报文时将16根信号中有15根线（即攻击信号线Agressor）的跳变方向一致，即15根信号线都同时从0跳变到1，同时让另一根被干扰的信号线（即Victim）从1下跳到0，让16根线都要遍历这个情况。

　　开关同步噪音也是RAM高速并行接口可能出现的我们所不期望的一种物理现象。当IC的驱动器同时开关时，会产生瞬间变化的大电流，在经过回流途径上存在的电感时，形成交流压降，从而产生噪音噪声（称为SSN），它可能影响信号接收端的信号电平判决。这是并行总线非常恶劣的一种工作状态，对信号驱动器的高速信号转变能力、驱动能力、电源的动态响应、电源的滤波设计构成了严峻的考验。为了验证产品在这种的工作条件下工作是否可靠，必须被测设备（DUT）加上一种特殊的测试负荷，即特殊的测试报文。

举例：

　　如果被测总线为16位宽，要使所有16跟信号线同步翻转，报文内容应该为：

　　FFFF0000FFFF0000

　　如果被测总线为32位宽，要使所有32跟信号线同步翻转，测试报文内容应该为：

　　FFFFFFFF00000000FFFFFFFF00000000

　　如果被测总线为64位宽，要使所有64根信号线同步翻转，测试报文内容应该为：

FFFFFFFFFFFFFFFF0000000000000000FFFFFFFFFFFFFFFF0000000000000000

　　如果报文在DUT内部的业务通道同时存在上述位宽的总线，业务测试必须加载上述的报文，看DUTUUT在每种报文下工作是否正常，同时在相应总线上进行信号测试，看信号是否正常。

　　2.2实例二：热测试

　　热测试通过使用多通道点温计测量产品内部关键点或关键器件的温度分布状况，测试结果是计算器件寿命（如E-Cap）、以及产品可靠性指标预测的输入条件，它是产品开发过程中的一个重要的可靠性活动。

　　一般而言，热测试主要是为了验证产品的热设计是否满足产品的工作温度范围规格，是实验室基准测试，这意味着为了保证测试结果的一致性，必然对测试环境进行严格要求，比如要求被测设备在一定范围内无热源和强制风冷设备运行、表面不能覆盖任何异物。但实际上很多产品的工作环境跟上述测试环境是有差异的：

　　有些产品使用时可能放在桌子上，也可能挂在墙上，而这些设备基本上靠自然散热，安装方法不同会直接影响到设备的热对流，进而影响到设备内部的温度分布。因此，测试此类设备时必须考虑不同的安装位置，在实验室条件把设备摆放在桌子热测试通过，并不代表设备挂在墙上热测试也能通过。

　　有些网络设备在网吧行业用得比较多，几台设备叠在一起使用比较常见，做类似产品的热测试时，必须考虑到产品在此情况下热测试是否符合要求。

　　一些机框式设备，由于槽位比较多，风道设计可能存在一定的死角。如果被测对象是一块业务板，而这块可以随便插在多个业务卡槽位，热测试时必须将被测板放在散热最差的槽位，并且在其旁边槽位插入规格所能支持的大功耗业务板，后让被测单板辅助单板和满负荷工作，在这种业务配置条件下进行热测试。

　　针对不同的产品形态，硬件可靠性测试项目可能有所差异，但是其测试的基本思想是一致的，其基本的思路都是完备分析测试对象可能的应用环境，在可能的应用环境下会承受可能工作状态包括极限工作状态，在实验室环境下制造各种应力条件、改变设备工作状态，设法让产品的每一个硬件特性、硬件功能都一一暴露在各种极限应力下，遗漏任何一种测试组合必然会影响到对产品的可靠性。

![](http://p1.pstatp.com/large/pgc-image/18e2e545b0e3448594f253f7f747104b)

**中国航天之父 钱学森手稿**