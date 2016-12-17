---
title: "Compilerwarnung (Stufe 4) C4366"
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
  - "C4366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4366"
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Ergebnis des unären Operators 'Operator' ist möglicherweise nicht ausgerichtet  
  
 Wenn ein Strukturmember aufgrund von Komprimierung nicht ausgerichtet sein könnte, gibt der Compiler eine Warnmeldung aus, wenn die Adresse dieses Members einem ausgerichteten Zeiger zugewiesen wird.  In der Standardeinstellung sind alle Zeiger ausgerichtet.  
  
 Zur Behebung von C4366 ändern Sie entweder die Ausrichtung der Struktur, oder Sie deklarieren den Zeiger mit dem [\_\_unaligned](../../cpp/unaligned.md)\-Schlüsselwort.  
  
 Weitere Informationen finden Sie unter \_\_unaligned und [pack](../../preprocessor/pack.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4366 generiert.  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```