---
title: CD2DLinearGradientBrush-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DLinearGradientBrush
- CD2DLinearGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DLinearGradientBrush class
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dd288478a751d921cc4d9fcd9433e391275cee66
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush-Klasse
Ein Wrapper für ID2D1LinearGradientBrush.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Erstellt ein CD2DLinearGradientBrush-Objekt.|  
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D linearer Farbverlaufspinselobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|  
|[CD2DLinearGradientBrush::Create](#create)|Erstellt einen CD2DLinearGradientBrush. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLinearGradientBrush::Destroy](#destroy)|Zerstört ein CD2DLinearGradientBrush-Objekt. (Überschreibt [CD2DGradientBrush:: Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DLinearGradientBrush::Detach](#detach)|Ressourcenschnittstelle aus dem Objekt getrennt|  
|[CD2DLinearGradientBrush::Get](#get)|Gibt die ID2D1LinearGradientBrush-Schnittstelle|  
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Ruft die Endkoordinaten des linearen Farbverlaufs|  
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Ruft die Anfangskoordinaten des linearen Farbverlaufs|  
|[CD2DLinearGradientBrush::setEndPoint](#setendpoint)|Legt die Endkoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels|  
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Legt die Anfangskoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Gibt die ID2D1LinearGradientBrush-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Die Start- und Endpunkte des Farbverlaufs.|  
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Ein Zeiger auf einen ID2D1LinearGradientBrush.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DLinearGradientBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dlineargradientbrusha--cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a>CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D linearer Farbverlaufspinselobjekt zerstört wird.  
  
```  
virtual ~CD2DLinearGradientBrush();
```  
  
##  <a name="a-nameattacha--cd2dlineargradientbrushattach"></a><a name="attach"></a>CD2DLinearGradientBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle für das Objekt  
  
```  
void Attach(ID2D1LinearGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="a-namecd2dlineargradientbrusha--cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a>CD2DLinearGradientBrush::CD2DLinearGradientBrush  
 Erstellt ein CD2DLinearGradientBrush-Objekt.  
  
```  
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,  
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
  
 `LinearGradientBrushProperties`  
 Die Start- und Endpunkte des Farbverlaufs.  
  
 `colorInterpolationGamma`  
 Der Speicherplatz in der die Interpolation zwischen den Farbverlaufsunterbrechungspunkten ausgeführt wird.  
  
 `extendMode`  
 Das Verhalten des Farbverlaufs außerhalb der normalisierten Bereich [0,1].  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="a-namecreatea--cd2dlineargradientbrushcreate"></a><a name="create"></a>CD2DLinearGradientBrush::Create  
 Erstellt einen CD2DLinearGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderingziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="a-namedestroya--cd2dlineargradientbrushdestroy"></a><a name="destroy"></a>CD2DLinearGradientBrush::Destroy  
 Zerstört ein CD2DLinearGradientBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dlineargradientbrushdetach"></a><a name="detach"></a>CD2DLinearGradientBrush::Detach  
 Ressourcenschnittstelle aus dem Objekt getrennt  
  
```  
ID2D1LinearGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Ressourcenschnittstelle.  
  
##  <a name="a-namegeta--cd2dlineargradientbrushget"></a><a name="get"></a>CD2DLinearGradientBrush::Get  
 Gibt die ID2D1LinearGradientBrush-Schnittstelle  
  
```  
ID2D1LinearGradientBrush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen ID2D1LinearGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namegetendpointa--cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a>CD2DLinearGradientBrush::GetEndPoint  
 Ruft die Endkoordinaten des linearen Farbverlaufs  
  
```  
CD2DPointF GetEndPoint() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweidimensionalen Endkoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels  
  
##  <a name="a-namegetstartpointa--cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a>CD2DLinearGradientBrush::GetStartPoint  
 Ruft die Anfangskoordinaten des linearen Farbverlaufs  
  
```  
CD2DPointF GetStartPoint() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweidimensionalen Anfangskoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels  
  
##  <a name="a-namemlineargradientbrushpropertiesa--cd2dlineargradientbrushmlineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a>CD2DLinearGradientBrush::m_LinearGradientBrushProperties  
 Die Start- und Endpunkte des Farbverlaufs.  
  
```  
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;  
```  
  
##  <a name="a-namemplineargradientbrusha--cd2dlineargradientbrushmplineargradientbrush"></a><a name="m_plineargradientbrush"></a>CD2DLinearGradientBrush::m_pLinearGradientBrush  
 Ein Zeiger auf einen ID2D1LinearGradientBrush.  
  
```  
ID2D1LinearGradientBrush* m_pLinearGradientBrush;  
```  
  
##  <a name="a-nameoperatorid2d1lineargradientbrushstara--cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a>CD2DLinearGradientBrush::Operator ID2D1LinearGradientBrush *  
 Gibt die ID2D1LinearGradientBrush-Schnittstelle  
  
```  
operator ID2D1LinearGradientBrush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen ID2D1LinearGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namesetendpointa--cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a>CD2DLinearGradientBrush::setEndPoint  
 Legt die Endkoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels  
  
```  
void SetEndPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Die zweidimensionalen Endkoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels  
  
##  <a name="a-namesetstartpointa--cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a>CD2DLinearGradientBrush::SetStartPoint  
 Legt die Anfangskoordinaten des linearen Farbverlaufs im Koordinatenraum des Pinsels  
  
```  
void SetStartPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Die zweidimensionalen Anfangskoordinaten des linearen Farbverlaufs, im Koordinatenraum des Pinsels  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

