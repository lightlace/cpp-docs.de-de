---
title: Vordefinierte Regeln | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3be1c8eea7b11f60e9ce9a7cbf5ebc0c2b99b698
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="predefined-rules"></a>Vordefinierte Regeln
Von vordefinierten Rückschlussregeln werden Befehls- und Optionenmakros von NMAKE verwendet.  
  
|Regel|Befehl|Standard<br /><br /> action|Batch<br /><br /> Regel|Plattform, auf der nmake funktioniert|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml $<|Nein|x86|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|ja|x86|  
|.asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Nein|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|ja|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
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