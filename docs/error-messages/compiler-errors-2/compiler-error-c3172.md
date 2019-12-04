---
title: Compilerfehler C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 1da2676d660d23e3fb71b56263779b1f1edacbf9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761737"
---
# <a name="compiler-error-c3172"></a>Compilerfehler C3172

"module_name": in einem Projekt können keine unterschiedlichen idl_module Attribute angegeben werden.

in zwei Dateien in einer Kompilierung wurden [idl_module](../../windows/idl-module.md) Attribute mit demselben Namen, aber unterschiedlichen `dllname`-oder `version` Parametern gefunden. Pro Kompilierung kann nur ein eindeutiges `idl_module` Attribut angegeben werden.

Identische `idl_module` Attribute können in mehr als einer Quell Code Datei angegeben werden.

Beispielsweise, wenn die folgenden `idl_module` Attribute gefunden wurden:

```cpp
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

und anschließend

```cpp
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

der Compiler generiert C3172 (Beachten Sie die verschiedenen Versions Werte).
