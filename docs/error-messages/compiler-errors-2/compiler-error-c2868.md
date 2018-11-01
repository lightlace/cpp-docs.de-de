---
title: Compilerfehler C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: 4cb259ed0f43831226fb7e1a1ccf7b28bcef7819
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614772"
---
# <a name="compiler-error-c2868"></a>Compilerfehler C2868

> "*Bezeichner*": Unzulässige Syntax für using-Deklaration; vollständiger Name erwartet

Ein [using-Deklaration](../../cpp/using-declaration.md) erfordert eine *qualifizierten Namen*, einen Bereichsoperator (`::`) getrennte Sequenz mit Namespace, Klasse oder eines Enumerationswerts-Namen, die mit den Namen des Bezeichners endet. Ein einzelnes Bereichsauflösungsoperator kann verwendet werden, um einen Namen aus dem globalen Namespace einzuführen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2868 generiert und zeigt auch die richtige Verwendung:

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```