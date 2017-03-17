---
title: CDCRenderTarget-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CDCRenderTarget class
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2bbd62b06f4287904fce49f8a6ce9900476b07c0
ms.lasthandoff: 02/24/2017

---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget-Klasse
Ein Wrapper für ID2D1DCRenderTarget.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDCRenderTarget::CDCRenderTarget](#cdcrendertarget)|Erstellt einen CDCRenderTarget-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDCRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern|  
|[CDCRenderTarget::BindDC](#binddc)|Bindet das Renderingziel an den Gerätekontext, den es Zeichenbefehle ausgibt|  
|[CDCRenderTarget::Create](#create)|Erstellt einen CDCRenderTarget.|  
|[CDCRenderTarget::Detach](#detach)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CDCRenderTarget::GetDCRenderTarget](#getdcrendertarget)|Gibt die ID2D1DCRenderTarget-Schnittstelle|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|Gibt die ID2D1DCRenderTarget-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDCRenderTarget::m_pDCRenderTarget](#m_pdcrendertarget)|Ein Zeiger auf ein ID2D1DCRenderTarget-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="attach"></a>CDCRenderTarget::Attach  
 Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern  
  
```  
void Attach(ID2D1DCRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pTarget`  
 Vorhandene Renderingzielschnittstelle. NULL darf nicht sein  
  
##  <a name="binddc"></a>CDCRenderTarget::BindDC  
 Bindet das Renderingziel an den Gerätekontext, den es Zeichenbefehle ausgibt  
  
```  
BOOL BindDC(
    const CDC& dc,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `dc`  
 Der Gerätekontext, an den das Renderingziel Zeichenbefehle ausgibt  
  
 `rect`  
 Die Dimensionen des Handles für einen Gerätekontext (HDC) an das Renderziel gebunden ist  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="cdcrendertarget"></a>CDCRenderTarget::CDCRenderTarget  
 Erstellt einen CDCRenderTarget-Objekt.  
  
```  
CDCRenderTarget();
```  
  
##  <a name="create"></a>CDCRenderTarget::Create  
 Erstellt einen CDCRenderTarget.  
  
```  
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```  
  
### <a name="parameters"></a>Parameter  
 `props`  
 Den Renderingmodus, Pixelformat, Remotingoptionen, DPI-Informationen und die minimale DirectX-Unterstützung für Hardwarerendering erforderlich.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="detach"></a>CDCRenderTarget::Detach  
 Trennt die Renderingzielschnittstelle vom Objekt  
  
```  
ID2D1DCRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Renderingzielschnittstelle.  
  
##  <a name="getdcrendertarget"></a>CDCRenderTarget::GetDCRenderTarget  
 Gibt die ID2D1DCRenderTarget-Schnittstelle  
  
```  
ID2D1DCRenderTarget* GetDCRenderTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1DCRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="m_pdcrendertarget"></a>CDCRenderTarget::m_pDCRenderTarget  
 Ein Zeiger auf ein ID2D1DCRenderTarget-Objekt.  
  
```  
ID2D1DCRenderTarget* m_pDCRenderTarget;  
```  
  
##  <a name="operator_id2d1dcrendertarget_star"></a>CDCRenderTarget::operator ID2D1DCRenderTarget *  
 Gibt die ID2D1DCRenderTarget-Schnittstelle  
  
```  
operator ID2D1DCRenderTarget*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1DCRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

