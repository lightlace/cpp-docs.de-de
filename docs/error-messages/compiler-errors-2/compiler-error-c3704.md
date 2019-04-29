---
title: Compilerfehler C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 4e26742de6c294018f81c6f49c1719fdb11d5149
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328535"
---
# <a name="compiler-error-c3704"></a>Compilerfehler C3704

'Funktion': eine Vararg-Methode kann keine Ereignisse auslösen

Sie haben versucht, verwenden Sie [__event](../../cpp/event.md) für eine Vararg-Methode. Um diesen Fehler zu beheben, ersetzen die `fireEvent(int i, ...)` rufen Sie mit der `fireEvent(int i)` rufen, wie im folgenden Codebeispiel gezeigt.

Im folgende Beispiel wird die C3704 generiert:

```
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