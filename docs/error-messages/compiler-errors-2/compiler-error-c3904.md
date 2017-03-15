---
title: "Compilerfehler C3904 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3904"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3904"
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C3904
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_accessor' : Muss Zahl Parameter angeben  
  
 Vergleichen Sie die Zahl der Parameter in der `get`\-Methode und der `set`\-Methode mit den Eigenschaftendimensionen.  
  
-   Die Anzahl der Parameter für die `get`\-Methode muss mit der Anzahl der Dimensionen der Eigenschaft übereinstimmen oder bei nicht indizierten Eigenschaften 0 \(null\) sein.  
  
-   Die Anzahl der Parameter der `set`\-Methode muss der Anzahl der Dimensionen der Eigenschaft plus 1 entsprechen.  
  
 Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3904 generiert.  
  
```  
// C3904.cpp  
// compile with: /clr /c  
ref class X {  
   property int P {  
      // set  
      void set();   // C3904  
      // try the following line instead  
      // void set(int);  
  
      // get  
      int get(int, int);   // C3904  
      // try the following line instead  
      // int get();  
   };  
};  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C3904 generiert.  
  
```  
// C3904b.cpp  
// compile with: /clr /c  
ref struct X {  
   property int Q[double, double, float, float, void*, int] {  
      // set  
      void set(double, void*);   // C3904  
      // try the following line instead  
      // void set(double, double, float, float, void*, int, int);  
  
      // get  
      int get();   // C3904  
      // try the following line instead  
      // int get(double, double, float, float, void*, int);  
   }  
};  
```