---
title: "Compilerfehler C3155"
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
  - "C3155"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3155"
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3155
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Attribute sind in einem Eigenschaften\-Indexer nicht zulässig  
  
 Eine indizierte Eigenschaft wurde falsch deklariert.  Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von indizierten Eigenschaften](../../misc/how-to-use-indexed-properties.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3155 generiert.  
  
```  
// C3155.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct R {  
   property int F[[ParamArray] int] {   // C3155  
   // try the following line instead  
   // property int F[ int] {   // OK  
      int get(int i) {   
         return 0;   
      }  
   }  
};  
```