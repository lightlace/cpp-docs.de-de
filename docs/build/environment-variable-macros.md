---
title: Makros von Umgebungsvariablen | Microsoft Docs
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
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69fae15b7a12d990d2fb2c8e457bfdc0407f7702
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="environment-variable-macros"></a>Makros von Umgebungsvariablen
NMAKE erbt Makrodefinitionen für Umgebungsvariablen, die vor dem Start der Sitzung vorhanden sind. Wenn eine Variable in der Umgebung des Betriebssystems festgelegt wurde, ist es als eines NMAKE-Makros zur Verfügung. Die geerbten Namen werden in Großbuchstaben konvertiert. Vererbung erfolgt vor dem Präprozessorlauf. Verwenden Sie die Option/e, Makros von Umgebungsvariablen Makros mit demselben Namen im Makefile überschreiben geerbte verursachen.  
  
 Makros von Umgebungsvariablen in der Sitzung neu definiert werden, und die entsprechenden Umgebungsvariablen geändert. Sie können auch Umgebungsvariablen mit dem Befehl SET ändern. Mit dem SET-Befehl so ändern eine Umgebungsvariable in einer Sitzung wird das entsprechende Makro, nicht jedoch geändert.  
  
 Zum Beispiel:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 In diesem Beispiel ändern `PATH` ändert die entsprechenden Umgebungsvariablen `PATH`; er fügt `\nonesuch` zu Ihrem Pfad.  
  
 Wenn eine Umgebungsvariable als Zeichenfolge, die in einem Makefile syntaktisch falsch wäre definiert ist, wird kein Makro erstellt und keine Warnung generiert wird. Wenn der Wert einer Variablen ein Dollarzeichen ($) enthält, wird es von NMAKE als Anfang eines Makroaufrufs interpretiert. Verwenden Sie das Makro kann zu unerwartetem Verhalten führen.  
  
## <a name="see-also"></a>Siehe auch  
 [Besondere NMAKE-Makros](../build/special-nmake-macros.md)