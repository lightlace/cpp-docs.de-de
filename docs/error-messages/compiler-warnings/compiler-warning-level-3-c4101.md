---
title: Compilerwarnung (Stufe 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: 5effdbb4c7e83999655641a248c389c7c4d260d0
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051904"
---
# <a name="compiler-warning-level-3-c4101"></a>Compilerwarnung (Stufe 3) C4101

"Bezeichner": nicht referenzierte lokale Variable

Die lokale Variable wird nie verwendet. Diese Warnung wird in der offensichtlichen Situation angezeigt:

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Diese Warnung tritt jedoch auch beim Aufrufen einer **statischen** Element Funktion durch eine Instanz der-Klasse auf:

```cpp
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

In diesem Fall verwendet der Compiler Informationen zu `si`, um auf die **statische** Funktion zuzugreifen, aber die Instanz der Klasse ist nicht erforderlich, um die **statische** Funktion aufzurufen. Daher wird die Warnung angezeigt. Um diese Warnung zu beheben, können Sie folgende Aktionen ausführen:

- Fügen Sie einen Konstruktor hinzu, in dem der Compiler die Instanz von `si` im Aufruf`func`verwendet.

- Entfernen Sie das **static** -Schlüsselwort aus der Definition von `func`.

- Explizites Abrufen der **statischen** Funktion: `int y = S::func();`.