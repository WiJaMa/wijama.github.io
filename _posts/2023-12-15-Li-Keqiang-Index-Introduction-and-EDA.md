---
layout: post
title:  "Testing the Li Keqiang Index: Project Introduction and EDA"
author: William Martindale
description: Introducing my Li Keqiang Index project.
image: /assets/images/blog-image.jpg
---

# Introduction

Li Keqiang was the former premier of the People's Republic of China. He was seen by many in the West as a moderate in the Chinese Communist Party; compared to Xi Jinping, Li was more friendly to the West and more open to liberal economics. He was widely expected to be a major candidate to succeed Hu Jintao as paramount leader in 2012.
However, he fell from grace, in large part due to a diplomatic cable stolen and leaked by Wikileaks in 2010. In this document, an ambassador claims to have been told by Li Keqiang that the GDP figures in Li's province of Liaoning were unreliable. Instead, Li said that he used three other indicators: the railway cargo volume, electricity consumption and loans disbursed by banks.
This was widely reported at the time, most famously by [The Economist](https://www.economist.com/asia/2010/12/09/keqiang-ker-ching). Li died in October 2023 after being ousted from power in the 20th National Congress of the Chinese Communist Party and was replaced as premier by the similarly-named Li Qiang.

<p align="center">
![image](https://github.com/WiJaMa/wijama.github.io/assets/73615879/48417fb0-10c6-4209-a787-41d48fa397bc)

_Li Keqiang in 2019 [Image Source]([url](https://commons.wikimedia.org/wiki/File:Shinz%C5%8D_Abe_Li_Keqiang_20191225_(1)_(cropped).jpg)
</p>

# Project

I wanted to see whether this index was actually a good reflection of modern economies. Two of the indicators are strongly connected with industrial development but not the modern service-oriented economy, while the other, volume of bank loans, is difficult to quantify. I was also curious whether the effectiveness of the indicator would vary with level of democracy.
The measurement of democracy is, of course, a widely contested field. The two most famous indices dedicated to measuring democracy are the Economist Democracy Index and the V-Dem Democracy Indices. The latter are plural because V-Dem (or, the Varieties of Democracy Institute) developed multiple indices to measure different types of democracy: electoral, liberal, participatory, deliberative, and egalitarian. For simplicity, I chose to use the Economist Democracy Index.

For control variables, I also included in my analysis the percentage of the economy made of services and the percentage of the population that was urban. I anticipated that these would have some effect on how, accurate the Li Keqiang index would be.

Because the Economist Democracy Index only includes the years 2006, 2008, and 2010-2022, those were the only years included in the analysis. This is where the V-Dem indices would likely have been more useful; they evaluate countries as far back as the year 1900.

# Gathering Data
