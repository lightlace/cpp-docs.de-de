---
title: Ausdrucksauswertungsfehler CXX0025 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0025
dev_langs:
- C++
helpviewer_keywords:
- CAN0025
- CXX0025
ms.assetid: 3e2fb541-63b3-46ac-9f93-3dadb253bcf6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd89faa4de7b296d6a6771f857f3d16dbe2f94f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043702"
---
# <a name="expression-evaluator-error-cxx0025"></a>Ausdrucksauswertungsfehler CXX0025

Operators bedürfen Struktur/union

Ein Operator, einen Ausdruck vom unterstützt `struct` oder **Union** Typ in einen Ausdruck, der nicht angewendet wurde eine `struct` oder **Union**.

Komponenten der Klasse, Struktur oder union-Variablen müssen einen vollqualifizierten Namen. Komponenten können nicht ohne vollständige Spezifikation eingegeben werden.

Dieser Fehler ist mit CAN0025 identisch.