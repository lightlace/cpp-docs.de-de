---
title: Compilerfehler C2338
ms.date: 11/04/2016
f1_keywords:
- C2338
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
ms.openlocfilehash: 4ca3feb2a71efa60229afdbf918109a5d5d59cad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539593"
---
# <a name="compiler-error-c2338"></a>Compilerfehler C2338

> *Fehlermeldung*

Dieser Fehler kann verursacht werden, indem eine `static_assert` Fehler während der Kompilierung. Die Nachricht wird vom die `static_assert` Parameter.

Diese Fehlermeldung kann auch von externen Anbietern für den Compiler generiert werden. In den meisten Fällen werden diese Fehler von einem Attributanbieter DLL, z. B. ATLPROV gemeldet. Einige allgemeinen Formen der dieser Nachricht gehören:

> "*Attribut*" Atl-Attributanbieter: Fehler ATL*Anzahl* *Nachricht*

> Falsche Verwendung des Attributs "*Attribut*"

> "*Nutzung*": falsches Format für das Attribut "Nutzung"

Diese Fehler sind häufig nicht behebbar, und ein schwerwiegender Compilerfehler gefolgt werden können.

Um diese Probleme zu beheben, korrigieren Sie die Verwendung von Attributen. In einigen Fällen müssen z. B. Zuordnen von Parametern deklariert werden, bevor sie verwendet werden können. Wenn eine ATL-Fehlernummer angegeben wird, überprüfen Sie die Dokumentation für Weitere Informationen zu diesem Fehler.
