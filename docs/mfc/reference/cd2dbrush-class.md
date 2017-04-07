---
title: CD2DBrush-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CD2DBrush class
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
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
ms.openlocfilehash: b9902445fb6e18df20073d132a2117c67e695b25
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbrush-class"></a>CD2DBrush-Klasse
Ein Wrapper für ID2D1Brush.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|Erstellt ein CD2DBrush-Objekt.|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Brush-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|  
|[CD2DBrush:: Destroy](#destroy)|Zerstört ein CD2DBrush-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DBrush::Detach](#detach)|Ressourcenschnittstelle aus dem Objekt getrennt|  
|[CD2DBrush::Get](#get)|Gibt die ID2D1Brush-Schnittstelle|  
|[CD2DBrush::GetOpacity](#getopacity)|Ruft den Grad von Deckkraft dieses Pinsels ab|  
|[CD2DBrush::GetTransform](#gettransform)|Ruft die aktuelle Transformation des Renderingziels ab|  
|[CD2DBrush::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DBrush::SetOpacity](#setopacity)|Legt den Grad von Deckkraft dieses Pinsels fest|  
|[CD2DBrush::setTransform](#settransform)|Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::Operator ID2D1Brush *](#operator_id2d1brush_star)|Gibt die ID2D1Brush-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|Speichert einen Zeiger auf eine ID2D1Brush-Objekt.|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|Pinseleigenschaften.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>CD2DBrush:: ~ CD2DBrush  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Brush-Objekt zerstört wird.  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>CD2DBrush::Attach  
 Hängt die vorhandene Ressourcenschnittstelle für das Objekt  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dbrush"></a>CD2DBrush::CD2DBrush  
 Erstellt ein CD2DBrush-Objekt.  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `pBrushProperties`  
 Ein Zeiger auf die Deckkraft und die Transformation eines Pinsels.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="destroy"></a>CD2DBrush:: Destroy  
 Zerstört ein CD2DBrush-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBrush::Detach  
 Ressourcenschnittstelle aus dem Objekt getrennt  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Ressourcenschnittstelle.  
  
##  <a name="get"></a>CD2DBrush::Get  
 Gibt die ID2D1Brush-Schnittstelle  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1Brush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getopacity"></a>CD2DBrush::GetOpacity  
 Ruft den Grad von Deckkraft dieses Pinsels ab  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert zwischen 0 und 1, der die Durchlässigkeit des Pinsels angibt. Dieser Wert ist ein konstanter Multiplikator, der den Alphawert aller vom Pinsel ausgefüllten Pixel linear skaliert. Die Deckkraftwerte werden im Bereich von 0 bis 1 festgelegt, bevor sie zusammen multipliziert werden  
  
##  <a name="gettransform"></a>CD2DBrush::GetTransform  
 Ruft die aktuelle Transformation des Renderingziels ab  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Wenn diese zurückgegeben wird, enthält die aktuelle Transformation des Renderingziels. Dieser Parameter wird nicht initialisiert übergeben.  
  
##  <a name="isvalid"></a>CD2DBrush::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls FALSE.  
  
##  <a name="m_pbrush"></a>CD2DBrush::m_pBrush  
 Speichert einen Zeiger auf eine ID2D1Brush-Objekt.  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties  
 Pinseleigenschaften.  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>CD2DBrush::Operator ID2D1Brush *  
 Gibt die ID2D1Brush-Schnittstelle  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1Brush-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="setopacity"></a>CD2DBrush::SetOpacity  
 Legt den Grad von Deckkraft dieses Pinsels fest  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>Parameter  
 `opacity`  
 Ein Wert zwischen 0 und 1, der die Durchlässigkeit des Pinsels angibt. Dieser Wert ist ein konstanter Multiplikator, der den Alphawert aller vom Pinsel ausgefüllten Pixel linear skaliert. Die Deckkraftwerte werden im Bereich von 0 bis 1 festgelegt, bevor sie zusammen multipliziert werden  
  
##  <a name="settransform"></a>CD2DBrush::setTransform  
 Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Die Transformation auf das Renderingziel angewendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

