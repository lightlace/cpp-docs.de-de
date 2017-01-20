---
title: "Compilerfehler C2425"
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
  - "C2425"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2425"
ms.assetid: 0ce59404-9aff-4e01-aa8d-27d23e92eb30
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2425
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token': nicht konstanter Ausdruck in 'Kontext'  
  
 Das Token ist Teil eines nicht konstanten Ausdrucks in diesem Kontext.  
  
 Um dieses Problem zu beheben, ersetzen Sie das Token mit einer Berechnung oder einem konstanten Buchstabensymbol.  
  
 Im folgenden Beispiel wird C2425 generiert:  
  
```  
// C2425.cpp  
// processor: x86  
int main() {  
   int i = 3;  
   __asm {  
      mov eax, [ebp - i]   // C2425  
      mov eax, [ebp - 3]   // OK  
   }  
}  
```