---
title: "Compilerfehler C2935 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2935"
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Die Typklassen\-ID ist als globale Funktion neu definiert  
  
 Eine generische oder Vorlagenklasse kann nicht als globale Funktion verwendet werden.  
  
 Dieser Fehler kann dadurch verursacht werden, dass geschweifte Klammern nicht korrekt übereinstimmen.  
  
 Im folgenden Beispiel wird C2935 generiert:  
  
```  
// C2935.cpp // compile with: /c template<class T> struct TC {}; void TC<int>() {}   // C2935 // OK struct TC2 {}; void TC2() {}  
```  
  
 C2935 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2935b.cpp // compile with: /clr /c generic<class T> ref struct GC { }; void GC<int>() {}   // C2935 void GC() {}   // OK  
```