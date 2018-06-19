---
title: 'Datum und Uhrzeit: Automatisierungsunterstützung | Microsoft Docs'
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
ms.openlocfilehash: 915bcd5487f423b6240061a0e85f5554a3224397
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357593"
---
# <a name="date-and-time-automation-support"></a>Datum und Uhrzeit:-Unterstützung
Dieser Artikel beschreibt, wie die Klasse Bibliotheksdienste im Zusammenhang mit der Verwaltung von Datum und Uhrzeit nutzen. Verfahren beschriebenen Schritten:  
  
-   [Abrufen der aktuellen Uhrzeit](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [Berechnen der verstrichenen Zeit](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [Eine Zeichenfolgendarstellung einer Datums-/Uhrzeit formatieren](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) -Klasse bietet eine Möglichkeit zur Darstellung von Datums-und Uhrzeitinformationen. Er bietet eine geringere Granularität und einen größeren Bereich als das [CTime](../atl-mfc-shared/reference/ctime-class.md) Klasse. Die [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) Klasse darstellt, verstrichene Zeit, beispielsweise den Unterschied zwischen zwei `COleDateTime` Objekte.  
  
 Die `COleDateTime` und `COleDateTimeSpan` Klassen dienen, mit der `COleVariant` Klasse zur Verwendung in Automation. `COleDateTime` und `COleDateTimeSpan` sind auch nützlich, bei der MFC-datenbankprogrammierung, aber Sie können jederzeit zum Bearbeiten von Datums-und Uhrzeitwerte verwendet werden können. Obwohl die `COleDateTime` -Klasse verfügt über einen größeren Bereich von Werten und feineren Granularität als die `CTime` -Klasse, es erfordert mehr Speicherplatz pro Objekt als `CTime`. Es gibt auch einige Besonderheiten beim Arbeiten mit den zugrunde liegenden **Datum** Typ. Finden Sie unter [DATE-Datentyps](../atl-mfc-shared/date-type.md) Weitere Details zur Implementierung **Datum**.  
  
 `COleDateTime` Objekte können verwendet werden, um die Datumsangaben zwischen dem 1. Januar 100 und dem 31. Dezember 9999 darstellen. `COleDateTime` Objekte sind Gleitkomma-Point-Werte mit einer Auflösung von 1 Millisekunde. `COleDateTime` basiert auf der **Datum** Datentyp in der MFC-Dokumentation unter [COleDateTime:: Operator Datum](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Die tatsächliche Implementierung der **Datum** diese Grenzen überschreitet. Die `COleDateTime` Implementierung erzwingt diese Grenzen, um die Arbeit mit der Klasse zu erleichtern.  
  
 `COleDateTime` julianischen unterstützt nicht. Wird davon ausgegangen, dass dem gregorianischen Kalender um zeitlich zurückversetzt auf dem 1. Januar 100 zu erweitern.  
  
 `COleDateTime` Daylight Saving Time (DST) wird ignoriert. Im folgenden Codebeispiel wird vergleicht zwei Methoden zur Berechnung eine Zeitspanne, die die DST-Umstellungsdatum schneidet: einer mit der CRT, und der andere mit `COleDateTime`. DST wechselt über, in den meisten Gebietsschemas in der zweiten Woche im April und der dritte im Oktober.  
  
 Die erste Methode legt zwei `CTime` Objekte *zeitpunkt1* und *zeitpunkt2*April 5 und 6. April, mithilfe der standard C-Typ-Strukturen **tm** und `time_t`. Zeigt der Code *zeitpunkt1* und *zeitpunkt2* und die Zeitspanne zwischen ihnen.  
  
 Die zweite Methode erstellt zwei `COleDateTime` Objekte `oletime1` und `oletime2`, und setzt sie auf der gleichen Datumsangaben als *zeitpunkt1* und *zeitpunkt2*. Es zeigt `oletime1` und `oletime2` und die Zeitspanne zwischen ihnen.  
  
 Die CRT berechnet ordnungsgemäß eine Differenz von 23 Stunden an. `COleDateTimeSpan` berechnet einen Unterschied von 24 Stunden.  
  
 Beachten Sie, dass dieses Problem zu umgehen gegen Ende des Beispiels verwendet wird, um das Datum, die ordnungsgemäß mit anzuzeigen `COleDateTime::Format`. Finden Sie im Knowledge Base-Artikel "BUG: Format("%D") Fails für `COleDateTime` und `COleDateTimeSpan`" (Q167338).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md)

