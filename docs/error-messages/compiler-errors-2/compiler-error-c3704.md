---
title: Compilerfehler C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 11e5792344b6f8fba6183f4ab87e1799db803b46
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757942"
---
# <a name="compiler-error-c3704"></a>Compilerfehler C3704

"Function": eine vararg-Methode kann keine Ereignisse auslösen.

Sie haben versucht, [__event](../../cpp/event.md) für eine vararg-Methode zu verwenden. Um diesen Fehler zu beheben, ersetzen Sie den `fireEvent(int i, ...)`-Befehl durch den `fireEvent(int i)`-Befehl, wie im folgenden Codebeispiel gezeigt.

Im folgenden Beispiel wird C3704 generiert:

```cpp
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```
