---
title: "Compilerfehler C2165 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2165"
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Schlüsselwort': Zeiger auf Daten können nicht geändert werden.  
  
 Das `__stdcall`\-, `__cdecl`\- oder `__fastcall`\-Schlüsselwort versucht, einen Zeiger auf Daten zu ändern.  
  
 Im folgenden Beispiel wird C2165 generiert:  
  
```  
// C2165.cpp // compile with: /c char __cdecl *p;   // C2165 char *p;   // OK  
```