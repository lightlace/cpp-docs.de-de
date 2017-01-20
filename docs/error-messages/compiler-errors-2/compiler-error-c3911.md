---
title: "Compilerfehler C3911"
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
  - "C3911"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3911"
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3911
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event\_accessor\_method': Funktion muss vom Typ 'Signatur' sein  
  
 Die Accessormethode eines Ereignisses wurde nicht ordnungsgemäß deklariert.  
  
 Weitere Informationen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3911 generiert:  
  
```  
// C3911.cpp  
// compile with: /clr  
using namespace System;  
delegate void H(String^, int);  
  
ref class X {  
   event H^ E1 {  
      void add() {}   // C3911  
      // try the following line instead  
      // void add(H ^ h) {}  
  
      void remove(){}  
      // try the following line instead  
      // void remove(H ^ h) {}  
  
      void raise(){}  
      // try the following line instead  
      // void raise(String ^ s, int i) {}  
   };  
};  
```