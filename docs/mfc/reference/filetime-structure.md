---
title: FILETIME-Struktur
ms.date: 11/04/2016
f1_keywords:
- FILETIME
helpviewer_keywords:
- FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
ms.openlocfilehash: f70792b83637018e707b6ee48d1b169f28d46d71
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514932"
---
# <a name="filetime-structure"></a>FILETIME-Struktur

Die `FILETIME` Struktur ist eine 64-Bit-Wert, der die Anzahl der 100-Nanosekunden-Intervalle seit dem 1. Januar 1601 darstellt.

## <a name="syntax"></a>Syntax

```
typedef struct _FILETIME {
    DWORD dwLowDateTime;   /* low 32 bits */
    DWORD dwHighDateTime;  /* high 32 bits */
} FILETIME, *PFILETIME, *LPFILETIME;
```

#### <a name="parameters"></a>Parameter

*dwLowDateTime*<br/>
Gibt den niedrigsten 32 Bits der Dateizeit an.

*dwHighDateTime*<br/>
Gibt das Tageshoch 32 Bits der Dateizeit an.

## <a name="requirements"></a>Anforderungen

**Header:** windef.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CTime:: CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

