---
title: _U_MENUorID Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 847a735cdba6b9ff4173e23acf78ea7dc4d3034c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="umenuorid-class"></a>_U_MENUorID-Klasse
Diese Klasse stellt den Wrapper für **CreateWindow** und **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class _U_MENUorID
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Der Konstruktor.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Ein Handle für ein Menü.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Argument-Adapterklasse ermöglicht entweder IDs ( **"uint"** s) oder im Menü Handles ( `HMENU`s) an eine Funktion übergeben werden, ohne eine explizite Umwandlung auf dem Teil des Aufrufers.  
  
 Diese Klasse zum Implementieren der Windows-API-Wrapper dient vor allem die [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) und [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktionen, die beide akzeptieren ein `HMENU` Argument, das möglicherweise ein untergeordnetes Element Fenster Bezeichner ( **"uint"**) anstatt ein Menü-Handle. Sie können diese Klasse verwendet z. B. sehen, als Parameter an [CWindowImpl:: Create](cwindowimpl-class.md#create).  

  
 Die Klasse definiert zwei Konstruktorüberladungen: einer akzeptiert eine **"uint"** Argument und die andere akzeptiert einen `HMENU` Argument. Die **"uint"** Argument nur umgewandelt wird ein `HMENU` im Konstruktor und das Ergebnis in die Klasse der einzelnen Datenmember, gespeicherten [M_hMenu](#_u_menuorid__m_hmenu). Das Argument für die `HMENU` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="_u_menuorid__m_hmenu"></a>  _U_MENUorID::m_hMenu  
 Die Klasse enthält den Wert, der entweder seiner Konstruktoren übergeben, als öffentliche `HMENU` -Datenmember.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>  _U_MENUorID::_U_MENUorID  
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
