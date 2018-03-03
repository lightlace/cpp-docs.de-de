---
title: BSCMAKE-Befehlsdatei (Antwortdatei) | Microsoft Docs
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
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c250af9f1af96bb051be0b2cd347ecd8d98d809
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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