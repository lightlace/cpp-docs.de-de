---
title: Ausdrucksauswertungsfehler CXX0064 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b16133484af5a2225f79c5d293a2c8edd948bdb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025892"
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