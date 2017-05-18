---
title: Klasse _U_MENUorID | Microsoft-Dokumentation
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f7c0a5c34c4e103f830a029f58cdfa00dcb58a32
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="umenuorid-class"></a>_U_MENUorID-Klasse
Diese Klasse stellt Wrapper für **CreateWindow** und **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
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
 Dieses Argument-Adapterklasse ermöglicht entweder IDs ( **UINT**s) oder im Menü Handles ( `HMENU`s) an eine Funktion übergeben werden, ohne eine explizite Umwandlung auf dem Teil des Aufrufers.  
  
 Diese Klasse dient zum Implementieren der Windows-API-Wrapper insbesondere der [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) und [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Funktionen, die akzeptiert ein `HMENU` -Argument, das möglicherweise ein Bezeichner des untergeordneten Fensters ( **UINT**) anstatt ein Menü-Handle. Beispielsweise sehen Sie diese Klasse verwendet als Parameter für [CWindowImpl:: Create](cwindowimpl-class.md#create).  

  
 Die Klasse definiert zwei Konstruktorüberladungen: eine akzeptiert einen **UINT** Argument und die andere akzeptiert einen `HMENU` Argument. Die **UINT** Argument nur umgewandelt wird ein `HMENU` im Konstruktor und das Ergebnis in der Klasse einzelnen Datenmember gespeicherten [M_hMenu](#_u_menuorid__m_hmenu). Das Argument für die `HMENU` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu  
 Die Klasse enthält den Wert, der zu einem seiner Konstruktoren übergeben, als öffentliche `HMENU` -Datenmember.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID  
 Die **UINT** Argument nur umgewandelt wird ein `HMENU` im Konstruktor und das Ergebnis in der Klasse einzelnen Datenmember gespeicherten [M_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Ein Bezeichner des untergeordneten Fensters.  
  
 `hMenu`  
 Ein Menühandle.  
  
### <a name="remarks"></a>Hinweise  
 Das Argument für die `HMENU` Konstruktor direkt ohne Konvertierung gespeichert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

