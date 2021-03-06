# **双FMGC失效的现象：**

1. 双MCDU黑屏
2. 自动驾驶、自动推力断开 FMA出现**THR LK**警告，推力可能会在短时间内跟随推力手柄角度进行突然变化，FMA完全消失
3. PFD上指引小时，并出现红色**FD**字样
4. ND地图不可用，且出现红色**MAP NOT AVAILABLE**
5. 两部MCDU顶部的琥珀色**FM1**和**FM2**灯亮
6. ND两部导航设备成虚线
7. 着陆标高自动调节功能失效
8. 飞机上的全重显示消失
9. 放出形态后反应式风切变探测失效警告响起

# **双FMGC失效的程序：**

1. 发现故障，PF报出**THR LK**，按照当前推力，将推力手柄移至当前推力所对应的角度之后，断开A-THR
2. 重新尝试接通两部**AP**，以及相对应通道的**A-THR**
3. 如果重新接通不成功，PF下口令：关FD，放小鸟，执行非正常程序
4. 如模拟机具有BACK UP F-PLAN功能，起动该功能在ND上显示记忆的航路，如当前未能找到合适的导航台，可根据此功能提供的航线，人工沿线飞行
5. 完成故障识别后进行短期决策，宣布PANPAN，申请雷达引导或自主导航飞向某点进行排故
6. 无论有无雷达引导，下口令使用备用导航设备进行导航和位置判断
7. 按照非正常程序进行计算机复位（短期复位/长期复位），之后进行长期决策
8. 使用舱单上ZFW+当前FOB的方式重新计算当前飞机的重量，得到当前飞机全重之后，根据重心查询着陆距离及进近速度，如果当前飞机重量超过最大着陆重量（参考"7. 限制"[^1]），应当联系ATC使用原始数据导航加入等待耗油
9. 长期决策后，如需要返场或备降，进行进近准备，决策依据先考虑天气因素，获取进近条件，复习ECAM
10. 之后使用原始导航设备进行进近

---

# **容易出现的问题：**

* 出现**THR LK**后没有正确的将推力手柄收回至当前的推力位置再断开推力，造成突然的俯仰或速度的改变
* 尝试重新接通不成功后第一时间不关FD，不放小鸟
* 对人工三脱飞行没有预期，无法保持速度、高度、方向
* 不按照标准的非正常程序进行处置，进近准备后不按照带故障的程序复习ECAM，遗漏目的地机场**着陆标高**的人工调节
* 不尝试进行系统复位
* 混淆每一部RMP频率调谐与对应导航设备的关系
* PM尝试使用PF一侧的RMP调谐ILS频率
* 使用备用导航设备后，选择电门没有选回VHF位，**SEL**灯常亮
* 没有获取足够的决策依据就开始准备直接返场
* 没有进行飞机全重的计算，造成无必要的超重着陆
* 在进行标准进场时，没有考虑导航台切换的优先顺序
* 遗忘跑道距离和V~app~的查询
* 反射式风切变在双FMGC失效时就已经失效，但是不会有相应的警告，在进近过程中放襟翼后会出现相关提示，不要去进行相关的非正常处置程序
* 试图执行ATC给出的RNAV程序


# **双FMGC失效涉及到的知识：**

* 为什么已经判断了双FMGC失效，但还是要尝试重新接通AP和A-THR？

  * 虽然双FMGC失效，但是FMGC其实同时在实现FM和FG两个功能，当双FMGC失效时，虽然从表象上看失去了FM和FG两个功能，但是实际上有可能仅有其中FM（飞行管理）功能失效，而FG（飞行引导）功能正常工作，我们需要进行积极尝试重新接通AP和A-THR，当一个通道不工作时还可以进行另外一个通道的尝试，只有确定了FMGC1+2确实无法提供任何功能，我们才再去继续使用人工飞行方式飞行
* 为什么PM不要去尝试使用PF一侧的RMP进行ILS频率的调谐？

  * 当双FMGC失效后，唯一的一套ILS系统可以通过两侧的RMP进行调谐，当需要进行相应侧的其他导航台频率调谐时，由于系统限制原因，只能在对侧调谐，但是机组需要明白手臂横越中央操纵台时误碰推力手柄的风险，为了减少这种风险，机组应该在进行ILS盲降频率调谐时尽量使用本侧的RMP设备
* 双MCDU失效和双FMGC失效的区别？

  * MCDU只是一个控制组件，相当于人机对话的接口，双MCDU失效只是进行人机对话的接口不可用，失去了进行FM指令的窗口，而FG功能健在，AP、A-THR功能都可以正常使用，但是双MCDU功能一旦失效，FM、FG功能都不可用，机组的工作负荷远大于单纯的失去双MCDU时的工作负荷
* 双FMGC失效的V~app~应该查有故障的还是无故障的？

  * 双FMGC失效虽然影响了自动飞行功能，但是飞机本身的性能并没有受到影响，因此在进近时着陆距离和V~app~的确定都应该使用无故障的性能表进行查询，唯一需要注意的是需要根据舱单上提供的实际重心进行查询。
* 双FMGC失效后，BACK UP F-PLAN功能其实并没有实际上的用处，能不能不起动？

  * 建议在飞机能够提供此功能的情况下还是起动BACK UP F-PLAN功能，该功能虽然不能帮助你重新恢复导航，但是能够给你进行航路的提示，在当前的运行环境下，大部分的航线都在使用RNAV或RNP程序，在没有在第一时间找到合适的导航台时，尽量沿线飞行，在进近期间如果觉得ND上的线段会对自己产生干扰，可以重新关闭BACK UP F-PLAN功能
* 双FMGC失效后，雷达显示的天气信息还准确吗？

  * 准确，雷达的天气信息是以实时探测到的信息为主，能够直观的通过ND上的距离弧直观判断当前飞机和天气的相对位置关系。基于金科玉律中对于导航的定义，在飞行过程中了解天气所在的位置以及是否会对后续飞行产生影响，这是机组所需要了解的必要信息。因此，在飞行的过程中，如果出现双FMGC失效，机组更应该谨慎通过ND上的天气信息来判断后续飞行的路线，并且以此作为决策依据

[^1]: # 7. 限制

    标签：#限制#

    **注意：**由于各公司运行机型与构型各不相同，因此本笔记中涉及到的限制仅供参考，具体限制以各公司手册对应的飞机编号为准。


    # 飞机概述：


    #### 飞行机动载荷加速：

    * 光洁形态：

      * -1g至+2.5g
    * 其他形态：

      * 0g至+2g

    #### 最大操作高度：

    * 光洁形态：

      * 39800ft（这是可以保持座舱压力低于8000ft的最大高度）
    * 带形态：

      * 20000ft

    #### 机场运行限制：

    跑道坡度：±2°

    跑道高度：9200ft

    标称跑道宽度：45m（某些机型为：30m，以公司手册为准）


    #### 飞机离地俯仰和坡度限制：

    参看各公司手册DSC-20-40

    ---

    # 风的限制：


    最大**验证**侧风：38kt（包含侧风）

    起落最大顺风限制：10kt


    客货舱门的操作：

    * 客舱门操作最大风速65kt
    * 前和后货舱门操作时的最大风为 40 节（或 50 节，如果飞机机头迎风，或如果前和后货舱门处在下风面）
    * 在风速超过 65 节前，必须关闭前和后货舱门


    #### 湿跑道和污染跑道上最大的**推荐**侧风：

    | 跑道状态/跑道污染物                                                                                                                                                                  | ESF^（1）^或PIREP^（2）^ | 最大起飞侧风（包括阵风） | 最大着陆侧风（包括阵风） |
    | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------- | :------------------------: | -------------------------- |
    | **潮湿：**<br />湿：3mm（1/8''）水<br />雪浆：3mm（1/8''）<br />干雪：3mm（1/8''）<br />湿雪：3mm（1/8''）<br />霜                                                                                 | 好                         |           38kt           | 38kt                     |
    | **实雪：**<br />OAT≤-15°C                                                                                                                                                        | 好至中                     |           29kt           | 29kt                     |
    | **干雪：**<br />大于3mm（1/8''），最多100mm（4''）<br />**湿雪：**<br />大于3mm（1/8''），最多30mm（6/5''）<br />**实雪：**<br />OAT＞15℃<br />**实雪上有干雪<br />实雪上有湿雪<br />湿滑** | 中                         |           25kt           | 25kt                     |
    | **水：**<br />大于3mm（1/8''），最多13mm(1/2'')<br />**雪浆：**<br />大于3mm（1/8''），最多13mm(1/2'')                                                                               | 中至差                     |           20kt           | 20kt                     |
    | **冰**（冷的&干的）<br />                                                                                                                                                          | 差                         |           15kt           | 15kt                     |

    EFS：预计道面摩擦力

    PIREP：刹车效应飞行员报告

    注：上表中给出的最大侧风的数值是基于计算得出的**推荐**值。


    自动着陆侧风限制请查看："自动着陆最大风条件："[^2]

    ---

    # 污染跑道起飞限制：


    以下跑道条件不推荐起飞：

    * 实雪顶部有水
    * 冰上有干雪或湿雪

    以下条件不允许起飞：

    * 湿冰

    ---

    # 速度限制：


    #### 驾驶舱窗户打开最大速度：

    200kt


    #### 最大使用速度：

    * VMO：350kt
    * MMO：M 0.82


    #### 最大襟缝翼速度：

    | 襟翼手柄位置 | 显示的形态 | 最大速度 | 飞行阶段         |
    | -------------- | ------------ | ---------- | ------------------ |
    | 1            | 1          | 230kt    | 下降、等待、进近 |
    | 1            | 1+F        | 215kt    | 起飞             |
    | 2            | 2          | 200kt    | 起飞、进近       |
    | 3            | 3          | 185kt    | 起飞、进近、着陆 |
    | FULL         | FULL       | 177kt    | 着陆             |


    #### 起落架速度限制：

    * 起落架放出时的最大速度（VLE）：280kt/M 0.67
    * 可以放下起落架的最大速度（VLO~放下~）：250kt/M 0.60
    * 可以手上起落架的最大速度（VLO~收上~）：220kt/M 0.54

    #### 最大轮速：

    195kt

    滑行速度：当飞机重量大于76000kg时，转弯速度不能超过20kt。

    #### 雨刷使用限制：

    最大使用雨刷速度：230kt

    ---

    # 重量限制：

    由于每个公司的重量限制因飞机构型不同而不同，因此请参考本公司对于本公司手册中关于重量限制部分内容。

    ---

    # 引气、空调、增压、通风限制：


    #### 引气：

    机上有旅客时，建议无空调供给时间不超过20分钟。

    不得同时使用地面HP气源装置和APU引气。


    #### 电子设备通风：

    | 外界温度        | 飞机供电时间 |
    | ----------------- | -------------- |
    | OAT≤49℃       | 无限制       |
    | 49℃＜OAT≤55℃ | 2h           |
    | 55℃＜OAT≤60℃ | 1h           |
    | 60℃＜OAT≤64℃ | 0.5h         |

    #### 座舱压力：

    * 最大正压差：

      * 9.0 PSI
    * 最大负压差：

      * -1 PSI
    * 安全释放活门设置：

      * 8.6 PSI

    飞行机组不得同时使用来自组件和来自 LP 空调装置的空调空气，以防止对空调系统产生任何不利的影响。

    ---

    # 自动飞行系统：


    #### 自动驾驶：

    | 状态                                              | 最低条件                   |
    | --------------------------------------------------- | ---------------------------- |
    | 起飞时                                            | 100ft（AGL）且离地至少5秒  |
    | 在使用FINAL APP，V/S或FPA模式的进近中             | 250ft (AGL)                |
    | 盘旋进近                                          | 500ft（AGL）               |
    | 在 ILS进近中，若FMA上未显示CAT 2或CAT 3能力<br />     | 160ft（AGL）               |
    | 在 ILS 进近中， 当FMA上显示 CAT 2或 CAT 3能力时<br /> | 参考CAT II/CAT III运行     |
    | 在PAR精密雷达进近或对等的进近中<br />                 | 250ft（AGL）               |
    | 人工复飞后<br />在所有其它飞行阶段<br />                  | 100ft (AGL)<br />500ft （AGL） |


    #### 导航方式的使用：

    **起飞后：**

    起飞后可以使用NAV方式，前提条件是：

    * GPS PRIMARY（GPS主用）可用，或
    * 飞行机组检查了FMGS起飞更新。

    **终端区域：**

    可在终端区域使用 NAV 方式，只要：

    * GPS PRIMARY（GPS主用）可用，或
    * 在MCDU上检查或输入了适当的RNP，并显示 HIGH 精度，或
    * 用导航设备原始数据交叉检查了FMS导航。


    #### 最低决断高：

    **特殊授权CAT I(SA CAT I)：**

    最低决断高：150ft（AGL）

    在 APPR 方式中至少一部自动驾驶仪必须接通下降至 决断高，并且 CAT 2，或 CAT 3 SINGLE 或 CAT 3 DUAL 必须显示在FMA 上。

    飞行机组必须使用 HUD 监控进近。飞行机组应该进行人工着陆。


    **低于标准的 CAT I（LTS CAT I）：**

    最低决断高：200ft（AGL）

    飞行机组必须使用 HUD 飞进近。

    飞行机组应执行人工着陆。


    **ILS Ⅱ 类：**

    最低决断高：100ft（AGL）

    至少一部自动驾驶仪必须接通在 APPR 方式，并且CAT 2, 或CAT 3 SINGLE或CAT 3DUAL 必须显示在 FMA 上。 人工着陆时，AP 应不晚于 80 ft AGL 断开。


    **特殊授权 CAT II (SA CAT II)**：

    最低决断高：100ft（AGL）

    至少一部自动驾驶仪必须接通在APPR方式，并且CAT 2, 或CAT 3 SINGLE 或 CAT 3 DUAL必须显示在FMA上。

    有HUD，飞行机组必须使用HUD监控进近并执行自动着陆或人工着陆。无自动着陆时，如果飞行机组执行自动进近，必须在不迟于80ft（AGL）前断开自动驾驶。

    没有HUD,飞行机组必须执行自动着陆。


    **不同于标准的 CAT II（ OTS CAT II）**：

    最低决断高：100ft（AGL）

    至少一部自动驾驶仪必须接通在APPR方式，并且CAT 2, 或CAT 3 SINGLE或CAT 3DUAL 必须显示在 FMA 上。  

    有HUD ,飞行机组必须使用HUD监控进近并执行自动着陆或人工着陆。无自动着陆时，如果飞行机组执行自动进近，须在不迟于 80 ft AGL 前断开自动驾驶。如无 HUD，飞行机组必须执行自动着陆。  


    **ILS III 类失效消极保护（单通道）：**

    最低决断高：50ft（AGL）

    在选择或管理速度下必须使用 自动推力。

    至少一部自动驾驶必须接通在APPR方式，并且FMA上必须显示CAT 3 SINGLE或CAT 3 DUAL。  


    **ILS III 类失效后保持工作（双通道）**：

    最低DH：100ft

    在选择或管理速度下必须使用自动推力。

    在 APPR 方式中必须接通两部自动驾驶，且 FMA 上必须显示 CAT 3 DUAL。

    * 无DH的CAT III

      * 最小RVR：75m


    #### 自动着陆：

    只有在进近中达到 1 000 ft 之前完成了发动机失效程序且在形态全（CEO）或形态3或者形态全（NEO）下，才允许进行 CAT II 和 CAT III 的失效消极保护自动着陆。  


    #### 自动着陆最大风条件：

    {{{col
    **NEO发动机：**

    **CEO发动机：**

    }}}

    {{{col
    * 顶风：30kt
    * 顺风：10kt
    * 侧风：20kt（15kt用于单发失效时的自动滑跑）

    * 顶风：30kt
    * 顺风：10kt
    * 侧风：20kt（无自动滑跑）/15kt（有自动滑跑）

    }}}

    ---

    # APU：


    #### APU起动：

    连续三次尝试起动 APU 后，飞行机组必须等待 60 min 才能进行新的起动尝试。

    在进行加/抽油程序时，允许APU的起动和关车，前提条件时：

    * 如果APU不能起动或自动关车，不要起动APU
    * 如果发生燃油溢出，执行正常APU关车


    #### APU转子速度：

    最大N转速：107%


    #### APU的EGT限制：

    最大EGT对于 APU 起动（低于 35 000 ft）：1090℃

    最大EGT对于 APU 起动（高于 35 000 ft）：1120℃ 

    APU运转时最大EGT：675℃


    #### APU电瓶起动限制：

    在应急电气构型下，最大电瓶起动APU高度为：FL2500

    且要求符合下列包线：

    ![APU.bmp](assets/APU-20210826125909-q834e9v.bmp)


    #### APU供气限制：

    辅助起动发动机最高限制：20000ft

    空调和增压的最大高度（单组件）：22500ft

    空调和增压的最大高度（双组件）：20000ft

    不允许使用APU引气用于机翼防冰

    ---

    # 发动机：


    #### 发动机推力/EGT限制：

    **NEO：**

    | 操作                 | 条件           | 时限   | EGT    |
    | ---------------------- | ---------------- | -------- | -------- |
    | TOGA（包含起飞FLEX） | 所有发动机工作 | 5min   | 1083℃ |
    | TOGA（包含起飞FLEX） | 一台发动机工作 | 10min  | 1083℃ |
    | MCT                  | 无限制         | 无限制 | 1043℃ |
    | 起动                 | 地面           |        | 1083℃ |
    | 起动                 | 空中           |        | 1083℃ |

    **CEO：**

    | 操作                 | 条件           | 时限   | EGT   |
    | ---------------------- | ---------------- | -------- | ------- |
    | TOGA（包含起飞FLEX） | 所有发动机工作 | 5min   | 950℃ |
    | TOGA（包含起飞FLEX） | 一台发动机工作 | 10min  | 950℃ |
    | MCT                  | 无限制         | 无限制 | 915℃ |
    | 起动<br />               | 地面<br />         |        | 725℃ |
    | 起动                 | 空中           |        | 725℃ |


    #### 轴转速：

    {{{col
    **NEO：**

    **CEO：**

    }}}

    {{{col
    正常操作中的最大N1：100%

    最大N1：:104%

    }}}

    {{{col
    最大允许N1:105%

    最大N2：105%

    }}}

    正常操作中的最大N2:100%

    最大允许N2:105%


    #### 滑油温度：

    {{{col
    **NEO：**

    **CEO：**

    }}}

    {{{col
    最大温度：151℃

    最大连续温度：140℃

    }}}

    {{{col
    最低起动温度：-40℃

    最大瞬时温度（15 min）：155℃

    }}}

    {{{col
    起飞前最低温度：52℃

    {{{row
    最低起动温度：-40℃

    起飞前最低温度：-10℃

    }}}

    }}}


    #### 滑油量：

    | NEO                                            | CEO                                      |
    | ------------------------------------------------ | ------------------------------------------ |
    | 滑油量≥14夸脱，如OAT＜-30℃，滑油量≥16.5夸脱 | 滑油量≥9.5夸脱+0.5夸脱/每小时预计消耗量 |


    #### 起动机：

    | <br />   | NEO                                                                       | CEO                                                                |
    | ------ | --------------------------------------------------------------------------- | -------------------------------------------------------------------- |
    | 循环 | 最多2次标准自动起动为一个循环                                             | 最多3次标准自动起动为一个循环                                      |
    | 间隔 | 对于地面起动（自动或人工），在连续的工作循环之间要求 35 s 的停顿<br />        | 对于地面起动（自动或人工），在连续的工作循环之间要求 20 s 的停顿<br /> |
    | 冷却 | 继3次失败的工作循环，或15min 连续或累积的冷转后, 要求有15 min的冷却时间<br /> | 继4次失败的工作循环，要求有15 min的冷却时间<br />                      |
    | 限制 | 当 N2高于20%时，不得运转起动机。<br />                                        | 当 N2高于20%时，不得运转起动机。                                   |


    #### 反推：

    飞行中严禁选择反推。

    不允许使用反推让飞机后退。

    70 kt 以下不应使用最大反推。允许使用慢车反推直至飞机停下。  


    #### 灵活起飞：

    仅当工作的发动机在灵活温度（ TFLEX）的可用推力情况下，飞机满足起飞重量的所有性能要求时，才允许减推力起飞，即所谓的 灵活 起飞。

    在存在任何影响性能的不工作项目的情况下，只有在应用了相关的性能差额来满足上述要求时，才允许减推力起飞。

    不允许在污染跑道上灵活起飞。  


    **灵活起飞的条件：**

    | NEO                                           | CEO                                           |
    | ----------------------------------------------- | ----------------------------------------------- |
    | T~Flex~不得高于T~MAXFLEX~，即 ISA + 50 ° C | T~Flex~不得高于T~MAXFLEX~，即 ISA + 53 ° C |
    | 低于平台温度（T~REF~）                       | 低于平台温度（T~REF~）                       |
    | 低于实际的 OAT                                | 低于实际的 OAT                                |


    #### 发动机最大侧风起动：

    最大验证起动侧风：35kt。

    ---

    # 飞行操纵：


    #### 飞行机动载荷加速限制：

    #### 飞行机动载荷加速：

    * 光洁形态：

      * -1g至+2.5g
    * 其他形态：

      * 0g至+2g


    #### 襟缝翼放出飞行的最大高度：

    #### 最大操作高度：

    * 光洁形态：

      * 39800ft（这是可以保持座舱压力低于8000ft的最大高度）
    * 带形态：

      * 20000ft


    #### 最大襟缝翼飞行速度：

    #### 最大襟缝翼速度：

    | 襟翼手柄位置 | 显示的形态 | 最大速度 | 飞行阶段         |
    | -------------- | ------------ | ---------- | ------------------ |
    | 1            | 1          | 230kt    | 下降、等待、进近 |
    | 1            | 1+F        | 215kt    | 起飞             |
    | 2            | 2          | 200kt    | 起飞、进近       |
    | 3            | 3          | 185kt    | 起飞、进近、着陆 |
    | FULL         | FULL       | 177kt    | 着陆             |


    ---

    # 燃油：


    #### 起飞时燃油不平衡：


    ###### 内侧油箱（外侧平衡）：

    | 油箱容量（较重的油箱） | 最大不平衡          |
    | :----------------------: | --------------------- |
    |           满           | 500 kg（1102 lb）   |
    |   3000 kg（6613 lb）   | 1050 kg（2314 lb）  |
    |  1450 kg （3196 lb）  | 1045 kg （3196 lb） |

    ###### 外侧油箱（内侧平衡）：

    | 最大不平衡 | 370 kg（815 lb） |
    | ------------ | ------------------ |


    #### 飞行和着陆时燃油不平衡：


    ###### 内侧油箱（外侧平衡）：

    | 油箱容量（较重的油箱） | 最大不平衡         |
    | :----------------------: | -------------------- |
    |           满           | 1500 kg（3306 lb） |
    |   4300 kg（9479 lb）   | 1600 kg（3527 lb） |
    |   2250 kg（4960 lb）   | 2250 kg（4960 lb） |
    | 小于2250 kg（4960 lb） | 无限制             |

    ###### 外侧油箱（内侧平衡）：

    | 最大不平衡 | 690 kg (1521 lb)^注^ |
    | ------------ | ----------------------- |

    注解：允许在外侧机翼油箱中达到最大不平衡（一满/一空），条件是：

    * 一侧的外侧和内侧机翼油箱燃油量等于另一侧的外侧和内侧机翼油箱燃油量，或
    * 在较轻的外侧油箱一侧，内侧油箱的燃油量大于另一侧内侧油箱的燃油量。内侧油箱之间的燃油量差值不得大于3000 kg（6613 lb）。


    #### 最小起飞油量：

    最小起飞油量：1500 kg（3307 lb）

    起飞时不可以出现与机翼油箱中燃油低油面相关的 ECAM (燃油 机翼油箱低油面等) 的警报。

    ---

    # 防冰排雨：


    # 结冰条件的定义：

    **地面时：**

    当在地面和起飞时 OAT 不超过 10 °C，且在机坪、滑行道或跑道上操作时，道面上的雪、积水或雪浆可能会被发动机吸入，或冻结在发动机、吊舱或发动机传感器探头上，在这种情况下视为存在结冰条件。

    **地面或空中：**

    当OAT（在地面或起飞后或TAT（飞行中）不超过10 °C，且存在任何形式的可见水汽（例如云、能见度为1sm（1600m）或以下的雾、雨、雪、雨夹雪或冰晶）时，就存在结冰条件。  


    当存在结冰条件或预计会出现结冰条件时，在所有的地面及飞行操作中都必须接通发动机防冰，在温度低于 -40 °C SAT 时的爬升和巡航期间除外。在结冰条件下下降前和下降期间，包括温度低于-40°CSAT时，必须接通发动机防冰。  <br />


    # 严重积冰的定义：

    当机身上累积的冰达到大约 5 mm (0.2 in) 厚或更厚时被视为严重积冰。


    # 薄白霜的定义：

    薄白霜通常是在寒冷无云的夜里在暴露的表面上均匀形成的白色结晶沉淀。<br />它很薄以致可辨别在其下面的表面特征（线条或标记）。  


    # 排雨剂：

    飞行机组应只在中到大雨的情况下才使用排雨剂。


    # **雨刷最大操作速度**：

    #### 雨刷使用限制：

    最大使用雨刷速度：230kt

    ---

    ---

    # 起落架：


    #### 刹车温度：

    起飞时的最大刹车温度：300℃


    #### 起落架速度限制：

    #### 起落架速度限制：

    * 起落架放出时的最大速度（VLE）：280kt/M 0.67
    * 可以放下起落架的最大速度（VLO~放下~）：250kt/M 0.60
    * 可以手上起落架的最大速度（VLO~收上~）：220kt/M 0.54


    #### 最大轮速：

    #### 最大轮速：

    195kt

    滑行速度：当飞机重量大于76000kg时，转弯速度不能超过20kt。


    #### 前轮转弯：

    使用空客批准的推车时，最大NWS角度：±85°


    #### 轮胎泄气或破损时的滑行：

    在轮胎泄气（未破损）的情况下脱离跑道或低速滑行，下列所有限制适用：

    * 如果每个起落架上最多一个轮胎泄气（考虑三个起落架），转弯时最大滑行速度：7kt
    * 如果同一主起落架（最多一个主起落架）上的两个轮胎泄气，最大滑行速度：3kt
    * 对于前轮转弯（ NWS）角：最大30°

    另外，如果怀疑轮胎破损，在脱离跑道或滑行之前飞行机组必须要求检查飞机。如果地面人员怀疑爆胎可能损坏起落架，则应采取维护措施。  <br />

    ---

    # 导航：

    #### IRS地面校准：

    IRS 的地面校准可能在北纬 82° 和南纬 82 ° 之间。


    #### 磁（MAG）基准：

    * 如果所有 ADIRU 有相同的磁差表：

      在NAV方式， IR 将不会提供有效的磁航向和磁航迹角：

      * 北纬 73 ° 以北，西经 90 ° 和西经 120 ° (磁极地区)之间，和
      * 北纬 82 ° 以北，和
      * 南纬 60 ° 以南。

      禁止在超过这些限制的纬度飞行。
    * 如果一部 ADIRU 有不同的磁差表：

      在 NAV 方式， IR 将不会提供有效的磁航向和磁航迹角：

      * 北纬 60 ° 以北，西经 30 ° 和西经 160 ° 之间，和<br />
      * 北纬 75 ° 以北，和<br />
      * 南纬 55 ° 以南。

      禁止在超过这些限制的纬度飞行。

    ---

    # 其他：

    其他数据限制请查阅各公司FCOM手册-限制。


    ---



[^2]: #### 自动着陆最大风条件：

    {{{col
    **NEO发动机：**

    **CEO发动机：**

    }}}

    {{{col
    * 顶风：30kt
    * 顺风：10kt
    * 侧风：20kt（15kt用于单发失效时的自动滑跑）

    * 顶风：30kt
    * 顺风：10kt
    * 侧风：20kt（无自动滑跑）/15kt（有自动滑跑）

    }}}

    ---
