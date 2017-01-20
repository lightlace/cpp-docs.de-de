---
title: "Schwerwiegender Fehler C1307"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C1307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1307"
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Programm wurde nach der Erfassung von Profildaten bearbeitet.  
  
 Bei Verwendung von [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md) stellt der Linker ein Eingabemodul fest, das nach Ausführen von \/LTCG:PGINSTRUMENT neu kompiliert worden ist. Des Weiteren wurde das Modul zu einem Zeitpunkt geändert, an dem vorhandene Profildaten nicht mehr von Bedeutung sind.  C1307 wird vom Compiler beispielsweise erzeugt, wenn das Aufrufdiagramm im neu kompilierten Modul geändert wurde.  
  
 Um diesen Fehler zu beheben, führen Sie \/LTCG:PGINSTRUMENT aus, wiederholen Sie alle Testläufe, und führen Sie \/LTCG:PGOPTIMIZE aus.  Wenn es Ihnen nicht möglich ist, \/LTCG:PGINSTRUMENT auszuführen und alle Testläufe zu wiederholen, verwenden Sie \/LTCG:PGUPDATE anstelle von \/LTCG:PGOPTIMIZE, um ein optimiertes Abbild zu erstellen.