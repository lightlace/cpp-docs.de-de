---
title: Compilerwarnung (Stufe 3) C4101 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1549a327329d438cb30bd6908e07419eb1b6bc1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060836"
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