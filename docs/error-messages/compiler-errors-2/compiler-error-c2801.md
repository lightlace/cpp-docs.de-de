---
title: "Compilerfehler C2801"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2801"
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator Operator' muss ist ein nicht statischer Member sein  
  
 Die folgenden Operatoren können nur als nicht statische Member überladen werden:  
  
-   Zuweisung `=`  
  
-   Klassenmemberzugriff `->`  
  
-   Indizierung `[]`  
  
-   Funktionsaufruf `()`  
  
 Mögliche Ursachen für C2801:  
  
-   Der überladene Operator ist kein Klassen\-, Struktur\- oder Unionmember.  
  
-   Der überladene Operator wurde als `static` deklariert.  
  
-   Im folgenden Beispiel wird C2801 generiert:  
  
```  
// C2801.cpp  
// compile with: /c  
operator[]();   // C2801 not a member  
class A {  
   static operator->();   // C2801 static  
   operator()();   // OK  
};  
```