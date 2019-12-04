---
title: Compilerfehler C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: e2d74a637e2902fcf636b49068882f32aa706f94
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761763"
---
# <a name="compiler-error-c3170"></a>Compilerfehler C3170

in einem Projekt können keine unterschiedlichen Modul Bezeichner vorhanden sein.

[Modul](../../windows/module-cpp.md) Attribute mit unterschiedlichen Namen wurden in zwei Dateien einer Kompilierung gefunden. Pro Kompilierung kann nur ein eindeutiges `module` Attribut angegeben werden.

Identische `module` Attribute können in mehr als einer Quell Code Datei angegeben werden.

Wenn z. b. die folgenden Modul Attribute gefunden wurden:

```cpp
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

und anschließend

```cpp
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

der Compiler generiert C3170 (Beachten Sie die unterschiedlichen Namen).
