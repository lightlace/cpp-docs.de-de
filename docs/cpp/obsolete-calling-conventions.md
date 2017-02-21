---
title: "Veraltete Aufrufkonventionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__fortran"
  - "__pascal"
  - "__syscall"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__fortran-Schlüsselwort [C++]"
  - "__pascal-Schlüsselwort [C++]"
  - "__syscall-Schlüsselwort [C++]"
  - "Aufrufkonventionen, Veraltet"
  - "WINAPI"
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Veraltete Aufrufkonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Die Aufrufkonventionen **\_\_pascal**, **\_\_fortran** und **\_\_syscall** werden nicht mehr unterstützt.  Sie können ihre Funktionalität emulieren, indem Sie eine der unterstützten Aufrufkonventionen und geeignete Linkeroptionen verwenden.  
  
 WINDOWS.H unterstützt jetzt das **WINAPI**\-Makro, das in die entsprechende Aufrufkonvention für das Ziel übersetzt.  Verwenden Sie **WINAPI**, wo Sie zuvor **PASCAL** oder **\_\_far \_\_pascal** verwendet haben.  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)