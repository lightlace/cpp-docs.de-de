---
title: Schwerwiegender Fehler C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: 1acdda77ac9cbf8d99752de3b78ab9c32bbb4cbc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338531"
---
# <a name="fatal-error-c1307"></a>Schwerwiegender Fehler C1307

Das Programm wurde seit dem Erfassen der Profildaten bearbeitet.

Bei Verwendung [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)der Linker ein Eingabemodul, die nach dem/LTCG: PGINSTRUMENT neu kompiliert wurde und, dass das Modul zum Zeitpunkt geändert wurde, in dem nicht mehr vorhandenen Profildaten relevant sind. Z. B. wenn das Aufrufdiagramm in der neu kompilierten Modul geändert wird, generiert der Compiler C1307.

Um diesen Fehler zu beheben, führen Sie/LTCG: PGINSTRUMENT, wiederholen Sie alle Testläufe und führen Sie/LTCG: PGOPTIMIZE. Wenn Sie nicht ausführen können/LTCG: PGINSTRUMENT und Wiederholung alle ausgeführt wird, verwenden Sie/LTCG: PGUPDATE anstelle von/LTCG: PGOPTIMIZE, um das optimierte Image zu erstellen.