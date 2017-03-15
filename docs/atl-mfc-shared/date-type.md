---
title: "DATE Type | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "DATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Date-Datentyp"
  - "Date-Datentyp, about Date data type"
  - "Date-Datentyp, Implementieren"
  - "DATE type"
  - "hour values representation"
  - "MFC, Datum und Uhrzeit"
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# DATE Type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der **date**\-Typ wird mithilfe einer 8\-Byte\-Gleitkommawert\-Zahl implementiert.  Tage werden durch die Schritte der ganzen Zahl dargestellt, die mit am 30. Dezember 1899, Mitternacht wie Zeit null starten.  Stundenwerte werden wie der absolute Wert des Nachkommastellen der Zahl ausgedrückt.  In der folgenden Tabelle werden einige Datumsangaben zusammen mit ihrer Entsprechung **date** numerischen Typs:  
  
|Datum und Uhrzeit|Darstellung|  
|-----------------------|-----------------|  
|30. Dezember 1899 Mitternacht|0.00|  
|1. Januar 1900 Mitternacht|2.00|  
|4. Januar 1900 Mitternacht|5.00|  
|4. Januar 1900 6 Uhr..|5.25|  
|4. Januar 1900 Mittag|5.50|  
|4. Januar 1900 9 PM..|5.875|  
  
 Der **date** Datumstyp sowie die `COleDateTime`\-Klasse, stellt Datumsangaben und Uhrzeiten als klassischer Zahlenstrahl dar.  Die `COleDateTime`\-Klasse enthält mehrere Methoden zum Bearbeiten von Datumswerten, einschließlich Konvertierung nach und anderen allgemeinen Datumsformate.  
  
 Die folgenden Punkte sollten beim Arbeiten erwähnt werden, mit diesen Datums\- und Uhrzeitformate in der Automatisierung:  
  
-   Datumsangaben werden in der Ortszeit angegeben; Synchronisierung muss manuell ausgeführt werden beim Arbeiten mit Datumsangaben in verschiedenen Zeitzonen.  
  
-   Die Datumstypen für nicht Sommerzeit.  
  
-   Die Datumszeitachse wird für Datumswerte kleiner als 0 unterbrochen \(vor dem 30. Dezember 1899\).  Das liegt daran, dass der Teil der ganzen Zahl des Datumswerts behandelt wird, wie signiert, während der Sekundenbruchteile Teil behandelt wird, wie ohne Vorzeichen.  Das heißt, kann der Teil der ganzen Zahl des Datumswerts positiv oder negativ, während der Sekundenbruchteile Teil des Datumswerts immer mit dem gesamten logischen Datum hinzugefügt wird.  In der folgenden Tabelle werden einige Beispiele:  
  
|Datum und Uhrzeit|Darstellung|  
|-----------------------|-----------------|  
|27. Dezember 1899 Mitternacht|\-3.00|  
|28. Dezember 1899 Mittag|\-2.50|  
|28. Dezember 1899 Mitternacht|\-2.00|  
|29. Dezember 1899 Mitternacht|\-1.00|  
|30. Dezember 1899 6 PM..|\-0.75|  
|30. Dezember 1899 Mittag|\-0.50|  
|30. Dezember 1899 6 Uhr..|\-0.25|  
|30. Dezember 1899 Mitternacht|0.00|  
|30. Dezember 1899 6 Uhr..|0.25|  
|30. Dezember 1899 Mittag|0.50|  
|30. Dezember 1899 6 PM..|0.75|  
|31. Dezember 1899 Mitternacht|1.00|  
|1. Januar 1900 Mitternacht|2.00|  
|1. Januar 1900 Mittag|2.50|  
|2. Januar 1900 Mitternacht|3.00|  
  
> [!CAUTION]
>  Beachten Sie, dass da 6:00 AM immer über einen Bruchen Wert 0,25 unabhängig davon, ob die ganze Zahl, die den Tag darstellt, dass positiv ist \(nach dem 30. Dezember 1899\) oder negativ \(vor dem 30. Dezember 1899\), ein einfacher Gleitkommavergleich würde fälschlicherweise sortieren jedes **date** dargestellt wird, das ein Tag um 6:00 Uhr früher als 12\/30\/1899 darstellt, wie *später* als **date**, das 7:00 Uhr an diesem gleichen Tag darstellt.  
  
 Weitere Informationen zu Problemen, die den **date** und `COleDateTime`\-Typen verknüpft sind, können mit [COleDateTime Class](../atl-mfc-shared/reference/coledatetime-class.md) und [Date and Time: Automation Support](../atl-mfc-shared/date-and-time-automation-support.md) gefunden werden.  
  
## Siehe auch  
 [Date and Time](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime Class](../atl-mfc-shared/reference/coledatetime-class.md)