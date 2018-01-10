---
title: Rekursionsmakros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8d9ef7f194151fb3259712759d0c29ed157d564
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recursion-macros"></a>Rekursionsmakros
Verwenden Sie Rekursionsmakros NMAKE rekursiv aufgerufen. Rekursive Sitzungen erben Befehlszeilen- und Umgebungsvariablen Makros und Tools.ini Informationen. Sie erben nicht die Makefiles definierte Rückschlussregeln oder **. SUFFIXE** und **. WERTVOLLE** Spezifikationen. Um Makros einer rekursiven NMAKE-Sitzung zu übergeben, legen Sie eine Umgebungsvariable mit Satz vor dem rekursiven Aufruf, definieren Sie ein Makro im Befehl für den rekursiven Aufruf, oder definieren Sie ein Makro in Tools.ini.  
  
|Makro|Definition|  
|-----------|----------------|  
|**STELLEN SIE**|Befehl, der ursprünglich zum Aufrufen von NMAKE verwendet.<br /><br /> Das $(make)-makro gibt den vollständigen Pfad zu nmake.exe.|  
|**MAKEDIR**|Aktuelle Verzeichnis Wenn NMAKE aufgerufen wurde.|  
|**MAKEFLAGS**|Optionen momentan in Kraft. Verwenden Sie als `/$(MAKEFLAGS)`.  Beachten Sie, dass/f nicht enthalten ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Besondere NMAKE-Makros](../build/special-nmake-macros.md)