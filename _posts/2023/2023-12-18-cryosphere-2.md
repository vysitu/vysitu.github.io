---
layout: post
title: 2023-12-18-整理 Global Cryosphere 知识点 3-4章
categories: [Learn]
description: 学习，课程
keywords: umanitoba
date: 2023-12-18
---

费了半天劲，LaTeX 在 Github Page 却老是不能正常的渲染出来，真的是艹了

<head>
    <script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
    <script type="text/x-mathjax-config">
        MathJax.Hub.Config({
            tex2jax: {
            inlineMath: [['$','$']],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
            }
        });
    </script>
</head>

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
\\[\frac{dV}{dt}=\text{advection}+\text{divergence}+\text{thermodynamic growth}\\]    
\\[\frac{dV}{dt}=V(\nabla \cdot u )-u\nabla \cdot V+\text{thermodynamic growth}\\]
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

\\[h_i = h_f(\frac{\rho_w}{\rho_w-\rho_i})\\]

对于激光测高数据，再把雪算上，注意雪那一项上面是学的密度，freeboard那一项上面是水的密度。
[原网页链接](https://www.star.nesdis.noaa.gov/socd/lsa/SeaIce/background.php)

\\[h_i = h_f(\frac{\rho_w}{\rho_w-\rho_i})+h_s(\frac{\rho_s}{\rho_w-\rho_s})\\]



# 第四章 Glaciers and Ice Sheets
## 定义
- glacier: a mass of moving ice 
    - pile up, squeeze air out, turns into ice
    - drive: gravity
## 冰川类型和对应名词
### Polar vs Temperate glaciers
- Polar : **below** the freezing point at most depths
    - may the ice near the bed may reach the freezing (melting) point due to high pressure
- Temperate : **at** the freezing point throughout

### Cirque glaciers
- bowl-shaped depressions. 冰斗
### Valley glaciers
- cirque glaciers spill out, flow into spots between mountains
### Piedmont glaciers 山麓的冰川
- valley glaciers flows out into an open area, spread in all directions, forming a piedmont
### Tidewater glaciers
- 流到海里的都可以叫这个
### Ice caps and icefields
- merged glaciers, can overtop higher elevations on an island
    - multiple outlet glaciers
    - big enough to ignore topography
### Ice sheet
- ice cap big enough to cover a continent 
    - Individual fast-flowing areas that lead to the edges are called “outlet glaciers” or “ice streams”
### ice streams
- Fast-flowing outlets from ice sheets
- Can be bounded by topography or by shear zones between fast- flowing and slow-flowing ice (perhaps determined by bed material)
### Ice shelves
- The floating extensions of ice sheets
- Floating but still connected 
- *Tidewater glaciers* might also have floating “ice tongues,” which are more confined than ice shelves
### Nunataks 冰原岛峰
- exposed rock peaks protruding through an ice cap, icefield, or ice sheet
### Grounding lines
- Where ice goes from sitting on land to floating
    -  Where tidewater glaciers are not floating, the coastline is the same as the grounding line
- Many grounding “lines” are actually grounding “zones”
### Icebergs
- ice shelves 形成
- 形成过程称为 "Calve", "Calving"
### 冰川地理
- 格陵兰岛冰盖全部融化，海平面上升约7米；南极洲冰盖全部融化，海平面上升约57米
- 全球约有 200,000个冰川
- cryogenian 成冰纪
- snowball earth 雪球地球
    - ~ 650 Ma
    - runaway ice-albedo feedback 
- Antarctic, ~35 Ma
- Greenland, ~10 Ma, mostly covered by ~3 Ma
- Pleistocene Glaciation 更新世大冰期
    - ~ 2.6 Ma
    - glacials - interglacials 
    - glacial cycles
        - Milankovitch Cycles
        - Eccentricity: 100,000 years
        - Obliquity: 41,000 years
        - Precession: 23,000 years
    - Last Glacial Maximum LGM
        - Wisconsinan Glaciation; Last major glacial advance
        - Laurentide Ice Sheet: eastern North America
        - Cordilleran Ice Sheet: smaller ice sheet in Western North America
        - At its peak ~20,000 years ago, followed by retreat to current interglacial

## 冰川模型
### 质量守恒
- 降水&蒸发，流入&流出
- Mass gain: precipitation (mostly in the form of snow), avalanching, wind redistribution, hoar frost formation
- Mass loss: avalanching, wind redistribution, surface melt, internal and basal melt, subaqueous melt, calving
- Ablation zone & Accumulation zone
    - Accumulation zone: net gain (上游)
        - snow -> granular ice -> firn（粒雪） -> glacial ice
    - Ablation zone: net loss (下游)

### Accumulation
- 主要是雪
    - 有时候有冻雨，形成一层冰
    - Cirque glacier 有时候从附近悬崖的雪崩获得补给
- 特征
    - Crevasses 冰隙
        - Snow bridges: 一层盖住 crevasse 的雪，很危险
        - Bergschrunds: largecrevasseat the head of a glacier between stagnant and flowing ice/firn
        - Seracs: crevasses 交错切割形成 tower
    - ELA Equilibrium Line Altitude
        - Equilibrium Line: annual accumulation = annual ablation
        - 温暖干燥，ELA 升高；寒冷潮湿，ELA 降低
        - On mountain glaciers, the snow line is typically close to the ELA at the end of the summer
    - AAR Accumulation Area Ratio 
        - 冰川上游面积和冰川总面积之比 $\frac{\text{Accumulation Area}}{\text{Glacier Area}}$
        - steady-state 可以认为通常在 0.5-0.6 的样子

### Ablation
- Typically has blue glacial ice exposed
    - in some polar regions calving/basal melt dominate
    - Ice can only exist in the ablation zone due to glacier flow
- **Ablation Mechanisms**    
    surface melt, basal/subaqueous melt, ice discharge, calving
    - Surface melt
        - 气温高的地区是主要方式
            - 例如 temperate galciers
        - Measured through ablation stakes, snow pits and ice-penetrating radar, estimates of surface melt and albedo from satellite imagery...
        - 可以用类似雪的那个模型的 energy flux （例如 PDD）方法来建模
    - 大多数冰川都有 basal melt, 不过融化总量不大
    - Glaciers terminating in ice shelves or ice tongues melt from below
    - calving, ice discharge
        - As ocean-terminating glaciers accelerate, for a variety of reasons (which we’ll cover later) calving rates tend to increase, sometimes drastically
- **Ablation zone features**
    - Supraglacial lakes and streams 
        - *Surface meltwater streams* sometimes cut downwards and form canyons
    - Moulins
        - *Vertical meltwater conduits* that bring meltwater to the base of a glacier to some point englacially
    - Dirt cones
        - (Thick) sediments insulate the ice and slow melt
    - Cryoconite holes
        - (Thin) sediments lower albedo, warms and melts the ice
    
### 冰川的运动
- ultimate 的驱动力是重力
- 底部滑动+上部蠕动
- sliding， responsible for fast velocities and rapid discharges
    - Hard-bed sliding
        - Regelation 重凝结: Movement of ice past relatively small bumps due to melting and refreezing
        - upstream : high pressure -> pressure melting -> take up latent heat -> lower temperature
        - downstream : the opposite, low pressure -> regelation -> release heat -> high temperature -> heat conduct through bump to upstream
        - bump > ~1m, 下游高压区释放的热量难以有效通过bump传回上游，但也可以通过 Glen's Law ，高压引起高形变，加快流动
    - cavitation
    - soft-bed deformation
        - **till**: deposits of sediments of mixed size and angularity
        - 受到压力，冰碛物堆积形状改变
    - subglacial hydrologic evolution
        - melt season 初期，冰川底部的往往是 inefficient, distributed subglacial hydrologic system，导致 fast sliding
        - 后期，水从底部导出的效率提高，sliding 减慢
    - **Trimlines**
    - **Moraines**  
        - lateral
        - terminal
        - recessional

## 冰川地貌
### erosion process
- Very efficient – typically 1-1000 mm/year
- 效率取决于
    - Ice flow volume and temperature (amount of sliding and associated pressure)
    - Rock characteristics (rock type, jointing and other structures)
    - Associated processes (fluvial, mass movements from oversteepening)
    - Supply of sediments to the glacier bed

#### hard-bed sliding

#### abrasion
- 冰川带着碎石刮擦底部，产生刮擦痕
- 碎石太多反而减少刮擦

#### glacial flour
- silt-sized pulverized (粉碎的) rock
- a result of glacial abrasion
- color rivers and lakes

#### sliding with cavitation （空化现象？）
- 上游压力大，下游侧面压力突然减小，bedrock 容易产生裂隙

### Roche moutonnée
- 上游坡度平缓，有 striations（条纹）
- 下游坡度较陡，基岩破碎

### U-shaped valley U型谷/U形谷
- 