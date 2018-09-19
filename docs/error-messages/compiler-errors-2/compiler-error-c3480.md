---
title: Compilerfehler C3480 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3480
dev_langs:
- C++
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd58a8c38ee6dc5f77ef280ba3b7a546a666cd6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107858"
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