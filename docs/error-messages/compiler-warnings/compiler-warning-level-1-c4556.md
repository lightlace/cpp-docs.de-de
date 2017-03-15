---
title: "Compilerwarnung (Stufe 1) C4556 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "xml"
  - "C4556"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4556"
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4556
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wert des systeminternen unmittelbaren Arguments 'Wert' liegt außerhalb des Bereichs 'lowerbound \- upperbound'  
  
 Ein als intrinsic deklariertes Element stimmt mit einer Hardwareanweisung überein.  Die Hardwareanweisung verfügt über eine feste Anzahl von Bits zur Codierung der Konstanten.  Wenn der ***Wert*** außerhalb des Gültigkeitsbereichs liegt, findet keine fehlerfreie Codierung statt.  Der Compiler schneidet die zusätzlichen Bits ab.  
  
 Im folgenden Beispiel wird C4556 generiert:  
  
```  
// C4556.cpp  
// compile with: /W1  
// processor: x86 IPF  
#include <xmmintrin.h>  
void test()  
{  
   __m64 m;  
   _m_pextrw(m, 5);   // C4556  
}  
int main()  
{  
}  
```