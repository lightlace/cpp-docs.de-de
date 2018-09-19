---
title: Linkertoolfehler Lnk1306 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1306
dev_langs:
- C++
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc007a4a594c8593d7820365377f1c811b1e23c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050566"
---
# <a name="linker-tools-error-lnk1306"></a>Linkertoolfehler LNK1306

> DLL-Einstiegspunktfunktion kann nicht verwaltet werden. als systemeigen kompilieren

`DllMain` kann nicht in MSIL kompiliert werden; Sie müssen in systemeigenen Code kompiliert werden.

Um dieses Problem zu beheben,

- Kompilieren Sie die Datei, die den Einstiegspunkt ohne enthält **"/ CLR"**.

- Fügen Sie den Einstiegspunkt in eine `#pragma unmanaged` Abschnitt.

Weitere Informationen finden Sie unter:

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [managed, unmanaged](../../preprocessor/managed-unmanaged.md)

- [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md)

- [DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](../../build/run-time-library-behavior.md)

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK1306 generiert.

```cpp
// LNK1306.cpp
// compile with: /clr /link /dll /entry:NewDllMain
// LNK1306 error expected
#include <windows.h>
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
```

Um dieses Problem zu beheben, verwenden Sie nicht die Option "/ CLR" Kompilieren Sie diese Datei oder ein `#pragma` Direktive, um die Definition der Eintrag Punkt in einem nicht verwalteten Abschnitt zu platzieren, wie im folgenden Beispiel gezeigt:

```cpp
// LNK1306fix.cpp
// compile with: /clr /link /dll /entry:NewDllMain
#include <windows.h>
#pragma managed(push, off)
int __stdcall NewDllMain( HINSTANCE h, ULONG ulReason, PVOID pvReserved ) {
   return 1;
}
#pragma managed(pop)
```
