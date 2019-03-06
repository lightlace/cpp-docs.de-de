---
title: Tools.ini und NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
ms.openlocfilehash: c50fef5d2fd36b8fb9327cad25bc5b2ab4ba61e2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419882"
---
# <a name="toolsini-and-nmake"></a>Tools.ini und NMAKE

NMAKE liest Tools.ini, bevor sie Makefiles, gelesen, wenn/r verwendet wird. Er sucht nach Tools.ini zuerst im aktuellen Verzeichnis, und klicken Sie dann in dem von der INIT-Umgebungsvariablen angegebenen Verzeichnis. Der Abschnitt für NMAKE-Einstellungen in der Initialisierungsdatei beginnt mit `[NMAKE]` und können alle Makefile-Informationen enthalten. Geben Sie einen Kommentar auf einer separaten Zeile beginnt mit einem Nummernzeichen (#).

## <a name="see-also"></a>Siehe auch

[Ausführen von NMAKE](../build/running-nmake.md)
