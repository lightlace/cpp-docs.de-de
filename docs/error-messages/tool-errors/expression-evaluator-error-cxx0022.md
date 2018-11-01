---
title: Ausdrucksauswertungsfehler CXX0022
ms.date: 11/04/2016
f1_keywords:
- CXX0022
helpviewer_keywords:
- CXX0022
- CAN0022
ms.assetid: f6b299ac-a4ee-492c-bd9f-6fff005bc537
ms.openlocfilehash: ac726c60d30a13d6458636d31dda6a8fb2cbd02d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623287"
---
# <a name="expression-evaluator-error-cxx0022"></a>Ausdrucksauswertungsfehler CXX0022

Funktionsaufruf vor dem _main

Eine Funktion kann von die C++-ausdrucksauswertung kann nicht ausgewertet werden, bevor der Debugger die Funktion eingegeben hat **_main**. Die Anwendung ist nicht ordnungsgemäß initialisiert bis **_main** aufgerufen wurde.

Dieser Fehler ist mit CAN0022 identisch.