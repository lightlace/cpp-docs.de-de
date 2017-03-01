---
title: CHwndRenderTarget-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- afxrendertarget/CHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget class
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
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
ms.openlocfilehash: 1af6795e89c995ba6b5a7b094f06b0aea776f561
ms.lasthandoff: 02/24/2017

---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget-Klasse
Ein Wrapper für ID2D1HwndRenderTarget.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|Erstellt ein CHwndRenderTarget-Objekt aus HWND.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|Gibt an, ob der diesem Renderingziel zugeordnete HWND okkludiert wird.|  
|[CHwndRenderTarget::Create](#create)|Erstellt ein Fenster zugeordneten Renderingziel|  
|[CHwndRenderTarget::Detach](#detach)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|Gibt das zugeordnete HWND Renderingziel.|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|Gibt die ID2D1HwndRenderTarget-Schnittstelle.|  
|[CHwndRenderTarget::ReCreate](#recreate)|Ein Fenster zugeordnetes Renderingziel erstellt neu|  
|[CHwndRenderTarget::Resize](#resize)|Ändert die Größe des Renderingziels in die angegebene Pixelgröße|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|Gibt die ID2D1HwndRenderTarget-Schnittstelle.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|Ein Zeiger auf ein ID2D1HwndRenderTarget-Objekt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-nameattacha--chwndrendertargetattach"></a><a name="attach"></a>CHwndRenderTarget::Attach  
 Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pTarget`  
 Vorhandene Renderingzielschnittstelle. NULL darf nicht sein  
  
##  <a name="a-namecheckwindowstatea--chwndrendertargetcheckwindowstate"></a><a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState  
 Gibt an, ob der diesem Renderingziel zugeordnete HWND okkludiert wird.  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, ob das Renderingziel zugeordneten HWND okkludiert wird.  
  
##  <a name="a-namechwndrendertargeta--chwndrendertargetchwndrendertarget"></a><a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget  
 Erstellt ein CHwndRenderTarget-Objekt aus HWND.  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `hwnd`  
 Das HWND zugeordnetes Renderingziel  
  
##  <a name="a-namecreatea--chwndrendertargetcreate"></a><a name="create"></a>CHwndRenderTarget::Create  
 Erstellt ein Fenster zugeordneten Renderingziel  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Das HWND zugeordnetes Renderingziel  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben  
  
##  <a name="a-namedetacha--chwndrendertargetdetach"></a><a name="detach"></a>CHwndRenderTarget::Detach  
 Trennt die Renderingzielschnittstelle vom Objekt  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Renderingzielschnittstelle.  
  
##  <a name="a-namegethwnda--chwndrendertargetgethwnd"></a><a name="gethwnd"></a>CHwndRenderTarget::GetHwnd  
 Gibt das zugeordnete HWND Renderingziel.  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das HWND zugeordnetes Renderingziel.  
  
##  <a name="a-namegethwndrendertargeta--chwndrendertargetgethwndrendertarget"></a><a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget  
 Gibt die ID2D1HwndRenderTarget-Schnittstelle.  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1HwndRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namemphwndrendertargeta--chwndrendertargetmphwndrendertarget"></a><a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget  
 Ein Zeiger auf ein ID2D1HwndRenderTarget-Objekt.  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="a-nameoperatorid2d1hwndrendertargetstara--chwndrendertargetoperator-id2d1hwndrendertarget"></a><a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 Gibt die ID2D1HwndRenderTarget-Schnittstelle.  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1HwndRenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namerecreatea--chwndrendertargetrecreate"></a><a name="recreate"></a>CHwndRenderTarget::ReCreate  
 Ein Fenster zugeordnetes Renderingziel erstellt neu  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>Parameter  
 `hWnd`  
 Das HWND zugeordnetes Renderingziel  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="a-nameresizea--chwndrendertargetresize"></a><a name="resize"></a>CHwndRenderTarget::Resize  
 Ändert die Größe des Renderingziels in die angegebene Pixelgröße  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Die neue Größe des Renderingziels in Gerätepixel  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

