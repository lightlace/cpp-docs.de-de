---
title: Linkertoolfehler LNK1158
ms.date: 11/04/2016
f1_keywords:
- LNK1158
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
ms.openlocfilehash: f2e3e1d9948960beed631861c5981f2d09daf632
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455938"
---
# <a name="linker-tools-error-lnk1158"></a>Linkertoolfehler LNK1158

'Dateiname' kann nicht ausgeführt werden.

Die angegebene ausführbare Datei, die aufgerufen werden, indem [LINK](../../build/reference/linker-command-line-syntax.md) ist nicht in das Verzeichnis mit LINK noch in einem in der PATH-Umgebungsvariablen angegebenen Verzeichnis.

Beispielsweise erhalten Sie diesen Fehler, wenn Sie versuchen, den PGOPTIMIZE-Parameter, um die ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md) Linkeroption auf einem Computer mit einem 32-Bit-Betriebssystem.