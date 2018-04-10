---
title: Ausführen von NMAKE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6c39612cf4df47665f7ea3d529b77ee4e70ce8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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