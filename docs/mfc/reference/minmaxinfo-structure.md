---
title: MINMAXINFO-Struktur
ms.date: 11/04/2016
f1_keywords:
- MINMAXINFO
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
ms.openlocfilehash: 11f55b1756623626769e21c006543b6993607b08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517844"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO-Struktur

Die `MINMAXINFO` Struktur enthält Informationen über die Größe eines Fensters maximiert und die Position und die nachverfolgung von minimalen und maximalen Größe.

## <a name="syntax"></a>Syntax

```
typedef struct tagMINMAXINFO {
    POINT ptReserved;
    POINT ptMaxSize;
    POINT ptMaxPosition;
    POINT ptMinTrackSize;
    POINT ptMaxTrackSize;
} MINMAXINFO;
```

#### <a name="parameters"></a>Parameter

*ptReserved*<br/>
Für die interne Verwendung vorgesehen.

*ptMaxSize*<br/>
Gibt an, die maximierten Breite (point.x) und der maximierten Höhe (point.y) des Fensters.

*ptMaxPosition*<br/>
Gibt die Position des linken Rands des maximierten Fensters (point.x) und die Position des oberen Rands der maximierten Fensters (point.y).

*ptMinTrackSize*<br/>
Gibt die minimale Trackingbreite (point.x) und die minimale Höhe (point.y) des Fensters nachverfolgen.

*ptMaxTrackSize*<br/>
Gibt die maximale Breite (point.x) nachverfolgen und die maximale Höhe (point.y) des Fensters nachverfolgen.

## <a name="requirements"></a>Anforderungen

**Header:** winuser.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

