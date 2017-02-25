---
title: "BSCMAKE-Befehlsdatei (Antwortdatei) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSCMAKE, Befehlsdatei"
  - "BSCMAKE, Antwortdatei"
  - "Befehlsdateien"
  - "Befehlsdateien, BSCMAKE"
  - "Antwortdateien"
  - "Antwortdateien, BSCMAKE"
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# BSCMAKE-Befehlsdatei (Antwortdatei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Befehlszeileneingabe kann ganz oder teilweise in einer Befehlsdatei bereitgestellt werden.  Geben Sie die Befehlsdatei in folgender Syntax an:  
  
```  
BSCMAKE @filename  
```  
  
 Die Verwendung mehrerer Befehlsdateien ist nicht zulässig.  Sie können einen Pfad mit *filename* angeben.  Geben Sie vor *filename* das @\-Zeichen an.  BSCMAKE nimmt keine Standarderweiterung an.  In der Befehlszeile können Sie nach *filename* zusätzliche *sbrfiles* angeben.  Bei der Befehlsdatei handelt es sich um eine Textdatei, die die Eingabe für BSCMAKE in derselben Reihenfolge enthält, wie Sie diese in der Befehlszeile angeben würden.  Trennen Sie die Befehlszeilenargumente durch ein oder mehrere Leerzeichen, Tabulatoren oder Zeilenumbruchzeichen.  
  
 Der folgende Befehl ruft BSCMAKE mit einer Befehlsdatei auf:  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Nachstehend ist eine Beispielbefehlsdatei angegeben:  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## Siehe auch  
 [BSCMAKE\-Referenz](../../build/reference/bscmake-reference.md)