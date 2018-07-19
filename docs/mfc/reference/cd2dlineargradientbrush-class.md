---
title: CD2DLinearGradientBrush-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61dc2134a2da6570c748cebbfc770b213863de04
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957246"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush-Klasse
Ein Wrapper für ID2D1LinearGradientBrush.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Erstellt ein CD2DLinearGradientBrush-Objekt.|  
|[CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D linearen Farbverlaufspinsel-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle, um das Objekt|  
|[CD2DLinearGradientBrush::Create](#create)|Erstellt einen CD2DLinearGradientBrush. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLinearGradientBrush::Destroy](#destroy)|Zerstört ein CD2DLinearGradientBrush-Objekt. (Überschreibt [CD2DGradientBrush:: Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DLinearGradientBrush::Detach](#detach)|Trennt Ressourcenschnittstelle aus dem Objekt|  
|[CD2DLinearGradientBrush::Get](#get)|Gibt die ID2D1LinearGradientBrush-Schnittstelle|  
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Ruft die Endkoordinaten des linearen Farbverlaufs ab|  
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Ruft die Anfangskoordinaten des linearen Farbverlaufs ab|  
|[CD2DLinearGradientBrush::setEndPoint](#setendpoint)|Legt die Endkoordinaten des linearen Farbverlaufs im Koordinatenbereich des Pinsels.|  
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Legt die Anfangskoordinaten des linearen Farbverlaufs in Koordinatenbereich des Pinsels.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Gibt die ID2D1LinearGradientBrush-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Die Start- und die Endpunkte des Farbverlaufs.|  
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Ein Zeiger auf einen ID2D1LinearGradientBrush.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DLinearGradientBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlineargradientbrush"></a>  CD2DLinearGradientBrush:: ~ CD2DLinearGradientBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D linearen Farbverlaufspinsel-Objekt zerstört wird.  
  
```  
virtual ~CD2DLinearGradientBrush();
```  
  
##  <a name="attach"></a>  CD2DLinearGradientBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle, um das Objekt  
  
```  
void Attach(ID2D1LinearGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 *pResource*  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dlineargradientbrush"></a>  CD2DLinearGradientBrush::CD2DLinearGradientBrush  
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
 *pParentTarget*  
 Ein Zeiger auf das Renderziel.  
  
 *gradientStops*  
 Ein Zeiger auf ein Array von D2D1_GRADIENT_STOP-Strukturen.  
  
 *gradientStopsCount*  
 Ein Wert größer als oder gleich 1, der die Anzahl der Farbverlaufsstopps im Array GradientStops angibt.  
  
 *LinearGradientBrushProperties*  
 Die Start- und die Endpunkte des Farbverlaufs.  
  
 *colorInterpolationGamma*  
 Der Speicherplatz in der die, den Farbe Interpolation zwischen dem Farbverlaufsstopps ausgeführt wird.  
  
 *extendMode*  
 Das Verhalten des Farbverlaufs außerhalb des Bereichs, [0,1] normalisierte.  
  
 *pBrushProperties*  
 Ein Zeiger auf die Deckkraft- und Transformation eines Pinsels.  
  
 *bAutoDestroy*  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="create"></a>  CD2DLinearGradientBrush::Create  
 Erstellt einen CD2DLinearGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 *pRenderTarget*  
 Ein Zeiger auf das Renderziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="destroy"></a>  CD2DLinearGradientBrush::Destroy  
 Zerstört ein CD2DLinearGradientBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DLinearGradientBrush::Detach  
 Trennt Ressourcenschnittstelle aus dem Objekt  
  
```  
ID2D1LinearGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Ressourcenschnittstelle.  
  
##  <a name="get"></a>  CD2DLinearGradientBrush::Get  
 Gibt die ID2D1LinearGradientBrush-Schnittstelle  
  
```  
ID2D1LinearGradientBrush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1LinearGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getendpoint"></a>  CD2DLinearGradientBrush::GetEndPoint  
 Ruft die Endkoordinaten des linearen Farbverlaufs ab  
  
```  
CD2DPointF GetEndPoint() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweidimensionalen Endkoordinaten des linearen Farbverlaufs, im Koordinatenbereich des Pinsels.  
  
##  <a name="getstartpoint"></a>  CD2DLinearGradientBrush::GetStartPoint  
 Ruft die Anfangskoordinaten des linearen Farbverlaufs ab  
  
```  
CD2DPointF GetStartPoint() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweidimensionalen Anfangskoordinaten des linearen Farbverlaufs, im Koordinatenbereich des Pinsels.  
  
##  <a name="m_lineargradientbrushproperties"></a>  CD2DLinearGradientBrush::m_LinearGradientBrushProperties  
 Die Start- und die Endpunkte des Farbverlaufs.  
  
```  
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;  
```  
  
##  <a name="m_plineargradientbrush"></a>  CD2DLinearGradientBrush::m_pLinearGradientBrush  
 Ein Zeiger auf einen ID2D1LinearGradientBrush.  
  
```  
ID2D1LinearGradientBrush* m_pLinearGradientBrush;  
```  
  
##  <a name="operator_id2d1lineargradientbrush_star"></a>  CD2DLinearGradientBrush::Operator ID2D1LinearGradientBrush *  
 Gibt die ID2D1LinearGradientBrush-Schnittstelle  
  
```  
operator ID2D1LinearGradientBrush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1LinearGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setendpoint"></a>  CD2DLinearGradientBrush::setEndPoint  
 Legt die Endkoordinaten des linearen Farbverlaufs im Koordinatenbereich des Pinsels.  
  
```  
void SetEndPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 *Punkt*  
 Die zweidimensionalen Endkoordinaten des linearen Farbverlaufs, im Koordinatenbereich des Pinsels.  
  
##  <a name="setstartpoint"></a>  CD2DLinearGradientBrush::SetStartPoint  
 Legt die Anfangskoordinaten des linearen Farbverlaufs in Koordinatenbereich des Pinsels.  
  
```  
void SetStartPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 *Punkt*  
 Die zweidimensionalen Anfangskoordinaten des linearen Farbverlaufs, im Koordinatenbereich des Pinsels.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
