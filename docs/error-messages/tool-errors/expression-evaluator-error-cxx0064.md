---
title: Ausdrucksauswertungsfehler CXX0064
ms.date: 11/04/2016
f1_keywords:
- CXX0064
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
ms.openlocfilehash: 71e4e3e87b33849e6b487b79268ebc9574c2e5a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511864"
---
# <a name="expression-evaluator-error-cxx0064"></a>Ausdrucksauswertungsfehler CXX0064

Haltepunkt kann nicht auf gebundene virtuelle Memberfunktion festgelegt werden.

Ein Haltepunkt wurde für eine virtuelle Memberfunktion durch einen Zeiger auf ein Objekt, z. B. festgelegt:

```
pClass->vfunc( int );
```

Für eine virtuelle Funktion kann ein Haltepunkt festgelegt werden, durch die Klasse, wie z. B. eingeben:

```
Class::vfunc( int );
```

Dieser Fehler ist mit CAN0064 identisch.