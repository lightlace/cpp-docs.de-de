---
title: "Hilfsfunktionen f&#252;r die Auflistungsklasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Auflistungsklassen, Hilfsfunktionen"
  - "ConstructElements-Funktion"
  - "DestructElements-Funktion"
  - "Hilfsprogrammfunktionen-Auflistungsklasse"
  - "SerializeElements-Funktion"
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
caps.latest.revision: 14
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Hilfsfunktionen f&#252;r die Auflistungsklasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Auflistungsklassen `CMap`, `CList` und auf Vorlagen basierende globale Hilfsfunktionen `CArray` verwenden zu solchen Zwecke, z Elemente Vergleichen, Kopieren und Serialisieren.  Als Teil der Implementierung von Klassen auf `CMap`, `CList` und `CArray`, müssen Sie diese Funktionen mit den Versionen ggf. überschreiben, die zum Typ der Daten angepasst werden, die in der Zuordnung, Auflisten oder im Array gespeichert werden.  Informationen zum Überschreiben von Hilfsfunktionen wie `SerializeElements`, finden Sie im Artikel [Auflistungen: Wie Sie eine typsichere Auflistung macht](../../mfc/how-to-make-a-type-safe-collection.md).  Beachten Sie, dass **ConstructElements** und **DestructElements** veraltet sind.  
  
 Die Microsoft Foundation Class\-Bibliothek stellt die folgenden globalen Funktionen, die Ihnen helfen, Ihre Auflistungsklassen anzupassen:  
  
### Auflistungsklassen\-Hilfen  
  
|||  
|-|-|  
|[CompareElements](../Topic/CompareElements.md)|Gibt an, ob Elemente gleich sind.|  
|[CopyElements](../Topic/CopyElements.md)|Kopienelemente von einem Array in ein anderes.|  
|[DumpElements](../Topic/DumpElements.md)|Bietet Stream\-ausgerichtete Diagnoseausgabe.|  
|[HashKey](../Topic/HashKey.md)|Berechnet eine Hashtaste.|  
|[SerializeElements](../Topic/SerializeElements.md)|Speicher oder ruft Elemente zu oder von einem Archiv ab.|  
  
## Siehe auch  
 [MFC\-Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMap Class](../../mfc/reference/cmap-class.md)   
 [CList Class](../../mfc/reference/clist-class.md)   
 [CArray Class](../../mfc/reference/carray-class.md)