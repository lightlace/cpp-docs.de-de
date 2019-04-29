---
title: Compilerwarnung (Stufe 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: d1109a32e754a6055e5e1d90632ad85332d832f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402319"
---
# <a name="compiler-warning-level-3-c4101"></a>Compilerwarnung (Stufe 3) C4101

"Bezeichner": Unreferenzierte lokale Variable

Die lokale Variable wird nie verwendet. Diese Warnung wird in der offensichtlichen Situation auftreten:

```
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Aber diese Warnung tritt auch beim Aufrufen einer **statische** Member-Funktion durch eine Instanz der Klasse:

```
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

In diesem Fall verwendet der Compiler Informationen über `si` für den Zugriff auf die **statische** -Funktion, aber die Instanz der Klasse ist nicht erforderlich, um das Aufrufen der **statische** Funktion daher die Warnung. Um diese Warnung zu beheben, können Sie folgende Aktionen ausführen:

- Fügen Sie einen Konstruktor, in denen der Compiler die Instanz von verwenden würden `si` im Aufruf von `func`.

- Entfernen Sie die **statische** Schlüsselwort aus der Definition der `func`.

- Rufen Sie die **statische** -Funktion legt explizit: `int y = S::func();`.