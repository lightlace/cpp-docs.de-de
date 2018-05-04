---
title: Novtable | Microsoft Docs
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
ms.openlocfilehash: 283ff09c320b67686e353f0497c665828cd8b5d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Dies ist ein erweitertes `__declspec`-Attribut.  
  
 Diese Form von `__declspec` kann auf eine beliebige Klassendeklaration angewendet werden. Sie sollte jedoch nur auf reine Schnittstellenklassen angewendet werden, d. h. auf Klassen, die nie separat instanziiert werden. Mit dem `__declspec`-Attribut wird die Codegenerierung des Compilers gestoppt, um "vfptr" im Konstruktor/in den Konstruktoren und dem Destruktor der Klasse zu initialisieren. In vielen Fällen werden hierdurch die einzigen Verweise auf "vtable" entfernt, die der Klasse zugeordnet sind, sodass der Linker diese entfernt. Mit dieser Form des `__declspec`-Attributs kann eine erhebliche Verringerung der Codegröße erreicht werden.  
  
 Wenn Sie versuchen, eine Klasse zu instanziieren, die mit `novtable` gekennzeichnet ist, und dann auf einen Klassenmember zugreifen, tritt eine Zugriffsverletzung (AV) auf.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
In Y  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [__declspec](../cpp/declspec.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)