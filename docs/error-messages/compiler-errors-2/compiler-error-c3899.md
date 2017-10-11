---
title: Compilerfehler C3899 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c7d9d32b3063dbecde375159ad90eec5bf128d56
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3899"></a>Compilerfehler C3899
"Var": l-Wert-Verwendung von Initonly-Datenmember ist direkt innerhalb eines parallelen Bereichs in Klasse 'Klasse' nicht zulässig  
  
 Ein [Initonly (C + c++ / CLI)](../../dotnet/initonly-cpp-cli.md) -Datenmember kann nicht initialisiert werden, in diesem Teil einen Konstruktor, der in einem [parallele](../../parallel/openmp/reference/parallel.md) Region.  Dies ist, da der Compiler eine interne Verschiebungen dieses Codes ist, sodass er effektiv nicht mehr Teil des Konstruktors ist.  
  
 Initialisieren Sie zum Beheben der Initonly-Datenmember im Konstruktor, aber außerhalb des parallelen Bereichs ein.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3899 generiert.  
  
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
