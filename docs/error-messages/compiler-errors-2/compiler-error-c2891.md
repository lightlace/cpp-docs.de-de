---
title: Compilerfehler C2891 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86d81662cb02fa3c8f6af75009daf4dab9b70196
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016558"
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