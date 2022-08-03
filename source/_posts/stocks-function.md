---
title: 技术验证
date: 2022-07-20 00:00:00
description: 交易记录
categories:
- stocks
---

```bash

ZT:= C/REF(C,1)>1.098;
LAST_ZT:= BARSLAST(ZT);
REF(VOL,LAST_ZT-1) / REF(VOL,LAST_ZT) >= 1.5 
and REF(C,LAST_ZT-1) < REF(C,LAST_ZT) 
and LAST_ZT <= 5 
AND C > REF(L,LAST_ZT) AND REF(C,LAST_ZT) / C >= 1.05
and REF(C,LAST_ZT) <= HHV(H,LAST_ZT+30);

```