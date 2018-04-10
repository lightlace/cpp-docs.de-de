---
title: CHwndRenderTarget-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget [MFC], CHwndRenderTarget
- CHwndRenderTarget [MFC], Attach
- CHwndRenderTarget [MFC], CheckWindowState
- CHwndRenderTarget [MFC], Create
- CHwndRenderTarget [MFC], Detach
- CHwndRenderTarget [MFC], GetHwnd
- CHwndRenderTarget [MFC], GetHwndRenderTarget
- CHwndRenderTarget [MFC], ReCreate
- CHwndRenderTarget [MFC], Resize
- CHwndRenderTarget [MFC], m_pHwndRenderTarget
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f11f7e329b623639fb1441e4d9e18720a6b6b94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget-Klasse
Ein Wrapper für ID2D1HwndRenderTarget.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Erstellt ein CHwndRenderTarget-Objekt aus der HWND.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle, um das Objekt zu rendern|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Gibt an, ob diese Renderziel zugeordnete HWND okkludierte ist.|  
|[CHwndRenderTarget::Create](#create)|Erstellt ein Fenster zugeordneten Renderziel|  
|[CHwndRenderTarget::Detach](#detach)|Trennt die Render-Ziel-Schnittstelle aus dem Objekt|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Gibt das zugeordnete HWND-Renderziel.|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Gibt ID2D1HwndRenderTarget-Schnittstelle.|  
|[CHwndRenderTarget::ReCreate](#recreate)|Ein Renderziel Fenster zugeordneten erstellt neu|  
|[CHwndRenderTarget::Resize](#resize)|Ändert die Größe des Renderziels auf die angegebene Pixelgröße|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Gibt ID2D1HwndRenderTarget-Schnittstelle.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Ein Zeiger auf ein ID2D1HwndRenderTarget-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="attach"></a>CHwndRenderTarget::Attach  
 Hängt die vorhandene Ziel-Schnittstelle, um das Objekt zu rendern  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pTarget`  
 Vorhandene Render-Ziel-Schnittstelle. NULL darf nicht sein  
  
##  <a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState  
 Gibt an, ob diese Renderziel zugeordnete HWND okkludierte ist.  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, ob das zugeordnete HWND-Renderziel okkludiert wird.  
  
##  <a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget  
 Erstellt ein CHwndRenderTarget-Objekt aus der HWND.  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hwnd`  
 Das zugeordnete HWND-Renderziel  
  
##  <a name="create"></a>CHwndRenderTarget::Create  
 Erstellt ein Fenster zugeordneten Renderziel  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Das zugeordnete HWND-Renderziel  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben  
  
##  <a name="detach"></a>CHwndRenderTarget::Detach  
 Trennt die Render-Ziel-Schnittstelle aus dem Objekt  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Rendern Ziel-Schnittstelle.  
  
##  <a name="gethwnd"></a>CHwndRenderTarget::GetHwnd  
 Gibt das zugeordnete HWND-Renderziel.  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das zugeordnete HWND-Renderziel.  
  
##  <a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget  
 Gibt ID2D1HwndRenderTarget-Schnittstelle.  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1HwndRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget  
 Ein Zeiger auf ein ID2D1HwndRenderTarget-Objekt.  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 Gibt ID2D1HwndRenderTarget-Schnittstelle.  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1HwndRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="recreate"></a>CHwndRenderTarget::ReCreate  
 Ein Renderziel Fenster zugeordneten erstellt neu  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Das zugeordnete HWND-Renderziel  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="resize"></a>CHwndRenderTarget::Resize  
 Ändert die Größe des Renderziels auf die angegebene Pixelgröße  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Die neue Größe des Renderziels in Pixeln  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
