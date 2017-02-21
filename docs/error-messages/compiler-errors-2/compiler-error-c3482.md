---
title: "Compilerfehler C3482 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3482"
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C3482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"this" kann nur als Lambdaerfassung innerhalb einer nicht statischen Memberfunktion verwendet werden.  
  
 Sie können `this` nicht an die Erfassungsliste eines Lambdaausdrucks übergeben, der in einer statischen Methode oder globalen Funktion deklariert ist.  
  
### So beheben Sie diesen Fehler  
  
-   Konvertieren Sie die einschließende Funktion in eine nicht statische Methode oder  
  
-   Entfernen Sie den `this`\-Zeiger aus der Erfassungsliste des Lambdaausdrucks.  
  
## Beispiel  
 Im folgenden Beispiel wird der Fehler C3482 generiert:  
  
```  
// C3482.cpp // compile with: /c class C { public: static void staticMethod() { [this] {}(); // C3482 } };  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)