---
title: Compilerfehler C2930
ms.date: 11/04/2016
f1_keywords:
- C2930
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
ms.openlocfilehash: 20fa3e81e66bb30bd63e579a863b6071de4ef871
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434826"
---
# <a name="compiler-error-c2930"></a>Compilerfehler C2930

'Klasse': 'Typ-Klassen-ID' wird als Enumerator von 'Enumerationsbezeichner' neu definiert.

Eine generische oder Vorlagenklasse kann nicht als Member einer Enumeration verwendet werden.

Dieser Fehler kann dadurch verursacht werden, dass geschweifte Klammern nicht korrekt übereinstimmen.

Im folgenden Beispiel wird C2930 generiert:

```
// C2930.cpp
// compile with: /c
template<class T>
class x{};
enum SomeEnum { x };   // C2930

class y{};
enum SomeEnum { y };
```

C2930 kann auch auftreten, wenn Generika verwendet werden:

```
// C2930c.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
enum SomeEnum { GC };   // C2930

ref struct GC2 {};
enum SomeEnum2 { GC2 };
```