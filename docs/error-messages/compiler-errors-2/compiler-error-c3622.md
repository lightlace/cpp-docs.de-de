---
title: Compilerfehler C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 2adcee4cb20c39c39b06e0ac2087478cfe2d8937
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740896"
---
# <a name="compiler-error-c3622"></a>Compilerfehler C3622

"Class": eine Klasse, die als "Schlüsselwort" deklariert wurde, kann nicht instanziiert werden.

Es wurde versucht, eine Klasse zu instanziieren, die als [abstrakt](../../extensions/abstract-cpp-component-extensions.md)markiert ist. Eine Klasse, die als `abstract` gekennzeichnet ist, kann eine Basisklasse sein, aber Sie kann nicht instanziiert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3622 generiert.

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
