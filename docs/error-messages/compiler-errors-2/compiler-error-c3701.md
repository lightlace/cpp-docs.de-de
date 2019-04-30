---
title: Compilerfehler C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: 2efbf3c48b7c366d262facac9cebb4f72d9f1513
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344560"
---
# <a name="compiler-error-c3701"></a>Compilerfehler C3701

'Funktion': Ereignisquelle hat keine Ereignisse

Sie haben versucht, verwenden Sie [Event_source](../../windows/event-source.md) auf eine Klasse, die keine Ereignismethoden enthält. Um diesen Fehler zu beheben, fügen Sie ein oder mehrere Ereignisse der Klasse hinzu.

Im folgende Beispiel wird die C3701 generiert:

```
// C3701.cpp
[ event_source(native) ]
class CEventSrc {
public:
   // uncomment the following line to resolve this C3701
   // __event void fireEvent(int i);
};   // C3701

int main() {
}
```