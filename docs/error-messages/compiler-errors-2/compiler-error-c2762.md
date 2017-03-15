---
title: "Compilerfehler C2762 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2762"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2762"
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2762
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Unzulässiger Ausdruck als Vorlagenargument für 'Argument'  
  
 Bei Verwendung von [\/Za](../../build/reference/za-ze-disable-language-extensions.md) konvertiert der Compiler eine ganze Zahl nicht in einen Zeiger.  
  
 Im folgenden Beispiel wird C2762 generiert:  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```