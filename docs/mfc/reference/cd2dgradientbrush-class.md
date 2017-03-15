---
title: CD2DGradientBrush-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DGradientBrush
- afxrendertarget/CD2DGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DGradientBrush class
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
caps.latest.revision: 17
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 0b0a692ef2b5194daf7b38eed9ebe3b2f4eda448
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush-Klasse
Die Basisklasse der CD2DLinearGradientBrush und der CD2DRadialGradientBrush-Klassen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|Erstellt ein CD2DGradientBrush-Objekt.|  
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#cd2dgradientbrush__~cd2dgradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsel mit Farbverlauf-Objekt zerstört wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGradientBrush:: Destroy](#destroy)|Zerstört ein CD2DGradientBrush-Objekt. (Überschreibt [CD2DBrush:: Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|Array von D2D1_GRADIENT_STOP-Strukturen.|  
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|Der Speicherplatz in der die Interpolation zwischen den Farbverlaufsunterbrechungspunkten ausgeführt wird.|  
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|Das Verhalten des Farbverlaufs außerhalb der normalisierten Bereich [0,1].|  
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DGradientBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dgradientbrusha--cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a>CD2DGradientBrush:: ~ CD2DGradientBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsel mit Farbverlauf-Objekt zerstört wird.  
  
```  
virtual ~CD2DGradientBrush();
```  
  
##  <a name="a-namecd2dgradientbrusha--cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a>CD2DGradientBrush::CD2DGradientBrush  
 Erstellt ein CD2DGradientBrush-Objekt.  
  
```  
CD2DGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `gradientStops`  
 Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.  
  
 `gradientStopsCount`  
 Ein Wert größer als oder gleich 1, der die Anzahl der Farbverlaufsstopps im GradientStops-Array angibt.  
  
 `colorInterpolationGamma`  
 Der Speicherplatz in der die Interpolation zwischen den Farbverlaufsunterbrechungspunkten ausgeführt wird.  
  
 `extendMode`  
 Das Verhalten des Farbverlaufs außerhalb der normalisierten Bereich [0,1].  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="a-namedestroya--cd2dgradientbrushdestroy"></a><a name="destroy"></a>CD2DGradientBrush:: Destroy  
 Zerstört ein CD2DGradientBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namemargradientstopsa--cd2dgradientbrushmargradientstops"></a><a name="m_argradientstops"></a>CD2DGradientBrush::m_arGradientStops  
 Array von D2D1_GRADIENT_STOP-Strukturen.  
  
```  
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;  
```  
  
##  <a name="a-namemcolorinterpolationgammaa--cd2dgradientbrushmcolorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a>CD2DGradientBrush::m_colorInterpolationGamma  
 Der Speicherplatz in der die Interpolation zwischen den Farbverlaufsunterbrechungspunkten ausgeführt wird.  
  
```  
D2D1_GAMMA m_colorInterpolationGamma;  
```  
  
##  <a name="a-namemextendmodea--cd2dgradientbrushmextendmode"></a><a name="m_extendmode"></a>CD2DGradientBrush::m_extendMode  
 Das Verhalten des Farbverlaufs außerhalb der normalisierten Bereich [0,1].  
  
```  
D2D1_EXTEND_MODE m_extendMode;  
```  
  
##  <a name="a-namempgradientstopsa--cd2dgradientbrushmpgradientstops"></a><a name="m_pgradientstops"></a>CD2DGradientBrush::m_pGradientStops  
 Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.  
  
```  
ID2D1GradientStopCollection* m_pGradientStops;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

