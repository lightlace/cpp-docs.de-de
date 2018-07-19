---
title: IConnectionPointContainerImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d70989be8e8535336c831cb59fb9422c6e2c63e0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37886231"
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl-Klasse
Diese Klasse implementiert eine Verbindungspunktcontainer zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IConnectionPointContainerImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte, die in dem verbindungsfähigen Objekt unterstützt.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Ruft einen Schnittstellenzeiger auf den Verbindungspunkt, der die angegebene IID unterstützt ab.|  
  
## <a name="remarks"></a>Hinweise  
 `IConnectionPointContainerImpl` implementiert eine Verbindungspunktcontainer zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte. `IConnectionPointContainerImpl` bietet zwei Methoden, die ein Client aufrufen kann, um weitere Informationen zu einem verbindungsfähigen Objekt abzurufen:  
  
- `EnumConnectionPoints` ermöglicht dem Client, um zu bestimmen, welche ausgehend vom Objekt unterstützte Schnittstellen.  
  
- `FindConnectionPoint` ermöglicht dem Client zu bestimmen, ob das Objekt eine bestimmte Schnittstelle für ausgehende unterstützt.  
  
 Informationen zur Verwendung von Verbindungspunkten in ATL, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>  IConnectionPointContainerImpl::EnumConnectionPoints  
 Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte, die in dem verbindungsfähigen Objekt unterstützt.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPointContainer:: EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) in das Windows SDK.  
  
##  <a name="findconnectionpoint"></a>  IConnectionPointContainerImpl::FindConnectionPoint  
 Ruft einen Schnittstellenzeiger auf den Verbindungspunkt, der die angegebene IID unterstützt ab.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPointContainer:: FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) in das Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPointContainer-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
