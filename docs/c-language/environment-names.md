---
title: Umgebungsnamen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efae64f64ef6b5ed92dffafb9f83a0e32ab38513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="environment-names"></a>Umgebungsnamen
**ANSI 4.10.4.4** Der Satz von Umgebungsnamen und die Methode zum Ändern der Umgebungsliste, die von der [getenv](../c-runtime-library/reference/getenv-wgetenv.md)-Funktion verwendet wird  
  
 Der Satz der Umgebungsnamen ist unbegrenzt.  
  
 Um die Umgebungsvariablen in einem C-Programm zu ändern, rufen Sie die [_putenv](../c-runtime-library/reference/putenv-wputenv.md)-Funktion auf. Um Umgebungsvariablen über die Befehlszeile in Windows zu ändern, verwenden Sie den SET-Befehl (z. B. SET LIB = D:\ LIBS).  
  
 Die Umgebungsvariablen, die aus einem C-Programm festgelegt werden, existieren nur, solange ihre Hostkopie der Befehlsshell des Betriebssystems ausgeführt wird (CMD.EXE oder COMMAND.COM). Beispiel: Die Zeile  
  
```  
system( SET LIB = D:\LIBS );  
```  
  
 würde eine Kopie der Befehlsshell (CMD.EXE) ausführen, die Umgebungsvariable LIB festlegen und zum C-Programm zurückkehren, wobei die sekundäre Kopie von CMD.EXE beendet wird. Durch das Beenden dieser Kopie der CMD.EXE wird die temporäre Umgebungsvariable LIB entfernt.  
  
 Entsprechend bleiben Änderungen, die von der `_putenv`-Funktion vorgenommen werden, nur bis zum Beenden des Programms erhalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)