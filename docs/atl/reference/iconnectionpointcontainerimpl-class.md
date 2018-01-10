---
title: IConnectionPointContainerImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs: C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f5e3a6ee6790c4fa0e93fe312d6a6b840b754a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iconnectionpointcontainerimpl-class"></a>IConnectionPointContainerImpl-Klasse
Diese Klasse implementiert einen Container für Verbindung zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IConnectionPointContainerImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte in das verbindungsfähige Objekt unterstützt.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|Ruft einen Schnittstellenzeiger auf dem Verbindungspunkt, der die angegebene IID unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
 `IConnectionPointContainerImpl`implementiert einen Container für Verbindung zur Verwaltung einer Auflistung von [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) Objekte. `IConnectionPointContainerImpl`bietet zwei Methoden, die ein Client aufrufen kann, um weitere Informationen über ein verbindungsfähiges Objekt abzurufen:  
  
- `EnumConnectionPoints`ermöglicht dem Client, um zu bestimmen, welche ausgehend vom Objekt unterstützte Schnittstellen.  
  
- `FindConnectionPoint`ermöglicht dem Client, um zu bestimmen, ob das Objekt einer bestimmten Ausgangsschnittstelle unterstützt.  
  
 Informationen zur Verwendung von Verbindungspunkten in ATL, finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints  
 Erstellt einen Enumerator zum Durchlaufen der Verbindungspunkte in das verbindungsfähige Objekt unterstützt.  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPointContainer:: EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) im Windows SDK.  
  
##  <a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint  
 Ruft einen Schnittstellenzeiger auf dem Verbindungspunkt, der die angegebene IID unterstützt.  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPointContainer:: FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
