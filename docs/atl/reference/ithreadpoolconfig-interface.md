---
title: IThreadPoolConfig Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IThreadPoolConfig
- ATLUTIL/ATL::IThreadPoolConfig
- ATLUTIL/ATL::GetSize
- ATLUTIL/ATL::GetTimeout
- ATLUTIL/ATL::SetSize
- ATLUTIL/ATL::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- IThreadPoolConfig interface
ms.assetid: 69e642bf-6925-46e6-9a37-cce52231b1cc
caps.latest.revision: 24
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: e10885373442890978feff42cda99309692a21d0
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ithreadpoolconfig-interface"></a>IThreadPoolConfig-Schnittstelle
Diese Schnittstelle stellt Methoden zum Konfigurieren eines Threadpools.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausgeführt werden, nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```
__interface
    __declspec(uuid("B1F64757-6E88-4fa2-8886-7848B0D7E660")) IThreadPoolConfig : public IUnknown
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[GetSize](#getsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool zu erhalten.|  
|[GetTimeout](#gettimeout)|Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool, bis ein Thread warten soll beendet.|  
|[SetSize](#setsize)|Rufen Sie diese Methode, um die Anzahl der Threads im Pool festgelegt.|  
|[SetTimeout](#settimeout)|Rufen Sie diese Methode, um die maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet.|  
  
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
 [!code-cpp[NVC_ATL_Utilities&#134;](../../atl/codesnippet/cpp/ithreadpoolconfig-interface_1.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden abzurufen, die der Threadpool, bis ein Thread warten soll beendet.  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>Parameter  
 `pdwMaxWait`  
 [out] Die Adresse der Variablen, die bei Erfolg die maximale Zeit in Millisekunden, die der Threadpool warten soll, bis ein Thread erhält beendet.  
  
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
  
 Wenn `nNumThreads` ist negativ, der Absolute Wert multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
 Wenn `nNumThreads` NULL ist, [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571) multipliziert die Anzahl der Prozessoren auf dem Computer, um die Gesamtzahl der Threads abzurufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 Rufen Sie diese Methode, um die maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet.  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>Parameter  
 `dwMaxWait`  
 Die angeforderte maximale Zeit in Millisekunden, die der Threadpool, bis ein Thread warten soll beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg S_OK oder einen HRESULT-Fehler bei einem Fehler zurück.  
  
### <a name="example"></a>Beispiel  
 Finden Sie unter [IThreadPoolConfig::GetSize](#getsize).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)   
 [CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)

