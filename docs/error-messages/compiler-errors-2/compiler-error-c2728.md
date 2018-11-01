---
title: Compilerfehler C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 3e3584d5e9166bb57e3be56e33f0198cacace7c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615175"
---
# <a name="compiler-error-c2728"></a>Compilerfehler C2728

'type' : Ein systemeigenes Array darf diesen Typ nicht enthalten.

Erstellung von Arraysyntax verwendet, um ein Array von verwalteten oder WinRT-Objekten zu erstellen. Sie können kein Array von verwalteten oder WinRT-Objekten mit systemeigener Array-Syntax erstellen.

Weitere Informationen finden Sie unter [Array](../../windows/arrays-cpp-component-extensions.md).

Im folgenden Beispiel wird C2728 generiert und gezeigt, wie Sie diesen Fehler beheben:

```
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
