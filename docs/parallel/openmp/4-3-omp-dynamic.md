---
title: "4.3 OMP_DYNAMIC"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 4.3 OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die **OMP\_DYNAMIC** Umgebungsvariablen aktiviert oder deaktiviert dynamische Anpassung der Anzahl von Threads, die für die Ausführung paralleler Bereichen verfügbar sind, es sei denn, dynamische Anpassung explizit aktiviert oder deaktiviert werden, indem Sie die **omp\_set\_dynamic** routine Bibliothek aufruft.  Der Wert muss **TRUE** oder **FALSE**sein.  
  
 Wenn auf true festgelegt ist die Anzahl von Threads, die zum Ausführen von parallelen Bereichen verwendet werden, von der Laufzeitumgebung für Bestes Systemressourcen verwenden.  Wenn auf " false " festgelegt wird, dynamische Anpassung deaktiviert.  Die Standardbedingung wird Implementierung\-definiert.  
  
 Beispiel:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## Querverweise:  
  
-   Weitere Informationen zu parallelen Bereiche finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite 8.  
  
-   **omp\_set\_dynamic**\-Funktion finden [3.1.7 Abschnitt](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.