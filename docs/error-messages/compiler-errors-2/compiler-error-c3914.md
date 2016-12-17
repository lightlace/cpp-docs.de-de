---
title: "Compilerfehler C3914"
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
  - "C3914"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3914"
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3914
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Standardeigenschaft kann nicht statisch sein  
  
 Eine Standardeigenschaft wurde falsch deklariert.  Weitere Informationen finden Sie unter [Gewusst wie: Verwenden von indizierten Eigenschaften](../../misc/how-to-use-indexed-properties.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3914 generiert.  
  
```  
// C3914.cpp  
// compile with: /clr /c  
ref struct X {  
   static property int default[int] {   // C3914  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```