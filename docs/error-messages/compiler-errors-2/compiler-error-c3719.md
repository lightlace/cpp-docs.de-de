---
title: Compilerfehler C3719 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3719
dev_langs:
- C++
helpviewer_keywords:
- C3719
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04761008bd7dcdfa9ecb8dc1d6c24be4a67a6360
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047862"
---
# <a name="compiler-error-c3719"></a>Compilerfehler C3719

'Schnittstelle': eine Ereignisquelle für die Schnittstelle basiert kann nur für COM-Ereignisse verwendet werden

Sie haben eine Schnittstelle in einem nicht-COM-Kontext deklariert.

Im folgende Beispiel wird die C3719 generiert:

```
// C3719a.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];

[object]
__interface I {
   HRESULT func1();
};

[event_source(native), coclass]
struct A {
   __event __interface I;   // C3719

   // try the following line instead
   // __event func2();
};

int main() {
}
```

Um diesen Fehler zu beheben, wenden die [Objekt](../../windows/object-cpp.md), [Co-Klasse](../../windows/coclass.md), [Event_source](../../windows/event-source.md), und [Event_receiver](../../windows/event-receiver.md) Attribute entsprechend um machen die Klassen, die in denen Sie die Schnittstelle COM-Klassen verwenden. Zum Beispiel:

```
// C3719b.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[module(name="xx")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I {
   HRESULT f();
};

[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]
struct MyStruct {
   __event __interface I;
};

[event_receiver(com)]
struct MyStruct2 {
   void f() {
   }
   MyStruct2(I* pB) {
      __hook(&I::f, pB, &MyStruct2::f);
   }
};

int main()
{
}
```