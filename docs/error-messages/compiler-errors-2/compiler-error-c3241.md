---
title: "Compilerfehler C3241 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3241"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3241"
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3241
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Methode': Diese Methode wurde nicht von 'Schnittstelle' eingeführt  
  
 Wenn Sie eine Funktion explizit überschreiben, muss die Funktionssignatur exakt mit der Deklaration für die Funktion übereinstimmen, die Sie überschreiben.  
  
 Im folgenden Beispiel wird C3241 generiert:  
  
```  
// C3241.cpp  
#pragma warning(disable:4199)  
  
__interface IX12A {  
   void mf();  
};  
  
__interface IX12B {  
   void mf(int);  
};  
  
class CX12 : public IX12A, public IX12B { // C3241  
   void IX12A::mf(int);  
};  
```