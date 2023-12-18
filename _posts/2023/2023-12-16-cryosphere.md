---
layout: post
title: 2023-12-16-整理 Global Cryosphere 知识点
categories: [Learn]
description: 学习，课程
keywords: umanitoba
date: 2023-12-16
---

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            inlineMath: [['$','$']],
            displayMath: [ ['$$','$$'] ],
            processEscapes: true
            }
        });
    </script>
</head>

```
skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
```

# 总纲
1. 课程内容分成 4 个章节（unit）
    1. Snow   
积雪变化和融化的几个阶段和影响因素    
编程部分主要是学习 Matlab 的基本用法，实现了几个基本的模型

    2. Permafrost   
永冻土的性质和受到影响的因素，通过基本的能量（热能的）守恒和热传输公式 Fourier's Law 推导出永冻土的温度变化过程    
编程部分开始使用基本的 numerical model 来预测永冻土在地表温度变化的情况下的表现了

    3. Sea Ice    
海冰的类型，形成过程和影响因素   
编程部分主要使用 Matlab 进行一些基本的 netcdf 文件、栅格图像的掩膜和统计操作，感觉 Matlab 这方面不太好用

    4. Glacier(land ice)   
冰川和冰川地貌的各种类型和名字，通过质量守恒和流动方程 Glen's Flow Law 推导出冰川流动的过程

2. 课外阅读的书不考，先不管。   
给的课外书是 The Cryosphere (Shawn J. Marshall)和 The little book of geomorphology    

3. 要读一本极地探险相关的课外书，还要做个 ppt 给老师和同学介绍书的剧情。和考试无关，先不说这个。

4. 有两个章节（unit）交作业的时候要交论文的总结。

# 第一章 Snow
Total volume of a snow pack:   
Volume = Depth * Area = V_ice + V_water + V_air   
实际计算时不考虑空气的重量

## SWE Snow Water Equivalent
一堆雪融化成等面积的水之后的深度，单位是米（或者其他长度单位）    
SWE = $\frac{\rho_{snow}}{\rho_{water}}*d_{snow}$

## 积雪的变化
- Compaction 压缩，重结晶，整体变硬
- Vapor transport based on surface curvature
- Vaport transport based on gradients
    - Movement of vapor forms “depth hoar” 形成松散积雪颗粒
- Wind redistribution
    - snow grains mainly move by saltation 类似于沙砾的跃移
    - 干、冷、强风区域形成 wind slab，小颗粒密集堆积。 Ridges of wind slab 称为 **sastrugi** 
    - 山顶背风方向堆积，称为 **cornice**

## 积雪的融化
### Warming
- warm up to $0 \degree C$
- ice heat capacity $2102 J/(kg*K)$
- $Q_{cc} = c_i*\rho_{water} * SWE * (T_{melt}-T_{snow})$     
Qcc 是 snow 上升到 0C 单位面积所需的热量，单位是 $J/m^2$ 
### Ripening
- liquid water is trapped in the empty pores between snow grains
- $Q_n = SWE * \rho_{water} * L_f$ ，Qn单位是$J/m^2$   
$L_f$ 是 latent heat ，相变所需热量，
对于冰而言 $334,000 J/kg$

### Melt output
- once the snowpack is saturated with liquid water, snow melts and drains away, becoming runoff

## 表面能量平衡（Physical models）
net energy flux at the surface = 
短波下行 - 短波上行 + 长波下行 - 长波上行 + 地热flux + sensible&latent heat flux + 降水带来的sensible heat - runoff sensible heat 

sensible&latent heat flux: sensible heat from sublimation/deposition 

## 模型
positive degree day models  积温模型，是 **parameterization** 
- 又叫 “temperature index” models
- melt = b * PDD    
b, 经验参数，一般是 mmSWE / PDD   
PDD, positive degree day

## 作业
- Q1，注意质量守恒：$\rho_{water}*V_{water} = \rho_{snow}*V_{snow}$   
- Q2，注意 SWE 定义： $(\frac{\rho_{snow}}{\rho_{water}}) d_{snow}$
- Q3，忽略空气的密度和加热空气所需热量：$Q_{cc}(J*m^{-2})=c_{ice}(J*K^{-1}*kg^{-1})*SWE(m)*\rho_{snow}(kg*m^{-3})*(T_{melt}-T_{snowpack})$


# 第二章 Permafrost
## 定义：地下物质至少两年低于冰点
- 通常冻结时间远远长于两年
- 可能连续，可能不连续，可能零星分布（sporadic）
- 不是“melt”而是**thaw**
其他特性：
- 结冰层不透水，permafrost 以上的土壤往往水饱和

## 相关定义
- Active layer : 永冻土顶部会随季节变化的部分
- Taliks : unfrozen areas within permafrost 永冻土中没有冻住的区域

## 常用参数：
- heat capacity (c, $J/(kg*K)$)
- thermal conductivity (k, $J/(s*m*K)$)
- thermal diffusivity ($\kappa=\frac{k}{\rho c}$, $m^2/s$)

## Vertical temperature profiles
垂直温度分布的决定因素：
- 地表气温
- 地热通量
- 地的热动力特性
- （非常重要）**温度梯度引起的热传导**
- （不太重要）水流动带来的热流动

## 含碳量
$1200 * 10^{15} g C$，相比之下全球土壤含碳量$1700 * 10^{15} g C$，陆地光合作用/呼吸作用$110 * 10^{15} g C$左右，海洋光合作用/呼吸作用$54 * 10^{15} g C$左右，大气中总共也就$(591+279) * 10^{15}g C$    

$10^{15}这个数量级对应的字母是P$

北极地区，每平方米可达几十公斤有机碳

## 永冻土碳排放的正反馈机制
大气升温，永冻土融化，释放碳，进一步升温，融化更多永冻土

Rising temperatures thaw permafrost, release carbon, warm the atmosphere, thaw more permafrost

## Thermosyphons 热管
一头在地里，一头在空气中。典型热管内部液体在 -30 摄氏度沸腾
- 大地温度低于 -30 摄氏度，液体不沸腾，聚集在热管底部，和大气不发生热交换。
- 大地温度高于 -30 摄氏度，液体沸腾，蒸汽聚集在热管顶部
    - 大气低于 -30 摄氏度时，蒸汽向大气散热，变会液体，回到热管底部，往复循环
    - 大气高于 -30 摄氏度时，蒸汽在热管顶部保持气体状态，不回到底部和地面发生热交换

此技术用于公共建筑和输油管道等地方。

## 永冻土地貌
- **Thermokarst** ("thaw lakes") 热岩溶   
    - 上层永冻土解冻，支撑降低，地面沉降，往往有积水（下层永冻土不透水）
    - 季节性变化
    - 积水降低表面 albedo，吸收更多太阳辐射，导致更多解冻，形成正反馈
- **Solifluction** 固流
    - 斜坡上 active layer 和下面的 永冻土 会发生缓慢的相对滑动，或者说蠕移
    - 表面土壤沿着斜坡缓慢往下滑动
    - 往往发生在5度到20度的斜坡上，因为需要有斜坡（重力驱动），同时 active layer 排水不是很快
- **Ice-wedge polygons**  冰楔 多边形
    - 土壤结冰时体积收缩，两块土之间拉出裂隙 cracks
    - 夏季，缝隙里会积水，冬季，积水结冰膨胀，进一步扩大裂隙
    - Recracking year after year allows more ice to be added year after year, growing the frost wedges
    - **Low-center polygons**
        - Indicates active/growing polygons
        - As soil expands again in the summer, and as the ice wedge grows into the polygon in the winter, soil at the edges is pushed upwards, making ridges around the edge and leaving a low center    
        crack的扩张把土壤推向裂隙两侧，相比之下没有裂开的中央土块就显得比较低了
    - **High-centered polygons**
        - When erosion is dominant, it concentrates in the cracks
        - 裂隙被侵蚀降低，相比之下中央土块就显得高了
    - **Flat-centered polygons**
        - 处于裂隙侵蚀和土壤推高之间
- **Frost heave**
    - Caused by the formation of “segregation ice” – ice lenses separate from surrounding soil
    - 水移动到结冰区边缘并且结冰，形成一坨冰，扩张并把上面的土、道路等顶起来
- **Upfreezing or frost-jacking**
    - frost heave 把较大块的石头顶起来，留在地表，silt等落在下面。
- **Sorted circles**
    - 在 silt 区域更明显
    - 凸起，将大的石块 pebbles 带到地面，然后大石块向周围滚下斜坡，中间较细的 silt 向下沉（subduct），形成环形结构
- **Pingos**
    - 定义：Round hills cored with ice
    - 冰核，有点像 frost heave
    - 有 open-system 和 closed-system 两种
        - open-system 由 artesian （自流）pressure 提供水和压力，形成冰核并且往上挤。常见于 talik 区域的 active layer
        - closed-system 由 hydrostatic pressure 提供压力，常见于干涸的湖泊区域的 active layer。
- **Rock glaciers**
    - Resemble glaciers, move like glaciers, but they’re made more of rocky debris than of glacier ice
        - Might form as glaciers that get covered in rubble
        - Might form as rock piles with pores filled in by water percolation (渗滤)
        - Might form in more than one way

## 模型
有两个基础方程，一个是能量（内能）的平衡（没有机械能、化学能 等其他形式的能量参与），一个是热量传输通量和温度的关系，也就是 Fourier's Law。    
还有就是根据定义，Heat = Volume * density * heat capacity * temperature 

### 推导过程中的假设
以下变量不变
- density, $\rho$
- heat capacity, c
- volume
- thermal conductivity, k
- 

### Energy balance
对于任何一层土（active layer 或者 permafrost）而言，流入的能量 Q_in * A 减去流出的能量 Q_out * A 等于能量的变化量。这里 Q 是 flux，$J/m^2$，A 是面积 $m^2$。
$$\frac{\partial E}{\partial t}=Q_{in}(t)\ast A-Q_{out}(t)\ast A=Q_{net}(t)\ast A$$

**假设：density, heat capacity, and volume remain constant**

$$\frac{dT}{dt}=Q_{net}\left(t\right)\ast\frac{1}{\rho cd}$$
其中体积等于面积乘以厚度， V = A * d，d 是厚度

从 time-varying **energy conservation equation** 开始
$$\frac{\partial E}{\partial t}=\frac{\partial\left[\rho cTV\right]}{\partial t}=\frac{\partial\left[\rho cT\delta x\delta y\delta z\right]}{\partial t}$$
经过一系列推导，然后对各个方向取微分得到
$$-\frac{1}{\rho c}*[\frac{\partial Q_x}{\partial x}+\frac{\partial Q_y}{\partial y}+\frac{\partial Q_z}{\partial z}]=\frac{\delta T}{\delta t}$$
**这个通常被称为 heat equation**，也可以写作
$$\frac{\partial T}{\partial t}=-\frac{1}{\rho c}\Big[\frac{\partial Q_x}{\partial x}-\frac{\partial Q_y}{\partial y} – \frac{\partial Q_z}{\partial z}\Big]$$

(发现直接从word粘贴的有的偏微分符号是一个单独的字符  ∂  ，并不影响在latex里正确显示，至少在VSCode里能够正确转换为latex里的偏微分符号 $\partial$ )

### Fourier's Law
1 dimension:
$$Q=-k\frac{dT}{dz}$$
Higher temperature gradient & higher thermal conductivity -> higher heat flux. 

### Diffusion equation
Substitute Fourier's Law into the heat equation:
$$\frac{\partial T}{\partial t}=\kappa\frac{\partial^2T}{\partial x^2}+\ \kappa\frac{\partial^2T}{\partial y^2}+\kappa\frac{\partial^2T}{\partial z^2}$$
其中$\kappa=\frac{k}{\rho c}$，单位是 $m^2/s$

### 作业里用到的两种形式
#### 第一种，steady-state
Steady-state, $\partial T/\partial t=0$，温度不随时间变化     
    - x和y（水平）方向没有温度梯度     
    - 温度只随 z 变化，因此改用常微分符号

得到$0=\kappa\frac{d^2T}{dz^2}$    

地温 flux Qm 是固定的，在 thermal conductivity 不变的情况下，地温梯度不变
$$\frac{dT}{dz}=\frac{Q_m}{k}=c_1$$
这样，知道了地表的温度，就可以知道整个温度随深度变化的曲线。
温度随深度变化：
$$T=\frac{Q_m}{k}\ast z+c_2$$
z = 0 时即地表温度，所以地表温度等于 c2
$$T\left(z\right)=T_s+\frac{Q_m}{k}z$$

#### 第二种，地表温度在变化
解方程会比较麻烦， analytic solution -> numerical solution 转换成数值解

1. 根据地表温度变化，计算出 $\frac{\Delta T}{\Delta z}$，
2. 然后根据 Fourier's Law 和 $k$ 计算出每一个深度 z 的 flux $Q$ ，
3. 再根据每一个深度的 $Q$ 算出 $\frac{\Delta Q}{\Delta z}$，
4. 最后，根据 heat equation，结合 $\rho$ 和 $c$ 算出 $\frac{\Delta T}{\Delta t}$

并不需要直接用到 diffusion equation 


# 第三章 Sea Ice

