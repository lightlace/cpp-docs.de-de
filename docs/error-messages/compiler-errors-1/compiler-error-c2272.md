---
title: "Compilerfehler C2272"
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
  - "C2272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2272"
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
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