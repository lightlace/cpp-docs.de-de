---
title: Compilerwarnung (Stufe 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 9681408841173bad4aca3305e727ddde6cd98f14
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966174"
---
# <a name="compiler-warning-level-1-c4383"></a>Compilerwarnung (Stufe 1) C4383

' Instance_dereference_operator ': die Bedeutung der Dereferenzierung eines Handles kann sich ändern, wenn ein benutzerdefinierter Operator Operator vorhanden ist. Schreiben Sie den Operator als statische Funktion, um explizit über den Operanden zu verfügen.

Wenn Sie eine benutzerdefinierte instanzüberschreibung des Dereferenzierungsoperators in einem verwalteten Typ hinzufügen, überschreiben Sie möglicherweise die Fähigkeit des Dereferenzierungsoperators des Typs, das-Objekt des Handles zurückzugeben. Schreiben Sie ggf. einen statischen, benutzerdefinierten Dereferenzierungsoperator.

Weitere Informationen finden Sie unter [handle to Object Operator (^)](../../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) und [Tracking Reference Operator](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

Außerdem ist ein instanzoperator für andere sprach Compiler über Metadaten, auf die verwiesen wird, nicht verfügbar. Weitere Informationen finden Sie unter [benutzerdefinierte Operatoren (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4383 generiert.

```cpp
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```