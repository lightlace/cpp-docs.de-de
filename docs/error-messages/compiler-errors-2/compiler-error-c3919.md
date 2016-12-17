---
title: "Compilerfehler C3919"
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
  - "C3919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3919"
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'event\_method': Funktion muss vom Typ 'Typ' sein  
  
 Eine Ereignisaccessormethode wurde nicht richtig deklariert.  
  
 Weitere Informationen über Ereignisse finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3919 generiert:  
  
```  
// C3919.cpp  
// compile with: /clr /c  
using namespace System;  
delegate void D(String^);  
ref class R {  
   event D^ e {  
      int add(int);   // C3919  
      int remove(int);   // C3919  
  
      void add(D^);   // OK  
      void remove(D^);   // OK  
   }  
};  
```