---
title: Vordefinierte Regeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52c9440a0320bbc59e5d2552a53e13fae5e29f05
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571870"
---
# <a name="predefined-rules"></a>Vordefinierte Regeln
Von vordefinierten Rückschlussregeln werden Befehls- und Optionenmakros von NMAKE verwendet.  
  
|Regel|Befehl|Standard<br /><br /> action|Batch<br /><br /> Regel|Plattform, auf der nmake funktioniert|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|Nein|x86|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|ja|x86|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Nein|x64|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|ja|x64|  
|.c.exe|$(CC) $(CFLAGS) $<|cl $<|nein|alle|  
|.c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|ja|alle|  
|.cc.exe|$(CC) $(CFLAGS) $<|cl $<|nein|alle|  
|.cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|ja|alle|  
|.cpp.exe|$(CPP) $(CPPFLAGS) $<|cl $<|nein|alle|  
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|ja|alle|  
|.cxx.exe|$(CXX) $(CXXFLAGS) $<|cl $<|nein|alle|  
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|ja|alle|  
|.rc.res|$(RC) $(RFLAGS) /r $<|rc /r $<|Nein|alle|  
  
## <a name="see-also"></a>Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)