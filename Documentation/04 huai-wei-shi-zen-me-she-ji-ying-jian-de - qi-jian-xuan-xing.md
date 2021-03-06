4 器件选型
===================

原创 硬件十万个为什么 2020-03-16 11:36:05

一、关于“器件选型规范”：

在我进入华为的时候，当时整个公司都在“规范”运动，什么都写规范，人人都写规范，什么任职、绩效、技术等级都看规范。（大公司用KPI来引导，容易搞成“运动”）。

所以当时，按照器件种类，很多人写了各种器件选型规范。当时，原理图评审的时候，听得最多的就是“规范就是这样写的”，这里面有一些问题：

1、写规范的人不一定水平高，或者写得不细致，如果出现错误那就更是害人了。

2、规范有时抑制了开发人的思维，什么都按照规范来，不一定适合实际的设计场景；例如我需要低成本设计，但是规范强调的是高质量，就不一定适用。

3、有了规范之后，也会导致部分开发人员不思考，例如晶振要求在50MHz以上，放pF级的电容进行电源滤波，而低于50MHz的不用。大家都不想为什么，自然也不知道为什么；再例如网口变压器防护，室内室外，按照各种EMC标准的设计要求，直接照着画就可以；但是很少有人想为什么，也不知道测试的结果怎样，等实际碰到困难时就抓瞎了。的确在有的时候提高了工作效率和产品质量，但是工具也发达，人也就越退化，这是必然。

4、有些器件的选型，不适合写规范，因为器件发展太快，有可能等你规范写好，器件都淘汰了。例如：在X86处理器进入通信领域了之后，处理器选型规范就显得多余。

规范确实能带来好处。但是，并不是所有工作都适合用规范来约束。硬件工程师要能跳出“参考电路”、跳出“规范”，从原理思考问题和设计。

当然规范还是非常有用的一个手段，是大量的理论分析+经验积累+实践数据的精华。我觉得当时我看得最多的规范，是《器件选型的降额规范》，这是基于大量试验，实际案例，总结出来的器件选型的时候，需要考虑的内容。

例如：规定选用铝电解电容的时候，需要考虑稳态的工作电压低于额定耐压90%；而钽电容，稳态的降额要求在50%；而陶瓷电容，稳态的降额要求在85%；因为这里考虑了一些器件的实效模式、最恶劣环境（高温、低温、最大功耗），稳态功率和瞬态功率的差异……等等因素。

二、器件选型需要考虑的因素：

在华为的PDM系统上，器件都有一个优选等级“优选”“非优选”“禁选”“终端专用”等几个等级。

工程师可以根据这个优选等级来直观的感受到器件是否优选。

那么器件的优选等级，是考虑了哪些因素呢？

**1．可供应性：**特别是华为这样厂家，有大量发货的产品。慎选生命周期处于衰落的器件，禁止选用停产的器件。我2005年时曾设计过一个电路，设计的时候就是拷贝别人的电路，结果加工的时候发现器件根本买不着，由于器件停产了，只能在电子市场买翻新的器件。

对于关键器件，至少有两个品牌的型号可以互相替代，有的还要考虑方案级替代。这点很重要，如果是独家供货的产品，是需要层层汇报，决策，评估风险的。

2．**可靠性：**

散热：功率器件优先选用RjA热阻小,Tj结温更大的封装型号；处理器选型，在性能满足的情况下，尽量选择功耗更小的器件。但是如果是Intel这样垄断的器件，你也只有忍受，加散热器，加风扇。

ESD：所选元器件抗静电能力至少达到250V。对于特殊的器件如：射频器件，抗ESD能力至少100V，并要求设计做防静电措施。（注：华为是严格要求，禁止裸手拿板的。我本来也不理解，后来我带团队之后，发现兄弟们花大量的时间在维修单板；我们的团队就非常严格要求这一点，看似降低效率，其实还是提高效率的。至少不用总怀疑器件被静电打坏了。）

所选元器件考虑更高的湿敏等级。

安全：使用的材料要求满足抗静电、阻燃、防锈蚀、抗氧化以及安规等要求。

失效率：避免失效率高的器件，例如标贴的拨码开关。尽量不要选择裸Die的器件，容易开裂。不要选择玻璃封装的器件。大封装的陶瓷电容不要选择。

失效模式：需要考虑一些器件的失效模式是，开路还是断路，会造成什么后果，都需要评估。这也是钽电容慎选的一个重要原因。

**3．可生产性：**不选用封装尺寸小于0402的器件。

尽量选择表贴器件，只做一次回流焊，就完成焊接，不需要进行波峰焊。部分插件器件不可避免选用的话，需要考虑，能否采用通孔回流焊的工艺完成焊接。减少焊接的工序和成本。

**4．环保：**由于华为大量的产品是发往欧洲的，所以环保的要求也比较严格。由于欧盟提出无铅化要求，曾经整个公司的几乎所有的硬件工程师都在做无铅化的整改。

**5.考虑归一化：**例如某产品已经选用了这个器件，并且在大量出货的时候，往往有时这个器件的选型并不是很适合，也会选择，因为不但可以通过数量的增多来重新谈成本，还可以放心的选用，因为经过了大批量的验证。这也是为什么倾向于选用成熟期的器件，而慎选导入期和衰落期的原因。

**6.行业管理：**某一个大类，例如：电源、时钟、处理器、内存、Flash等等都是有专门的人做整个公司的使用的规划和协调，提前进行市场调研，分析，编写规范。他们会参与到新器件的选型上来。

**7、器件部门：**专门有器件部门的同事，会分析器件的失效原因，可靠性分析，拍摄器件的X光，评估器件寿命等等工作。

**8、成本：如果在上述因素都不是致命的情况下——上述的因素都是浮云，紧盯第八条。**