---
title: "Compilerfehler C3280 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3280"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3280"
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3280
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Klasse": Eine Memberfunktion eines verwalteten Typs kann nicht als eine nicht verwaltete Funktion kompiliert werden  
  
 Es ist nicht möglich, Memberfunktionen mit verwalteten Klassen als nicht verwaltete Funktionen zu kompilieren.  
  
 Im folgenden Beispiel wird C3280 generiert:  
  
```  
// C3280_2.cpp // compile with: /clr ref struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```  
  
 Im folgenden Beispiel wird C3280 generiert:  
  
```  
// C3280.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```