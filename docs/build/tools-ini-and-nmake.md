---
title: Tools.ini und NMAKE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84406886c9aa0c0053ed7c183912bf8a7f1f4771
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723579"
---
# <a name="toolsini-and-nmake"></a>Tools.ini und NMAKE

NMAKE liest Tools.ini, bevor sie Makefiles, gelesen, wenn/r verwendet wird. Er sucht nach Tools.ini zuerst im aktuellen Verzeichnis, und klicken Sie dann in dem von der INIT-Umgebungsvariablen angegebenen Verzeichnis. Der Abschnitt für NMAKE-Einstellungen in der Initialisierungsdatei beginnt mit `[NMAKE]` und können alle Makefile-Informationen enthalten. Geben Sie einen Kommentar auf einer separaten Zeile beginnt mit einem Nummernzeichen (#).

## <a name="see-also"></a>Siehe auch

[Ausführen von NMAKE](../build/running-nmake.md)