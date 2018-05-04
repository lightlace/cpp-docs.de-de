---
title: Ereigniszuordnungs-Makros Service | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_SERVICE_MAP
- atlcom/ATL::END_SERVICE_MAP
- atlcom/ATL::SERVICE_ENTRY
- atlcom/ATL::SERVICE_ENTRY_CHAIN
dev_langs:
- C++
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2d2fa313c574951a8f8ba7c85d5b405707ec220
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="service-map-macros"></a>Dienst-Zuordnungsmakros
Diese Makros definieren dienstzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|Markiert den Beginn einer dienstzuordnung ATL an.|  
|[END_SERVICE_MAP](#end_service_map)|Markiert das Ende einer dienstzuordnung ATL an.|  
|[SERVICE_ENTRY](#service_entry)|Gibt an, dass das Objekt eine bestimmten Dienst-ID unterstützt.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Weist [IServiceProviderImpl:: QueryService](#queryservice) zu verketten, für das angegebene Objekt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="begin_service_map"></a>  BEGIN_SERVICE_MAP  
 Markiert den Beginn der dienstzuordnung.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 `theClass`  
 [in] Gibt die Klasse, die die dienstzuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die dienstzuordnung, um Service Anbieterfunktionen für COM-Objekt zu implementieren. Zuerst, leiten Sie eine Klasse von [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Es gibt zwei Arten von Einträgen:  
  
- [SERVICE_ENTRY](#service_entry) gibt die Unterstützung für den angegebenen-ID (SID Dienst) an.  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) weist [IServiceProviderImpl:: QueryService](#queryservice) zu verketten, die auf einem anderen, angegebenen Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#57](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="end_service_map"></a>  END_SERVICE_MAP  
 Markiert das Ende der dienstzuordnung.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry"></a>  SERVICE_ENTRY  
 Gibt an, dass das Objekt die Dienst-Id, die vom angegebenen unterstützt *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Parameter  
 *SID*  
 Die Dienst-ID.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry_chain"></a>  SERVICE_ENTRY_CHAIN  
 Weist [IServiceProviderImpl:: QueryService](#queryservice) zu verketten, auf das Objekt vom angegebenen `punk`.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Parameter  
 `punk`  
 Ein Zeiger auf die **IUnknown** Schnittstelle, die zu verketten.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="queryservice"></a>  IServiceProviderImpl:: QueryService  
 Erstellt oder greift auf den angegebenen Dienst aus, und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.  
  
```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 [IN] `guidService`  
 Ein Zeiger auf eine Dienst-ID (SID).  
  
 [IN] `riid`  
 Der Bezeichner der Schnittstelle, auf die der Aufrufer Zugriff zu erhalten.  
  
 [OUT] `ppvObj`  
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
 `QueryService` Gibt einen indirekten Zeiger auf die angeforderte Schnittstelle in den angegebenen Dienst. Der Aufrufer ist verantwortlich für die Freigabe dieser Zeiger, wenn er nicht mehr benötigt wird.  
  
 Beim Aufruf `QueryService`, übergeben Sie einen Service-Bezeichner ( `guidService`) und einen Schnittstellenbezeichner ( `riid`). Die `guidService` gibt den Dienst zugreifen, werden sollen und die `riid` identifiziert eine Schnittstelle, die Teil des Diensts ist. Im Gegenzug erhalten Sie einen indirekten Zeiger auf die Schnittstelle an.  
  
 Das Objekt, das die Schnittstelle implementiert, kann auch Schnittstellen implementieren, die von anderen Diensten gehören. Nehmen wir einmal die folgende Situation:  
  
-   Einige dieser Schnittstellen können optional sein. Nicht alle Schnittstellen, die gemäß der Beschreibung des Diensts sind unbedingt vorhanden, auf jede Implementierung des Diensts oder für jedes zurückgegebene Objekt.  
  
-   Im Gegensatz zu Aufrufen `QueryInterface`, übergeben einen anderen Dienstbezeichner bedeutet nicht unbedingt, dass ein anderes Component Object Model (COM)-Objekt zurückgegeben wird.  
  
-   Das zurückgegebene Objekt möglicherweise weitere Schnittstellen, die nicht Teil der Definition des Diensts sind.  
  
 Zwei verschiedene Dienste, z. B. SID_SMyService und SID_SYourService, können sowohl die Verwendung derselben Schnittstelle angeben, auch wenn die Implementierung der Schnittstelle keine Gemeinsamkeit zwischen den beiden Diensten verfügen. Dies funktioniert, weil ein Aufruf von `QueryService` (SID_SMyService, IID_IDispatch) kann ein anderes Objekt als zurückgeben `QueryService` (SID_SYourService, IID_IDispatch). Objektidentität wird nicht angenommen werden, wenn Sie eine anderen Dienst-ID angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
