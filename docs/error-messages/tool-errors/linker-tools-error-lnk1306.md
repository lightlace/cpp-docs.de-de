---
title: Linkertoolfehler LNK1306
ms.date: 11/04/2016
f1_keywords:
- LNK1306
helpviewer_keywords:
- LNK1306
ms.assetid: fad1df6a-0bd9-412f-b0d1-7c9bc749c584
ms.openlocfilehash: ddaa8797e0cf8ff617408aedc770b21cc656cec4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659669"
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
