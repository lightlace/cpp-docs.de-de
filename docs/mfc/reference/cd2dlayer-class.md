---
title: CD2DLayer-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DLayer
- AFXRENDERTARGET/CD2DLayer
- AFXRENDERTARGET/CD2DLayer::CD2DLayer
- AFXRENDERTARGET/CD2DLayer::Attach
- AFXRENDERTARGET/CD2DLayer::Create
- AFXRENDERTARGET/CD2DLayer::Destroy
- AFXRENDERTARGET/CD2DLayer::Detach
- AFXRENDERTARGET/CD2DLayer::Get
- AFXRENDERTARGET/CD2DLayer::GetSize
- AFXRENDERTARGET/CD2DLayer::IsValid
- AFXRENDERTARGET/CD2DLayer::m_pLayer
dev_langs:
- C++
helpviewer_keywords:
- CD2DLayer [MFC], CD2DLayer
- CD2DLayer [MFC], Attach
- CD2DLayer [MFC], Create
- CD2DLayer [MFC], Destroy
- CD2DLayer [MFC], Detach
- CD2DLayer [MFC], Get
- CD2DLayer [MFC], GetSize
- CD2DLayer [MFC], IsValid
- CD2DLayer [MFC], m_pLayer
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: cdb6cfe624b0b3ba22d91ab30998aebf5bc96820
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dlayer-class"></a>CD2DLayer-Klasse
Ein Wrapper für ID2D1Layer.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLayer::CD2DLayer](#cd2dlayer)|Erstellt ein CD2DLayer-Objekt.|  
|[CD2DLayer:: ~ CD2DLayer](#_dtorcd2dlayer)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Ebenenobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLayer::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle, um das Objekt|  
|[CD2DLayer::Create](#create)|Erstellt einen CD2DLayer. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLayer::Destroy](#destroy)|Zerstört ein CD2DLayer-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DLayer::Detach](#detach)|Trennt Ressourcenschnittstelle aus dem Objekt|  
|[CD2DLayer::Get](#get)|Gibt die ID2D1Layer-Schnittstelle|  
|[CD2DLayer::GetSize](#getsize)|Gibt die Größe des Renderingziels in geräteunabhängigen Pixeln|  
|[CD2DLayer::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (Außerkraftsetzungen [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLayer::Operator ID2D1Layer *](#operator_id2d1layer_star)|Gibt die ID2D1Layer-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DLayer::m_pLayer](#m_player)|Speichert einen Zeiger auf ein ID2D1Layer-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DLayer`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dlayer"></a>CD2DLayer:: ~ CD2DLayer  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Ebenenobjekt zerstört wird.  
  
```  
virtual ~CD2DLayer();
```  
  
##  <a name="attach"></a>CD2DLayer::Attach  
 Hängt die vorhandene Ressourcenschnittstelle, um das Objekt  
  
```  
void Attach(ID2D1Layer* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dlayer"></a>CD2DLayer::CD2DLayer  
 Erstellt ein CD2DLayer-Objekt.  
  
```  
CD2DLayer(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderziel.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="create"></a>CD2DLayer::Create  
 Erstellt einen CD2DLayer.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="destroy"></a>CD2DLayer::Destroy  
 Zerstört ein CD2DLayer-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DLayer::Detach  
 Trennt Ressourcenschnittstelle aus dem Objekt  
  
```  
ID2D1Layer* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Ressourcenschnittstelle.  
  
##  <a name="get"></a>CD2DLayer::Get  
 Gibt die ID2D1Layer-Schnittstelle  
  
```  
ID2D1Layer* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1Layer-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getsize"></a>CD2DLayer::GetSize  
 Gibt die Größe des Renderingziels in geräteunabhängigen Pixeln  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Größe des Renderingziels in geräteunabhängigen Pixeln  
  
##  <a name="isvalid"></a>CD2DLayer::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls "false".  
  
##  <a name="m_player"></a>CD2DLayer::m_pLayer  
 Speichert einen Zeiger auf ein ID2D1Layer-Objekt.  
  
```  
ID2D1Layer* m_pLayer;  
```  
  
##  <a name="operator_id2d1layer_star"></a>CD2DLayer::Operator ID2D1Layer *  
 Gibt die ID2D1Layer-Schnittstelle  
  
```  
operator ID2D1Layer* ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1Layer-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

