---
title: "Compilerfehler C3275 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3275"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3275"
ms.assetid: 5752680f-7d3e-4c42-ba9c-845e09d32e7a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3275
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Enumerationsmember": Dieses Symbol kann nicht ohne Qualifizierer verwendet werden.  
  
 Wird verwalteter Code verwendet und enthalten mehrere Enumerationen einen Bezeichner mit demselben Namen, müssen Sie explizit Verweise auf den Bezeichner beschreiben.  
  
 C3275 ist nur über **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel sind zwei Situationen gezeigt, in denen C3275 generiert werden könnte:  
  
```  
// C3275.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __value enum Jewelry { necklace, brooch, pin, ring, earring }; __value enum Phone { busy, ring, disconnect }; int main() { Phone p = ring;   // C3275 // try the following line instead // Phone p = Phone::ring; Console::Out->Write(ring);   // C3275 // try the following line instead // Console::Out->Write(Phone::ring); }  
```