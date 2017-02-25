---
title: "Compilerfehler C2130 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2130"
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#line erwartet eine Zeichenfolge mit dem Dateinamen, "Token" gefunden  
  
 Das optionale Dateinamenstoken, das auf [\#line](../../preprocessor/hash-line-directive-c-cpp.md) `linenumber` folgt, muss eine Zeichenfolge sein.  
  
 Im folgenden Beispiel wird C2130 generiert:  
  
```  
// C2130.cpp int main() { #line 1000 test   // C2130 #line 1000 "test"   // OK }  
```