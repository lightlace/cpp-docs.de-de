---
title: Compilerfehler C3484 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3484
dev_langs:
- C++
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a79574f85d05c6b1ac32416509ba1f8c05e26b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019185"
---
# <a name="compiler-error-c3484"></a>Compilerfehler C3484

Vor dem Rückgabetyp wird '->' erwartet.

Sie müssen vor dem Rückgabetyp eines Lambdaausdrucks `->` bereitstellen.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Stellen Sie `->` vor dem Rückgabetyp bereit.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Fehler C3484 generiert:

```
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C3484 durch Bereitstellen von `->` vor dem Rückgabetyp des Lambdaausdrucks behoben:

```
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)