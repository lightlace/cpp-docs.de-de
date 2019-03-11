---
title: Datum und Uhrzeit
ms.date: 11/04/2016
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 32222b4a2a529716db2c414e0281e1b1ba16a0dd
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739169"
---
# <a name="date-and-time"></a>Datum und Uhrzeit

MFC unterstützt mehrere verschiedene Möglichkeiten zum Arbeiten mit Datums- und Uhrzeitangaben. Dazu gehören:

- Allgemeine Zeit-Klassen. Die [CTime](../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md) Klassen kapseln die meisten der Funktionen im Zusammenhang mit der ANSI-Standard-Zeit-Bibliothek, die in-TIME deklariert ist. H.

- Unterstützung für die Systemuhr. Mit MFC, Version 3.0,-Unterstützung wurde hinzugefügt, um `CTime` für die Win32- `SYSTEMTIME` und `FILETIME` -Datentypen.

- Unterstützung für die Automatisierung [DATE-Datentyps](../atl-mfc-shared/date-type.md). Datum unterstützt das Datum, Uhrzeit und Datum/Uhrzeit-Werten. Die [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) und [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) Klassen kapseln, diese Funktionalität. Sie funktionieren mit der [COleVariant](../mfc/reference/colevariant-class.md) -Klasse unter Verwendung von-Unterstützung.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Datum und Uhrzeit: SYSTEMTIME-Unterstützung](../atl-mfc-shared/date-and-time-systemtime-support.md)

- [Datum und Uhrzeit: Automatisierungsunterstützung](../atl-mfc-shared/date-and-time-automation-support.md)

- [Datum und Uhrzeit: Datenbankunterstützung](../atl-mfc-shared/date-and-time-database-support.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
