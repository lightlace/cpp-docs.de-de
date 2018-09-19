---
title: Ausdrucksauswertungsfehler CXX0024 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0024
dev_langs:
- C++
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2816be7bb1d33757d9722d605d461ac6fb34fadd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118193"
---
# <a name="expression-evaluator-error-cxx0024"></a>Ausdrucksauswertungsfehler CXX0024

Vorgang benötigt l-Wert

Ein Ausdruck, der nicht auf einen l-Wert ausgewertet wird, wurde für einen Vorgang angegeben, der einen l-Wert erfordert.

Ein l-Wert (so genannt, weil er auf der linken Seite einer zuweisungsanweisung angezeigt wird) ist ein Ausdruck, der auf einen Speicherbereich verweist.

Z. B. `buffer[count]` ist ein gültiger l-Wert, da er an einem bestimmten Speicherort zeigt. Der logische Vergleich `zed != 0` ist kein gültiger l-Wert, da er auf "true" oder "FALSE" ausgewertet, nicht auf eine Speicheradresse wird.

Dieser Fehler ist mit CAN0024 identisch.