---
title: Compilerfehler C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 5c9c1561b63c740b9f7f5d85b2bf3e04de2542c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175185"
---
# <a name="compiler-error-c3172"></a>Compilerfehler C3172

"Modulname": Geben Sie unterschiedliche Idl_module-Attribute können nicht in einem Projekt

[Idl_module](../../windows/idl-module.md) Attribute mit demselben Namen, aber unterschiedliche `dllname` oder `version` Parameter wurden in zwei Dateien in einer Kompilierung gefunden. Nur ein eindeutiges `idl_module` Attribut pro Kompilierung angegeben werden kann.

Identische `idl_module` Attribute können in mehr als eine Quellcodedatei angegeben werden.

Z. B. wenn die folgenden `idl_module` Attribute gefunden wurden:

```
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

und anschließend

```
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

der Compiler den Fehler C3172 (Beachten Sie die Werte für die andere Version).