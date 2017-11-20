---
title: Tools.ini und NMAKE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 638132f640fd342a752ec45541275178f6f26692
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini und NMAKE
NMAKE liest Tools.ini, bevor sie Makefiles, gelesen, wenn/r verwendet wird. Sucht nach Tools.ini zuerst im aktuellen Verzeichnis, und klicken Sie dann in das Verzeichnis, das von der INIT-Umgebungsvariablen angegeben. NMAKE-Einstellungen in der Initialisierungsdatei im Abschnitt beginnt mit `[NMAKE]` und Makefile Informationen enthalten können. Geben Sie einen Kommentar auf einer separaten Zeile Anfang mit einem Nummernzeichen (#).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)