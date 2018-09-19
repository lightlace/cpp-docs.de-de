---
title: Compilerfehler C3482 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3482
dev_langs:
- C++
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9921c25575888ab2db1c092f9325002d1becb921
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053374"
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