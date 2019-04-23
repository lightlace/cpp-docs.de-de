---
title: Compilerfehler C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 6ff269d719dd354932ef79946ae99a9b60490199
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039423"
---
# <a name="compiler-error-c3482"></a>Compilerfehler C3482

"this" kann nur als Lambdaerfassung innerhalb einer nicht statischen Memberfunktion verwendet werden.

Sie können `this` nicht an die Erfassungsliste eines Lambdaausdrucks übergeben, der in einer statischen Methode oder globalen Funktion deklariert ist.

### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Konvertieren Sie die einschließende Funktion in eine nicht statische Methode oder

- Entfernen Sie den `this` -Zeiger aus der Erfassungsliste des Lambdaausdrucks.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Fehler C3482 generiert:

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>Siehe auch

[Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)