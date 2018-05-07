---
title: 'NMAKE: Schwerwiegender Fehler U1051 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1051
dev_langs:
- C++
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 570c7e5d8e6e8250a67e4f032ac26b04388cfd00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE: Schwerwiegender Fehler U1051
Nicht genügend Arbeitsspeicher  
  
 NMAKE war nicht genügend Arbeitsspeicher, einschließlich des virtuellen Speichers, da das Makefile zu groß oder komplex war.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Geben Sie Speicherplatz auf dem Datenträger frei.  
  
2.  Erhöhen Sie die Größe der Auslagerungsdatei des Windows NT oder Windows-Auslagerungsdatei.  
  
3.  Wenn nur ein Teil des Makefiles verwendet wird, teilen Sie dieses in separate Dateien auf, oder verwenden Sie **! IF** Präprozessordirektiven zur Begrenzung des Umfangs, der NMAKE verarbeiten muss. Die **! IF** Includedirektiven **! IF**, `!IFDEF`, **! IFNDEF**, **! ElseIf**, **! ELSE** `IFDEF`, und **! ELSE** `IFNDEF`.