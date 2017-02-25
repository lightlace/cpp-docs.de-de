---
title: "Compilerfehler C2272 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2272"
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Modifizierer bei statischen Memberfunktionen nicht zulässig  
  
 Eine `static`\-Memberfunktion wurde mit einem Spezifizierer für ein Speichermodell, z. B. [const](../../cpp/const-cpp.md) oder [volatile](../../cpp/volatile-cpp.md), deklariert. Diese Modifizierer sind für `static`\-Memberfunktionen nicht zulässig.  
  
 Im folgenden Beispiel wird C2272 generiert:  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```