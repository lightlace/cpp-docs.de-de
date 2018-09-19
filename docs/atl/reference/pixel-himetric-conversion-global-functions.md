---
title: Globale Pixel HIMETRIC-Konvertierungsfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b5ab980813eec09fe0eef35f54280444d8c08b80
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105387"
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
