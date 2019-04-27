---
title: Compilerfehler C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: 99c49be746cea6fb80c5e24667bcd97556a0ad04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161042"
---
# <a name="compiler-error-c2847"></a>Compilerfehler C2847

sizeof kann nicht auf verwalteten oder WinRT-Typ „Klasse“ angewendet werden.

Die ["sizeof"](../../cpp/sizeof-operator.md) Operator Ruft den Wert eines Objekts zum Zeitpunkt der Kompilierung. Die Größe einer verwalteten oder WinRT-Klasse, Schnittstelle oder eines Werttyps ist dynamisch und ist zur Kompilierzeit nicht bekannt.

Im folgenden Beispiel wird C2847 generiert:

```
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
