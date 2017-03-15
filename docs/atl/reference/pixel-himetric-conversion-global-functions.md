---
title: Globale Pixel HIMETRIC-Konvertierungsfunktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: efb7e7da896aea4e377225f4c1e2c9948e635705
ms.lasthandoff: 02/24/2017

---
# <a name="pixelhimetric-conversion-global-functions"></a>Globale Pixel/HIMETRIC-Konvertierungsfunktionen
Diese Funktionen bieten Unterstützung für die Konvertierung von Pixel und HIMETRIC-Einheiten.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC-Einheiten (à 0,01 Millimeter) konvertiert in Pixel.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Konvertiert Pixel HIMETRIC-Einheiten (à ist 0,01 Millimeter).|  
  
##  <a name="a-nameatlhimetrictopixela--atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
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
 [out] Ein Zeiger auf, in denen die Größe des Objekts in Pixel zurückgegeben werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM NR.&49;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-nameatlpixeltohimetrica--atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
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
 [out] Ein Zeiger auf, in denen die Größe des Objekts in HIMETRIC-Einheiten, die zurückgegeben werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&51;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  

## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

