---
title: BSCMAKE-Warnung BK4502 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK4502
- BK1513
dev_langs:
- C++
helpviewer_keywords:
- BK1513
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4142993b3f4f5bda2b3e4ce322aa26d7beca8584
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056325"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE-Warnung BK4502

abgeschnitten. SBR-Datei "Filename" nicht in Dateinamen

Eine Zeichenfolge der Länge Null SBR-Datei, die ursprünglich nicht Teil der BSC-Datei war, wurde während einer Aktualisierung angegeben.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Falscher Dateiname angegeben.

1. Datei wurde gelöscht. (Fehler [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) Ergebnisse.)

1. Datei ist beschädigt, dass BSCMAKE veranlasst, einen vollständigen Build durchzuführen.