---
title: Tools.ini und NMAKE | Microsoft Docs
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
ms.openlocfilehash: 860a334274a3a1a4ac9e11c3e7b5e9a0f136ecc0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380549"
---
# <a name="toolsini-and-nmake"></a>Tools.ini und NMAKE
NMAKE liest Tools.ini, bevor sie Makefiles, gelesen, wenn/r verwendet wird. Sucht nach Tools.ini zuerst im aktuellen Verzeichnis, und klicken Sie dann in das Verzeichnis, das von der INIT-Umgebungsvariablen angegeben. NMAKE-Einstellungen in der Initialisierungsdatei im Abschnitt beginnt mit `[NMAKE]` und Makefile Informationen enthalten können. Geben Sie einen Kommentar auf einer separaten Zeile Anfang mit einem Nummernzeichen (#).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)