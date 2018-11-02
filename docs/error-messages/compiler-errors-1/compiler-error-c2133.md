---
title: Compilerfehler C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: 68672ae76024d3d09d738d997c485a3205c7dd2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588060"
---
# <a name="compiler-error-c2133"></a>Compilerfehler C2133

'Bezeichner': Unbekannte Größe

Ein Array ohne Größenangabe wird als ein Mitglied aus einer Klasse, Struktur, Union oder Enumeration deklariert. Die Option/Za (ANSI-C) lässt sich nicht auf Memberarrays aus.

Im folgende Beispiel wird die C2133 generiert:

```
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

Mögliche Lösung:

```
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```