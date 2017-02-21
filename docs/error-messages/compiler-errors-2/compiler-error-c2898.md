---
title: "Compilerfehler C2898 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2898"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2898"
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2898
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Deklaration': Vorlagen der Memberfunktion können nicht virtuell sein  
  
 Im folgenden Beispiel wird C2898 generiert:  
  
```  
// C2898.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> virtual void f(T t) {}   // C2898  
};  
```