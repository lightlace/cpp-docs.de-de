---
title: Compilerwarnung (Stufe 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 1948342e1ff97c38ca3a44694dc7e7d399d96825
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568040"
---
# <a name="compiler-warning-level-1-c4953"></a>Compilerwarnung (Stufe 1) C4953

> Inlinee "*Funktion*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, Profildaten werden nicht verwendet

Bei Verwendung von [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)hat der Compiler ein Eingabemodul erkannt, das nach `/LTCG:PGINSTRUMENT` neu kompiliert wurde und eine Funktion (*function*) aufweist, die bearbeitet wurde und die in vorhandenen Testläufen als Kandidat für Inlining identifiziert wurde. Infolge der Neukompilierung des Moduls ist die Funktion jedoch kein Kandidat für Inlining mehr.

Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie `/LTCG:PGINSTRUMENT`aus, wiederholen alle Testläufe und führen `/LTCG:PGOPTIMIZE`aus.

Bei Verwendung von `/LTCG:PGOPTIMIZE` würde diese Warnung durch einen Fehler ersetzt.