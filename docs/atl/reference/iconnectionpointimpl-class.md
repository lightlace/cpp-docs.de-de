---
title: IConnectionPointImpl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c9788496bbed3734b959d0ab4c49c89a176ea199
ms.lasthandoff: 02/24/2017

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
 Abgeleitet von die Klasse `IConnectionPointImpl`.  
  
 `piid`  
 Ein Zeiger auf die IID für die Schnittstelle, die durch das Objekt dargestellt wird.  
  
 `CDV`  
 Eine Klasse, die Verbindungen verwaltet. Der Standardwert ist [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), wodurch unbegrenzte Verbindungen. Sie können auch [CComUnkArray](../../atl/reference/ccomunkarray-class.md), die eine feste Anzahl von Verbindungen angibt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IConnectionPointImpl::Advise](#advise)|Stellt eine Verbindung zwischen dem Verbindungspunkt und Senke.|  
|[IConnectionPointImpl::EnumConnections](#enumconnections)|Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.|  
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|Ruft die IID der Schnittstelle dargestellt, die von den Verbindungspunkt ab.|  
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|Ruft einen Schnittstellenzeiger auf das verbindungsfähige Objekt ab.|  
|[IConnectionPointImpl::Unadvise](#unadvise)|Beendet eine Verbindung zuvor mit `Advise`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IConnectionPointImpl::m_vec](#m_vec)|Verwaltet die Verbindungen für den Verbindungspunkt.|  
  
## <a name="remarks"></a>Hinweise  
 `IConnectionPointImpl`implementiert einen Verbindungspunkt, wodurch ein Objekt, das eine Ausgangsschnittstelle an den Client verfügbar machen. Der Client implementiert diese Schnittstelle für ein Objekt, das als Sink bezeichnet.  
  
 ATL verwendet [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) das verbindungsfähige Objekt implementiert. Jeder Verbindungspunkt in das verbindungsfähige Objekt stellt Ausgangsschnittstelle identifizierten `piid`. Klasse *CDV* verwaltet die Verbindungen zwischen dem Verbindungspunkt und Senke. Jede Verbindung wird durch ein "Cookie" eindeutig identifiziert.  
  
 Weitere Informationen zur Verwendung von Verbindungspunkten in ATL finden Sie im Artikel [Verbindungspunkte](../../atl/atl-connection-points.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="advise"></a>IConnectionPointImpl::Advise  
 Stellt eine Verbindung zwischen dem Verbindungspunkt und Senke.  
  
```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [Unadvise](#unadvise) Verbindung beendet.  
  
 Finden Sie unter [IConnectionPoint:: Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="enumconnections"></a>IConnectionPointImpl::EnumConnections  
 Erstellt einen Enumerator zum Durchlaufen der Verbindungen für den Verbindungspunkt.  
  
```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: EnumConnections](http://msdn.microsoft.com/library/windows/desktop/ms680755) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getconnectioninterface"></a>IConnectionPointImpl::GetConnectionInterface  
 Ruft die IID der Schnittstelle dargestellt, die von den Verbindungspunkt ab.  
  
```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: GetConnectionInterface](http://msdn.microsoft.com/library/windows/desktop/ms693468) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getconnectionpointcontainer"></a>IConnectionPointImpl::GetConnectionPointContainer  
 Ruft einen Schnittstellenzeiger auf das verbindungsfähige Objekt ab.  
  
```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: GetConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms679669) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_vec"></a>IConnectionPointImpl::m_vec  
 Verwaltet die Verbindungen zwischen dem Objekt und Senke.  
  
```
CDV m_vec;
```     
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung `m_vec` ist vom Typ [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md).  
  
##  <a name="unadvise"></a>IConnectionPointImpl::Unadvise  
 Beendet eine Verbindung zuvor mit [Advise](#advise).  
  
```
STDMETHOD(Unadvise)(DWORD dwCookie);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [IConnectionPoint:: Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

