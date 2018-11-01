---
title: 'NMAKE: Schwerwiegender Fehler U1056'
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: b15b14c04dd91ae648ea4311612c122f04f90477
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635928"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE: Schwerwiegender Fehler U1056

Befehlsprozessor nicht gefunden werden.

Der Befehlsprozessor wies nicht den im angegebenen Pfad die **COMSPEC** oder **Pfad** Umgebungsvariablen.

NMAKE verwendet COMMAND.COM oder cmd ein. EXE-Datei als ein Befehlsprozessor, wenn Sie Befehle ausführen. Es sucht der Befehlsprozessor zuerst in den Pfad an, legen Sie in **COMSPEC**. Wenn **COMSPEC** ist nicht vorhanden, NMAKE-Suchvorgänge, die die Verzeichnisse im angegebenen **Pfad**.