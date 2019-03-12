---
title: DATE-Typ
ms.date: 11/04/2016
f1_keywords:
- DATE
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
ms.openlocfilehash: bd63b400cad6efc3b3899c17a3bf835596b4008c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750389"
---
# <a name="date-type"></a>DATE-Typ

Der DATE-Datentyp wird über eine 8-Byte-Gleitkommazahl implementiert. Tage werden durch ganze Zahl erhöht werden ab 30. Dezember 1899 Mitternacht als Zeit 0 (null) dargestellt. Stundenwerte werden als der Absolute Wert des Bruchteils der Zahl ausgedrückt. Die folgende Tabelle zeigt verschiedene Datumsangaben sowie das Datum numerischen Typ-äquivalent:

|Datum und Uhrzeit|Darstellung|
|-------------------|--------------------|
|Am 30. Dezember 1899 Mitternacht|0.00|
|1. Januar 1900, Mitternacht|2.00|
|4. Januar 1900, Mitternacht|5.00|
|4. Januar 1900, 6 Uhr morgens|5.25|
|4. Januar 1900 Mittag|5.50|
|4. Januar 1900, 21: 00 Uhr|5.875|

Der DATE-Datentyp, als auch die `COleDateTime` Klasse, stellt-Datumsangaben und Uhrzeiten als eine klassische-Position. Die `COleDateTime` Klasse enthält mehrere Methoden zum Bearbeiten von Datumswerten, einschließlich der Konvertierung in und aus anderen gängige Datumsformate.

Folgendes sollte geachtet werden, bei der Arbeit mit diesen Datums- und Uhrzeitformate in Automation:

- Datumsangaben werden in Ortszeit angegeben. Synchronisierung muss manuell ausgeführt werden, bei der Arbeit mit Daten in verschiedenen Zeitzonen.

- Der Date-Datentypen werden nicht für die Sommerzeit berücksichtigt.

- Die Date-Zeitachse wird (vor dem 30. Dezember 1899) für die Date-Werte kleiner als 0 ist nicht zusammenhängend. Dies ist, da der ganzzahlige Teil des Datumswerts behandelt wird, als signiert, während der Bruchteil behandelt wird, als Zahl ohne Vorzeichen. Das heißt, der ganzzahlige Teil des Datumswerts möglicherweise positiv oder negativ ist, während der Bruchteil den Date-Wert immer dem gesamten logischen Datum hinzugefügt wird. Die folgende Tabelle zeigt einige Beispiele:

|Datum und Uhrzeit|Darstellung|
|-------------------|--------------------|
|27 Dezember 1899 wieder, Mitternacht|-3.00|
|28 Dezember 1899 wieder, Noon|-2.50|
|28 Dezember 1899 wieder, Mitternacht|-2.00|
|29. Dezember 1899, Mitternacht|-1.00|
|Am 30. Dezember 1899 18: 00 Uhr|-0.75|
|Am 30. Dezember 1899 Mittag|-0.50|
|Am 30. Dezember 1899 6 Uhr morgens|-0.25|
|Am 30. Dezember 1899 Mitternacht|0.00|
|Am 30. Dezember 1899 6 Uhr morgens|0.25|
|Am 30. Dezember 1899 Mittag|0.50|
|Am 30. Dezember 1899 18: 00 Uhr|0.75|
|31. Dezember 1899, Mitternacht|1.00|
|1. Januar 1900, Mitternacht|2.00|
|1. Januar 1900 Mittag|2.50|
|2 Januar 1900 (Mitternacht)|3.00|

> [!CAUTION]
>  Beachten Sie, dass 06:00 Uhr wird immer durch einen Teilwert 0,25 unabhängig davon, ob die ganze Zahl, die den Tag darstellt (nach dem 30. Dezember 1899 wieder) positiv ist dargestellt oder negativ (vor dem 30. Dezember 1899 wieder), ein einfachen floating-Point-Vergleich wird fälschlicherweise sortieren beliebiges Datum für 6:00 an einem Tag älter als 12/30/1899 zurück als *später* als ein Datum, der für 7:00 für denselben Tag.

Weitere Informationen zu Problemen im Zusammenhang mit der das Datum und `COleDateTime` Typen finden Sie unter [COleDateTime-Klasse](../atl-mfc-shared/reference/coledatetime-class.md) und [Datum und Uhrzeit: Automatisierungsunterstützung](../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="see-also"></a>Siehe auch

[Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md)<br/>
[COleDateTime-Klasse](../atl-mfc-shared/reference/coledatetime-class.md)
