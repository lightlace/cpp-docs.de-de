---
title: "Compilerfehler C2229 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2229"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2229"
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2229
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Typ 'Bezeichner' enthält ein Array der unzulässigen Größe 0 \(null\).  
  
 Ein Member einer Struktur oder eines Bitfelds enthält ein Array der Größe 0 \(null\), bei dem es sich nicht um den letzten Member handelt.  
  
 Da Sie als letzten Member einer Struktur ein Array der Größe 0 \(null\) verwenden können, müssen Sie beim Zuweisen der Struktur seine Größe angeben.  
  
 Wenn das Array der Größe 0 \(null\) nicht der letzte Member der Struktur ist, ist der Compiler nicht in der Lage, den Offset für die übrigen Felder zu berechnen .  
  
 Im folgenden Beispiel wird C2229 generiert:  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```