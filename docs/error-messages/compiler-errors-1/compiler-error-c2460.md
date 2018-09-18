---
title: Compilerfehler C2460 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2d85ffbc7aa799f0688fbb10021a04ef9455ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022615"
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