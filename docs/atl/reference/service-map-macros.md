---
title: Service Map-Makros | Microsoft-Dokumentation
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
ms.openlocfilehash: 932cc50095ddbe908e9a3f451c1d6f8e3803fb74
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882370"
---
# <a name="service-map-macros"></a>Servicezuordnungs-Makros
Diese Makros definieren dienstzuordnungen und Einträge.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|Kennzeichnet den Anfang ein ATL-dienstzuordnung.|  
|[END_SERVICE_MAP](#end_service_map)|Markiert das Ende der ein ATL-dienstzuordnung.|  
|[SERVICE_ENTRY](#service_entry)|Gibt an, dass das Objekt eine bestimmten Dienst-ID unterstützt.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|Weist [IServiceProviderImpl:: QueryService](#queryservice) , eine Verkettung mit dem angegebenen Objekt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
   
##  <a name="begin_service_map"></a>  BEGIN_SERVICE_MAP  
 Markiert den Beginn der dienstzuordnung.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>Parameter  
 *theClass*  
 [in] Gibt die Klasse, die die dienstzuordnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die dienstzuordnung, um Service Provider-Funktionalität für das COM-Objekt zu implementieren. Sie müssen zunächst ableiten, können die Klasse von [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md). Es gibt zwei Arten von Einträgen:  
  
- [SERVICE_ENTRY](#service_entry) gibt die Unterstützung für den angegebenen-ID (SID Dienst).  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) weist [IServiceProviderImpl:: QueryService](#queryservice) , eine Verkettung mit einer anderen angegebenen Objekt.  
  
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
 Gibt an, dass das Objekt die Dienst-Id gemäß unterstützt *SID*.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>Parameter  
 *SID*  
 Die Dienst-ID.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="service_entry_chain"></a>  SERVICE_ENTRY_CHAIN  
 Weist [IServiceProviderImpl:: QueryService](#queryservice) , eine Verkettung mit angegebene Objekt *Punk*.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 Ein Zeiger auf die **IUnknown** Schnittstelle, die zu verketten.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [BEGIN_SERVICE_MAP](#begin_service_map).  
  
##  <a name="queryservice"></a>  IServiceProviderImpl:: QueryService  
 Erstellt oder auf den angegebenen Dienst zugreift, und gibt einen Schnittstellenzeiger zurück, auf die angegebene Schnittstelle für den Dienst.  
  
```
STDMETHOD(QueryService)( 
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>Parameter  
 [IN] *GuidService*  
 Zeiger auf eine Dienst-ID (SID).  
  
 [IN] *Riid*  
 Der Bezeichner der Schnittstelle, die der Aufrufer ist, um Zugriff zu erhalten.  
  
 [OUT] *PpvObj*  
 Indirekter Zeiger auf die angeforderte Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Der zurückgegebene HRESULT-Wert ist eine der folgenden:  
  
|Rückgabewert|Bedeutung|  
|------------------|-------------|  
|S_OK|Der Dienst wurde erfolgreich erstellt oder abgerufen.|  
|E_INVALIDARG|Mindestens eines der Argumente ist ungültig.|  
|E_OUTOFMEMORY|Speicher ist nicht ausreichend, um den Dienst zu erstellen.|  
|E_UNEXPECTED|Es ist ein unbekannter Fehler aufgetreten.|  
|E_NOINTERFACE|Die angeforderte Schnittstelle ist nicht Teil dieses Dienstes oder des Diensts ist unbekannt.|  
  
### <a name="remarks"></a>Hinweise  
 `QueryService` Gibt einen indirekten Zeiger auf die angeforderte Schnittstelle in den angegebenen Dienst zurück. Der Aufrufer ist verantwortlich für das this-Zeiger freigeben, wenn es nicht mehr benötigt wird.  
  
 Beim Aufruf `QueryService`, übergeben Sie sowohl eine Dienst-ID (*GuidService*) und einen Schnittstellenbezeichner (*Riid*). Die *GuidService* gibt Sie den Dienst, der Zugriff und die *Riid* identifiziert eine Schnittstelle, die Teil des Diensts ist. Im Gegenzug erhalten Sie einen indirekten Zeiger auf die Schnittstelle an.  
  
 Das Objekt, das die Schnittstelle implementiert, kann auch Schnittstellen implementieren, die von anderen Diensten gehören. Nehmen wir einmal die folgende Situation:  
  
-   Einige dieser Schnittstellen kann optional sein. Nicht alle Schnittstellen, die in der dienstbeschreibung definiert sind notwendigerweise vorhanden, für jede Implementierung des Diensts oder für jedes zurückgegebene Objekt.  
  
-   Im Gegensatz zum Aufrufen von `QueryInterface`, übergeben einen anderen Dienstbezeichner bedeutet nicht unbedingt, dass ein anderes Component Object Model (COM)-Objekt zurückgegeben wird.  
  
-   Das zurückgegebene Objekt möglicherweise weitere Schnittstellen, die nicht Teil der Definition des Diensts sind.  
  
 Zwei verschiedene Dienste, z. B. SID_SMyService und SID_SYourService, können sowohl die Verwendung der gleichen Schnittstelle angeben, auch wenn die Implementierung der Schnittstelle keine Gemeinsamkeit zwischen den beiden Diensten verfügen. Dies funktioniert, weil ein Aufruf von `QueryService` (SID_SMyService, IID_IDispatch) kann ein anderes Objekt als zurückgeben `QueryService` (SID_SYourService, IID_IDispatch). Identität des Objekts wird nicht angenommen werden, wenn Sie einen anderen Dienstbezeichner angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
