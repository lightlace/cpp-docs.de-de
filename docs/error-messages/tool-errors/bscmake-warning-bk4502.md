---
title: BSCMAKE-Warnung BK4502
ms.date: 11/04/2016
f1_keywords:
- BK4502
- BK1513
helpviewer_keywords:
- BK1513
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
ms.openlocfilehash: 34b0204744b390ac32371ff2611e43b215dc0f40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596351"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE-Warnung BK4502

abgeschnitten. SBR-Datei "Filename" nicht in Dateinamen

Eine Zeichenfolge der Länge Null SBR-Datei, die ursprünglich nicht Teil der BSC-Datei war, wurde während einer Aktualisierung angegeben.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Falscher Dateiname angegeben.

1. Datei wurde gelöscht. (Fehler [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) Ergebnisse.)

1. Datei ist beschädigt, dass BSCMAKE veranlasst, einen vollständigen Build durchzuführen.