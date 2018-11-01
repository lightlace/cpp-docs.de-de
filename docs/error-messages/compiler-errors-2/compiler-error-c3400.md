---
title: Compilerfehler C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: 70d23e22780b6efc8220675655d8ed095ca50bab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557377"
---
# <a name="compiler-error-c3400"></a>Compilerfehler C3400

Zirkuläre Einschränkungsabhängigkeit mit „constraint_1“ und „constraint_2“

Der Compiler hat zirkuläre Einschränkungen erkannt.

Weitere Informationen finden Sie unter [Einschränkungen für generische Typparameter (C++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3400 generiert:

```
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```