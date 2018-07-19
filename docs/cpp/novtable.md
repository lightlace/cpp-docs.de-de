---
title: Novtable | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad0c50330d174a6139ce6e588b278e03cd99562
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943610"
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Dies ist eine **__declspec** erweitertes Attribut.  
  
 Diese Form der **__declspec** kann auf eine beliebige Klassendeklaration angewendet werden, aber nur auf reine Schnittstellenklassen, d. h. Klassen, die auf ihre eigenen nie instanziiert werden angewendet werden soll. Die **__declspec** beendet den Compiler generiert Code, um die Vfptr in den Konstruktoren und der Destruktor der Klasse zu initialisieren. In vielen Fällen werden hierdurch die einzigen Verweise auf "vtable" entfernt, die der Klasse zugeordnet sind, sodass der Linker diese entfernt. Mit dieser Form des **__declspec** kann zu einer erheblichen Verringerung Codegröße führen.  
  
 Wenn Sie versuchen, eine Klasse zu instanziieren, die mit `novtable` gekennzeichnet ist, und dann auf einen Klassenmember zugreifen, tritt eine Zugriffsverletzung (AV) auf.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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
  
```Output  
In Y  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)