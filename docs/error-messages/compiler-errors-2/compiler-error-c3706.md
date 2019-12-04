---
title: Compilerfehler C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 810ec59a814b04349913648fb49a03eb63912cd9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757981"
---
# <a name="compiler-error-c3706"></a>Compilerfehler C3706

"Function": muss eine COM-Schnittstelle zum Auslösen von COM-Ereignissen sein.

Die Ereignis Schnittstelle, mit der com-Ereignisse ausgelöst werden, muss eine COM-Schnittstelle sein. In dieser Situation muss die Schnittstelle entweder mit einem visuellen C++ Attribut definiert oder mithilfe von [#Import](../../preprocessor/hash-import-directive-cpp.md) aus einer Typbibliothek mit dem embedded_idl-Attribut des #Import importiert werden.

Beachten Sie, dass die `#include` Zeilen der ATL-Header Dateien, die im folgenden Beispiel angezeigt werden, für die Verwendung von COM-Ereignissen erforderlich sind. Um diesen Fehler zu beheben, stellen Sie `IEvents` (die Ereignis Schnittstelle) zu einer COM-Schnittstelle, indem Sie eines der folgenden Attribute auf die Schnittstellen Definition anwenden: [Object](../../windows/object-cpp.md), [Dual](../../windows/dual.md)oder [dispinterface](../../windows/dispinterface.md).

Wenn eine Schnittstelle aus einer von "Mittel l" generierten Header Datei besteht, wird Sie vom Compiler nicht als COM-Schnittstelle erkannt.

Im folgenden Beispiel wird C3706 generiert:

```cpp
// C3706.cpp
// compile with: /c
// C3706 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following line to resolve.
// [object, uuid="12341234-1234-1234-1234-123412341237"]
__interface IEvents : IUnknown {
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]
};

[dual, uuid="12341234-1234-1234-1234-123412341235"]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]
class CEventSrc : public IBase {
   public:
   __event __interface IEvents;

   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```
