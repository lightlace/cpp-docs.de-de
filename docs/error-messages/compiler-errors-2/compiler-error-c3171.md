---
title: Compilerfehler C3171 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3171
dev_langs:
- C++
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32c58f2ecd9651c347f45c29139ffe0ed65a6e3b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082260"
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