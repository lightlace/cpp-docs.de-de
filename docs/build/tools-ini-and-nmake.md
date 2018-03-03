---
title: Tools.ini und NMAKE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4516c3206a08c2b9ee32aea4bbb669ce4cdf0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini und NMAKE
NMAKE liest Tools.ini, bevor sie Makefiles, gelesen, wenn/r verwendet wird. Sucht nach Tools.ini zuerst im aktuellen Verzeichnis, und klicken Sie dann in das Verzeichnis, das von der INIT-Umgebungsvariablen angegeben. NMAKE-Einstellungen in der Initialisierungsdatei im Abschnitt beginnt mit `[NMAKE]` und Makefile Informationen enthalten können. Geben Sie einen Kommentar auf einer separaten Zeile Anfang mit einem Nummernzeichen (#).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausführen von NMAKE](../build/running-nmake.md)