---
title: CD2DBrush-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324e6411673a509bdf75954634ff9c6dffc5ce1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dbrush-class"></a>CD2DBrush-Klasse
Ein Wrapper für ID2D1Brush.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Erstellt ein CD2DBrush-Objekt.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsel-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle, um das Objekt|  
|[CD2DBrush:: Destroy](#destroy)|Zerstört ein CD2DBrush-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|Trennt Ressourcenschnittstelle aus dem Objekt|  
|[CD2DBrush::Get](#get)|Gibt die ID2D1Brush-Schnittstelle|  
|[CD2DBrush::GetOpacity](#getopacity)|Ruft den Grad der Deckkraft, der diese Pinsel|  
|[CD2DBrush::GetTransform](#gettransform)|Ruft die aktuelle Transformation des Renderziels|  
|[CD2DBrush::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (Außerkraftsetzungen [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Legt den Grad der Deckkraft, der diese Pinsel|  
|[CD2DBrush::setTransform](#settransform)|Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation an. Alle nachfolgenden Zeichenvorgänge treten in den transformierten Speicherplatz|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::Operator ID2D1Brush *](#operator_id2d1brush_star)|Gibt die ID2D1Brush-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|Ein Zeiger auf ein Objekt ID2D1Brush gespeichert.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Pinseleigenschaften.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Pinsel-Objekt zerstört wird.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>  CD2DBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle, um das Objekt  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush  
 Erstellt ein CD2DBrush-Objekt.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderziel.  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft- und Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="destroy"></a>  CD2DBrush:: Destroy  
 Zerstört ein CD2DBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DBrush::Detach  
 Trennt Ressourcenschnittstelle aus dem Objekt  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Ressourcenschnittstelle.  
  
##  <a name="get"></a>  CD2DBrush::Get  
 Gibt die ID2D1Brush-Schnittstelle  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1Brush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getopacity"></a>  CD2DBrush::GetOpacity  
 Ruft den Grad der Deckkraft, der diese Pinsel  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert zwischen 0 und 1, der die Deckkraft des Pinsels angibt. Dieser Wert ist ein konstanter Multiplikator, der den Alphawert alle Pixel, die durch den Pinsel gefüllt linear skaliert. Die Deckkraftwerte werden im Bereich von 0 bis 1 gebunden ist, bevor sie zusammen multipliziert werden  
  
##  <a name="gettransform"></a>  CD2DBrush::GetTransform  
 Ruft die aktuelle Transformation des Renderziels  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Wenn dieser Wert zurückgibt, enthält die aktuelle Transformation des Renderziels. Dieser Parameter wird nicht initialisiert übergeben.  
  
##  <a name="isvalid"></a>  CD2DBrush::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls "false".  
  
##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush  
 Ein Zeiger auf ein Objekt ID2D1Brush gespeichert.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties  
 Pinseleigenschaften.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::Operator ID2D1Brush *  
 Gibt die ID2D1Brush-Schnittstelle  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1Brush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setopacity"></a>  CD2DBrush::SetOpacity  
 Legt den Grad der Deckkraft, der diese Pinsel  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Parameter  
 `opacity`  
 Ein Wert zwischen 0 und 1, der die Deckkraft des Pinsels angibt. Dieser Wert ist ein konstanter Multiplikator, der den Alphawert alle Pixel, die durch den Pinsel gefüllt linear skaliert. Die Deckkraftwerte werden im Bereich von 0 bis 1 gebunden ist, bevor sie zusammen multipliziert werden  
  
##  <a name="settransform"></a>  CD2DBrush::setTransform  
 Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation an. Alle nachfolgenden Zeichenvorgänge treten in den transformierten Speicherplatz  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Die Transformation, die auf das Renderziel anwenden  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
