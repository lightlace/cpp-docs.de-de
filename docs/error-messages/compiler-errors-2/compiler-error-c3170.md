---
title: Compilerfehler C3170 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7a193abcd59c3e9454eec1108f1e3bbb66efcc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070365"
---
# <a name="compiler-error-c3170"></a>Compilerfehler C3170

in einem Projekt können nicht verschiedene Modulbezeichner haben werden.

[Modul](../../windows/module-cpp.md) Attribute mit unterschiedlichen Namen wurden in zwei Dateien in einer Kompilierung gefunden. Nur ein eindeutiges `module` Attribut pro Kompilierung angegeben werden kann.

Identische `module` Attribute können in mehr als eine Quellcodedatei angegeben werden.

Wenn beispielsweise die folgenden Attribute des Moduls gefunden wurden:

```
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

und anschließend

```
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

der Compiler den Fehler C3170 (Beachten Sie die verschiedenen Namen).