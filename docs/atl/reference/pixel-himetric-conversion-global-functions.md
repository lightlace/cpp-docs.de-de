---
title: Globale Pixel HIMETRIC-Konvertierungsfunktionen | Microsoft Docs
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
ms.openlocfilehash: 92d84204bdf02e75f1baf64bd52d96eab0b3d271
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="pixelhimetric-conversion-global-functions"></a>Globale Pixel/HIMETRIC-Konvertierungsfunktionen
Diese Funktionen bieten Unterstützung für das Konvertieren von Pixel- und HIMETRIC-Einheiten.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC-Einheiten (à 0,01 Millimeter) konvertiert in Pixel.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Konvertiert von Pixel in HIMETRIC-Einheiten (à ist 0,01 Millimeter).|  
  
##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel  
 Konvertiert die Größe eines Objekts von HIMETRIC-Einheiten (à 0,01 Millimeter) in Pixel auf dem Bildschirmgerät.  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>Parameter  
 `lpSizeInHiMetric`  
 [in] Zeiger auf die Größe des Objekts in HIMETRIC-Einheiten.  
  
 `lpSizeInPix`  
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
 `lpSizeInPix`  
 [in] Ein Zeiger auf die Größe des Objekts in Pixel.  
  
 `lpSizeInHiMetric`  
 [out] Zeiger, in dem sich die Größe des Objekts in HIMETRIC-Einheiten, die zurückgegeben werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  

## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)
