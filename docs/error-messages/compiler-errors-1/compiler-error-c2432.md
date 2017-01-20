---
title: "Compilerfehler C2432"
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
  - "C2432"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2432"
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2432
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unzulässiger Verweis auf 16\-Bit\-Daten in 'Bezeichner'  
  
 Ein 16\-Bit\-Register wurde als Index\- oder Basisregister verwendet.  Der Compiler unterstützt keine Verweise auf 16\-Bit\-Daten. Bei der Kompilierung für 32\-Bit\-Code können 16\-Bit\-Register nicht als Index\- oder Basisregister verwendet werden.  
  
 Im folgenden Beispiel wird C2432 generiert:  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```