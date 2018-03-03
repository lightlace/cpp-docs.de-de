---
title: IServiceProviderImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4946a88e6bf6767de0e3965670f94b91d1ddaf90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl-Klasse
Diese Klasse stellt eine Standardimplementierung von der `IServiceProvider` Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IServiceProviderImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IServiceProviderImpl:: QueryService](#queryservice)|Erstellt oder greift auf den angegebenen Dienst aus, und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `IServiceProvider` Schnittstelle sucht nach einem Dienst, angegeben durch ihre GUID Schnittstellenzeiger und gibt die für die angeforderte Schnittstelle für den Dienst. Klasse `IServiceProviderImpl` stellt eine Standardimplementierung dieser Schnittstelle.  
  
 **IServiceProviderImpl** gibt eine Methode: ["QueryService"](#queryservice), das erstellt wird, oder greift auf den angegebenen Dienst und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.  
  
 `IServiceProviderImpl`Mithilfe eine dienstzuordnung, beginnend mit [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) und endend mit [END_SERVICE_MAP](service-map-macros.md#end_service_map).  
  
 Die Dienst-Karte enthält zwei Einträge angezeigt werden: [SERVICE_ENTRY](service-map-macros.md#service_entry), gibt eine angegebene Dienst-Id (SID) unterstützt, von dem Objekt an und [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), welche Aufrufe `QueryService` Kette zu einem anderen -Objekt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="queryservice"></a>IServiceProviderImpl:: QueryService  
 Erstellt oder greift auf den angegebenen Dienst aus, und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.  
  
```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 [IN]`guidService`  
 Ein Zeiger auf eine Dienst-ID (SID).  
  
 [IN]`riid`  
 Der Bezeichner der Schnittstelle, auf die der Aufrufer Zugriff zu erhalten.  
  
 [OUT]`ppvObj`  
 Indirekter Zeiger auf die angeforderte Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Das zurückgegebene `HRESULT` Wert ist eine der folgenden:  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|S_OK|Der Dienst wurde erfolgreich erstellt oder abgerufen werden.|  
|E_INVALIDARG|Mindestens eines der Argumente ist ungültig.|  
|E_OUTOFMEMORY|Speicher ist nicht ausreichend, um den Dienst zu erstellen.|  
|E_UNEXPECTED|Es ist ein unbekannter Fehler aufgetreten.|  
|E_NOINTERFACE|Die angeforderte Schnittstelle ist nicht Teil des Diensts oder der Dienst ist unbekannt.|  
  
### <a name="remarks"></a>Hinweise  
 `QueryService`Gibt einen indirekten Zeiger auf die angeforderte Schnittstelle in den angegebenen Dienst. Der Aufrufer ist verantwortlich für die Freigabe dieser Zeiger, wenn er nicht mehr benötigt wird.  
  
 Beim Aufruf `QueryService`, übergeben Sie einen Service-Bezeichner ( `guidService`) und einen Schnittstellenbezeichner ( `riid`). Die `guidService` gibt den Dienst zugreifen, werden sollen und die `riid` identifiziert eine Schnittstelle, die Teil des Diensts ist. Im Gegenzug erhalten Sie einen indirekten Zeiger auf die Schnittstelle an.  
  
 Das Objekt, das die Schnittstelle implementiert, kann auch Schnittstellen implementieren, die von anderen Diensten gehören. Nehmen wir einmal die folgende Situation:  
  
-   Einige dieser Schnittstellen können optional sein. Nicht alle Schnittstellen, die gemäß der Beschreibung des Diensts sind unbedingt vorhanden, auf jede Implementierung des Diensts oder für jedes zurückgegebene Objekt.  
  
-   Im Gegensatz zu Aufrufen `QueryInterface`, übergeben einen anderen Dienstbezeichner bedeutet nicht unbedingt, dass ein anderes Component Object Model (COM)-Objekt zurückgegeben wird.  
  
-   Das zurückgegebene Objekt möglicherweise weitere Schnittstellen, die nicht Teil der Definition des Diensts sind.  
  
 Zwei verschiedene Dienste, z. B. SID_SMyService und SID_SYourService, können sowohl die Verwendung derselben Schnittstelle angeben, auch wenn die Implementierung der Schnittstelle keine Gemeinsamkeit zwischen den beiden Diensten verfügen. Dies funktioniert, weil ein Aufruf von `QueryService` (SID_SMyService, IID_IDispatch) kann ein anderes Objekt als zurückgeben `QueryService` (SID_SYourService, IID_IDispatch). Objektidentität wird nicht angenommen werden, wenn Sie eine anderen Dienst-ID angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
