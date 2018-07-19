---
title: CNoWorkerThread-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16eafd8c33bf1c9a42b95c31a333ff1df55b3495
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962503"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread-Klasse
Verwenden Sie diese Klasse als Argument für die `MonitorClass` Vorlagenparameter für Cacheklassen, wenn Sie dynamische Cache Wartung deaktivieren möchten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|Nicht funktionsbezogene Äquivalent [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|  
|[CNoWorkerThread::AddTimer](#addtimer)|Nicht funktionsbezogene Äquivalent [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Nicht funktionsbezogene Äquivalent [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|Nicht funktionsbezogene Äquivalent [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|  
|[CNoWorkerThread::Initialize](#initialize)|Nicht funktionsbezogene Äquivalent [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|Nicht funktionsbezogene Äquivalent [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|  
|[CNoWorkerThread::Shutdown](#shutdown)|Nicht funktionsbezogene Äquivalent [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt die gleiche öffentliche Schnittstelle wie [CWorkerThread](../../atl/reference/cworkerthread-class.md). Diese Schnittstelle wird vom bereitzustellenden erwartet die `MonitorClass` Vorlagenparameter für Cacheklassen.  
  
 Die Methoden in dieser Klasse werden implementiert, um den Vorgang. Gibt S_OK zurück, die Methoden, die ein HRESULT immer zurückgeben, und die Methoden, die eine HANDLE oder Thread-ID, immer zurückgeben 0 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlutil.h"  
  
##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.  
  
##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).  
  
```
HRESULT AddTimer(DWORD /* dwInterval
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */,
    HANDLE* /* phTimer
 */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.  
  
##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.  
  
##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.  
  
##  <a name="initialize"></a>  CNoWorkerThread::Initialize  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.  
  
##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.  
  
##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown  
 Nicht funktionsbezogene Äquivalent [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer gibt S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten hat keine Auswirkungen.
