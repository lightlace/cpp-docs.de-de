---
title: "Compilerfehler C3899"
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
  - "C3899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3899"
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : Die Verwendung des L\-Werts eines initonly\-Datenmembers ist nicht direkt innerhalb eines parallelen Bereichs in der Klasse 'Klasse' zulässig  
  
 Ein [initonly](../../dotnet/initonly-cpp-cli.md)\-Datenmember kann nicht in dem Teil eines Konstruktors initialisiert werden, der sich innerhalb eines [parallel](../../parallel/openmp/reference/parallel.md)\-Bereichs befindet.  Der Grund hierfür ist, dass der Compiler intern eine Verschiebeung dieses Codes vornimmt, sodass der Code anschließend nicht mehr Teil des Konstruktors ist.  
  
 Um dieses Problem zu beheben, initialisieren Sie den initonly\-Datenmember im Konstruktor, aber außerhalb des parallelen Bereichs.  
  
## Beispiel  
 Im folgenden Beispiel wird C3899 generiert.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```