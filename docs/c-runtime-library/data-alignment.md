---
title: "Datenausrichtung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data.alignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenausrichtung [C++]"
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Datenausrichtung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Datenausrichtung C\-Laufzeitfunktionen unterstützen.  
  
### Daten\-Ausrichtungs\-Routinen  
  
|Routine|Verwendung|.NET Framework\-Entsprechung|  
|-------------|----------------|----------------------------------|  
|[\_aligned\_free](../c-runtime-library/reference/aligned-free.md)|Gibt einen Speicherblock freigeben, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_free\_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|Gibt einen Speicherblock freigeben, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde \(Debug nur\).|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md)|Belegt in einer angegebenen Grenze integralen Speicher.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_malloc\_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Belegt auf einer integralen angegebenen Grenze mit zusätzlichem Speicher für eine Debuggingskopfzeile Speicher und überschreibt Puffer \(nur Debugversion\).|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_msize](../c-runtime-library/reference/aligned-msize.md)|Gibt die Größe eines Speicherblocks zurück, der im Heap zugeordnet wird.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_msize\_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Gibt die Größe eines im Heap belegten Speicherblocks zurück \(nur Debugversion\).|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Belegt in einer angegebenen Grenze integralen Speicher.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_malloc\_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Belegt Speicher in einer angegebenen Ausrichtungsgrenze \(nur Debugversion\).|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_realloc\_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(nur\) Debugversion zugeordnet wurde.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Arbeitsspeicher von 0.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_offset\_recalloc\_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Arbeitsspeicher von 0 \(nur Debugversion\).|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_realloc](../c-runtime-library/reference/aligned-realloc.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_realloc\_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) \(nur\) Debugversion zugeordnet wurde.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Arbeitsspeicher von 0.|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
|[\_aligned\_recalloc\_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|Ändert die Größe eines Speicherblocks, der mit [\_aligned\_malloc](../c-runtime-library/reference/aligned-malloc.md) oder [\_aligned\_offset\_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) zugeordnet wurde und initialisiert den Arbeitsspeicher von 0 \(nur Debugversion\).|Nicht zutreffend.  Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf.  Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).|  
  
## Siehe auch  
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)