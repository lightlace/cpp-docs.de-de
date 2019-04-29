---
title: Compilerfehler C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 2d474db5a4d50aed7b59e6f48fb5a3e8165f10c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400291"
---
# <a name="compiler-error-c3706"></a>Compilerfehler C3706

'Funktion': muss eine COM-Schnittstelle zum Auslösen von COM-Ereignisse

Die Schnittstelle, mit denen Sie COM-Ereignisse auslösen muss es sich um eine COM-Schnittstelle sein. In diesem Fall die Schnittstelle sollte entweder definiert werden mit einem visuellen C++ Attribut- oder importierten mit [#import](../../preprocessor/hash-import-directive-cpp.md) aus einer Typbibliothek mit #import Embedded_idl-Attribut.

Beachten Sie, dass die `#include` Codezeilen die ATL-Headerdateien, die im folgenden Beispiel gezeigt sind erforderlich, für die Verwendung von COM-Ereignisse. Um diesen Fehler zu beheben, stellen `IEvents` (die ereignisauslösende Schnittstelle) eine COM-Schnittstelle durch Anwenden eines der folgenden Attribute auf die Schnittstellendefinition: [Objekt](../../windows/object-cpp.md), [dual](../../windows/dual.md), oder [ Dispinterface](../../windows/dispinterface.md).

Ist eine Schnittstelle aus einer Headerdatei, die von MIDL generiert werden, werden Sie von vom Compiler nicht als COM-Schnittstelle erkannt.

Im folgende Beispiel wird die C3706 generiert:

```
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