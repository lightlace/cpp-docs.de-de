---
title: SYSTEMTIME-Struktur 1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79c7cec92550ad51b53242b44b3aee334be21f3f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397207"
---
# <a name="systemtime-structure1"></a>SYSTEMTIME-Struktur 1

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

