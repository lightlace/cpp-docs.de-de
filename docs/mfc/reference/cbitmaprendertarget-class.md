---
title: CBitmapRenderTarget-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f07e3783de7efe4e279a4f8d69563349cb72a362
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget-Klasse
Ein Wrapper für ID2D1BitmapRenderTarget.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBitmapRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapRenderTarget::CBitmapRenderTarget](#cbitmaprendertarget)|Erstellt ein CBitmapRenderTarget-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle, um das Objekt zu rendern|  
|[CBitmapRenderTarget::Detach](#detach)|Trennt die Render-Ziel-Schnittstelle aus dem Objekt|  
|[CBitmapRenderTarget::GetBitmap](#getbitmap)|Ruft die Bitmap für diese Renderziel ab. Die zurückgegebene Bitmap kann für Zeichenvorgänge verwendet werden.|  
|[CBitmapRenderTarget::GetBitmapRenderTarget](#getbitmaprendertarget)|Gibt die ID2D1BitmapRenderTarget-Schnittstelle|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|Gibt die ID2D1BitmapRenderTarget-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CBitmapRenderTarget::m_pBitmapRenderTarget](#m_pbitmaprendertarget)|Ein Zeiger auf ein ID2D1BitmapRenderTarget-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 `CBitmapRenderTarget` 
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="attach"></a>CBitmapRenderTarget::Attach  
 Hängt die vorhandene Ziel-Schnittstelle, um das Objekt zu rendern  
  
```  
void Attach(ID2D1BitmapRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pTarget`  
 Vorhandene Render-Ziel-Schnittstelle. NULL darf nicht sein  
  
##  <a name="cbitmaprendertarget"></a>CBitmapRenderTarget::CBitmapRenderTarget  
 Erstellt ein CBitmapRenderTarget-Objekt.  
  
```  
CBitmapRenderTarget();
```  
  
##  <a name="detach"></a>CBitmapRenderTarget::Detach  
 Trennt die Render-Ziel-Schnittstelle aus dem Objekt  
  
```  
ID2D1BitmapRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Rendern Ziel-Schnittstelle.  
  
##  <a name="getbitmap"></a>CBitmapRenderTarget::GetBitmap  
 Ruft die Bitmap für diese Renderziel ab. Die zurückgegebene Bitmap kann für Zeichenvorgänge verwendet werden.  
  
```  
BOOL GetBitmap(CD2DBitmap& bitmap);
```  
  
### <a name="parameters"></a>Parameter  
 `bitmap`  
 Bei Rückgabe dieser Methode enthält die gültigen Bitmap für diese Renderziel. Diese Bitmap kann für Zeichenvorgänge verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="getbitmaprendertarget"></a>CBitmapRenderTarget::GetBitmapRenderTarget  
 Gibt die ID2D1BitmapRenderTarget-Schnittstelle  
  
```  
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1BitmapRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="m_pbitmaprendertarget"></a>CBitmapRenderTarget::m_pBitmapRenderTarget  
 Ein Zeiger auf ein ID2D1BitmapRenderTarget-Objekt.  
  
```  
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;  
```  
  
##  <a name="operator_id2d1bitmaprendertarget_star"></a>CBitmapRenderTarget::operator ID2D1BitmapRenderTarget *  
 Gibt die ID2D1BitmapRenderTarget-Schnittstelle  
  
```  
operator ID2D1BitmapRenderTarget*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1BitmapRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
