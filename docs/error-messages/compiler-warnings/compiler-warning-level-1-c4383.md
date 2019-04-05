---
title: Compilerwarnung (Stufe 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 2510dda59047632e2a4823f734feeffd0c0a5b02
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778038"
---
# <a name="compiler-warning-level-1-c4383"></a>Compilerwarnung (Stufe 1) C4383

'Instanzendereferenzierungsoperator': die Bedeutung der Dereferenzierung eines Handles kann sich ändern, wenn ein User-defined 'Operator' Operator vorhanden ist. Schreiben Sie den Operator als statische Funktion, damit der Operand explizit sein.

Wenn Sie eine benutzerdefinierte Instanz zum Überschreiben der Dereferenzierungsoperator in einem verwalteten Typ hinzufügen, überschreiben Sie potenziell die Fähigkeit der Dereferenzierungsoperator des Typs, das Handle des Objekts zurückzugeben. Berücksichtigen Sie beim Schreiben eines statischen, benutzerdefinierten Dereferenzierungsoperator.

Weitere Informationen finden Sie unter [Handle für Objekt (^)](../../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) und [Verweisoperator nachverfolgung](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

Darüber hinaus steht ein Instanzenoperator nicht andere Sprachcompiler über Metadaten verwiesen wird. Weitere Informationen finden Sie unter [User-Defined Operators (C++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4383 generiert.

```
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