---
title: Compilerfehler C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: 6960dbf62fd30b822f0d7c7a3c46a29a4115913f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428352"
---
# <a name="compiler-error-c3071"></a>Compilerfehler C3071

Der „operator“-Operator kann nur auf eine Instanz einer Verweisklasse oder auf einen Werttyp angewendet werden.

Ein CLR-Operator kann nicht für einen systemeigenen Typ verwendet werden. Der Operator kann für eine Verweisklasse oder einer Referenzstruktur (Werttyp), jedoch nicht für einen systemeigenen Typ, z. B. Int, oder einen Alias für einen systemeigenen Typ, z. B. System::Int32 verwendet werden. Diese Typen können nicht vom C++-Code so geschachtelt werden, dass sie auf die systemeigene Variable verweisen, sodass der Operator nicht verwendet werden kann.

Weitere Informationen finden Sie unter [Verweisoperator nachverfolgung](../../windows/tracking-reference-operator-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3071 generiert.

```
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```