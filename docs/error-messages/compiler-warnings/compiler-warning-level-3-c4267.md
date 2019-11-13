---
title: Compilerwarnung (Stufe 3) C4267
ms.date: 11/04/2016
f1_keywords:
- C4267
helpviewer_keywords:
- C4267
ms.assetid: 2fa2f13f-fa4f-47bb-ad8f-6cb19cfc91e6
ms.openlocfilehash: b49696632fb567a943b42ac35b8fc244e6cc4fb4
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051701"
---
# <a name="compiler-warning-level-3-c4267"></a>Compilerwarnung (Stufe 3) C4267

'var': Konvertierung von 'size_t' nach 'type', Datenverlust möglich

Der Compiler hat eine Konvertierung von `size_t` zu einem kleineren Typ ermittelt.

Verwenden Sie zum Beheben dieser Warnung `size_t` anstelle von `type`. Verwenden Sie alternativ einen integralen Typ, der mindestens so groß wie `size_t` ist.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Fehler C4267 generiert:

```cpp
// C4267.cpp
// compile by using: cl /W4 C4267.cpp
void Func1(short) {}
void Func2(int) {}
void Func3(long) {}
void Func4(size_t) {}

int main() {
   size_t bufferSize = 10;
   Func1(bufferSize);   // C4267 for all platforms
   Func2(bufferSize);   // C4267 only for 64-bit platforms
   Func3(bufferSize);   // C4267 only for 64-bit platforms
   Func4(bufferSize);   // OK for all platforms
}
```