---
title: 技术验证
date: 2022-07-20 00:00:00
description: 交易记录
categories:
- stocks
---


```bash
逻辑：
1、趋势向上
2、涨停后出现倍量阴
3、出现一个5个点的上涨修复放量阴线的收盘价（涨停最佳）
4、股价没有创新高
5、阴线的收盘价就是止损位


ZT:= C/REF(C,1)>1.098;
LAST_ZT:= BARSLAST(ZT);
BLY:=REF(VOL,LAST_ZT-1) / REF(VOL,LAST_ZT) >= 1.5  AND REF(C,LAST_ZT-1) < REF(O,LAST_ZT-1);
DY_BLY:=C/O >= 1.03 AND C >= REF(C,LAST_ZT-1);
STN:= LAST_ZT <= 14 AND LAST_ZT >=3;
BLY AND DY_BLY AND STN and REF(C,LAST_ZT) <= HHV(H,LAST_ZT+30);

```