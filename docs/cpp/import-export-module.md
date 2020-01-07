---
title: module, import, export
ms.date: 12/12/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Verwenden Sie Import-und Export Deklarationen zum Zugreifen auf und zum Veröffentlichen von Typen und Funktionen, die im angegebenen Modul definiert sind.
ms.openlocfilehash: ae28bce8e06840cafa5c92521f6e9a62aa5bfde6
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301456"
---
# <a name="module-import-export"></a>module, import, export

Die **Module**-, **Import**-und **Export** Deklarationen sind in c++ 20 verfügbar und erfordern den [/experimental: Module](../build/reference/experimental-module.md) -Compilerschalter zusammen mit [/Std: C + + Latest](../build/reference/std-specify-language-standard-version.md). Weitere Informationen finden Sie unter [Übersicht über Module in C++ ](modules-cpp.md).

## <a name="module"></a>module

Legen Sie eine **Modul** Deklaration am Anfang einer Modul Implementierungs Datei ab, um anzugeben, dass der Dateiinhalt zum benannten Modul gehört.

```cpp
module ModuleA;
```

## <a name="export"></a>export

Verwenden Sie für die primäre Schnittstellen Datei des Moduls eine **Export Modul** Deklaration, die die Erweiterung **. IXX**aufweisen muss:

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

Das **Export** Schlüsselwort wird möglicherweise nicht in einer Modul Implementierungs Datei angezeigt. Wenn **Export** auf einen Namespace Namen angewendet wird, werden alle Namen im-Namespace exportiert.

## <a name="import"></a>import

Verwenden Sie eine **Import** Deklaration, um die Namen eines Moduls in Ihrem Programm sichtbar zu machen. Die Import Deklaration muss nach der Modul Deklaration und nach allen #include Direktiven, aber vor allen Deklarationen in der Datei stehen.

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

## <a name="remarks"></a>Hinweise

**Import** und **Module** werden nur dann als Schlüsselwörter behandelt, wenn Sie am Anfang einer logischen Zeile angezeigt werden:

```cpp

// OK:
module ;
module module-name
import :
import <
import "
import module-name
export module ;
export module module-name
export import :
export import <
export import "
export import module-name

// Error:
int i; module ;
```

**Microsoft-spezifisch**

In Microsoft C++sind der Token- **Import** und das- **Modul** immer Bezeichner und nie-Schlüsselwörter, wenn Sie als Argumente für ein Makro verwendet werden.

### <a name="example"></a>Beispiel

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Übersicht über Module inC++](modules-cpp.md)
