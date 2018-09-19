---
title: Compilerfehler C3071 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f004de3ed133ea77d543014ae1adcdc4e1eddef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077801"
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