---
title: Compilerfehler C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 0d2ea3677d883fa4843c37a41d733872b23cbba0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760672"
---
# <a name="compiler-error-c2801"></a>Compilerfehler C2801

"Operator Operator" muss ein nicht statischer Member sein.

Die folgenden Operatoren können nur als nicht statische Member überladen werden:

- Zuweisungs `=`

- Zugriffs `->` für Klassenmember

- Abonnement `[]`

- Funktions Aufruf`()`

Mögliche C2801 Ursachen:

- Der überladene Operator ist kein Klassen-, Struktur-oder Union-Member.

- Der überladene Operator ist `static`deklariert.

- Im folgenden Beispiel wird C2801 generiert:

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
