---
title: Ausdrucksauswertungsfehler CXX0022 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0022
dev_langs:
- C++
helpviewer_keywords:
- CXX0022
- CAN0022
ms.assetid: f6b299ac-a4ee-492c-bd9f-6fff005bc537
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf067a1024b8ac344c1490bc9ec25b0b7d57540
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082351"
---
# <a name="expression-evaluator-error-cxx0022"></a>Ausdrucksauswertungsfehler CXX0022

Funktionsaufruf vor dem _main

Eine Funktion kann von die C++-ausdrucksauswertung kann nicht ausgewertet werden, bevor der Debugger die Funktion eingegeben hat **_main**. Die Anwendung ist nicht ordnungsgemäß initialisiert bis **_main** aufgerufen wurde.

Dieser Fehler ist mit CAN0022 identisch.