---
title: "Date and Time: General-Purpose Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "date and time classes"
  - "time classes"
ms.assetid: b8115d7f-428a-4c41-9970-18502f2caca2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Date and Time: General-Purpose Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie die allgemeinen Dienste der Klassenbibliothek nutzt, die bisher verknüpft und Zeitverwaltung.  Prozeduren beschriebenes zählen:  
  
-   [Abrufen der aktuellen Uhrzeit](../atl-mfc-shared/current-time-general-purpose-classes.md)  
  
-   [Berechnen der verstrichenen Zeit](../atl-mfc-shared/elapsed-time-general-purpose-classes.md)  
  
-   [Formatieren einer Zeichenfolgendarstellung einer Datum\/Uhrzeit](../atl-mfc-shared/formatting-time-values-general-purpose-classes.md)  
  
 Die `CTime`\-Klasse bietet eine Möglichkeit, Datums\- und Uhrzeitinformationen leicht darzustellen.  Die Klasse stellt `CTimeSpan` Laufzeit, wie der Unterschied zwischen zwei `CTime`\-Objekten dar.  
  
> [!NOTE]
>  CTime\-Objekte können verwendet werden, um Datumsangaben und dem 18. Januar 2038 zwischen dem 1. Januar 1970 darzustellen.  `CTime`\-Objekte haben eine Auflösung von 1 Sekunden.  `CTime` basiert auf dem `time_t` Datentyp definiert, in der Laufzeitbibliotheksreferenz.  
  
## Siehe auch  
 [Date and Time](../atl-mfc-shared/date-and-time.md)