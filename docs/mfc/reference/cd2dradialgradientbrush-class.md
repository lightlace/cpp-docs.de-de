---
title: CD2DRadialGradientBrush-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRadialGradientBrush
- afxrendertarget/CD2DRadialGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DRadialGradientBrush class
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
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
ms.openlocfilehash: 8b3fd7f468745567969ba1f7e9d6871a9060582b
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush-Klasse
Ein Wrapper für ID2D1RadialGradientBrush.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Erstellt ein CD2DLinearGradientBrush-Objekt.|  
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Radialer Farbverlauf-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|  
|[CD2DRadialGradientBrush::Create](#create)|Erstellt einen CD2DRadialGradientBrush. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DRadialGradientBrush::Destroy](#destroy)|Zerstört ein CD2DRadialGradientBrush-Objekt. (Überschreibt [CD2DGradientBrush:: Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DRadialGradientBrush::Detach](#detach)|Ressourcenschnittstelle aus dem Objekt getrennt|  
|[CD2DRadialGradientBrush::Get](#get)|Gibt die ID2D1RadialGradientBrush-Schnittstelle|  
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Ruft den Mittelpunkt der Ellipse Farbverlauf|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Ruft den Offset des Farbverlaufs Ursprungs relativ zur Mitte der Farbverlauf ellipse|  
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Ruft den X-Radius der Ellipse Farbverlauf|  
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Ruft den y-Radius der Ellipse Farbverlauf|  
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Gibt den Mittelpunkt der Farbverlaufsellipse im Koordinatenraum des Pinsels|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Gibt den Offset des Farbverlaufs Ursprungs relativ zur Mitte der Farbverlauf ellipse|  
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Gibt den X-Radius der Farbverlaufsellipse im Koordinatenraum des Pinsels|  
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Gibt den y-Radius der Farbverlaufsellipse im Koordinatenraum des Pinsels|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::Operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|Gibt die ID2D1RadialGradientBrush-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|Ein Zeiger auf eine ID2D1RadialGradientBrush.|  
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Das Center, Farbverlaufsursprungsoffset und X-Radius und y-Radius des Pinsels Farbverlauf des.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DRadialGradientBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dradialgradientbrusha--cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Radialer Farbverlauf-Objekt zerstört wird.  
  
```  
virtual ~CD2DRadialGradientBrush();
```  
  
##  <a name="a-nameattacha--cd2dradialgradientbrushattach"></a><a name="attach"></a>CD2DRadialGradientBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle für das Objekt  
  
```  
void Attach(ID2D1RadialGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="a-namecd2dradialgradientbrusha--cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush  
 Erstellt ein CD2DLinearGradientBrush-Objekt.  
  
```  
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,  
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
  
 `RadialGradientBrushProperties`  
 Das Center, Farbverlaufsursprungsoffset und X-Radius und y-Radius des Pinsels Farbverlauf des.  
  
 `colorInterpolationGamma`  
 Der Speicherplatz in der die Interpolation zwischen den Farbverlaufsunterbrechungspunkten ausgeführt wird.  
  
 `extendMode`  
 Das Verhalten des Farbverlaufs außerhalb der normalisierten Bereich [0,1].  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="a-namecreatea--cd2dradialgradientbrushcreate"></a><a name="create"></a>CD2DRadialGradientBrush::Create  
 Erstellt einen CD2DRadialGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderingziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="a-namedestroya--cd2dradialgradientbrushdestroy"></a><a name="destroy"></a>CD2DRadialGradientBrush::Destroy  
 Zerstört ein CD2DRadialGradientBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dradialgradientbrushdetach"></a><a name="detach"></a>CD2DRadialGradientBrush::Detach  
 Ressourcenschnittstelle aus dem Objekt getrennt  
  
```  
ID2D1RadialGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Ressourcenschnittstelle.  
  
##  <a name="a-namegeta--cd2dradialgradientbrushget"></a><a name="get"></a>CD2DRadialGradientBrush::Get  
 Gibt die ID2D1RadialGradientBrush-Schnittstelle  
  
```  
ID2D1RadialGradientBrush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1RadialGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namegetcentera--cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter  
 Ruft den Mittelpunkt der Ellipse Farbverlauf  
  
```  
CD2DPointF GetCenter() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Mitte des Farbverlaufs Ellipse. Dieser Wert wird im Koordinatenraum des Pinsels ausgedrückt.  
  
##  <a name="a-namegetgradientoriginoffseta--cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset  
 Ruft den Offset des Farbverlaufs Ursprungs relativ zur Mitte der Farbverlauf ellipse  
  
```  
CD2DPointF GetGradientOriginOffset() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Offset vom Ursprung Farbverlauf vom Mittelpunkt der Farbverlauf Ellipse. Dieser Wert wird im Koordinatenraum des Pinsels ausgedrückt.  
  
##  <a name="a-namegetradiusxa--cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX  
 Ruft den X-Radius der Ellipse Farbverlauf  
  
```  
FLOAT GetRadiusX() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der X-Radius der Ellipse Farbverlauf. Dieser Wert wird im Koordinatenraum des Pinsels ausgedrückt.  
  
##  <a name="a-namegetradiusya--cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY  
 Ruft den y-Radius der Ellipse Farbverlauf  
  
```  
FLOAT GetRadiusY() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der y-Radius der Ellipse Farbverlauf. Dieser Wert wird im Koordinatenraum des Pinsels ausgedrückt.  
  
##  <a name="a-namempradialgradientbrusha--cd2dradialgradientbrushmpradialgradientbrush"></a><a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush  
 Ein Zeiger auf eine ID2D1RadialGradientBrush.  
  
```  
ID2D1RadialGradientBrush* m_pRadialGradientBrush;  
```  
  
##  <a name="a-namemradialgradientbrushpropertiesa--cd2dradialgradientbrushmradialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties  
 Das Center, Farbverlaufsursprungsoffset und X-Radius und y-Radius des Pinsels Farbverlauf des.  
  
```  
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;  
```  
  
##  <a name="a-nameoperatorid2d1radialgradientbrushstara--cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::Operator ID2D1RadialGradientBrush *  
 Gibt die ID2D1RadialGradientBrush-Schnittstelle  
  
```  
operator ID2D1RadialGradientBrush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1RadialGradientBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namesetcentera--cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter  
 Gibt den Mittelpunkt der Farbverlaufsellipse im Koordinatenraum des Pinsels  
  
```  
void SetCenter(CD2DPointF point);
```  
  
### <a name="parameters"></a>Parameter  
 `point`  
 Die Mitte der Farbverlaufsellipse im Koordinatenraum des Pinsels  
  
##  <a name="a-namesetgradientoriginoffseta--cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset  
 Gibt den Offset des Farbverlaufs Ursprungs relativ zur Mitte der Farbverlauf ellipse  
  
```  
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```  
  
### <a name="parameters"></a>Parameter  
 `gradientOriginOffset`  
 Der Offset vom Ursprung Farbverlauf vom Mittelpunkt der Ellipse Farbverlauf  
  
##  <a name="a-namesetradiusxa--cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX  
 Gibt den X-Radius der Farbverlaufsellipse im Koordinatenraum des Pinsels  
  
```  
void SetRadiusX(FLOAT radiusX);
```  
  
### <a name="parameters"></a>Parameter  
 `radiusX`  
 Der X-Radius der Ellipse Farbverlauf. Dieser Wert liegt im Koordinatenraum des Pinsels  
  
##  <a name="a-namesetradiusya--cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY  
 Gibt den y-Radius der Farbverlaufsellipse im Koordinatenraum des Pinsels  
  
```  
void SetRadiusY(FLOAT radiusY);
```  
  
### <a name="parameters"></a>Parameter  
 `radiusY`  
 Der y-Radius der Ellipse Farbverlauf. Dieser Wert liegt im Koordinatenraum des Pinsels  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

