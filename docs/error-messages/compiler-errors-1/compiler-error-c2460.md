---
title: Compilerfehler C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 414b6e53cf1610a55db984a1127bfc884102494f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230320"
---
# <a name="compiler-error-c2460"></a>Compilerfehler C2460

'Bezeichner1': verwendet "Bezeichner2", die definiert wird

Eine Klasse oder Struktur (`identifier2`) wird als Mitglied von sich selbst deklariert (`identifier1`). Rekursive Definitionen von Klassen und Strukturen sind nicht zulässig.

Im folgende Beispiel wird die C2460 generiert:

```
// C2460.cpp
class C {
   C aC;    // C2460
};
```

Verwenden Sie stattdessen einen Zeigerverweis in der Klasse.

```
// C2460.cpp
class C {
   C * aC;    // OK
};
```