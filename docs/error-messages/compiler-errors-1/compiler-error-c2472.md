---
title: "Compilerfehler C2472 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2472"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2472"
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2472
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"function" kann nicht in verwaltetem Code generiert werden: "message". Kompilieren Sie mit \/clr, um ein gemischtes Image zu generieren  
  
 Dieser Fehler tritt auf, wenn von verwaltetem Code nicht unterstützte Typen innerhalb einer reinen CLR\-Umgebung \(Common Language Runtime\) verwendet werden. Kompilieren Sie mit **\/clr**, um den Fehler zu beheben.  
  
## Beispiel  
 Im folgenden Beispiel wird C2472 generiert.  
  
```  
// C2472.cpp // compile with: /clr:pure // C2472 expected #include <cstdlib> int main() { int * __ptr32 p32; int * __ptr64 p64; p32 = (int * __ptr32)malloc(4); p64 = p32; }  
```  
  
## Siehe auch  
 [\/clr \(Common Language Runtime\-Kompilierung\)](../../build/reference/clr-common-language-runtime-compilation.md)