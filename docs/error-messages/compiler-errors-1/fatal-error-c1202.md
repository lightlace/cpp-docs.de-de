---
title: "Schwerwiegender Fehler C1202"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C1202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1202"
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Kontext für einen rekursiven Typ oder eine Funktionsabhängigkeit ist zu komplex  
  
 Eine Vorlagendefinition war rekursiv oder hat die zulässige Komplexität überschritten.  
  
## Beispiel  
 Im folgenden Beispiel wird C1202 generiert.  
  
```  
// C1202.cpp // processor: x86 IPF template<int n> class Factorial : public Factorial<n-1>  {   // C1202 public: operator int () { return Factorial <n-1>::operator int () * n; } }; Factorial<7> facSeven;  
```  
  
## Beispiel  
 Mögliche Lösung:  
  
```  
// C1202b.cpp // compile with: /c template<int n> class Factorial : public Factorial<n-1> { public: operator int () { return Factorial <n-1>::operator int () * n; } }; template <> class Factorial<0> { public: operator int () { return 1; } }; Factorial<7> facSeven;  
```