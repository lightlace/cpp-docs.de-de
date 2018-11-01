---
title: Compilerfehler C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 602c9ca1051646fca2c5788c036354047fad2522
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599476"
---
# <a name="compiler-error-c3171"></a>Compilerfehler C3171

"Module": können keine verschiedenen Modulattribute in einem Projekt

[Modul](../../windows/module-cpp.md) Attribute mit unterschiedlichen Parameterlisten wurden in zwei Dateien in einer Kompilierung gefunden. Nur ein eindeutiges `module` Attribut pro Kompilierung angegeben werden kann.

Identische `module` Attribute können in mehr als eine Quellcodedatei angegeben werden.

Z. B. wenn die folgenden `module` Attribute gefunden wurden:

```
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

und anschließend

```
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

der Compiler den Fehler C3171 (Beachten Sie die Werte für die andere Version).