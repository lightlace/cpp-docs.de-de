---
title: Tools.ini und NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
ms.openlocfilehash: 38eebb3aaf07438da85b0cfe6bd3f26fb5d6db29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317678"
---
# <a name="toolsini-and-nmake"></a>Tools.ini und NMAKE

NMAKE liest Tools.ini, bevor sie Makefiles, gelesen, wenn/r verwendet wird. Er sucht nach Tools.ini zuerst im aktuellen Verzeichnis, und klicken Sie dann in dem von der INIT-Umgebungsvariablen angegebenen Verzeichnis. Der Abschnitt für NMAKE-Einstellungen in der Initialisierungsdatei beginnt mit `[NMAKE]` und können alle Makefile-Informationen enthalten. Geben Sie einen Kommentar auf einer separaten Zeile beginnt mit einem Nummernzeichen (#).

## <a name="see-also"></a>Siehe auch

[Ausführen von NMAKE](running-nmake.md)
