---
title: Globale Pixel HIMETRIC-Konvertierungsfunktionen
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
ms.openlocfilehash: 43a12985f259603a9b67f22f7a7891bf847c0b0f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62276834"
---
# <a name="pixelhimetric-conversion-global-functions"></a>Globale Pixel/HIMETRIC-Konvertierungsfunktionen

Diese Funktionen bieten Unterstützung für die Konvertierung zu und von Pixel- und den HIMETRIC-Einheiten.

> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter) konvertiert in Pixel.|
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Konvertiert Pixel HIMETRIC-Einheiten (jede Einheit ist 0,01 Millimeter).|

##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel

Konvertiert die Größe eines Objekts von HIMETRIC-Einheiten (à 0,01 Millimeter) in Pixel auf dem Bildschirmgerät.

```
extern void AtlHiMetricToPixel(
    const SIZEL* lpSizeInHiMetric,
    LPSIZEL lpSizeInPix);
```

### <a name="parameters"></a>Parameter

*lpSizeInHiMetric*<br/>
[in] Zeiger auf die Größe des Objekts in HIMETRIC-Einheiten.

*lpSizeInPix*<br/>
[out] Zeiger, in dem sich die Größe des Objekts in Pixel, die zurückgegeben werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="atlpixeltohimetric"></a>  AtlPixelToHiMetric

Konvertiert die Größe eines Objekts von Pixeln auf dem Bildschirmgerät in HIMETRIC-Einheiten (à 0,01 Millimeter).

```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix,
    LPSIZEL lpSizeInHiMetric);
```

### <a name="parameters"></a>Parameter

*lpSizeInPix*<br/>
[in] Zeiger auf die Größe des Objekts in Pixel.

*lpSizeInHiMetric*<br/>
[out] Zeiger, in dem sich die Größe des Objekts in HIMETRIC-Einheiten, die zurückgegeben werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)
