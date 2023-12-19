---
layout: post
title: 2023-12-18-整理 Global Cryosphere 知识点 3-4章
categories: [Learn]
description: 学习，课程
keywords: umanitoba
date: 2023-12-18
---

费了半天劲，LaTeX 在 Github Page 却老是不能正常的渲染出来，真的是艹了

# 第三章 Sea Ice
## 海冰
**直接由海水形成的冰**
- 不包括 icebergs（陆冰崩解形成）

## 相关定义
- Sea-ice **concentration**: The percentage of ocean area that is covered by sea ice，区域内海冰覆盖面积百分比，一般是 0-1 的一个值
- Sea-ice **extent**: The total ocean area that is considered to be covered by sea ice 一般是 >=0.15 的 concentration
- Sea-ice **area**: Total area covered by sea ice, taking into account the percent coverage in each pixel
- First-year ice FYI: sea ice formed in the **CURRENT** season
- Multi-year ice MYI: sea ice that survided >=1 melt season
    - Most sea ice is first-year ice, particularly in the Antarctic
    - Multi-year ice tends to be **thicker** and **fresher** than first-year ice    
    多年冰更厚，含盐量更低
        - melt season -> intergranular veins -> permeable -> water and brine transport -> brine rejection 含盐量降低

## 海冰生长过程
- 气温降低，水面散热，水面结冰
- 大气温度变化是主要的结冰和融化的动力
- speed of ice growth is limited by the (low) rate of heat conduction through the ice layer
    - typical limit is 1-2m per year
    - plow the snow so the ice keeps losing heat to the atmosphere, keeps ice growing
- salt - lower freezing point
    - adding freshwater promotes sea ice formation 
    - sea ice **always** has some salt in it
- 根据[海冰的中文维基百科](https://zh.wikipedia.org/wiki/%E6%B5%B7%E5%86%B0)，海水盐度大于24.69（一般都大于这个数）时，表层海水先达到结冰点，继续降温密度还会增加。在这种情况下，表层海水到达结冰点就会比底下的水密度更大，会下沉，把下面温度较高的水翻上来。所以这种情况下结冰比较慢。海冰不仅仅可以在表面形成，也可以在其他深度甚至还低形成。

### Stages
frazil -> grease -> thin coherent layer -> young ice
- Frazil ice: Disconnected crystals and needles
- Grease ice: A bunch of frazil ice stuck together
- thin corehent layer 
    - calm: nilas
    - waves: pancakes
congelation ice (凝结冰)
- melt (melt water)
    - initial melt water gets trapped at the surface, lower the albedo     
    **seasonal ice-albedo feedback**
    - eventually drain through cracks and channels

## Movement
- Advection: mainly the **wind**. ~2% of wind speed. Also ocean currents.
- Ice **floes** 浮冰，裂开成一块块的海冰
    - 两个 floe 相对远离形成 leads，再远离形成 polynyas 小型开放水域。两个 floe 相向而行形成 pressure ridges
    - **Leads**: Narrow lines of open water between ice floes
    - **Pressure ridges**: Crumpled edges of ice floes where they are driven into each other
        - 向上堆起来的叫 sail，向下沉入水下的叫 keel
    - **Polynyas**: Larger open-water areas between floes or between sea ice and land
        - latent heat polynyas：风吹的（实际上可能仍然具备形成新海冰的条件）
        - sensible heat polynyas: 热水上涌引起的
        
## Land-fast ice 固定冰
- 又叫 fast ice
- 连接到 shoreline 或者 seafloor
- many polynyas between fast ice and mobile ice floes 

## 一个区域的海冰受到三个因素的影响
$$\frac{dV}{dt}=\text{advection}+\text{divergence}+\text{thermodynamic growth}$$    
$$\frac{dV}{dt}=V(\nabla \cdot u )-u\nabla \cdot V+\text{thermodynamic growth}$$
- advection, v = 0, u = constant
- divergence, v = 0 , H = constant

## 全球海冰趋势
- Arctic：sea ice extent 持续降低，厚度降低，多年冰减少，九月最明显，2012年创纪录
- Antarctic：sea ice increase, larger variability over time 可能原因有 1. ice sheet melt, 更多表层淡水输入 2. wind patterns, driving sea ice away from the continent 风吹的。 最近波动大可能是风向变了

## Arctic amplification 
- ice-albedo feedback，有 seasonal and interannual 的影响
- other variables 

## Bering Strait, Chukchi Sea（Alex Crawford）
- Retreat date (RD): 区域平均 sea ice concentration 第一次低于 30% 的那天。平均值是 7月17日
- Advance Date (AD): 在抵达了最低 concentration 之后（回升过程中），区域平均 sea ice concentration 第一次超过 30% 的那天。平均值是 10月18日

### Bering Strait
- Water flow: Pacific -> Arctic -> Atlantic
- Local wind blows **against** the current

### 能量交换
- More energy -> faster melting -> earlier retreat
- More Northerly winds -> ice pushed South -> later retreat
- More Southerly winds -> ice pushed North -> earlier retreat

## 海冰遥感
- Passive microwave 
    - 弱点：分辨率低（25km * 25km）
    - 常见 Sensor 
        - SSM/I
        - AMSR-E
    - 地面温度也高，emissivity 越高，发射能量越强。 $E = \sigma \epsilon T^4$ 其中 $\sigma=5.67*10^{-8}\frac{W}{m^2K^4}$
    - 难点
        - mixed picels
        - surface effects (e.g. liquid water)
        - (weak) energy interact with atmosphere
- ASCAT (scatterometer)
- MODIS (VIS/IR)
- ICESat (laser altimeter)
- Cryosat (radar altimeter，可以穿透表层的雪)

Altimeter 测量海冰只能测量 freeboard，也就是海冰高出水面的部分的高度。
根据浮力的原理，$V_{ice}*\rho_{ice}=V_{water}*\rho_{water}$，而 $V_{ice}*\rho_{ice}=V_{water}*\rho_{water}=V_{ice}*\rho_{water}-V_{ice}*\rho_{water}$

$$h_i = h_f(\frac{\rho_w}{\rho_w-\rho_i})$$

对于激光测高数据，再把雪算上，注意雪那一项上面是学的密度，freeboard那一项上面是水的密度。
[原网页链接](https://www.star.nesdis.noaa.gov/socd/lsa/SeaIce/background.php)

$$h_i = h_f(\frac{\rho_w}{\rho_w-\rho_i})+h_s(\frac{\rho_s}{\rho_w-\rho_s})$$

