---
title: Compilerfehler C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: 2ebcce496fd06c30420558d80cc0a0c9318d4376
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173419"
---
# <a name="compiler-error-c3480"></a>Compilerfehler C3480

"Var": Eine Lambdaerfassungsvariable muss aus einem einschließenden Funktionsbereich stammen.

Die Lambdaerfassungsvariable stammt nicht aus einem einschließenden Funktionsbereich.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Entfernen Sie die Variable aus der Erfassungsliste des Lambda-Ausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3480 generiert, da die Variable `global` nicht aus einem einschließenden Funktionsbereich stammt:

```
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3480 durch Entfernen der Variablen `global` aus der Erfassungsliste des Lambdaausdrucks behoben:

```
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)