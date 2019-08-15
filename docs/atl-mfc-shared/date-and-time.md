---
title: Datum und Uhrzeit
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 2a5e6977acfca51b8074399f6f9b3166c8a358bc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491298"
---
# <a name="date-and-time"></a>Datum und Uhrzeit

MFC unterstützt verschiedene Arten der Arbeit mit Datums-und Uhrzeitwerten:

- Unterstützung für den Datentyp "Automation [Date](../atl-mfc-shared/date-type.md)". Date unterstützt Datums-, Uhrzeit-und Datums-/Uhrzeitwerte. Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) -und [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) -Klassen Kapseln diese Funktionalität. Sie arbeiten mit der [COleVariant](../mfc/reference/colevariant-class.md) -Klasse unter Verwendung von Automatisierungsunterstützung.

- Allgemeine Zeit Klassen. Die [ctime](../atl-mfc-shared/reference/ctime-class.md) -und [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) -Klassen kapseln den größten Teil der mit der ANSI-Standard time-Bibliothek verknüpften Funktionalität, die zeitlich deklariert wird. Micha.

- Unterstützung für die Systemuhr. Bei MFC-Version 3,0 wurde die Unterstützung `CTime` für den Win32 `SYSTEMTIME` - `FILETIME` und den-Datentypen hinzugefügt.

## <a name="date-and-time-automation-support"></a>Datum und Uhrzeit: Automatisierungsunterstützung

Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) -Klasse bietet eine Möglichkeit zur Darstellung von Datums-und Uhrzeit Informationen. Sie bietet eine präzisere Granularität und einen größeren Bereich als die [ctime](../atl-mfc-shared/reference/ctime-class.md) -Klasse. Die [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) -Klasse stellt die verstrichene Zeit dar, z `COleDateTime` . b. den Unterschied zwischen zwei Objekten.

Die `COleDateTime` - `COleDateTimeSpan` und-Klassen sind für die Verwendung `COleVariant` mit der-Klasse konzipiert. `COleDateTime`und `COleDateTimeSpan` sind auch bei der MFC-Datenbankprogrammierung nützlich, aber Sie können immer dann verwendet werden, wenn Sie Datums-und Uhrzeitwerte bearbeiten möchten. Obwohl die `COleDateTime` -Klasse über einen größeren Wertebereich und eine präzisere Granularität `CTime` als die-Klasse verfügt, erfordert Sie mehr `CTime`Speicherplatz pro Objekt als. Beim Arbeiten mit dem zugrunde liegenden Date-Typ gibt es auch einige besondere Überlegungen. Weitere Informationen zur Implementierung von Date finden Sie [unter Date Type](../atl-mfc-shared/date-type.md).

`COleDateTime`-Objekte können zum Darstellen von Datumsangaben zwischen dem 1. Januar 100 und dem 31. Dezember 9999 verwendet werden. `COleDateTime`bei-Objekten handelt es sich um Gleit Komma Werte mit einer ungefähren Auflösung von 1 Millisekunden. `COleDateTime`basiert auf dem Date-Datentyp, der in der MFC-Dokumentation unter [COleDateTime:: Operator Date](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)definiert ist. Die tatsächliche Implementierung von Date erstreckt sich über diese Grenzen hinaus. Die `COleDateTime` -Implementierung erzwingt diese Begrenzungen, um die Arbeit mit der-Klasse zu vereinfachen.

`COleDateTime`unterstützt keine Julischen Datumsangaben. Es wird davon ausgegangen, dass der gregorianische Kalender die Zeit bis zum 1. Januar 100 verlängert.

`COleDateTime`ignoriert Sommerzeit (DST). Im folgenden Codebeispiel werden zwei Methoden zum Berechnen einer Zeitspanne verglichen, die das DST-Wechsel-Datum überschreitet: eine, die die `COleDateTime`CRT verwendet, und die andere mithilfe von.

Mit der ersten Methode werden `CTime` zwei Objekte, *zeitpunkt1 zeitlich* und *zeitpunkt2?* , auf den 5. April und den 6. April festgelegt. `tm` dabei werden die standardmäßigen C-Typstrukturen und verwendet `time_t` Im Code werden *zeitpunkt1 zeitlich* und *zeitpunkt2?* sowie die Zeitspanne zwischen Ihnen angezeigt.

Mit der zweiten Methode werden `COleDateTime` zwei- `oletime1` Objekte `oletime2`, und, erstellt und auf die gleichen Datumsangaben wie *zeitpunkt1 zeitlich* und *zeitpunkt2?* festgelegt. Darin werden `oletime1` und `oletime2` und die Zeitspanne zwischen Ihnen angezeigt.

Die CRT berechnet ordnungsgemäß einen Unterschied von 23 Stunden. `COleDateTimeSpan`berechnet einen Unterschied von 24 Stunden.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>Fragt die aktuelle Zeit ab

Im folgenden Verfahren wird gezeigt, wie ein `COleDateTime` -Objekt erstellt und mit der aktuellen Uhrzeit initialisiert wird.

#### <a name="to-get-the-current-time"></a>So erhalten Sie die aktuelle Zeit

1. Erstellen eines `COleDateTime`-Objekts

1. Rufen Sie `GetCurrentTime` auf.

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>Verstrichene Zeit berechnen

In diesem Verfahren wird gezeigt, wie Sie den unter `COleDateTime` schied zwischen zwei Objekten `COleDateTimeSpan` berechnen und ein Ergebnis erhalten.

#### <a name="to-calculate-elapsed-time"></a>So berechnen Sie verstrichene Zeit

1. Erstellen Sie `COleDateTime` zwei-Objekte.

1. Legen Sie eines der `COleDateTime` -Objekte auf die aktuelle Zeit fest.

1. Führen Sie eine zeitaufwändige Aufgabe aus.

1. Legen Sie das `COleDateTime` andere-Objekt auf die aktuelle Zeit fest.

1. Nehmen Sie den Unterschied zwischen den beiden Zeiten vor.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>Uhrzeit formatieren

#### <a name="to-format-a-time"></a>So formatieren Sie eine Uhrzeit

Verwenden Sie `Format` die Member-Funktion von [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) oder [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) , um eine Zeichenfolge zu erstellen, die die Uhrzeit oder die verstrichene Zeit darstellt.

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

Weitere Informationen finden Sie Unterklasse [COleVariant](../mfc/reference/colevariant-class.md).

## <a name="date-and-time-database-support"></a>Datum und Uhrzeit: Datenbankunterstützung

Ab Version 4,0 werden von der MFC-Datenbankprogrammierung die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) -und [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) -Klassen verwendet, um Datums-und Uhrzeit Daten darzustellen. Diese Klassen, die auch in Automation verwendet werden, werden von der Klasse [COleVariant](../mfc/reference/colevariant-class.md)abgeleitet. Sie bieten eine bessere Unterstützung für die Verwaltung von Datums-und Uhrzeitdaten als [ctime](../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md).

## <a name="date-and-time-systemtime-support"></a>Datum und Uhrzeit: SYSTEMTIME-Unterstützung

Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) -Klasse verfügt über Konstruktoren, die System-und Datei Zeiten von Win32 akzeptieren.

Die Win32 `FILETIME` -Struktur stellt die Zeit als 64-Bit-Wert dar. Es ist ein bequemeres Format für den internen Speicher als `SYSTEMTIME` eine Struktur und das von Win32 verwendete Format zum Darstellen der Zeit der Dateierstellung. Weitere Informationen zur SYSTEMTIME-Struktur finden Sie unter [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime). Weitere Informationen zur FILETIME-Struktur finden Sie unter [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime).

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)\
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
