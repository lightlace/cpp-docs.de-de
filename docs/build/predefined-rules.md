---
title: "Vordefinierte Regeln"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Regeln, Vordefinierte"
  - "NMAKE (Programm), Vordefinierte Regeln"
  - "Vordefinierte Regeln in NMAKE"
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Vordefinierte Regeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Von vordefinierten Rückschlussregeln werden Befehls\- und Optionenmakros von NMAKE verwendet.  
  
|Regel|Befehl|Default<br /><br /> action|Batch<br /><br /> Regel|Plattform, auf der nmake funktioniert|  
|-----------|------------|------------------------|---------------------|-------------------------------------------|  
|.asm.exe|$\(AS\) $\(AFLAGS\) $\<|ml $\<|nein|x86|  
|.asm.obj|$\(AS\) $\(AFLAGS\) \/c $\<|ml \/c $\<|ja|x86|  
|.asm.exe|$\(AS\) $\(AFLAGS\) $\<|ml64 $\<|nein|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.asm.obj|$\(AS\) $\(AFLAGS\) \/c $\<|ml64 \/c $\<|ja|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|.c.exe|$\(CC\) $\(CFLAGS\) $\<|cl $\<|nein|all|  
|.c.obj|$\(CC\) $\(CFLAGS\) \/c $\<|cl \/c $\<|ja|all|  
|.cc.exe|$\(CC\) $\(CFLAGS\) $\<|cl $\<|nein|all|  
|.cc.obj|$\(CC\) $\(CFLAGS\) \/c $\<|cl \/c $\<|ja|all|  
|.cpp.exe|$\(CPP\) $\(CPPFLAGS\) $\<|cl $\<|nein|all|  
|.cpp.obj|$\(CPP\) $\(CPPFLAGS\) \/c $\<|cl \/c $\<|ja|all|  
|.cxx.exe|$\(CXX\) $\(CXXFLAGS\) $\<|cl $\<|nein|all|  
|.cxx.obj|$\(CXX\) $\(CXXFLAGS\) \/c $\<|cl \/c $\<|ja|all|  
|.rc.res|$\(RC\) $\(RFLAGS\) \/r $\<|rc \/r $\<|nein|all|  
  
## Siehe auch  
 [Rückschlussregeln](../build/inference-rules.md)