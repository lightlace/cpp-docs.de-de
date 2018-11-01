---
title: SYSTEMTIME-Struktur
ms.date: 11/04/2016
f1_keywords:
- SYSTEMTIME
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
ms.openlocfilehash: b46482a9f4eb0165b72d74cb7d69e96e2a15e953
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559047"
---
# <a name="systemtime-structure"></a>SYSTEMTIME-Struktur

Die Struktur `SYSTEMTIME` stellt ein Datum und eine Uhrzeit dar, mit jeweils einzelnen Membern für Monat, Tag, Jahr, Wochentag, Stunde, Minute, Sekunde und Millisekunde.

## <a name="syntax"></a>Syntax

```
typedef struct _SYSTEMTIME {
    WORD wYear;
    WORD wMonth;
    WORD wDayOfWeek;
    WORD wDay;
    WORD wHour;
    WORD wMinute;
    WORD wSecond;
    WORD wMilliseconds;
} SYSTEMTIME;
```

#### <a name="parameters"></a>Parameter

*Mitglieder "wYear"*<br/>
Das aktuelle Jahr.

*"wMonth"*<br/>
Der aktuelle Monat; Januar ist 1.

*wDayOfWeek*<br/>
Der aktuelle Wochentag; Sonntag ist 0, Montag ist 1, usw.

*"wDay"*<br/>
Der aktuelle Tag des Monats.

*wHour*<br/>
Die aktuelle Stunde.

*"wMinute"*<br/>
Die aktuelle Minute.

*wSecond*<br/>
Der aktuelle Sekunde.

*wMilliseconds*<br/>
Die aktuelle Millisekunde.

## <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]

## <a name="requirements"></a>Anforderungen

**Header:** winbase.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime:: CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

