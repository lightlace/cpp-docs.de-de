---
title: CD2DBitmapBrush-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBitmapBrush class
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
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
ms.openlocfilehash: a9ab15dcae8715b98cc9f723a710b64e83649bf9
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush-Klasse
Ein Wrapper für ID2D1BitmapBrush.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](#cd2dbitmapbrush)|Überladen. Erstellt ein CD2DBitmapBrush-Objekt aus der Datei.|  
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Bitmap Brush-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|  
|[CD2DBitmapBrush::Create](#create)|Erstellt einen CD2DBitmapBrush. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmapBrush::Destroy](#destroy)|Zerstört ein CD2DBitmapBrush-Objekt. (Überschreibt [CD2DBrush:: Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DBitmapBrush::Detach](#detach)|Ressourcenschnittstelle aus dem Objekt getrennt|  
|[CD2DBitmapBrush::Get](#get)|Gibt die ID2D1BitmapBrush-Schnittstelle|  
|[CD2DBitmapBrush::getBitmap](#getbitmap)|Ruft die Bitmapquelle, die mit dieser Pinsel zeichnet|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Ruft die Methode ab, der Pinsel jene Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Ruft die Methode ab, der Pinsel vertikal Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Ruft die Interpolationsmethode verwendet, wenn die Pinselbitmap skaliert oder rotiert wird|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Gibt die Bitmapquelle, die mit dieser Pinsel zeichnet|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Gibt den Interpolationsmodus verwendet, wenn die Pinselbitmap skaliert oder rotiert wird|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBitmapBrush::CommonInit](#commoninit)|Initialisiert das Objekt|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBitmapBrush::Operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|Gibt die ID2D1BitmapBrush-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBitmapBrush::m_pBitmap](#m_pbitmap)|Speichert einen Zeiger auf ein CD2DBitmap-Objekt.|  
|[CD2DBitmapBrush::m_pBitmapBrush](#m_pbitmapbrush)|Speichert einen Zeiger auf ein ID2D1BitmapBrush-Objekt.|  
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Bitmap-Pinseleigenschaften.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Bitmap Brush-Objekt zerstört wird.  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="attach"></a>CD2DBitmapBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle für das Objekt  
  
```  
void Attach(ID2D1BitmapBrush* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dbitmapbrush"></a>CD2DBitmapBrush::CD2DBitmapBrush  
 Erstellt ein CD2DBitmapBrush-Objekt.  
  
```  
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    UINT uiResID,  
    LPCTSTR lpszType = NULL,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);

 
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,  
    LPCTSTR lpszImagePath,  
    CD2DSizeU sizeDest = CD2DSizeU(0, 0), 
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `pBitmapBrushProperties`  
 Ein Zeiger auf die Erweiterungsmodi und den Interpolationsmodus eines Pinsels Bitmap.  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
 `uiResID`  
 Die Ressourcen-ID der Ressource.  
  
 `lpszType`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Ressourcentyp enthält.  
  
 `sizeDest`  
 Zielgröße der Bitmap.  
  
 `lpszImagePath`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Datei enthält.  
  
##  <a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 Initialisiert das Objekt  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmapBrushProperties`  
 Ein Zeiger auf die Pinseleigenschaften Bitmap.  
  
##  <a name="create"></a>CD2DBitmapBrush::Create  
 Erstellt einen CD2DBitmapBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderingziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="destroy"></a>CD2DBitmapBrush::Destroy  
 Zerstört ein CD2DBitmapBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBitmapBrush::Detach  
 Ressourcenschnittstelle aus dem Objekt getrennt  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Ressourcenschnittstelle.  
  
##  <a name="get"></a>CD2DBitmapBrush::Get  
 Gibt die ID2D1BitmapBrush-Schnittstelle  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1BitmapBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getbitmap"></a>CD2DBitmapBrush::getBitmap  
 Ruft die Bitmapquelle, die mit dieser Pinsel zeichnet  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein CD2DBitmap-Objekt oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 Ruft die Methode ab, der Pinsel jene Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
##  <a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 Ruft die Methode ab, der Pinsel vertikal Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
##  <a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 Ruft die Interpolationsmethode verwendet, wenn die Pinselbitmap skaliert oder rotiert wird  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Interpolationsmethode verwendet, wenn die Pinselbitmap skaliert oder rotiert wird  
  
##  <a name="m_pbitmap"></a>CD2DBitmapBrush::m_pBitmap  
 Speichert einen Zeiger auf ein CD2DBitmap-Objekt.  
  
```  
CD2DBitmap* m_pBitmap;  
```  
  
##  <a name="m_pbitmapbrush"></a>CD2DBitmapBrush::m_pBitmapBrush  
 Speichert einen Zeiger auf ein ID2D1BitmapBrush-Objekt.  
  
```  
ID2D1BitmapBrush* m_pBitmapBrush;  
```  
  
##  <a name="m_pbitmapbrushproperties"></a>CD2DBitmapBrush::m_pBitmapBrushProperties  
 Bitmap-Pinseleigenschaften.  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::Operator ID2D1BitmapBrush *  
 Gibt die ID2D1BitmapBrush-Schnittstelle  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1BitmapBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 Gibt die Bitmapquelle, die mit dieser Pinsel zeichnet  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Die vom Pinsel verwendete Bitmapquelle  
  
##  <a name="setextendmodex"></a>CD2DBitmapBrush::SetExtendModeX  
 Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
```  
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```  
  
### <a name="parameters"></a>Parameter  
 `extendModeX`  
 Ein Wert, der angibt, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
##  <a name="setextendmodey"></a>CD2DBitmapBrush::SetExtendModeY  
 Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
```  
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```  
  
### <a name="parameters"></a>Parameter  
 `extendModeY`  
 Ein Wert, der angibt, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
##  <a name="setinterpolationmode"></a>CD2DBitmapBrush::SetInterpolationMode  
 Gibt den Interpolationsmodus verwendet, wenn die Pinselbitmap skaliert oder rotiert wird  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>Parameter  
 `interpolationMode`  
 Der Interpolationsmodus verwendet, wenn die Pinselbitmap skaliert oder rotiert wird  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

