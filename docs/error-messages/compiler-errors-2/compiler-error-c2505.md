---
title: Compilerfehler C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: bf5ffb9b6bad3db1d264941a6aefa391be521c98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165037"
---
# <a name="compiler-error-c2505"></a>Compilerfehler C2505

'Symbol': '__declspec(modifer)' kann nur auf Deklarationen oder Definitionen globaler Objekte oder statischer Datenmember angewendet werden

Ein `__declspec` Modifizierer, die nur im globalen Gültigkeitsbereich verwendet werden soll, wurde in einer Funktion verwendet.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).

Im folgende Beispiel wird die C2505 generiert:

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```