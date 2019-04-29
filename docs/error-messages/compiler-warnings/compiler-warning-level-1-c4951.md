---
title: Compilerwarnung (Stufe 1) C4951
ms.date: 08/27/2018
f1_keywords:
- C4951
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
ms.openlocfilehash: 73e048aeaa044c35e09539b07d51398829a0fdfd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408055"
---
# <a name="compiler-warning-level-1-c4951"></a>Compilerwarnung (Stufe 1) C4951

> "*Funktion*" wurde bearbeitet wurde, seit die Profildaten erfasst Daten wurden, funktionsprofildaten werden nicht verwendet

Eine Funktion wurde in einem Eingabemodul für [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)bearbeitet, sodass die Profildaten jetzt ungültig sind. Das Eingabemodul wurde nach **/LTCG:PGINSTRUMENT** neu kompiliert und verfügt über eine Funktion (*Funktion*) mit einer anderen Ablaufsteuerung als der, die zum Zeitpunkt des **/LTCG:PGINSTRUMENT** -Vorgangs im Modul enthalten war.

Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, führen Sie **/LTCG:PGINSTRUMENT**aus, wiederholen alle Testläufe und führen **/LTCG:PGOPTIMIZE**aus.

Bei Verwendung von **/LTCG:PGOPTIMIZE** würde diese Warnung durch einen Fehler ersetzt.