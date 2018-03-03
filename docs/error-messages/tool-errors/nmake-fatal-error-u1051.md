---
title: 'NMAKE: Schwerwiegender Fehler U1051 | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93c109bf723b3c4cf08e998a715fe8f6f33be466
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE: Schwerwiegender Fehler U1051
Nicht genügend Arbeitsspeicher  
  
 NMAKE war nicht genügend Arbeitsspeicher, einschließlich des virtuellen Speichers, da das Makefile zu groß oder komplex war.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Geben Sie Speicherplatz auf dem Datenträger frei.  
  
2.  Erhöhen Sie die Größe der Auslagerungsdatei des Windows NT oder Windows-Auslagerungsdatei.  
  
3.  Wenn nur ein Teil des Makefiles verwendet wird, teilen Sie dieses in separate Dateien auf, oder verwenden Sie **! IF** Präprozessordirektiven zur Begrenzung des Umfangs, der NMAKE verarbeiten muss. Die **! IF** Includedirektiven **! IF**, `!IFDEF`, **! IFNDEF**, **! ElseIf**, **! ELSE** `IFDEF`, und **! ELSE** `IFNDEF`.