---
title: "Compilerfehler C2279 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2279"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2279"
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2279
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ausnahmespezifikation kann nicht in einer typedef\-Deklaration enthalten sein  
  
 Bei Verwendung von **\/Za** sind [Ausnahmespezifikationen](../../cpp/exception-specifications-throw-cpp.md) in einer typedef\-Deklaration nicht zulässig.  
  
 Im folgenden Beispiel wird C2279 generiert:  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```