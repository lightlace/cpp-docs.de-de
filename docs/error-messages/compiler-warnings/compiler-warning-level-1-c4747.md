---
title: Compilerwarnung (Stufe 1) C4747
ms.date: 11/04/2016
f1_keywords:
- C4747
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
ms.openlocfilehash: 623b29d345a850cc312f23e4c521aa0be5b47242
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052443"
---
# <a name="compiler-warning-level-1-c4747"></a>Compilerwarnung (Stufe 1) C4747

Der verwaltete "EntryPoint" wird aufgerufen: verwalteter Code darf nicht unter der Loadersperre ausgeführt werden, einschließlich des dll-Einstiegs Punkts und der Aufrufe, die vom DLL-Einstiegspunkt aus erreicht werden.

Der Compiler hat einen (wahrscheinlichen) DLL-Einstiegspunkt gefunden, der in MSIL kompiliert wurde.  Aufgrund möglicher Probleme beim Laden einer DLL, deren Einstiegspunkt in MSIL kompiliert wurde, wird dringend davon abgeraten, eine DLL-Einstiegspunkt Funktion in MSIL zu kompilieren.

Weitere Informationen finden Sie unter [Initialisierung gemischter](../../dotnet/initialization-of-mixed-assemblies.md) Assemblys und [Linker-Tools Error Linkertoolfehler LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Kompilieren Sie das Modul nicht mit **/CLR**.

1. Markieren Sie die Einstiegspunkt Funktion mit `#pragma unmanaged`.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4747 generiert.

```cpp
// C4747.cpp
// compile with: /clr /c /W1
// C4747 expected
#include <windows.h>

// Uncomment the following line to resolve.
// #pragma unmanaged

BOOL WINAPI DllMain(HANDLE hInstance, ULONG Command, LPVOID Reserved) {
   return TRUE;
};
```