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
ms.openlocfilehash: 2de25452d708545481bdc4a65cab998930b2778e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068430"
---
# <a name="novtable"></a>novtable

## <a name="microsoft-specific"></a>Microsoft-spezifisch

Dies ist eine **__declspec** erweitertes Attribut.

Diese Form der **__declspec** kann auf eine beliebige Klassendeklaration angewendet werden, aber nur auf reine Schnittstellenklassen, d. h. Klassen, die auf ihre eigenen nie instanziiert werden angewendet werden soll. Die **__declspec** beendet den Compiler generiert Code, um die Vfptr in den Konstruktoren und der Destruktor der Klasse zu initialisieren. In vielen Fällen werden hierdurch die einzigen Verweise auf "vtable" entfernt, die der Klasse zugeordnet sind, sodass der Linker diese entfernt. Mit dieser Form des **__declspec** kann zu einer erheblichen Verringerung Codegröße führen.

Wenn Sie versuchen, eine Klasse, die mit instanziieren **Novtable** , und klicken Sie dann auf einen Klassenmember zuzugreifen, erhalten Sie eine zugriffsverletzung (AV).

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

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)