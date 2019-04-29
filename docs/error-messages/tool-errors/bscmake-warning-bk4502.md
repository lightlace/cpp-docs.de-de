---
title: BSCMAKE-Warnung BK4502
ms.date: 11/04/2016
f1_keywords:
- BK4502
helpviewer_keywords:
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
ms.openlocfilehash: 47bb81827bb6ae1f580ff907be6c0acf7139a29a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299737"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE-Warnung BK4502

abgeschnitten. SBR-Datei "Filename" nicht in Dateinamen

Eine Zeichenfolge der Länge Null SBR-Datei, die ursprünglich nicht Teil der BSC-Datei war, wurde während einer Aktualisierung angegeben.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Falscher Dateiname angegeben.

1. Datei wurde gelöscht. (Fehler [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) Ergebnisse.)

1. Datei ist beschädigt, dass BSCMAKE veranlasst, einen vollständigen Build durchzuführen.