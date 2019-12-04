---
title: Compilerfehler C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: 94a6f180c93839646d771509145b2f65a00780fd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746863"
---
# <a name="compiler-error-c2505"></a>Compilerfehler C2505

' Symbol ': ' __declspec (Modifizierer) ' kann nur auf Deklarationen oder Definitionen globaler Objekte oder statischer Datenmember angewendet werden.

Ein `__declspec` Modifizierer, der nur für den globalen Gültigkeitsbereich verwendet werden soll, wurde in einer Funktion verwendet.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).

Im folgenden Beispiel wird C2505 generiert:

```cpp
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
