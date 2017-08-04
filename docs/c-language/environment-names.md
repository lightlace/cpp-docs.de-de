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
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 25c493f7f25b8fd1239aea70bcf059c4137b7bc3
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

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
