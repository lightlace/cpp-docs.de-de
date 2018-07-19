---
title: BSCMAKE-Befehlsdatei (Antwortdatei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a879306078c52e0ad11d29f1786a2e55c2480d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369564"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE-Befehlsdatei (Antwortdatei)
Sie können die Befehlszeileneingabe in einer Befehlsdatei ganz oder teilweise bereitstellen. Geben Sie die Befehlsdatei, die mit der folgenden Syntax:  
  
```  
BSCMAKE @filename  
```  
  
 Nur eine Befehlsdatei ist zulässig. Sie können angeben, einen Pfad mit *Filename*. Vorausgehen *Filename* mit einem at-Zeichen (@). Eine Erweiterung von BSCMAKE nicht vorausgesetzt. Sie können zusätzliche angeben *Sbrfiles* in der Befehlszeile nach *Filename*. Die Befehlsdatei ist eine Textdatei, die die Eingabe für BSCMAKE in derselben Reihenfolge enthält, wie Sie es in der Befehlszeile angeben würden. Trennen Sie die Befehlszeilenargumente durch ein oder mehrere Leerzeichen, Tabstopps oder neue Zeilenumbruchzeichen.  
  
 Der folgende Befehl ruft BSCMAKE eine Befehlsdatei mit:  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Im folgenden finden eine Beispieldatei für Befehl:  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## <a name="see-also"></a>Siehe auch  
 [BSCMAKE-Referenz](../../build/reference/bscmake-reference.md)