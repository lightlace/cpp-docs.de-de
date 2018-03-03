---
title: ISupportErrorInfoImpl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 61e8dc6b277f8eb59ade428d3ef8ea3dd5c083ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl-Klasse
Diese Klasse stellt eine Standardimplementierung von der [ISupportErrorInfo-Schnittstelle](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>Parameter  
 `piid`  
 Ein Zeiger auf die IID der Schnittstelle, die unterstützt [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447).  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Gibt an, ob die Schnittstelle identifizierte `riid` unterstützt die [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) Schnittstelle.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ISupportErrorInfo-Schnittstelle](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32) wird sichergestellt, dass die Fehlerinformationen an den Client zurückgegeben werden kann. Objekten, **IErrorInfo** implementieren müssen **ISupportErrorInfo**.  
  
 Klasse `ISupportErrorInfoImpl` stellt eine Standardimplementierung von **ISupportErrorInfo** und kann verwendet werden, wenn nur eine einzige Schnittstelle Fehler für ein Objekt generiert. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 Gibt an, ob die Schnittstelle identifizierte `riid` unterstützt die [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447) Schnittstelle.  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [ISupportErrorInfo:: InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a) im Windows SDK.  
  
##  <a name="getsize"></a>IThreadPoolConfig::GetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>Parameter  
 `pnNumThreads`  
 [out] Die Adresse der Variablen, die bei Erfolg, die Anzahl der Threads im Pool empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Parameter  
 `pdwMaxWait`  
 [out] Die Adresse der Variablen, die bei Erfolg, die maximale Zeit in Millisekunden empfängt, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="setsize"></a>IThreadPoolConfig::SetSize  
 Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>Parameter  
 `nNumThreads`  
 Die angeforderte Anzahl von Threads im Pool.  
  
 Wenn `nNumThreads` ist negativ ist, dessen absoluter Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtanzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` ist 0 (null), [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtanzahl der Threads abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
