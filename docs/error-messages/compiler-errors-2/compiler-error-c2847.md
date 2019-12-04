---
title: Compilerfehler C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: b8b31dc461c1d589151701c6946f6ac1a95c5517
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738985"
---
# <a name="compiler-error-c2847"></a>Compilerfehler C2847

sizeof kann nicht auf verwalteten oder WinRT-Typ „Klasse“ angewendet werden.

Der [sizeof](../../cpp/sizeof-operator.md) -Operator Ruft den Wert eines Objekts zur Kompilierzeit ab. Die Größe einer verwalteten oder WinRT-Klasse, Schnittstelle oder eines Werttyps ist dynamisch und ist zur Kompilierzeit nicht bekannt.

Im folgenden Beispiel wird C2847 generiert:

```cpp
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
