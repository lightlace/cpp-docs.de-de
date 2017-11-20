---
title: "Ausführen von NMAKE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1d3ff8c58b411d796ceb72876d5728a358e885f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="running-nmake"></a>Ausführen von NMAKE
## <a name="syntax"></a>Syntax  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## <a name="remarks"></a>Hinweise  
 NMAKE-Builds nur angegebene *Ziele* oder, wenn keine Angabe erfolgt, wird die erste im Makefile Ziel. Das erste Makefileziel kann ein [Pseudoziel](../build/pseudotargets.md) andere Ziele wird erstellt. NMAKE verwendet mit/f angegebene Makefiles. Wenn/f nicht angegeben ist, verwendet er die Makefile-Datei im aktuellen Verzeichnis. Wenn kein Makefile angegeben wird, verwendet er Rückschlussregeln für Befehlszeilen erstellen *Ziele*.  
  
 Die `commandfile` Text (oder Antwortdatei) enthält die Befehlszeileneingabe. Andere Eingabe kann vorausgehen oder folgen Sie`commandfile`. Ein Pfad ist zulässig. In `commandfile`, Zeilenumbrüche als Leerzeichen behandelt werden. Schließen Sie Makrodefinitionen in Anführungszeichen ein, wenn diese Leerzeichen enthalten.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [NMAKE-Optionen](../build/nmake-options.md)  
  
 [Tools.ini und NMAKE](../build/tools-ini-and-nmake.md)  
  
 [Exitcodes von NMAKE](../build/exit-codes-from-nmake.md)  
  
## <a name="see-also"></a>Siehe auch  
 [NMAKE-Referenz](../build/nmake-reference.md)