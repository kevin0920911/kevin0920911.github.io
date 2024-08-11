---
title: "[writeup] AIS3 2024 preexam"
subtitle: "writeup"
layout: post
author: "Hsu"
published: true
header-style: text
tags:
  - write up
---
# AIS3 pre-exam writeup

## Misc
### Welcome
![image](https://hackmd.io/_uploads/r1qJ49M4A.png)

> flag: AIS3{Welc0me_to_AIS3_PreExam_2o24!}

### Quantum Nim Heist
- 他是一個nim game，要獲勝才能拿到FLAG
- 但是遊戲有bug
    ![image](https://hackmd.io/_uploads/Hk9uEcfEC.png)
    - 在遊玩時選單並沒有做太多檢查
    - 所以我只要輸入超過2的數字就好了
- 也因此，我每次選擇都選擇5，遊戲就會一直給人機放置play，我只要在最後當個賤人拿走就好
    ![image](https://hackmd.io/_uploads/BJtES9G4C.png)

> flag:  AIS3{Ar3_y0u_a_N1m_ma57er_0r_a_Crypt0_ma57er?}
    
    
### Three Dimensional Secret
- 他是一個wire shark封包，打開看一下
    ![image](https://hackmd.io/_uploads/r1jZ8cMNC.png)
- 太多東西了我們整理一下
    - 有ARP封包 => 主要處理MAC address對應IP address的協定
        - 沒甚麼用
    - 有SSDP封包 => 那應該理論上這個封包應該在處理物聯網的東東
    - 有TCP封包 => 應該是主要數據的東西
- 好有了上面的東西，我們初步判斷，FLAG藏在TCP當中
    - 所以 analyze -> follow -> tcp stream
        ![image](https://hackmd.io/_uploads/BkDVP5MVR.png)
    - 好如果tcp stream中有flag不是很棒嗎，所以查查看有沒有
        ![image](https://hackmd.io/_uploads/HJ6vD5GEC.png)
        - 事實證明沒有，所以等等要努力看一下封包內容
- 稍微整理一下封包傳送內容
    1. 第一個它的IoT設備是Creality Ender-3 Max
        ![image](https://hackmd.io/_uploads/HJ83DcG4A.png)
        - 看了一下CVE似乎沒有漏洞可以鑽
    2. 他傳送的是一個3D max模型，使用G-code
        ![image](https://hackmd.io/_uploads/Sywg_cGER.png)
- 好所以第一點好像沒機會了，第二點可能有一點機會，我們執行他看看
    - [tools](https://nraynaud.github.io/webgcode/)
    ![image](https://hackmd.io/_uploads/SyeLYcf4C.png)
    - 好看到flag了，果然

> flag: AIS3{b4dy_tun3d_PriN73r}

## Web
### Evil Calculator
- 好首先先打開網站，是一台計算機，應該是拿來算算樂的
    ![image](https://hackmd.io/_uploads/ByJTt5G4R.png)
- 那我們再開一下程式碼
    ![image](https://hackmd.io/_uploads/HkGLqqG40.png)
    - 當送出時，網站會使用POST進入`/calculate`，然後刪除空白與底線，將字串送入到`eval()`函數
    - 好重點來了eval函數可以執行任意python的程式
        - 好啦現在可以壞壞了
- 我們先看一下flag在哪
    ![image](https://hackmd.io/_uploads/Sk79oqz4A.png)
    - 在app外面，所以本程式存取要`../flag`
- 想一下payload
    - 已知幾點
        1. 沒有`import os`，所以沒辦法用貓咪
        2. flag相對路徑是`../flag`
    - 所以用open最為合適
        > Payload: open('../flag','r').readline()
> flag: AIS3{7RiANG13_5NAK3_I5_50_3Vi1}

## rev
### The Long Print
- 首先解開文建檔案，可以看到他是一個二進位檔案
- 那我們先拿IDA看一下
    ![image](https://hackmd.io/_uploads/rkAHTqGNR.png)
    - 可以看到反組譯後的程式碼顯示以下資訊
        1. flag可能藏在secret當中
        2. 每印出一個字元他會sleep 0x3674u毫秒，很久
- 所以最好的做法就是用gdb將sleep設斷點
    - 以下資訊
        ![image](https://hackmd.io/_uploads/HyfmesMVR.png)
        1. Sleep在呼叫時需要參數rdi
- 好接下來可以壞壞了
    1. 先開gdb下break
        ```s
        b sleep
        run
        ```
    2. 然後開始一直重複以下行為直到程式結束
        ```s
        set $rdi = 1
        continue
        ```
    ![image-1](https://hackmd.io/_uploads/HytMZsfN0.png)
> flag: AIS3{You_are_the_master_of_time_management!!!!?}

