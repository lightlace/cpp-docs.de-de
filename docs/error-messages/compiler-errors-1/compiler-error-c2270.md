---
title: "Compilerfehler C2270"
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
  - "C2270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2270"
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Modifizierer für Funktionen, die keine Memberfunktionen sind, nicht zulässig  
  
 Eine Funktion, die keine Memberfunktion ist, wurde mit [const](../../cpp/const-cpp.md), [volatile](../../cpp/volatile-cpp.md) oder einem anderen Modifizierer für Speichermodelle deklariert.  
  
 Im folgenden Beispiel wird C2270 generiert:  
  
```  
// C2270.cpp  
// compile with: /c  
void func1(void) const;   // C2270, nonmember function  
  
void func2(void);  
  
class CMyClass {  
public:  
   void func2(void) const;  
};  
```