---
title: Klasse IServiceProviderImpl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IServiceProviderImpl<T>
- ATL.IServiceProviderImpl<T>
- ATL.IServiceProviderImpl
- ATL::IServiceProviderImpl
- IServiceProviderImpl
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 69a59fe23b3ca787dee86b1bbdc6775a44903f91
ms.lasthandoff: 02/24/2017

---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl-Klasse
Diese Klasse enthält die standardmäßige Implementierung der `IServiceProvider` Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Abgeleitet von die Klasse `IServiceProviderImpl`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IServiceProviderImpl:: QueryService](#queryservice)|Erstellt oder den angegebenen Dienst zugreift, und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Die `IServiceProvider` Schnittstelle sucht nach einem Dienst anhand seiner GUID angegeben ist, und gibt den Schnittstellenzeiger für die angeforderte Schnittstelle für den Dienst. Klasse `IServiceProviderImpl` stellt eine Standardimplementierung dieser Schnittstelle.  
  
 **IServiceProviderImpl** gibt eine Methode an: [QueryService](#queryservice), die erstellt oder den angegebenen Dienst zugreift und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.  
  
 `IServiceProviderImpl`verwendet eine dienstzuordnung, beginnend mit [BEGIN_SERVICE_MAP](http://msdn.microsoft.com/library/3c6ae156-8776-4588-8227-2d234daec236) und endend mit [END_SERVICE_MAP](http://msdn.microsoft.com/library/9a35d02a-014c-413a-bb0b-bcca11ab45a6).  
  
 Die dienstzuordnung enthält zwei Einträge: [SERVICE_ENTRY](http://msdn.microsoft.com/library/e65ff9cc-15e8-41cf-b686-f99eb6686ca9), gibt einen angegebenen Dienst-Id (SID), die vom Objekt unterstützten an und [SERVICE_ENTRY_CHAIN](http://msdn.microsoft.com/library/09be4ce4-3ccd-4ff2-a95e-a9d5275354c1), welche `QueryService` Kette zu einem anderen Objekt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="a-namequeryservicea--iserviceproviderimplqueryservice"></a><a name="queryservice"></a>IServiceProviderImpl:: QueryService  
 Erstellt oder den angegebenen Dienst zugreift, und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.  
  
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
 Bezeichner der Schnittstelle, auf die der Aufrufer zugreifen.  
  
 [OUT]`ppvObj`  
 Indirekter Zeiger auf die angeforderte Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Das zurückgegebene `HRESULT` Wert ist einer der folgenden:  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|S_OK|Der Dienst wurde erfolgreich erstellt oder abgerufen.|  
|E_INVALIDARG|Mindestens eines der Argumente ist ungültig.|  
|E_OUTOFMEMORY|Speicher ist nicht ausreichend, um den Dienst zu erstellen.|  
|E_UNEXPECTED|Es ist ein unbekannter Fehler aufgetreten.|  
|E_NOINTERFACE|Die angeforderte Schnittstelle ist nicht Teil des Diensts oder der Dienst ist unbekannt.|  
  
### <a name="remarks"></a>Hinweise  
 `QueryService`Gibt einen indirekten Zeiger auf die angeforderte Schnittstelle im angegebenen Dienst. Der Aufrufer ist verantwortlich für die Freigabe this-Zeiger, wenn er nicht mehr benötigt wird.  
  
 Beim Aufruf von `QueryService`, übergeben Sie einen Service-Bezeichner ( `guidService`) und einen Schnittstellenbezeichner ( `riid`). Die `guidService` gibt den Dienst zugreifen, werden soll und die `riid` identifiziert eine Schnittstelle, die Teil des Diensts. Im Gegenzug erhalten Sie einen indirekten Zeiger auf die Schnittstelle.  
  
 Das Objekt, das die Schnittstelle implementiert, kann auch Schnittstellen implementieren, die von anderen Diensten gehören. Nehmen wir einmal die folgende Situation:  
  
-   Einige dieser Schnittstellen können optional sein. Nicht alle Schnittstellen, die in der Dienstdefinition definiert sind unbedingt auf jede Implementierung des Diensts oder für jedes zurückgegebene Objekt vorhanden.  
  
-   Im Gegensatz zu Aufrufen von `QueryInterface`, eine anderen Dienst-ID übergeben bedeutet nicht unbedingt, dass ein anderes Component Object Model (COM)-Objekt zurückgegeben wird.  
  
-   Das zurückgegebene Objekt möglicherweise weitere Schnittstellen, die nicht Teil der Definition des Diensts sind.  
  
 Zwei verschiedene Dienste, wie z. B. SID_SMyService und SID_SYourService, können beide die gleiche Schnittstelle verwenden, obwohl die Implementierung der Schnittstelle keine gemeinsame zwischen den beiden Diensten möglicherweise. Dies funktioniert, weil ein Aufruf von `QueryService` (SID_SMyService, IID_IDispatch) kann ein anderes Objekt als zurückgeben `QueryService` (SID_SYourService, IID_IDispatch). Identität des Objekts ist nicht angenommen werden, wenn Sie einen anderen Dienstbezeichner angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

