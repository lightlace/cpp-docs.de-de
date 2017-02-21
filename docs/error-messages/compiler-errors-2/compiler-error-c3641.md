---
title: "Compilerfehler C3641 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3641"
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Ungültige Aufrufkonvention 'calling\_convention' für eine Funktion, die mit \/clr:pure oder \/clr:safe kompiliert wurde.  
  
 Nur die [\_\_clrcall](../../cpp/clrcall.md)\-Aufrufkonvention ist bei [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md) zulässig.  
  
 Im folgenden Beispiel wird C3641 generiert:  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```