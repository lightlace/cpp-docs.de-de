---
title: "novtable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "novtable"
  - "novtable_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], novtable"
  - "novtable __declspec-Schlüsselwort"
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# novtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Dies ist ein erweitertes `__declspec`\-Attribut.  
  
 Diese Form von `__declspec` kann auf eine beliebige Klassendeklaration angewendet werden. Sie sollte jedoch nur auf reine Schnittstellenklassen angewendet werden, d. h. auf Klassen, die nie separat instanziiert werden.  Mit dem `__declspec`\-Attribut wird die Codegenerierung des Compilers gestoppt, um "vfptr" im Konstruktor\/in den Konstruktoren und dem Destruktor der Klasse zu initialisieren.  In vielen Fällen werden hierdurch die einzigen Verweise auf "vtable" entfernt, die der Klasse zugeordnet sind, sodass der Linker diese entfernt.  Mit dieser Form des `__declspec`\-Attributs kann eine erhebliche Verringerung der Codegröße erreicht werden.  
  
 Wenn Sie versuchen, eine Klasse zu instanziieren, die mit `novtable` gekennzeichnet ist, und dann auf einen Klassenmember zugreifen, tritt eine Zugriffsverletzung \(AV\) auf.  
  
## Beispiel  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
  **In Y**   
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)