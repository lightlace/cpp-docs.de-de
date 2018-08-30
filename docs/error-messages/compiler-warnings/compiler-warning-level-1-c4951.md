---
title: Compilerwarnung (Stufe 1) C4951 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e26c4bc176a54f063a3f9bce2faf451a9c0406f0
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204234"
---
# <a name="compiler-warning-level-1-c4951"></a>Compilerwarnung (Stufe 1) C4951

> "*Funktion*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, funktionsprofildaten werden nicht verwendet

Eine Funktion wurde in einem Eingabemodul für [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)bearbeitet, sodass die Profildaten jetzt ungültig sind. Das Eingabemodul wurde nach der neu kompiliert **/LTCG: PGINSTRUMENT** und verfügt über eine Funktion (*Funktion*) mit einer anderen ablaufsteuerung als zum Zeitpunkt der im Modul war die  **/LTCG: PGINSTRUMENT** Vorgang.

Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie **/LTCG:PGINSTRUMENT**aus, wiederholen alle Testläufe und führen **/LTCG:PGOPTIMIZE**aus.

Bei Verwendung von **/LTCG:PGOPTIMIZE** würde diese Warnung durch einen Fehler ersetzt.