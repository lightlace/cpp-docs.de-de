---
title: "Compilerfehler C2157 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2157"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2157"
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2157
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': muss vor der Verwendung in der Pragma\-Liste deklariert werden.  
  
 Der Funktionsname ist nicht deklariert, bevor auf ihn in der Liste der Funktionen für ein [alloc\_text](../../preprocessor/alloc-text.md)\-Pragma verwiesen wird.  
  
 Im folgenden Beispiel wird C2157 generiert:  
  
```  
// C2157.cpp // compile with: /c #pragma alloc_text( "func", func)   // C2157 // OK extern "C" void func(); #pragma alloc_text( "func", func)  
```