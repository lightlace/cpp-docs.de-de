---
title: Service-Makros | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
caps.latest.revision: 16
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
ms.openlocfilehash: eea45a3315237c77eff0231d485111cefb8557cc
ms.lasthandoff: 02/24/2017

---
# <a name="service-map-macros"></a>Dienst-Map-Makros
Diese Makros definieren dienstzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|Markiert den Beginn einer ATL-Service-Zuordnung.|  
|[END_SERVICE_MAP](#end_service_map)|Markiert das Ende einer ATL-Service-Zuordnung.|  
|[SERVICE_ENTRY](#service_entry)|Gibt an, dass das Objekt eine bestimmten Dienst-ID unterstützt.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Weist [IServiceProviderImpl:: QueryService](#queryservice) Kette für das angegebene Objekt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
   
##  <a name="a-namebeginservicemapa--beginservicemap"></a><a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 Markiert den Anfang der dienstzuordnung.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Gibt die Klasse, die die dienstzuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die dienstzuordnung, Service Provider-Funktionalität für das COM-Objekt implementiert. Erstens leiten Sie eine Klasse von [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Es gibt zwei Arten von Einträgen:  
  
- [SERVICE_ENTRY](#service_entry) gibt die Unterstützung für den angegebenen-ID (SID Dienst).  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) weist [IServiceProviderImpl:: QueryService](#queryservice) zu verketten, die auf einem anderen, angegebenen Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#57;](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="a-nameendservicemapa--endservicemap"></a><a name="end_service_map"></a>END_SERVICE_MAP  
 Markiert das Ende der Zuordnung Service.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="a-nameserviceentrya--serviceentry"></a><a name="service_entry"></a>SERVICE_ENTRY  
 Gibt an, dass das Objekt die Dienst-Id, die durch angegebene unterstützt *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Parameter  
 *SID*  
 Die Dienst-ID.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="a-nameserviceentrychaina--serviceentrychain"></a><a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 Weist [IServiceProviderImpl:: QueryService](#queryservice) zu verketten, das angegebene Objekt `punk`.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Parameter  
 `punk`  
 Ein Zeiger auf die **IUnknown** Schnittstelle, die zu verketten.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
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
 [Makros](../../atl/reference/atl-macros.md)

