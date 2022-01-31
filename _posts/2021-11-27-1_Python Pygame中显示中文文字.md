---
title: Python Pygame中显示中文文字
author: luthree
date: 2021-11-27
category: posts
layout: post
---

```python
'''
-*- coding: utf-8 -*-
@Author  : luthree
@Software: VS code
@File    : main.py
'''
import pygame
from pygame.locals import *
import os
import sys

pygame.init()
screen = pygame.display.set_mode((800, 600))
WHITE = (255, 255, 255)  # 设置颜色：白
score = 0

while True:
    for event in pygame.event.get():  # 循环获取事件
        if event.type == QUIT:  # 若检测到事件类型为退出，则退出
            pygame.quit()
            sys.exit()
    pygame.display.update()  # 刷新屏幕内容
    font = pygame.font.Font('fonts/simsun.ttc', 29)  # 设置字体，'fonts/simsun.ttc'是字库位置
    text = '得分：' + str(score)  # 文本。可与变量一起使用，但需转换为字符串
    text = font.render(text, True, WHITE)
    textS = text.get_rect()
    textS.center = (400, 15)  # 位置
    screen.blit(text, textS)  # 绘制
```

以上代码搭配中文字库，即可实现显示中文

[luthree](https://luthr.ee)
