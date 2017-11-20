---
title: CD2DBitmapBrush-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 678ab34828e1b650dc94d773c5a79cb608a41b9e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[CD2DBitmapBrush:: ~ CD2DBitmapBrush](#dtor)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Bitmap-Pinsel-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBitmapBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle, um das Objekt|  
|[CD2DBitmapBrush::Create](#create)|Erstellt einen CD2DBitmapBrush. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DBitmapBrush::Destroy](#destroy)|Zerstört ein CD2DBitmapBrush-Objekt. (Überschreibt [CD2DBrush:: Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
|[CD2DBitmapBrush::Detach](#detach)|Trennt Ressourcenschnittstelle aus dem Objekt|  
|[CD2DBitmapBrush::Get](#get)|Gibt die ID2D1BitmapBrush-Schnittstelle|  
|[CD2DBitmapBrush::getBitmap](#getbitmap)|Ruft die Bitmapquelle, die zum Zeichnen dieser Pinsel verwendet werden|  
|[CD2DBitmapBrush::GetExtendModeX](#getextendmodex)|Ruft die Methode, mit der die Pinsel jene Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen, ab|  
|[CD2DBitmapBrush::GetExtendModeY](#getextendmodey)|Ruft die Methode mit der der Pinsel, der vertikal jene Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen ab|  
|[CD2DBitmapBrush::GetInterpolationMode](#getinterpolationmode)|Ruft die Interpolationsmethode verwendet, wenn die Pinselbitmap skaliert wird oder gedreht wird|  
|[CD2DBitmapBrush::SetBitmap](#setbitmap)|Gibt die Bitmapquelle, die zum Zeichnen dieser Pinsel verwendet werden|  
|[CD2DBitmapBrush::SetExtendModeX](#setextendmodex)|Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet|  
|[CD2DBitmapBrush::SetExtendModeY](#setextendmodey)|Gibt an, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet|  
|[CD2DBitmapBrush::SetInterpolationMode](#setinterpolationmode)|Gibt den Interpolationsmodus verwendet, wenn die Pinselbitmap skaliert wird oder gedreht wird|  
  
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
|[CD2DBitmapBrush::m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|Bitmap Pinseleigenschaften.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DBitmapBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="dtor"></a>CD2DBitmapBrush:: ~ CD2DBitmapBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Bitmap-Pinsel-Objekt zerstört wird.  
  
```  
virtual ~CD2DBitmapBrush();
```  
  
##  <a name="attach"></a>CD2DBitmapBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle, um das Objekt  
  
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
 Ein Zeiger auf das Renderziel.  
  
 `pBitmapBrushProperties`  
 Ein Zeiger auf die Erweiterungsmodi und den Interpolationsmodus eines Bitmappinsels mithilfe einer.  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft- und Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
 `uiResID`  
 Die Ressourcen-ID-Nummer der Ressource.  
  
 `lpszType`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Ressourcentyp enthält.  
  
 `sizeDest`  
 Die Zielgröße der Bitmap.  
  
 `lpszImagePath`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen der Datei enthält.  
  
##  <a name="commoninit"></a>CD2DBitmapBrush::CommonInit  
 Initialisiert das Objekt  
  
```  
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmapBrushProperties`  
 Ein Zeiger auf die Bitmap Pinsel-Eigenschaften.  
  
##  <a name="create"></a>CD2DBitmapBrush::Create  
 Erstellt einen CD2DBitmapBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="destroy"></a>CD2DBitmapBrush::Destroy  
 Zerstört ein CD2DBitmapBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBitmapBrush::Detach  
 Trennt Ressourcenschnittstelle aus dem Objekt  
  
```  
ID2D1BitmapBrush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Ressourcenschnittstelle.  
  
##  <a name="get"></a>CD2DBitmapBrush::Get  
 Gibt die ID2D1BitmapBrush-Schnittstelle  
  
```  
ID2D1BitmapBrush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1BitmapBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getbitmap"></a>CD2DBitmapBrush::getBitmap  
 Ruft die Bitmapquelle, die zum Zeichnen dieser Pinsel verwendet werden  
  
```  
CD2DBitmap* GetBitmap();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf ein CD2DBitmap-Objekt oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getextendmodex"></a>CD2DBitmapBrush::GetExtendModeX  
 Ruft die Methode, mit der die Pinsel jene Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen, ab  
  
```  
D2D1_EXTEND_MODE GetExtendModeX() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
##  <a name="getextendmodey"></a>CD2DBitmapBrush::GetExtendModeY  
 Ruft die Methode mit der der Pinsel, der vertikal jene Bereiche nebeneinander anordnet, die über seine Bitmap hinausreichen ab  
  
```  
D2D1_EXTEND_MODE GetExtendModeY() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, wie der Pinsel jene Bereiche, die über seine Bitmap hinausreichen nebeneinander anordnet  
  
##  <a name="getinterpolationmode"></a>CD2DBitmapBrush::GetInterpolationMode  
 Ruft die Interpolationsmethode verwendet, wenn die Pinselbitmap skaliert wird oder gedreht wird  
  
```  
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Interpolationsmethode verwendet, wenn die Pinselbitmap skaliert wird oder gedreht wird  
  
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
 Bitmap Pinseleigenschaften.  
  
```  
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;  
```  
  
##  <a name="operator_id2d1bitmapbrush_star"></a>CD2DBitmapBrush::Operator ID2D1BitmapBrush *  
 Gibt die ID2D1BitmapBrush-Schnittstelle  
  
```  
operator ID2D1BitmapBrush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1BitmapBrush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setbitmap"></a>CD2DBitmapBrush::SetBitmap  
 Gibt die Bitmapquelle, die zum Zeichnen dieser Pinsel verwendet werden  
  
```  
void SetBitmap(CD2DBitmap* pBitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Die Bitmapquelle, die durch den Pinsel verwendet  
  
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
 Gibt den Interpolationsmodus verwendet, wenn die Pinselbitmap skaliert wird oder gedreht wird  
  
```  
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```  
  
### <a name="parameters"></a>Parameter  
 `interpolationMode`  
 Der Interpolationsmodus verwendet, wenn die Pinselbitmap skaliert wird oder gedreht wird  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
