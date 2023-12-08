# Discovering IoT Physical Channel Vulnerabilities
> [!info] Bibliography
> [1]  Muslum Ozgur Ozmen, Xuansong Li, Andrew Chu, Z. Berkay Celik, Bardh Hoxha, and Xiangyu Zhang, “Discovering IoT Physical Channel Vulnerabilities,” in _Proceedings of the 2022 ACM SIGSAC Conference on Computer and Communications Security_, in CCS ’22. New York, NY, USA: Association for Computing Machinery, Nov. 2022, pp. 2415–2428. doi: [10.1145/3548606.3560644](https://doi.org/10.1145/3548606.3560644).

## Information

| Key          |                                   Value                                   |
| :----------- | :-----------------------------------------------------------------------: |
| Date         |                                      2022-11  |
| Author       |                         Muslum Ozgur Ozmen, Xuansong Li, Andrew Chu, Z. Berkay Celik, Bardh Hoxha, Xiangyu Zhang                          |
| Contributors |                                                           |
| Tags         |                           #/unread, #physical-channel-vulnerabilities, #security-analysis, #smart-homes, #zotero                           |
| Journal      |                            #              |
| DOI          |                            [10.1145/3548606.3560644](https://dl.acm.org/doi/10.1145/3548606.3560644)                             |
| Extra        |                                              |
| Type         |                            conferencePaper                           |
| Publisher    |                               Association for Computing Machinery                               |
| Others       |     ACM Digital Library         |
| Zotero Link  |                             [Full Text PDF](zotero://select/library/items/W9IDEFHX)                             |

## Abstract
> [!abstract]
> Smart homes contain diverse sensors and actuators controlled by IoT apps that provide custom automation. Prior works showed that an adversary could exploit physical interaction vulnerabilities among apps and put the users and environment at risk, e.g., to break into a house, an adversary turns on the heater to trigger an app that opens windows when the temperature exceeds a threshold. Currently, the safe behavior of physical interactions relies on either app code analysis or dynamic analysis of device states with manually derived policies by developers. However, existing works fail to achieve sufficient breadth and fidelity to translate the app code into their physical behavior or provide incomplete security policies, causing poor accuracy and false alarms. In this paper, we introduce a new approach, IoTSeer, which efficiently combines app code analysis and dynamic analysis with new security policies to discover physical interaction vulnerabilities. IoTSeer works by first translating sensor events and actuator commands of each app into a physical execution model (PeM) and unifying PeMs to express composite physical execution of apps (CPeM). CPeM allows us to deploy IoTSeer in different smart homes by defining its execution parameters with minimal data collection. IoTSeer supports new security policies with intended/unintended physical channel labels. It then efficiently checks them on the CPeM via falsification, which addresses the undecidability of verification due to the continuous and discrete behavior of IoT devices. We evaluate IoTSeer in an actual house with 14 actuators, six sensors, and 39 apps. IoTSeer discovers 16 unique policy violations, whereas prior works identify only 2 out of 16 with 18 falsely flagged violations. IoTSeer only requires 30 mins of data collection for each actuator to set the CPeM parameters and is adaptive to newly added, removed, and relocated devices.

## Annotations
> [!warning]
> ANYTHING OUT OF %begin%...%end% BLOCK WILL BE CLEARED WHEN UPDATE

%% begin annotations %%

***Imported on 2023-12-08 09:56***
***
> [!Highlight]
> <mark style="background: #2ea8e5">Prior works showed that an adversary could exploit physical interaction vulnerabilities among apps and put the users and environment </mark> [(p.1)](zotero://open-pdf/library/items/W9IDEFHX?page=1&annotation=JR95G3IK)

🔤先前的研究表明，对手可以利用应用程序之间的物理交互漏洞，并将用户和环境置于危险之中。🔤
> [!Highlight]
> <mark style="background: #2ea8e5">which efficiently combines app code analysis and dynamic analysis with new security policies to discover physical interaction vulnerabilities. </mark> [(p.1)](zotero://open-pdf/library/items/W9IDEFHX?page=1&annotation=2KRFD2W5)

🔤程序代码分析和动态分析与新的安全策略有效地结合起来🔤
> [!Highlight]
> <mark style="background: #2ea8e5">There are two fundamental sources of app interactions, software and physical. </mark> [(p.1)](zotero://open-pdf/library/items/W9IDEFHX?page=1&annotation=7TD2LXPW)

🔤应用程序交互有两个基本来源：软件交互和物理交互。🔤
> [!Highlight]
> <mark style="background: #2ea8e5">These apps interact through a common light device ( smoke −−−−−→ light-on light-on −−−−−−→ door-locked) and makes residents get trapped during a fire. </mark> [(p.1)](zotero://open-pdf/library/items/W9IDEFHX?page=1&annotation=8UN6N7IL)

🔤这些应用程序通过一个常见的灯光设备进行交互（烟雾------→灯亮灯亮------→门锁），并使居民在火灾中被困。🔤
> [!Highlight]
> <mark style="background: #2ea8e5">Physical interactions </mark> [(p.1)](zotero://open-pdf/library/items/W9IDEFHX?page=1&annotation=BLLMJNP5)

🔤身体互动🔤
> [!Highlight]
> <mark style="background: #2ea8e5">These apps interact through the temperature channel (heater-on∼∼∼∼ temp. window-open). </mark> [(p.1)](zotero://open-pdf/library/items/W9IDEFHX?page=1&annotation=JH5FM544)

🔤这些应用程序通过温度通道进行交互（加热器打开∼∼∼∼温度窗口打开）。🔤
> [!Image]
> ![](assets/Discovering%20IoT%20Physical%20Channel%20Vulnerabilities/image-2-x309-y594.png)  [(p.2)](zotero://open-pdf/library/items/W9IDEFHX?page=2&annotation=PRMRYF5H)

物联通道的是否有意而为之，判断是机器人做的 还是真人做的（标签
），根据这个漏洞 提出
> [!Image]
> ![](assets/Discovering%20IoT%20Physical%20Channel%20Vulnerabilities/image-2-x320-y300.png)  [(p.2)](zotero://open-pdf/library/items/W9IDEFHX?page=2&annotation=6TJ83X9Y)

方法：
1.驱动命令和传感器事件转换为物理执行模型，以定义其物理行为
2.新颖的复合物理执行模型架构
3.物理通道策略验证：我们使用有意/无意的物理通道标签开发新的安全策略
> [!note]
> <span style="color: #2ea8e5">三种设计方法：<br />C1：正确的物理交互<br />C2：意外的物理交互<br />C3：运行时问题<br />C4：设备的放置灵敏性 </span> [(p.3)](zotero://open-pdf/library/items/W9IDEFHX?page=3&annotation=R6DSHK45)

> [!Image]
> ![](assets/Discovering%20IoT%20Physical%20Channel%20Vulnerabilities/image-4-x51-y619.png)  [(p.4)](zotero://open-pdf/library/items/W9IDEFHX?page=4&annotation=2UKBTZWP)

IOTSEER 架构
> [!note]
> <span style="color: #2ea8e5">这篇论文探讨了智能家居中存在的物联网（IoT）物理通道漏洞。文章指出，先前的研究已经显示，对手可以利用应用程序之间的物理交互漏洞，从而对用户和环境造成风险，例如，对手可以打开加热器以触发打开窗户的应用程序，从而进入房屋。当前，对物理交互的安全行为依赖于应用程序代码分析或动态分析设备状态，并由开发人员手动制定策略。然而，现有的工作未能足够广泛地将应用程序代码转化为其物理行为，或提供不完整的安全策略，导致准确性不高且存在虚警。<br />为了解决这一问题，论文介绍了一种名为IoTSeer的新方法，它通过有效地将应用程序代码分析和动态分析与新的安全策略相结合，以发现物理交互漏洞。IoTSeer首先将每个应用程序的传感器事件和执行命令转化为物理执行模型（PeM），并将这些PeM统一为表达应用程序的综合物理执行（CPeM）。CPeM允许将IoTSeer部署在不同的智能家居中，并通过最少的数据收集定义其执行参数[1]。IoTSeer支持新的安全策略，并通过验证来检查这些策略，以解决由于物联网设备的连续和离散行为所导致的不可判定性[1]。文章还指出，在实际的拥有14个执行器、6个传感器和39个应用程序的智能家居中，IoTSeer发现了16个唯一的策略违规行为，而先前的工作只发现了其中的2个，且存在18个虚警的情况。最后，IoTSeer只需每个执行器进行30分钟的数据收集就能够设定CPeM的参数，并且对新增、移除和重新安放的设备也有适应性。<br />因此，这篇论文介绍了IoTSeer系统，重点讨论了它的设计原理、工作方式以及在实际环境中的性能评估结果，以及其在发现物理通道漏洞方面的应用前景。 </span> [(p.13)](zotero://open-pdf/library/items/W9IDEFHX?page=13&annotation=7S48XTK8)


***
%% end annotations %%

## Zotero-Notes




## Notes
%% begin Obsidian-Notes %%



%% end Obsidian-Notes %%
> [!danger]
> NEVER MODIFY ANYTHING BELOW

%% Import Date: 2023-12-08T09:56:58.707+08:00 %%
