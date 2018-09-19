---
title: Compilerwarnung (Stufe 1) C4747 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4747
dev_langs:
- C++
helpviewer_keywords:
- C4747
ms.assetid: af37befd-ba1f-4bdc-96e1-a953f7a2ad9c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d3eb5b83fedc7455cbf1b97119296a6eb6a1ab1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118478"
---
# <a name="compiler-warning-level-1-c4747"></a>Compilerwarnung (Stufe 1) C4747

Aufrufen von verwalteten "Entrypoint": verwalteter Code kann nicht ausgeführt werden, unter der Loadersperre, einschließlich des DLL-Einstiegspunkts und Aufrufen von DLL-Einstiegspunkt eingehen

Der Compiler hat einen (wahrscheinlichen) in MSIL kompilierte DLL-Einstiegspunkt gefunden.  Aufgrund der Probleme mit dem Laden einer DLL, deren Einstiegspunkt in MSIL kompiliert wurde, sind Sie dringend davon abgeraten, eine DLL-Einstiegspunktfunktion in MSIL kompiliert.

Weitere Informationen finden Sie unter [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md) und [Linkertoolfehler LNK1306](../../error-messages/tool-errors/linker-tools-error-lnk1306.md).

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Kompilieren Sie das Modul mit nicht **"/ CLR"**.

1. Markieren Sie die Einstiegspunktfunktion mit `#pragma unmanaged`.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4747 generiert.

```
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