---
title: IConnectionPointImpl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 444dea401fa711b40e4d8229b26c9cdbf6d1fcbc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362639"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl-Klasse
Diese Klasse implementiert einen Verbindungspunkt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>  
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IConnectionPointImpl`.  
  
 `piid`  
 Ein Zeiger auf die IID der Schnittstelle, die durch das Objekt dargestellt wird.  
  
 `CDV`  
 Eine Klasse, die Verbindungen verwaltet. Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), womit unbegrenzte Verbindungen. Sie können auch [CComUnkArray](../../atl/reference/ccomunkarray-class.md), die eine feste Anzahl von Verbindungen angibt.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Herstellen einer Verbindung zwischen dem Verbindungspunkt und Senke.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Ruft die IID der Schnittstelle dargestellt, die durch den Verbindungspunkt ab.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Ruft einen Schnittstellenzeiger auf das verbindungsfähige Objekt ab.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Beendet eine Verbindung zuvor über `Advise`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Verwaltet die Verbindungen des Verbindungspunkts an.|  
  
## <a name="remarks"></a>Hinweise  
 `IConnectionPointImpl` implementiert einen Verbindungspunkt, der ein Objekt, das eine Ausgangsschnittstelle an den Client verfügbar machen kann. Der Client implementiert diese Schnittstelle für ein Objekt, das als Sink bezeichnet wird.  
  
 ATL verwendet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) das verbindungsfähige Objekt zu implementieren. Jeder Verbindungspunkt in das verbindungsfähige Objekt stellt eine Ausgangsschnittstelle identifizierten `piid`. Klasse *CDV* verwaltet die Verbindungen zwischen dem Verbindungspunkt und Senke. Jede Verbindung wird durch ein "Cookie" eindeutig identifiziert.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="advise"></a>  IConnectionPointImpl::Advise  
 Herstellen einer Verbindung zwischen dem Verbindungspunkt und Senke.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [Unadvise](#unadvise) Verbindung beendet.  
  
 Finden Sie unter [IConnectionPoint:: Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) im Windows SDK.  
  
##  <a name="enumconnections"></a>  IConnectionPointImpl::EnumConnections  
 Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) im Windows SDK.  
  
##  <a name="getconnectioninterface"></a>  IConnectionPointImpl::GetConnectionInterface  
 Ruft die IID der Schnittstelle dargestellt, die durch den Verbindungspunkt ab.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) im Windows SDK.  
  
##  <a name="getconnectionpointcontainer"></a>  IConnectionPointImpl::GetConnectionPointContainer  
 Ruft einen Schnittstellenzeiger auf das verbindungsfähige Objekt ab.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) im Windows SDK.  
  
##  <a name="m_vec"></a>  IConnectionPointImpl::m_vec  
 Verwaltet die Verbindungen zwischen dem Verbindungspunktobjekt und Senke.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `m_vec` ist vom Typ [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="unadvise"></a>  IConnectionPointImpl::Unadvise  
 Beendet eine Verbindung zuvor über [Advise](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
