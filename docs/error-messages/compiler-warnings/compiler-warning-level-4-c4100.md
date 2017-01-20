---
title: "Compilerwarnung (Stufe 4) C4100"
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
  - "C4100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4100"
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Nicht referenzierter formaler Parameter  
  
 Auf den formalen Parameter wird im Funktionsrumpf nicht verwiesen.  Der nicht referenzierte Parameter wird ignoriert.  
  
 C4100 kann auch ausgelöst werden, wenn der Code einen Destruktor für einen anderweitig nicht referenzierten Parameter des primitiven Typs aufruft.  Dies ist eine Einschränkung des Visual C\+\+\-Compilers.  
  
 Im folgenden Beispiel wird C4100 generiert:  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```