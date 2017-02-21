---
title: "Compilerfehler C3279 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3279"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3279"
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3279
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Teilweise oder explizite Spezialisierungen sowie explizite Instanziierungen von Klassenvorlagen, die im cli\-Namespace deklariert sind, sind nicht zulässig.  
  
 Der `cli`\-Namespace wird von Microsoft definiert und enthält Pseudovorlagen. Der Visual C\+\+\-Compiler lässt keine benutzerdefinierten partiellen und expliziten Spezialisierungen und keine expliziten Instanziierungen von Klassenvorlagen in diesem Namespace zu.  
  
 Im folgenden Beispiel wird C3279 generiert:  
  
```  
// C3279.cpp // compile with: /clr namespace cli { template <> ref class array<int> {};   // C3279 template <typename T> ref class array<T, 2> {};   // C3279 }  
```