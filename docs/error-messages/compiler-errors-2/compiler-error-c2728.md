---
title: Compilerfehler C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: ac9efa88fc4ab17a656172c44de2e49e82108108
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755667"
---
# <a name="compiler-error-c2728"></a>Compilerfehler C2728

'type' : Ein systemeigenes Array darf diesen Typ nicht enthalten.

Erstellung von Arraysyntax verwendet, um ein Array von verwalteten oder WinRT-Objekten zu erstellen. Sie können kein Array von verwalteten oder WinRT-Objekten mit systemeigener Array-Syntax erstellen.

Weitere Informationen finden Sie unter [Array](../../extensions/arrays-cpp-component-extensions.md).

Im folgenden Beispiel wird C2728 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
