---
title: 'Datum und Uhrzeit: Automatisierungsunterstützung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- formatting [Visual Studio], dates
- dates, Automation support
- elapsed time, calculating in Automation
- COleDateTime class, Automation date/time support
- COleDateTimeSpan class, Automation date/time support
- Automation, date and time support
- formatting [Visual Studio], time
- calculations, date and time
- time [Visual Studio], Automation support
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5f6f0c6bf9933f06da4b50f9754a0d68814e16b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883751"
---
# <a name="date-and-time-automation-support"></a>Datum und Uhrzeit: Automatisierungsunterstützung
Dieser Artikel beschreibt, wie Sie die Dienste im Zusammenhang mit der Verwaltung von Datum und Uhrzeit-Bibliothek nutzen. Beschriebenen Verfahren zählen:  
  
-   [Die aktuelle Uhrzeit abrufen](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [Berechnen der verstrichenen Zeit](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [Eine Zeichenfolgendarstellung einer Datums-/Uhrzeit formatieren](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) -Klasse bietet eine Möglichkeit zur Darstellung von Datums-und Uhrzeitinformationen. Es bietet eine feinere Granularität und einen größeren Bereich als die [CTime](../atl-mfc-shared/reference/ctime-class.md) Klasse. Die [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) Klasse stellt die verstrichene Zeit an, wie z. B. den Unterschied zwischen zwei `COleDateTime` Objekte.  
  
 Die `COleDateTime` und `COleDateTimeSpan` Klassen dienen, mit der `COleVariant` Klasse zur Verwendung in Automation. `COleDateTime` und `COleDateTimeSpan` eignen sich auch bei der MFC-datenbankprogrammierung, aber sie können verwendet werden, wenn Sie die Datums-und Uhrzeitwerte ändern möchten. Obwohl die `COleDateTime` -Klasse verfügt über einen größeren Bereich von Werten und eine feinere Abstufung der `CTime` -Klasse, es benötigt mehr Speicher pro Objekt als `CTime`. Es gibt auch einige besonderen Überlegungen bei der Arbeit mit der zugrunde liegenden DATE-Datentyp. Finden Sie unter [den Datumstyp](../atl-mfc-shared/date-type.md) für Weitere Informationen zur Implementierung des DATUMS.  
  
 `COleDateTime` Objekte können verwendet werden, um Daten zwischen dem 1. Januar 100 und dem 31. Dezember 9999 darstellen. `COleDateTime` Objekte sind Point-Werte, mit der eine Auflösung von 1 Millisekunde Gleitkommawert. `COleDateTime` basiert auf der DATE-Datentyp, in die MFC-Dokumentation unter definierten [COleDateTime:: Operator Datum](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Die tatsächliche Implementierung des DATUMS ist diese Grenzen überschreitet. Die `COleDateTime` Implementierung erzwingt diese Grenzen, um die Arbeit mit der Klasse zu erleichtern.  
  
 `COleDateTime` julianischen unterstützt nicht. Dem gregorianischen Kalender wird angenommen, in der Zeit zurück, der dem 1. Januar 100 erweitern.  
  
 `COleDateTime` Sommerzeit (DST) wird ignoriert. Im folgenden Codebeispiel werden zwei Methoden zum Berechnen der Zeitspanne, die die DST-Umstellungsdatum überschreitet verglichen: eins mit der CRT und der andere mit `COleDateTime`. DST umgestellt, in den meisten Regionen, in der zweiten Woche im April und der dritte im Oktober.  
  
 Die erste Methode legt zwei `CTime` Objekte *zeitpunkt1 zeitlich* und *zeitpunkt2*, 5. April und dem 6. April, mithilfe der standardmäßigen C-Typ-Strukturen `tm` und `time_t`. Der Code zeigt *zeitpunkt1 zeitlich* und *zeitpunkt2* und der Zeitspanne zwischen ihnen.  
  
 Die zweite Methode erstellt zwei `COleDateTime` Objekte `oletime1` und `oletime2`, und sie auf die gleichen Daten als *zeitpunkt1 zeitlich* und *zeitpunkt2*. Es zeigt `oletime1` und `oletime2` und der Zeitspanne zwischen ihnen.  
  
 Die CRT wird ordnungsgemäß einen Unterschied in der nächsten 23 Stunden berechnet. `COleDateTimeSpan` berechnet einen Unterschied von 24 Stunden.  
  
 Beachten Sie, dass eine problemumgehung in der Nähe des des Beispiels verwendet wird, zum Anzeigen des Datums, die ordnungsgemäß mit `COleDateTime::Format`. Finden Sie unter im Knowledge Base-Artikel "BUG: Format("%D") fehlschlägt `COleDateTime` und `COleDateTimeSpan`" (Q167338).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md)

