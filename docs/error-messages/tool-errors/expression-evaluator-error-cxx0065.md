---
title: Ausdrucksauswertungsfehler CXX0065 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c100b1edbd36f4384e8deb1abf5b36465e8da479
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024163"
---
# <a name="expression-evaluator-error-cxx0065"></a>Ausdrucksauswertungsfehler CXX0065

Variable erfordert Stapelrahmen

Ein Ausdruck enthält eine Variable, die im aktuellen Gültigkeitsbereich vorhanden ist, aber nicht noch erstellt wurde.

Dieser Fehler kann auftreten, wenn Sie der Prolog einer Funktion aber noch nicht richten Sie den Stapelrahmen der Funktion schrittweise ausführen oder Sie haben den Exitcode für die Funktion schrittweise.

Durchlaufen der Prologcode aus, bis der Stapelrahmen eingerichtet wurde, bevor die Auswertung des Ausdrucks.

Dieser Fehler ist mit CAN0065 identisch.