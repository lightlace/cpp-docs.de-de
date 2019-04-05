---
title: Probleme bei Inlinefunktionen
ms.date: 11/04/2016
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
ms.openlocfilehash: fec3884dff0dda7140f18fa53e493c12996edcf0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031523"
---
# <a name="function-inlining-problems"></a>Probleme bei Inlinefunktionen

Wenn Sie Inlinefunktionen verwenden, müssen Sie folgende Schritte ausführen:

- Haben Sie die Inlinefunktionen, die implementiert werden, in der Headerdatei, die Sie aufnehmen.

- Haben inlining in der Headerdatei aktiviert.

```
// LNK2019_function_inline.cpp
// compile with: /c
// post-build command: lib LNK2019_function_inline.obj
#include <stdio.h>
struct _load_config_used {
   void Test();
   void Test2() { printf("in Test2\n"); }
};

void _load_config_used::Test() { printf("in Test\n"); }
```

und anschließend

```
// LNK2019_function_inline_2.cpp
// compile with: LNK2019_function_inline.lib
struct _load_config_used {
   void Test();
   void Test2();
};

int main() {
   _load_config_used x;
   x.Test();
   x.Test2();   // LNK2019
}
```

Bei Verwendung der `#pragma inline_depth` Compiler, stellen Sie sicher, dass Sie einen Wert von 2 oder höher festgelegt haben. Der Wert 0 (null) deaktiviert inlineersetzung. Stellen Sie außerdem sicher, dass Sie die **/Ob1** oder **/Ob2** Compileroptionen.

Das Kombinieren von Inline- und nicht Kompilierungsoptionen auf verschiedene Module kann gelegentlich Probleme verursachen. Wenn eine C++-Bibliothek mit Inlinefunktionen eingeschaltet erstellt wird ([/Ob1](../../build/reference/ob-inline-function-expansion.md) oder [/Ob2](../../build/reference/ob-inline-function-expansion.md)) jedoch die entsprechende Headerdatei, beschreibt die Funktionen hat inlining (keine Option) deaktiviert, erhalten Sie die Fehlermeldung LNK2001. Die Funktionen sind nicht "inline" in den Code aus der Headerdatei, aber da sie nicht in der Library-Datei können keine Adresse auflösen des Verweises vorhanden ist.

Auf ähnliche Weise definiert ein Projekt, verwendet der inlineersetzung, noch die Funktionen in einer CPP-Datei anstelle Datei in der Kopfzeile auch LNK2019 erhält. Die Header-Datei enthalten ist überall als geeignet, aber die Funktionen sind nur inline, wenn die CPP-Datei durch den Compiler; übergibt aus diesem Grund wird der Linker die Funktionen als nicht aufgelöste externe bei der Verwendung in anderen Modulen angezeigt.

```
// LNK2019_FIP.h
struct testclass {
   void PublicStatMemFunc1(void);
};
```

Und dann

```
// LNK2019_FIP.cpp
// compile with: /c
#include "LNK2019_FIP.h"
inline void testclass::PublicStatMemFunc1(void) {}
```

Und dann

```
// LNK2019_FIP_2.cpp
// compile with: LNK2019_FIP.cpp
// LNK2019 expected
#include "LNK2019_FIP.h"
int main() {
   testclass testclsObject;

   // module cannot see the implementation of PublicStatMemFunc1
   testclsObject.PublicStatMemFunc1();
}
```

## <a name="see-also"></a>Siehe auch

[Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)