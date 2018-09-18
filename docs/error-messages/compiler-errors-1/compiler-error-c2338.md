---
title: Compilerfehler C2338 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2338
dev_langs:
- C++
helpviewer_keywords:
- C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77bc98afdad36e0505abb58ee06ec1c7e7654ae5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071574"
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
