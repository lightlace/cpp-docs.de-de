---
title: "Systeminterne Funktionen und Inlineassemblys | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Systeminterne Funktionen und Inlineassemblys
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]\-Compiler ist u. a. dadurch in seiner Leistung eingeschränkt, dass er über keine Unterstützung für Inlineassemblys verfügt.  Dies hat zur Folge, dass Funktionen, die nicht in C oder C\+\+ geschrieben werden können, entweder als Unterroutinen oder als systeminterne Funktionen geschrieben werden müssen, die vom Compiler unterstützt werden.  Manche Funktionen sind leistungsabhängig, andere wiederum nicht.  Leistungsabhängige Funktionen sollten als systeminterne Funktionen implementiert werden.  
  
 Eine Beschreibung der vom Compiler unterstützten systeminternen Funktionen finden Sie unter [Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md).  
  
## Siehe auch  
 [x64\-Softwarekonventionen](../build/x64-software-conventions.md)