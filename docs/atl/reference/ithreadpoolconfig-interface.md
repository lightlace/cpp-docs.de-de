---
title: IThreadPoolConfig Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs: C++
helpviewer_keywords: IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d967720778305eace4eff9ad8b2163456fb4bb46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig-Schnittstelle
Diese Schnittstelle bietet Methoden zum Konfigurieren eines Threadpools.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetSize](#getsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.|  
|[GetTimeout](#gettimeout)|Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool darauf gewartet, dass ein Thread beendet wird.|  
|[SetSize](#setsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.|  
|[SetTimeout](#settimeout)|Rufen Sie diese Methode zum Festlegen der maximalen Zeit in Millisekunden, die der Threadpool darauf gewartet, dass ein Thread beendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird implementiert, indem [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
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
 [!code-cpp[NVC_ATL_Utilities#134](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
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
 [Klassen](../../atl/reference/atl-classes.md)   
 [CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)
