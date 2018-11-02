---
title: Compilerfehler C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 44f7988f9fedb882972b2823f2fe70d9512d4e87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484785"
---
# <a name="compiler-error-c2801"></a>Compilerfehler C2801

'Operator Operator' muss einen nicht statischen Member sein.

Die folgenden Operatoren können überladen werden, nur als nicht statische Member:

- Zuweisung `=`

- Klassenmemberzugriff `->`

- Indizierung `[]`

- Funktionsaufruf `()`

Mögliche Ursachen für C2801:

- Überladener Operator ist nicht an eine Klasse, Struktur oder union-Member.

- Überladener Operator deklariert `static`.

- Im folgende Beispiel wird die C2801 generiert:

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```