---
title: Compilerfehler C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: fd8909b664f739afa1ab1208be0984b8f410154d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468638"
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