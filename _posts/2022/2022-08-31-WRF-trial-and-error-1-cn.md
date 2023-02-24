---
layout: post
title: WRF debug 笔记 1 CN
categories: [Learn, WRF]
description: WRF debug notes 1
keywords: WRF
date: 2022-08-31
---

```
ERROR: For nest 2, (e_we-s_we+1) must be one greater than 
       an integer multiple of the parent_grid_ratio of 3.
```
geogrid.exe遇到类似上面的错误，修改对应的e_we或者e_sn，
让其不要是parent_grid_ratio的整数倍而是要整数倍+1。例如放大倍数是3，那么就是3x+1

-----

```
WPS/ungrib.exe报错：ECMWF data ERROR: Grib2 file or date problem, stopping in edition_num.
```
去namelist.wps下面添加grib1文件长度     
		ec_rec_len = 26214508

-----

```
WPS/metgrid.exe报错 Error in ext_pkg_write_field 
```
这个应该单纯就是输入文件损坏之类的问题，检查一下每个文件的体积，以及是不是每个grib2文件都能打开（可以用gdalinfo检查）

-----

```
WRF运行wrf.exe出现：segmentation fault - invalid memory reference
```
打开主domain的边缘平滑功能:  smooth_cg_topo = .true.     
打开vertical sound waves的偏移:  epssm = 0.2，分辨率提高的话要设置得更大

-----

```
program wrf: error opening wrfinput_d01 for reading ierr=       -1021
```
这个问题是wrfinput_d01文件创建失败，是real.exe报错。出现这个问题的时候考虑检查num_metgrid_levels是否根据要求进行了设置。