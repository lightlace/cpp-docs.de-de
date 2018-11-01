---
title: Compilerfehler C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 69565a1a2d159623bca927a94543834d18c13299
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518091"
---
# <a name="compiler-error-c3622"></a>Compilerfehler C3622

'Klasse': eine Klasse deklariert werden, da 'Schlüsselwort' kann nicht instanziiert werden

Es wurde versucht, zum Instanziieren einer Klasse, die als [abstrakte](../../windows/abstract-cpp-component-extensions.md). Eine Klasse als markiert `abstract` kann eine Basisklasse sein, aber nicht instanziiert werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3622 generiert.

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
