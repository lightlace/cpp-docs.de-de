---
title: Compilerfehler C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 71f0fe3211ce253bcf30347658692651e84ab608
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344748"
---
# <a name="compiler-error-c2614"></a>Compilerfehler C2614

'Klasse1': Unzulässige elementinitialisierung: 'Klasse2' ist kein Basis noch Element

Nur Member oder Basisklassen, können in der Initialisierungsliste für eine Klasse oder Struktur angezeigt werden.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2614 generiert.

```
// C2614.cpp
// compile with: /c
struct A {
   int i;
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A
};

struct A2 {
   int B;
   int i;
   A2( int ia ) : B( i ) {};   // OK
};
```