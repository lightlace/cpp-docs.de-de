---
title: Ausdrucksauswertungsfehler CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: 93f8389ed3959d5747e46c1234fd8d2eae0f1ae5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359838"
---
# <a name="expression-evaluator-error-cxx0024"></a>Ausdrucksauswertungsfehler CXX0024

Vorgang benötigt l-Wert

Ein Ausdruck, der nicht auf einen l-Wert ausgewertet wird, wurde für einen Vorgang angegeben, der einen l-Wert erfordert.

Ein l-Wert (so genannt, weil er auf der linken Seite einer zuweisungsanweisung angezeigt wird) ist ein Ausdruck, der auf einen Speicherbereich verweist.

Z. B. `buffer[count]` ist ein gültiger l-Wert, da er an einem bestimmten Speicherort zeigt. Der logische Vergleich `zed != 0` ist kein gültiger l-Wert, da er auf "true" oder "FALSE" ausgewertet, nicht auf eine Speicheradresse wird.

Dieser Fehler ist mit CAN0024 identisch.