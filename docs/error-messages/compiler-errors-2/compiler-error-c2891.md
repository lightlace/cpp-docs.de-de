---
title: Compilerfehler C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: d9a1cdafdf7d3a2843aee4a20f71c7e6a4693150
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547946"
---
# <a name="compiler-error-c2891"></a>Compilerfehler C2891

'Parameter': die Adresse eines Vorlagenparameters nicht übernehmen

Sie können nicht die Adresse eines Vorlagenparameters übernehmen, wenn es sich um einen l-Wert ist. Typparameter sind nicht Lvalues, da sie keine Adresse aufweisen. Nichttyp-Werte in Vorlagenparameterlisten, die nicht Lvalues sind müssen sich auch nicht auf eine Adresse aus. Dies ist ein Beispiel für Code, der bewirkt, Compilerfehler C2891 dass, weil der Wert als den Vorlagenparameter übergeben eine vom Compiler generierte Kopie der Template-Argument.

```
template <int i> int* f() { return &i; }
```

Vorlagenparameter, die l-Werte, z. B. Verweistypen sind, kann ihre Adresse erstellt haben.

```
template <int& r> int* f() { return &r; }
```

Um diesen Fehler zu beheben, nehmen Sie nicht die Adresse eines Vorlagenparameters, wenn es sich um einen l-Wert ist.