---
title: _U_MENUorID Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0ef6563166c658506a33ffa21da285207fbf5275
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="umenuorid-class"></a>_U_MENUorID-Klasse
Diese Klasse stellt den Wrapper für **CreateWindow** und **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Der Konstruktor.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Ein Handle für ein Menü.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Argument-Adapterklasse ermöglicht entweder IDs ( **"uint"**s) oder im Menü Handles ( `HMENU`s) an eine Funktion übergeben werden, ohne eine explizite Umwandlung auf dem Teil des Aufrufers.  
  
 Diese Klasse zum Implementieren der Windows-API-Wrapper dient vor allem die [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) und [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktionen, die beide akzeptieren ein `HMENU` Argument, das möglicherweise ein untergeordnetes Element Fenster Bezeichner ( **"uint"**) anstatt ein Menü-Handle. Sie können diese Klasse verwendet z. B. sehen, als Parameter an [CWindowImpl:: Create](cwindowimpl-class.md#create).  

  
 Die Klasse definiert zwei Konstruktorüberladungen: einer akzeptiert eine **"uint"** Argument und die andere akzeptiert einen `HMENU` Argument. Die **"uint"** Argument nur umgewandelt wird ein `HMENU` im Konstruktor und das Ergebnis in die Klasse der einzelnen Datenmember, gespeicherten [M_hMenu](#_u_menuorid__m_hmenu). Das Argument für die `HMENU` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 Die Klasse enthält den Wert, der entweder seiner Konstruktoren übergeben, als öffentliche `HMENU` -Datenmember.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 Die **"uint"** Argument nur umgewandelt wird ein `HMENU` im Konstruktor und das Ergebnis in die Klasse der einzelnen Datenmember, gespeicherten [M_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ein untergeordnetes Fenster-Bezeichner.  
  
 `hMenu`  
 Ein Menühandle.  
  
### <a name="remarks"></a>Hinweise  
 Das Argument für die `HMENU` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

