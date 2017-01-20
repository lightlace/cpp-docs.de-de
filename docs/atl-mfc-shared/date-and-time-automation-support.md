---
title: "Date and Time: Automation Support"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adding dates"
  - "Automatisierung, date and time support"
  - "calculating dates and times"
  - "Berechnungen, Datum und Uhrzeit"
  - "COleDateTime class, Automation date/time support"
  - "COleDateTimeSpan class, Automation date/time support"
  - "Datumsangaben, Automation support"
  - "Verstrichene Zeit, calculating in Automation"
  - "Formatieren [Visual Studio], Datumsangaben"
  - "Formatieren [Visual Studio], Uhrzeit"
  - "Uhrzeit [Visual Studio], Automation support"
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Date and Time: Automation Support
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie die Klassenbibliotheksdienstleistungen nutzt, die bisher verknüpft und Zeitverwaltung.  Prozeduren beschriebenes zählen:  
  
-   [Abrufen der aktuellen Uhrzeit](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [Berechnen der verstrichenen Zeit](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [Formatieren einer Zeichenfolgendarstellung einer Datum\/Uhrzeit](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)\-Klasse bietet eine Möglichkeit, Datums\- und Uhrzeitinformationen darzustellen.  Es stellt feinere Granularität und einen größeren Bereich als die [CTime](../atl-mfc-shared/reference/ctime-class.md)\-Klasse.  Die Klasse stellt [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) Laufzeit, wie der Unterschied zwischen zwei `COleDateTime`\-Objekten dar.  
  
 Die `COleDateTime` und `COleDateTimeSpan`\-Klassen dienen dazu, mit der `COleVariant`\-Klasse verwendet werden, die in der Automatisierung verwendet wird.  `COleDateTime` und `COleDateTimeSpan` sind auch in der MFC\-Datenbankprogrammierung hilfreich, aber sie können verwendet werden, wenn Sie Datums\- und Uhrzeitwerte bearbeiten möchten.  Obwohl die `COleDateTime`\-Klasse einen größeren Wertebereich und eine feinere Granularität als die `CTime`\-Klasse hat, erfordert sie mehr Speicherplatz pro Objekt als `CTime`.  Es gibt auch einige besondere Überlegungen beim Arbeiten mit dem zugrunde liegenden **DATE**\-Typ.  Siehe [Der DATUM Typ](../atl-mfc-shared/date-type.md) für weitere Details auf der Implementierung von **DATE**.  
  
 `COleDateTime`\-Objekte können verwendet werden, um Datumsangaben, 100, 9999 und 31. Dezember zwischen 1. Januar darzustellen.  `COleDateTime`\-Objekte sind Gleitkommawerte, mit einer ungefähren Auflösung von 1 Millisekunden.  `COleDateTime` basiert auf dem **DATE** Datentyp definiert, in der MFC\-Dokumentation unter [COleDateTime::operator\-DATUM](../Topic/COleDateTime::operator%20DATE.md).  Die tatsächliche Implementierung von **DATE** erstreckt sich über diesen Grenzen hinaus.  Die `COleDateTime` Implementierung erzwingt diese Grenzen auf, um mit der Klasse zu arbeiten, erleichtern.  
  
 `COleDateTime` unterstützt nicht julianische Datumsangaben.  Der gregorianische Kalender wird angenommen, dass die in der Zeit 1. Januar zu erweitern, 100.  
  
 `COleDateTime` ignoriert Sommerzeit \(DST\).  Im folgenden Codebeispiel vergleicht zwei Methoden der Ableitung einer Zeit, die das DST\-Umschaltendatum überschreitet: ein mithilfe des CRT und das andere mithilfe `COleDateTime`.  DST\-Schalter von, in den meisten Gebietsschemas, in der zweiten Woche im April und im dritten im Oktober.  
  
 Die erste Methode werden zwei `CTime`\-Objekte, *time1* und *time2*, um 5. April und 6. April verwenden, mithilfe der standardmäßigen Cstrukturen **tm** und `time_t` fest.  Der Code zeigt *time1* und *time2* und die Zeitspanne zwischen ihnen.  
  
 Die zweite Methode erstellt zwei `COleDateTime`\-Objekte, `oletime1` und `oletime2`, und legt sie auf die gleichen Daten wie *time1* und *time2* fest.  Sie zeigt `oletime1` und `oletime2` und die Zeitspanne zwischen ihnen.  
  
 Die CRT\- berechnet ordnungsgemäß einen Unterschied von 23 Stunden.  `COleDateTimeSpan` berechnet einen Unterschied von 24 Stunden.  
  
 Beachten Sie, dass eine Problemumgehung neben dem Ende des Beispiels verwendet wird, um das Datum mit dem `COleDateTime::Format` ordnungsgemäß angezeigt wird.  Weitere Informationen finden Sie im Knowledge Base\-Artikel "FEHLER: Format\("%D"\) schlägt für `COleDateTime` und `COleDateTimeSpan` fehl" \(Q167338\).  
  
 [!CODE [NVC_ATLMFC_Utilities#176](../CodeSnippet/VS_Snippets_Cpp/NVC_ATLMFC_Utilities#176)]  
  
## Siehe auch  
 [Date and Time](../atl-mfc-shared/date-and-time.md)