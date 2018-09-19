---
title: Schwerwiegender Fehler C1307 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65f398dd9885c571ea0d66171889f20d3321a3b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085861"
---
# <a name="fatal-error-c1307"></a>Schwerwiegender Fehler C1307

Das Programm wurde seit dem Erfassen der Profildaten bearbeitet.

Bei Verwendung [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)der Linker ein Eingabemodul, die nach dem/LTCG: PGINSTRUMENT neu kompiliert wurde und, dass das Modul zum Zeitpunkt geändert wurde, in dem nicht mehr vorhandenen Profildaten relevant sind. Z. B. wenn das Aufrufdiagramm in der neu kompilierten Modul geändert wird, generiert der Compiler C1307.

Um diesen Fehler zu beheben, führen Sie/LTCG: PGINSTRUMENT, wiederholen Sie alle Testläufe und führen Sie/LTCG: PGOPTIMIZE. Wenn Sie nicht ausführen können/LTCG: PGINSTRUMENT und Wiederholung alle ausgeführt wird, verwenden Sie/LTCG: PGUPDATE anstelle von/LTCG: PGOPTIMIZE, um das optimierte Image zu erstellen.