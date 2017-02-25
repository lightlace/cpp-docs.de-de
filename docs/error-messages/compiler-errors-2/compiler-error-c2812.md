---
title: "Compilerfehler C2812 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2812"
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#Import wird zusammen mit \/clr:pure und \/clr:safe nicht unterstützt  
  
 [\#import\-Direktive](../../preprocessor/hash-import-directive-cpp.md) wird zusammen mit **\/clr:pure** und **\/clr:safe** nicht unterstützt, da `#import` die Verwendung systemeigener Unterstützungsbibliotheken des Compilers erfordert.  
  
## Beispiel  
 Im folgenden Beispiel wird C2812 generiert.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```