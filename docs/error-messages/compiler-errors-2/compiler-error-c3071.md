---
title: Compilerfehler C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: 1debe431711681a98b9472c85864d84373ec42d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406638"
---
# <a name="compiler-error-c3071"></a>Compilerfehler C3071

Der „operator“-Operator kann nur auf eine Instanz einer Verweisklasse oder auf einen Werttyp angewendet werden.

Ein CLR-Operator kann nicht für einen systemeigenen Typ verwendet werden. Der Operator kann für eine Verweisklasse oder einer Referenzstruktur (Werttyp), jedoch nicht für einen systemeigenen Typ, z. B. Int, oder einen Alias für einen systemeigenen Typ, z. B. System::Int32 verwendet werden. Diese Typen können nicht vom C++-Code so geschachtelt werden, dass sie auf die systemeigene Variable verweisen, sodass der Operator nicht verwendet werden kann.

Weitere Informationen finden Sie unter [Verweisoperator nachverfolgung](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

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