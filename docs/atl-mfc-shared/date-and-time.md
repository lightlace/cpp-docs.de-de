---
title: "Date and Time | Microsoft Docs"
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
  - "Datumsangaben, MFC"
  - "MFC, Datum und Uhrzeit"
  - "Uhrzeit"
  - "Uhrzeit, MFC-Programmierung"
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Date and Time
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC unterstützt mehrere verschiedene Möglichkeiten der Arbeit mit Datums\- und Uhrzeitangaben.  Dazu gehören:  
  
-   Allgemeine Zeitklassen.  Die [CTime](../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)\-Klassen kapseln die Funktionalität, die der ANSI\-Standard Zeitbibliothek zugeordnet ist, die in TIME.H. deklariert wird.  
  
-   Unterstützung für Systemuhr.  Mit MFC\-Version 3.0, wurde die Unterstützung zu `CTime` für Win32 `SYSTEMTIME` und `FILETIME` Datentypen hinzugefügt.  
  
-   Unterstützung für die Automatisierung [DATUMSdatentyp](../atl-mfc-shared/date-type.md).  **DATE** Unterstützung wurde, wird und Datums\-\/Uhrzeitwert Zeit fest.  Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) und [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)\-Klassen kapseln diese Funktion.  Sie können mit der [COleVariant](../mfc/reference/colevariant-class.md)\-Klasse mithilfe der Automatisierungsunterstützung.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Datum und Uhrzeit: Allgemeine Klassen](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
-   [Datum und Uhrzeit: SYSTEMTIME\-Unterstützung](../atl-mfc-shared/date-and-time-systemtime-support.md)  
  
-   [Datum und Uhrzeit: Automatisierungs\-Unterstützung](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Datum und Uhrzeit: Datenbankunterstützung](../atl-mfc-shared/date-and-time-database-support.md)  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)