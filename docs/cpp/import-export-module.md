---
title: module, import, export
ms.date: 07/15/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Verwenden Sie die Import-Anweisung für den Zugriff auf Typen und Funktionen, die im angegebenen Modul definiert sind.
ms.openlocfilehash: ee1d50a76a3304359c0771aa0174968439f5faa4
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273625"
---
# <a name="module-import-export"></a>module, import, export

Die Schlüsselwörter " **Module**", " **Import**" und " **Export** " sind in c++ 20 verfügbar und erfordern den [/experimental: Module](../build/reference/experimental-module.md) -Compilerschalter zusammen mit [/Std: C + + Latest](../build/reference/std-specify-language-standard-version.md). Weitere Informationen finden Sie unter [Übersicht über Module in C++ ](modules-cpp.md).

## <a name="module"></a>module

Verwenden Sie die **Module** -Anweisung am Anfang einer Modul Implementierungs Datei, um anzugeben, dass der Dateiinhalt zum benannten Modul gehört. 

```cpp
module ModuleA;
```

## <a name="export"></a>"export"

Verwenden Sie die **Export Module** -Anweisung für die primäre Schnittstellen Datei des Moduls, die die Erweiterung **. IXX**aufweisen muss:

```cpp
export module ModuleA;
```

Verwenden Sie in einer Schnittstellen Datei den **exportmodifizierer** für Namen, die Teil der öffentlichen Schnittstelle sein sollen:

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

Nicht exportierte Namen sind für Code, der das Modul importiert, nicht sichtbar:

```cpp
//MyProgram.cpp

import module ModuleA;

void main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

Das **Export** Schlüsselwort wird möglicherweise nicht in einer Modul Implementierungs Datei angezeigt. Wenn der **Export** -Modifizierer auf einen Namespace Namen angewendet wird, werden alle Namen im-Namespace exportiert.

## <a name="import"></a>import

Verwenden Sie die **Import** -Anweisung, um die Namen eines Moduls in Ihrem Programm sichtbar zu machen. Die Import-Anweisung muss nach der Modul Anweisung und nach allen #include Anweisungen, aber vor allen Deklarationen in der Datei angezeigt werden.

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="see-also"></a>Siehe auch

[Übersicht über Module inC++](modules-cpp.md)
