---
title: "CMemoryState Structure"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMemoryState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemoryState structure"
  - "Erkennen von Speicherverlusten"
  - "Speicherverluste, Ermitteln"
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CMemoryState Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine bequeme Möglichkeit, Speicherverluste im Programm zu erkennen.  
  
## Syntax  
  
```  
struct CMemoryState  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](../Topic/CMemoryState::CMemoryState.md)|Erstellt eine Klasse ähnliche Struktur, die Arbeitsspeicherprüfpunkte steuert.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](../Topic/CMemoryState::Checkpoint.md)|Ruft eine Momentaufnahme \(Prüfpunkt\) des aktuellen Speicherzustands.|  
|[CMemoryState::Difference](../Topic/CMemoryState::Difference.md)|Berechnet den Unterschied zwischen zwei Objekten Typ `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md)|Sichert eine Zusammenfassung aller aktuell zugeordneten Objekte seit einem vorherigen Prüfpunkt.|  
|[CMemoryState::DumpStatistics](../Topic/CMemoryState::DumpStatistics.md)|Drucksspeicherbelegungsstatistik für ein `CMemoryState`\-Objekt.|  
  
## Hinweise  
 `CMemoryState` ist eine Struktur und hat keine Basisklasse.  
  
 Ein "Speicherverlust" tritt auf, wenn Speicher für ein Objekt zugeordnet, auf dem Heap jedoch nicht freigegeben wird, wenn es nicht mehr benötigt wird.  Solche Speicherverluste können zu Fehlern führen schließlich mit ungenügenden Arbeitsspeicher.  Es gibt mehrere Möglichkeiten, in Ihrem Programm Speicher reserviert und freigegeben werden:  
  
-   Verwenden der `malloc`\/**free**\-Funktionsreihe von der Laufzeitbibliothek.  
  
-   Verwenden der Windows\-API\-Speicherverwaltungsfunktionen, **LocalAlloc**\/**LocalFree** und **GlobalAlloc**\/**GlobalFree**.  
  
-   Die Verwendung der **new** und **delete**\-Operatoren.  
  
 Die Hilfe `CMemoryState` Diagnose nur erkennen die Speicherverluste, die auftreten, wenn der Arbeitsspeicher, der mithilfe des Operators **new** zugeordnet ist, nicht mit **delete** freigegeben wird.  Die anderen beiden Gruppen von Speicherverwaltungsfunktionen sind für Nicht\-C\+\+\-Programme, und das Kombinieren sie mit **new** und **delete** im selben Programm wird nicht empfohlen.  Ein zusätzliches Makro, `DEBUG_NEW`, wird bereitgestellt, um den **new**\-Operator zu ersetzen, wenn Sie Datei\- und Zeilennummerennachverfolgung der Speicherbelegungen erfordern.  `DEBUG_NEW` wird verwendet, wenn Sie normalerweise den **new**\-Operator verwenden.  
  
 Wie bei anderen Diagnose, ist die `CMemoryState` Diagnose in den Debugversionen des Programms nur verfügbar.  Eine Debugversion muss die definierte Konstante **\_DEBUG** haben.  
  
 Wenn Sie vermuten, hat das Programm einen Speicherverlust, können Sie `Checkpoint`, **Difference** und `DumpStatistics`\-Funktionen verwenden, um den Unterschied zwischen dem Speicherzustand \(die Objekte zugeordnet\) unter zwei verschiedenen Punkten in der Programmausführung zu ermitteln.  Diese Informationen können beim Ermitteln nützlich sein, ob eine Funktion alle Objekte von, die sie zuordnet.  
  
 Wenn einfach wissen, wo die Unausgeglichenheit in der Zuordnung und in der Freigabe auftritt, nicht genügend Informationen bereitstellt, können Sie die `DumpAllObjectsSince`\-Funktion verwenden, um alle zugeordneten Objekte zu speichern wie der vorherige Aufruf `Checkpoint`.  Dieser Dump zeigt die Reihenfolge der Zuordnung, der Quelldatei sowie die Zeile, in der das Objekt zugeordnet wurde \(wenn Sie `DEBUG_NEW` für Zuordnung verwenden\), und der Ableitung des Objekts, dessen Adresse und seiner Größe.  `DumpAllObjectsSince` ruft auch `Dump`\-Funktion jedes Objekts auf, um Informationen über seinen aktuellen Zustand bereitzustellen.  
  
 Weitere Informationen dazu, wie `CMemoryState` und andere Diagnoseinformationen, finden Sie unter [Debuggen von MFC\-Anwendungen](../Topic/MFC%20Debugging%20Techniques.md) verwendet.  
  
> [!NOTE]
>  Deklarationen von Objekten des Typs `CMemoryState` und der Aufrufe der Memberfunktionen sollten durch `#if defined(_DEBUG)/#endif`\-Direktive gekennzeichnet werden.  Dadurch wird die Speicherdiagnose, nur in den Debuggingsbuildern des Programms erwartet werden.  
  
## Vererbungshierarchie  
 `CMemoryState`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)