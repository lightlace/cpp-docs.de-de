---
title: Ausdrucksauswertungsfehler CXX0021 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0021
dev_langs:
- C++
helpviewer_keywords:
- CXX0021
- CAN0021
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef765286d022b26aeed0ca98c9f43f94f5d17f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025775"
---
# <a name="expression-evaluator-error-cxx0021"></a>Ausdrucksauswertungsfehler CXX0021

Struktur oder Union als Skalarwert verwendet

Eine Struktur oder Union in einem Ausdruck verwendet wurde, aber es wurde kein Element angegeben.

Wenn eine Struktur oder union-Variable zu bearbeiten, kann der Name der Variablen selbst ohne Feldqualifizierer angezeigt. Wenn eine Struktur oder Union in einem Ausdruck verwendet wird, müssen sie mit dem bestimmte Element, das gewünschte qualifiziert werden.

Geben Sie das Element, dessen Wert im Ausdruck verwendet werden.

Dieser Fehler ist mit CAN0021 identisch.