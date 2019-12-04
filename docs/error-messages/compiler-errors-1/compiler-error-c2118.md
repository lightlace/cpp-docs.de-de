---
title: Compilerfehler C2118
ms.date: 11/04/2016
f1_keywords:
- C2118
helpviewer_keywords:
- C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
ms.openlocfilehash: 944109ba3531f2e3fca50300f26000fdaf850d19
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755199"
---
# <a name="compiler-error-c2118"></a>Compilerfehler C2118

negativer Index

Der Wert, der die Array Größe definiert, ist größer als die maximale Array Größe oder kleiner als 0 (null).

Im folgenden Beispiel wird C2118 generiert:

```cpp
// C2118.cpp
int main() {
   int array1[-1];   // C2118
   int array2[3];   // OK
}
```
