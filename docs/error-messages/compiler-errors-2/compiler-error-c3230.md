---
title: "Compilerfehler C3230 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3230"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3230"
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3230
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Das Vorlagentypargument für 'Vorlage' kann keinen generischen Typparameter enthalten: 'param'  
  
 Vorlagen werden zur Kompilierzeit, aber Generika zur Laufzeit instanziiert. Daher ist es nicht möglich, generischen Code zu generieren, der die Vorlage aufrufen kann, da die Vorlage nicht zur Laufzeit instanziiert werden kann, wenn der generische Typ schließlich bekannt ist.  
  
 Im folgenden Beispiel wird C3230 generiert:  
  
```  
// C3230.cpp // compile with: /clr /LD template <class S> void f(S t); generic <class U> ref class C { void f1(U x) { f(x);   // C3230 } };  
```