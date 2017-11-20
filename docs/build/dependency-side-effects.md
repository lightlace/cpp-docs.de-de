---
title: "Seiteneffekte bei Abh&#228;ngigkeiten | Microsoft Docs"
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
  - "Abhängigkeiten von Nebeneffekten"
  - "NMAKE (Programm), abhängige Dateien"
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Seiteneffekte bei Abh&#228;ngigkeiten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Ziel mit einem Doppelpunkt (:) in zwei Verknüpfungslinien an verschiedenen Orten angegeben ist, und Befehle nach nur eine der Zeilen angezeigt werden, interpretiert NMAKE Abhängigkeiten, als ob angrenzende oder kombiniert. Es keine Rückschlussregel für die Abhängigkeit aufgerufen werden, die keine Befehle, aber stattdessen nimmt an, dass die Abhängigkeiten gehören zur Beschreibung einer Block und führt die Befehle, die mit den anderen Abhängigkeit angegeben. Legen Sie beispielsweise diesen Regeln:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 wird folgendermaßen ausgewertet:  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 Dieser Effekt tritt nicht auf, wenn zwei Doppelpunkte (`::`) verwendet wird. Legen Sie beispielsweise diesen Regeln:  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 wird folgendermaßen ausgewertet:  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ziele](../build/targets.md)