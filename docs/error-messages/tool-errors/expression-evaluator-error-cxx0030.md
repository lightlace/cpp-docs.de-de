---
title: Ausdrucksauswertungsfehler CXX0030 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2921013d116b7d8f02e1e29380ca3cd14086b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102810"
---
# <a name="expression-evaluator-error-cxx0030"></a>Ausdrucksauswertungsfehler CXX0030

Ausdruck kann nicht ausgewertet werden

Ausdrucksauswertung des Debuggers konnte einen Wert für den Ausdruck nicht abrufen, laut. Eine wahrscheinliche Ursache ist, dass der Ausdruck in den Speicher verweist, die außerhalb des Programms-Adressraum ist (einen null-Zeiger zu dereferenzieren, ist ein Beispiel). Windows lässt sich nicht auf den Zugriff auf den Speicher aus, die außerhalb des Programms Adressraum ist.

Möglicherweise möchten den Ausdruck, der die Verwendung von Klammern zur Steuerung der Reihenfolge der Auswertung zu schreiben.

Dieser Fehler ist mit CAN0030 identisch.