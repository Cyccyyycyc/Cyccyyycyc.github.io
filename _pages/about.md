---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

大家好！我是 **龙雨洁**，目前是本科三年级，就读于[武汉大学国家网络安全学院](https://cse.whu.edu.cn/)信息安全专业。

我对人工智能充满热情，自入学以来，积极参与各类科研项目和学术竞赛，曾获得阮立平奖学金和多项校内外奖项。在科研方面，我参与并主导了多个项目，包括但不限于**时序点过程**、**计算机视觉**、**人工智能安全**、**序列建模**等领域。

# 🎓 Education Background

- **排名：** GPA排名：**4/146 (2.7%)**、加权平均分排名：**3/146 (2.1%)**  
- **成绩均分：** GPA：3.94/4.0、加权平均分：92.78/100  
- **语言能力：** 以良好成绩通过 CET4(596)、CET6(553)；具备良好的英语文献阅读和写作能力  
- **核心课程：** 高等数学 (95,96)、线性代数 (95)、概率论与数理统计 (97)、数据结构 (96,96)、离散数学 (94)、信息安全数学基础 (95)、编译原理 (97)、计算机网络 (93)、密码学 (97,93)、安全创客实践 (98)  
- **编程能力：** 编程常用语言为 C++、Python，熟悉算法与数据结构，抽象能力强，代码风格良好；熟练掌握 PyTorch、Numpy、Pandas、OpenCV，熟悉各类深度学习模型及其编程实现；具备优秀的编程、建模、理论推导能力，多次获数学建模/数据挖掘 (kaggle) 类比赛奖项  
- **开发工具：** VS Code，PyCharm，Jupyter Notebook，LaTeX (Overleaf)，Git  
- **在校荣誉：** 曾获武汉大学阮立平奖学金 (￥6000，全院共 2 人)、武汉大学三好学生 (10%)、武汉大学社会活动积极分子及多项竞赛奖金，在校累计获奖逾 35000 元  

# 🔥 News

# 📈 Research Experience-Temporal Point Process

## **💡 BregmanADMM-用于时序点过程中事件分支推断的即插即用模块**  

- **时间：** 2024.2 - 2024.8  
- **领域：** **时序点过程**，**最优传输**  
- **角色：** 第三作者  
- **研究背景：**  
  1. **时序点过程 (TPPs)** 是对连续时间域上离散事件点进行建模的强大工具，已被广泛用于地震预测、金融分析、推荐系统等多个领域。
  2. 对于事件序列，通常存在一个分支过程来捕获隐藏在序列中的事件级触发模式，这个分支过程提供了对事件之间因果关系的洞察，帮助我们识别触发后续事件级联的关键事件，这对于揭示事件产生和信息扩散的潜在机制至关重要。
  3. 推断事件分支有着重要意义，但其同样十分具有挑战性，因为事件分支是在实践中无法观察到的潜在变量。
  4. 现有方法如经典TPP（例如Hawkes Process）的EM框架或神经TPP中的注意力图，往往存在过平滑问题，导致非结构化的事件分支。
  5. 目前亟需一种简单但有效的解决方案来准确推断各种TPP模型的结构增强事件分支。
- **我们的方法：**  
  1. **引入一个新的即插即用模块：** 基于Bregman交替方向乘子法(BADMM)的模块，用于在TPPs的最大似然估计框架中推断与事件序列相关的事件分支。
  2. **BADMM模块的关键特性：** 在行归一化的下三角矩阵上施加低秩和稀疏结构，使得在经典TPP的EM算法中能得出结构化的责任矩阵，同时也有助于神经TPP的注意力图生成。
  3. **事件分支的有效表征：** 结构化的责任矩阵和注意力图可以有效表征事件分支，提供关于事件产生和信息扩散机制的有价值见解。
- **项目成果：**  
  * 在合成数据和现实数据上的实验表明，将我们的BADMM模块插入到现有的TPP模型和学习范式中可以稳定提高模型的性能，并产出可解释的事件分支。
  * 论文已投稿至**AAAI 2025**（第三作者，第一本科生作者）。

---

## **💡 ClusterTPP-使用可扩展非参数正则化学习结构增强时序点过程**  

- **时间：** 2023.11 - 2024.8  
- **领域：** **时序点过程**，**聚类**  
- **角色：** 第五作者  
- **研究背景：**  
  1. **时序点过程 (TPPs)** 是对连续时间域上离散事件点进行建模的强大工具，广泛应用于地震预测、金融分析、推荐系统等多个领域。
  2. 事件序列通常包含一个分支过程来捕捉事件级触发模式，提供事件间因果关系的洞察，识别关键事件，这对于揭示事件产生和信息扩散机制至关重要。
  3. 推断事件分支具有挑战性，因为它们是无法直接观察到的潜在变量。传统方法往往过于平滑，导致事件分支非结构化。
  4. 亟需一种简单但有效的解决方案，准确推断各种TPP模型的结构增强事件分支。
- **我们的方法：**  
  1. **引入一个新的即插即用模块：** 基于Bregman交替方向乘子法(BADMM)的模块，用于在TPPs的最大似然估计框架中推断与事件序列相关的事件分支。
  2. **增强神经TPP模型：** BADMM模块有助于导出低秩和稀疏的注意力图，能够有效地表征事件分支。
  3. **实验验证：** 在合成数据和现实数据上的结果表明，插入BADMM模块能够提升现有TPP模型的性能，提供事件生成和信息扩散机制的宝贵见解。
- **项目成果：**  
  * 研究论文已投稿至**AAAI 2025**（第五作者，第二本科生作者）。

---

## **💡 用Granger因果一致性正则化学习多元时序点过程**  

- **时间：** 2024.1 - 2024.5  
- **领域：** **时序点过程**，**Granger因果**  
- **角色：** 共同第一作者  
- **研究背景：**  
  1. **时序点过程 (TPPs)** 是对连续时间域上离散事件点进行建模的强大工具，广泛应用于地震预测、金融分析、推荐系统等多个领域。
  2. 事件序列通常包含一个分支过程来捕捉事件级触发模式，提供事件间因果关系的洞察，识别关键事件，这对于揭示事件产生和信息扩散机制至关重要。
  3. 推断事件分支具有挑战性，因为它们是无法直接观察到的潜在变量。现有方法要么过于平滑，要么无法生成结构化的事件分支。
- **我们的方法：**  
  1. **引入Granger因果一致性正则化：** 使用Bregman交替方向乘子法(BADMM)模块来推断TPP模型中的事件分支。
  2. **TPP模型正则化：** BADMM模块在行归一化的下三角矩阵上施加低秩和稀疏结构，增强推断的责任矩阵和注意力图的结构，这些矩阵和图有效表征了事件分支。
- **项目进度：**  
  * 已完成基本实验，目前正在进行分析性实验和论文写作，预计投稿至**WWW 2025**（共同第一作者）。

# 📝 Research Experience-Other

## **💡HaMonitorSentry - 高层建筑智能监测系统** <sub> &nbsp;&nbsp;[[项目主页]](https://mumuyeye.github.io/HaMonitorSentry/README.html) | [[项目代码]](https://github.com/mumuyeye/HaMonitorSentry) </sub>

- **时间：** 2023.1 - 2024.5
- **领域：** **计算机视觉**，**Geo AI**
- **角色：** 团队(负责人)
- **针对痛点**：
  1. **高层建筑监测局限性**：当前的监测系统主要聚焦于高空抛物，应用范围有限且性能不理想。常见问题包括实时性不足以及较高的漏检和错检率。
  2. **复杂场景下的挑战**：现有的运动目标检测与跟踪技术在复杂场景下尚未成熟，小目标快速检测尤其困难。
  3. **天气因素的影响**：监测效果受天气因素影响较大，这增加了对算法进行进一步优化的迫切需求。
- **我们的方法**：
  1. **引入轻量化的语义分割网络和知识蒸馏技术**：使用这些技术精确识别视频中的建筑物区域，定位可能的抛物区域，有效减少环境干扰。
  2. **采用背景差分法和帧差法**：根据环境变化和亮度条件的不同，这些方法提高了目标检测的速度和准确度。
  3. **结合2D和3D网络，利用自注意力机制**：这种结合方式融合时空信息，显著提高高层动作识别的精度。
  4. **构建专门的高层场景危险动作识别数据集并进行网络微调**：通过这种方法，能够更精确地识别和响应高层建筑中的潜在危险动作。

* **项目成果**：
  * 作为主力队员带队参加第17届中国大学生计算机设计大赛，并**以中南地区赛人工智能应用组第一名（1/314）的成绩进入全国总决赛**。

---

## **💡 FaceShield-基于可逆神经网络的 DeepFake 溯源追踪系统**  

- **时间：** 2023.11 ~ 2024.6  
- **领域：** 人工智能安全  
- **角色：** 团队 (主力成员)  
- **研究背景：**  
  1. 随着人工智能技术的发展，DeepFake 技术的进步使得虚假人脸生成和视频篡改变得更加普遍，这给社会带来了严重的信息安全和信任问题。尽管现有的 DeepFake 检测技术不断迭代，但在鲁棒性和溯源追踪能力方面仍存在不足。
- **我们的方法：**  
  1. 利用可逆神经网络（INN）进行视频隐写与提取，设计了一种 DeepFake 溯源追踪系统。通过将人脸信息隐藏在视频的非人脸区域，当视频遭受 DeepFake 攻击时，可以从非人脸区域提取出原始人脸信息，实现溯源追踪。
  2. 具体而言，系统首先提取视频的人脸掩码信息，作为 INN 网络的条件输入，确保信息分布在非人脸区域。同时，为了增强 INN 的非线性表示能力，引入了一个关系模块捕捉视频间的相互关系。在 INN 隐写过程中，添加可逆 Haar 小波变换以扩大网络的感受野。
- **项目成果：**  
  * 实验结果显示，该方法在鲁棒性和可溯源性上优于当前方法。相关工作已进入 2024 年全国大学生信息安全竞赛国赛阶段。

---

## **💡 Google-American Sign Language Fingerspelling Recognition**  

- **时间：** 2023.5 ~ 2023.8  
- **领域：** 序列建模  
- **角色：** 团队 (主力成员)  
- **研究背景：**  
  1. 虽然语音识别等人工智能技术正在逐渐改变世界，但全球7000万聋哑人士和15亿听障患者难以使用这些技术。现有的手语识别 AI 相比语音转文本技术有较大差距。本次比赛旨在开发一种手语识别技术，帮助聋哑人和听障用户更顺畅地与听力正常人士交流。
- **我们的方法：**  
  1. 基于单个 encoder-decoder 架构：encoder 是 Squeezeformer 的改进版本，特征提取部分适用于 mediapipe 信号处理，decoder 是双层 transformer。
  2. 预测置信度分数来识别损坏的示例，辅助后处理。
  3. 使用多种高效数据增强技术对模型进行正则化，包括 CutMix、FingerDropout、TimeStretch 和 DecoderInput Masking。
- **项目成果：**  
  * 最终取得 0.662 的 Final Score，在 1315 支参赛队伍中排名 118，获得铜牌。

---

## **💡 数据解读乡村发展**  

- **时间：** 2024.3 ~ 2024.4  
- **领域：** 数据分析、数据挖掘  
- **角色：** 团队 (主力成员)  
- **研究背景：**  
  1. 乡村发展是我国的重要基础，面临全球化和城市化带来的挑战和机遇。通过多维度、跨学科的数据分析，可以为乡村振兴提供科学依据和决策支持。
- **我们的作品：**  
  1. 通过数据分析和挖掘，研究了人口、粮食、消费等对乡村发展的影响，并为乡村振兴提出建议。
  2. 基于面板回归分析了各种农作物产量对粮食安全的影响；基于文本挖掘研究了农民工的社会现状并给出针对性建议；基于聚类分析探讨了中国饮食结构变化。
- **项目成果：**  
  * 参加第 17 届中国大学生计算机设计大赛，获中南地区赛二等奖。

---

## **💡 从“堆盒子”到动态规划**  

- **时间：** 2022.1 ~ 2022.5  
- **领域：** 算法教学、算法可视化  
- **角色：** 团队 (主力成员)  
- **研究背景：**  
  1. 算法的抽象性往往使学习者难以理解，进行算法可视化可以帮助学习者更直观地理解算法逻辑。
- **我们的作品：**  
  1. 使用基于 Python 的数学动画制作引擎 Manim 制作了算法可视化视频，编写了 3000 余行代码，经过后期大量调整和优化，最终完成作品。
- **项目成果：**  
  * 视频发布在 Manim 爱好者交流社区，得到了广泛好评，并在多所高中和高校中进行应用推广，收到了良好的反馈。

# 🏆 Competition Awards

- **中国大学生计算机设计大赛：全国二等奖** *国家级* 2024 &nbsp;&nbsp;[[证明]](..\docs\全国二等奖.pdf)  
- **中国大学生计算机设计大赛：赛区第一名/并晋级 8 月的全国总决赛** *国家级* 2024 &nbsp;&nbsp;[[证明]](..\docs\赛区第一名.pdf)  
- **全国大学生数学竞赛：一等奖** *国家级* 2023 &nbsp;&nbsp;[[证明]](..\docs\全国大学生数学竞赛一等奖.pdf)  
- **Kaggle-American Sign Language Fingerspelling Recognition：铜牌** *国家级* 2023 &nbsp;&nbsp;[[证明]](..\docs\Kaggle铜牌.pdf)  
- **中国大学生计算机设计大赛 (中南地区赛)：一等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\中南地区赛一等奖.pdf)  
- **中国大学生计算机设计大赛 (中南地区赛)：二等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\中南地区赛二等奖.pdf)  
- **湖北省大学生数学竞赛：一等奖** *省部级* 2023 &nbsp;&nbsp;[[证明]](..\docs\湖北省大学生数学竞赛一等奖.pdf)  
- **“华中杯” 大学生数学建模挑战赛：二等奖** *省部级* 2023 &nbsp;&nbsp;[[证明]](..\docs\华中杯二等奖.pdf)  
- **“蓝桥杯”软件赛道 C++ 程序设计赛 (湖北赛区)：三等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\蓝桥杯三等奖.pdf)     

# 🥇 Scholarships and Honors

- *2023.10* **武汉大学阮立平奖学金** (￥6000，全院共2人) *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\ruanliping.jpg)
- *2023.10* **武汉大学三好学生** (获奖率：全校10%) *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\sanhaoxuesheng.jpg)
- *2023.10* **武汉大学社会活动积极分子** *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\shehuohuodong.jpg)
# 📖 Educations

- **2021.9 - 至今**，本科生，武汉大学国家网络安全学院，专业：信息安全