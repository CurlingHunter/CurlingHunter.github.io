---
layout: post
title:  "An AI-Based Curling Game System for Winter Olympics"
date:   2022-10-22 15:35:41 +0800
categories: jekyll update
---

## **Introduction**

A multi-target multi-camera curling tracking system, termed [CurlingHunter](https://spj.sciencemag.org/journals/research/2022/9805054/), is proposed, which can be applied in actual curling games in real time to assist athletes to compete, enhance the interest of the game, etc. Due to the regulations of curling game, no auxiliary equipment can be added to the curling stones, hence only non-contact measurement methods such as machine vision can be used in CurlingHunter. CurlingHunter has solved these problems: 
 -  The problem of accurately capturing relatively small curling stones through long-sighted distance (> 20 m) in the super-large space environment with many occlusions; 
 -  The problem of lens distortion correction in large scenes without interfering with the ice tracks; 
 -  The problem of accuracy of curling stone's visual positioning on the ice sheet; 
 -  The problem of occlusions which would interfere with tracking and accuracy, while curling stone is easily blocked by athletes wiping ice, other peoples or objects during games; 
 -  The problem of tracking and re-identifying multiple curling stones due to that all curling stones have identical appearance features; 
 -  The problem of runtime in sing-camera system and multi-camera system. 
 
As the first system to be applied to curling game, CurlingHunter demonstrated excellent performances in 2022 Beijing Winter Olympic Games of curling and 2022 Beijing Winter Paralympic Games of curling. 
Although we focus on curling, our system is readily transferable to other sports.

## **System Archetecture**

![System Archetecture]({{"/images/Components.jpg"|absolute_url}})

The curling game of the 2022 Beijing Winter Olympics was held in Beijing "Ice Cube" (Fig. 1a), the largest curling stadiums in the history of the Olympics. There were four ice tracks about 46-meter length and 5-meter width in the middle of "Ice Cube" . 
Our CurlingHunter consisted of forty-two cameras arranged in "Ice Cube" (Fig. 1a) with overlapping field of views (Fig. 1b) to ensure that every part of ice tracks was captured by at least three cameras from different angles so as to solve the problem of occlusions including people, truss, camera, etc. 

CurlingHunter consists of three main modules (Fig. 1d): single-camera tracking and visual positioning, multi-camera data association and trajectory generation, and motion analysis and trajectory prediction.  

## **Algorithm**
![Method]({{"/images/Methods.jpg"|absolute_url}})

 We overview of three main module for CurlingHunter. 
- Single-camera tracking and visual positioning(Fig. 2a). The module consists of three stages, i.e. sing-camera detection and tracking, landmark detection, and lens distortion correction. 
- Multi-camera data association and trajectory generation (Fig. 2b). The module consists of three components, i.e. homography projection, time synchronization, LSTMM based region growing and multi-camera fusion module. 
- Trajectory prediction(Fig. 2c). The framework consists of three components, i.e. Encoder, Rotation Fusion Module and Decoder.


![Method]({{"/images/Undistort.jpg"|absolute_url}})

In particular, we show the result of lens distortion correction from single image. It solved the problem of camera calibration in the stadium very gracefully.


## **Results**
![Results]({{"/images/Results.jpg"|absolute_url}})

Existing AI systems are used in tennis, basketball, and football, which are mainly used for post-game analysis to help athletes train or assist the referee in judging the games, and cannot be applied in real time to assist games. 
Hawk-Eye System used in tennis is the most mature and advanced technologies applied in sports, but its runtime is ~ 10 s, which is above 1,000 times slower than ours (Our CurlingHunter only takes ~ 9.005 ms). 
The supplementary material of our paper compares CurlingHunter with existing AI systems in detail, demonstrating that CurlingHunter is the first AI sports system in history that can be applied in real time to assist the game, improve the interest of watching game, etc.

## **Media Reports**
[CCTV5](https://2022.cctv.com/2022/03/02/VIDEo6c7b8tv2DhGSIeAwrnY220302.shtml) | 
[CCTV10](https://tv.cctv.com/2022/02/17/VIDEYNtTNJj9Jkbg0HD0hMME220217.shtml?spm=C53121759377.PvNzMjwOU8x4.0.0) |
[WAIC 2022](http://sh-aia.com/dynamics/detail389.htm) | 
[?????????????????????](http://www.cinn.cn/dfgy/202202/t20220216_252673_wap.html) | 
[?????????](https://www.baidu.com/link?url=XNs_ZUGZHU1_ta0oC--VvYEjBRtK0YTgE5aF9LoGn_jOIxhLiU5t83ON-noDK6nA7IgmWdkH3XTPKmlxiQwnCsCbhZeCBuSqU_YaBmEaonC&wd=&eqid=bb8aba1e000921f0000000036353c367) | 
[??????????????????????????????](https://jxt.zj.gov.cn/art/2022/2/22/art_1657979_58928232.html) | 
[????????????](https://baijiahao.baidu.com/s?id=1724073030087092396&wfr=spider&for=pc) |  
[????????????](https://new.qq.com/rain/a/20211030A0446N00) | 
[??????](https://www.sohu.com/a/498023908_120181749) | 
[?????????](http://www.titan24.com/publish/app/data/2020/04/26/315681/os_news.html) | 
[????????????](http://hw.yidianzixun.com/article/0bHe9PzU?s=hwbrowser&appid=hwbrowser&s_real=hwbrowser&ctype=news&from_related=1) | 
[?????????](https://export.shobserver.com/baijiahao/html/447890.html) | 
[????????????](https://www.baidu.com/link?url=8PENrdD4JtTbU4FRLbMgAmKw8P5l1K8k2sP9R_-Hprk-11CvYGXxTie0ZzFDkRqJLBGjRpDNM8jbqds-ReyDXOeNqOA1TgP07MLuOgZ30yG&wd=&eqid=bca23d5b001ccf48000000036353c1a0) | 
[?????????](https://baijiahao.baidu.com/s?id=1724791100724675147&wfr=spider&for=pc) | 
[????????????](https://www.sensetime.com/cn/news-detail/41164739) | 
[???????????????](https://baijiahao.baidu.com/s?id=1729136742236108141&wfr=spider&for=pc) | 
[???????????????](https://baijiahao.baidu.com/s?id=1724508134127922968&wfr=spider&for=pc) | 
[????????????](https://baijiahao.baidu.com/s?id=1728608215909288051&wfr=spider&for=pc) | 
[?????????](https://page.om.qq.com/page/OLcb7f1Zh26fP2HlVty6z1cg0) | 
[????????????](https://www.takefoto.cn/news/2022/02/25/10047236.shtml) | 


## **Supplementary Videos**

<center>
<iframe 
	width="640"
	height="368"
	src="/videos/1.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 
<br/>
<font size="3">Verification the accuracy of CurlingHunter </font>
<br/>

<iframe 
	width="640"
	height="368"
	src="/videos/2.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 
<br/>

<font size="3">Performance Test of CurlingHunter </font>
<br/>

<iframe 
	width="640"
	height="368"
	src="/videos/3.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 
<br/>
<font size="3">Application in Beijing 2022 Winter Olympics </font>
<br/>

<iframe 
	width="640"
	height="368"
	src="/videos/4.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 
<br/>
<font size="3">Application in Beijing 2022 Winter Paralympic </font>
<br/>

<iframe 
	width="640"
	height="368"
	src="/videos/5.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 

<br/>
<font size="3">Live broadcast of Winter Olympics </font>
<br/>

<iframe 
	width="640"
	height="368"
	src="/videos/6.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 
<br/>
<font size="3">Live broadcast of Winter Paralympic </font>
<br/>

<iframe 
	width="640"
	height="368"
	src="/videos/7.mp4"
	frameborder="0"
	allowfullscreen>
</iframe> 
<br/>
<font size="3">Motion Analysis </font>
<br/>
</center>

## **Citation**

>Xuanke Shi, Quan Wang, Chao Wang, Rui Wang, Longshu Zheng, Chen Qian, Wei Tang, "An AI-Based Curling Game System for Winter Olympics", Research, vol. 2022, Article ID 9805054, 17 pages, 2022. https://doi.org/10.34133/2022/9805054



