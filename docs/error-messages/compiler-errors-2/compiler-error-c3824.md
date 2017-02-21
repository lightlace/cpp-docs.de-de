---
title: "Compilerfehler C3824 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3824"
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3824
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Dieser Typ kann nur in diesem Kontext \(Funktionsparameter, Rückgabetyp oder statischer Member\) auftreten  
  
 Feste Zeiger können keine Funktionsparameter oder Rückgabetypen sein oder als `static` deklariert werden.  
  
 Im folgenden Beispiel wird C3824 generiert:  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
  
 **Managed Extensions for C\+\+**  
  
 Lokale Zeiger, die mit dem Schlüsselwort `__pin` deklariert sind, können nicht als `static` deklariert werden und auch keine inneren Zeiger sein.  
  
 Im folgenden Beispiel wird C3824 generiert:  
  
```  
// C3824b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc struct A {};  
  
void func() {  
   static A __pin* a;   // C3824  
   A __pin* b;   // OK  
}  
```