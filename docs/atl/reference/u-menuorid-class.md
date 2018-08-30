---
title: _U_MENUorID-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: b9853cbcecd691f0ea16358259c8a0ac7b213433
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211186"
---
# <a name="umenuorid-class"></a>_U_MENUorID-Klasse
Diese Klasse stellt den Wrapper für `CreateWindow` und `CreateWindowEx`.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
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
 Dieses Argument-Adapterklasse ermöglicht entweder-IDs (jenem) oder im Menü-Handles (HMENUs) an eine Funktion übergeben werden, ohne eine explizite Umwandlung seitens des Aufrufers.  
  
 Diese Klasse zum Implementieren der Windows-API-Wrapper dient insbesondere die [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679) und [CreateWindowEx](https://msdn.microsoft.com/library/windows/desktop/ms632680) Funktionen, die beide ein HMENU-Argument, das ein untergeordnetes Fenster möglicherweise akzeptieren Bezeichner (UINT), anstatt ein Menühandle. Beispielsweise sehen Sie diese Klasse verwendet als Parameter an [CWindowImpl:: Create](cwindowimpl-class.md#create).  

  
 Die Klasse definiert zwei Konstruktorüberladungen: eine ein UINT-Argument akzeptiert und die andere ein HMENU-Argument akzeptiert. Das Argument "uint" umgewandelt wird nur ein HMENU im Konstruktor und in das Ergebnis gespeichert werden, in der Klasse der einzelnen Datenmember, [M_hMenu](#_u_menuorid__m_hmenu). Das Argument für das HMENU-Konstruktor wird direkt ohne Konvertierung gespeichert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="_u_menuorid__m_hmenu"></a>  _U_MENUorID::m_hMenu  
 Die Klasse enthält den Wert als einen öffentlichen Datenmember von HMENU an eines ihrer Konstruktoren übergeben.  
  
```
HMENU m_hMenu;
```  
  
##  <a name="_u_menuorid___u_menuorid"></a>  _U_MENUorID::_U_MENUorID  
 Das Argument "uint" umgewandelt wird nur ein HMENU im Konstruktor und in das Ergebnis gespeichert werden, in der Klasse der einzelnen Datenmember, [M_hMenu](#_u_menuorid__m_hmenu).  
  
```
_U_MENUorID(UINT nID);  
_U_MENUorID(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Ein Bezeichner des untergeordneten Fensters.  
  
 *hMenu*  
 Ein Menühandle.  
  
### <a name="remarks"></a>Hinweise  
 Das Argument für das HMENU-Konstruktor wird direkt ohne Konvertierung gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
