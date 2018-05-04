---
title: CNoWorkerThread Klasse | Microsoft Docs
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
ms.openlocfilehash: 85e1962d10f274f4f8c35ba27cb05c41e8bf19cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread-Klasse
Verwenden Sie diese Klasse als Argument für die `MonitorClass` Vorlagenparameter Cacheklassen, wenn Sie dynamische Cache Wartung deaktivieren möchten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|Nicht-funktionelles Äquivalent von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|  
|[CNoWorkerThread::AddTimer](#addtimer)|Nicht-funktionelles Äquivalent von [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Nicht-funktionelles Äquivalent von [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|Nicht-funktionelles Äquivalent von [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|  
|[CNoWorkerThread::Initialize](#initialize)|Nicht-funktionelles Äquivalent von [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|Nicht-funktionelles Äquivalent von [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|  
|[CNoWorkerThread::Shutdown](#shutdown)|Nicht-funktionelles Äquivalent von [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet die gleiche öffentliche Schnittstelle wie [CWorkerThread](../../atl/reference/cworkerthread-class.md). Diese Schnittstelle wird erwartet, bereitgestellt werden, indem die `MonitorClass` Vorlagenparameter Cacheklassen.  
  
 Die Methoden in dieser Klasse werden implementiert, um keine weiteren Aktionen erforderlich. Geben Sie die Methoden, die ein HRESULT zurück, die immer S_OK zurück, und die Methoden, mit denen eine HANDLE oder Thread-ID immer 0 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle  
 Nicht-funktionelles Äquivalent von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer  
 Nicht-funktionelles Äquivalent von [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).  
  
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
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle  
 Nicht-funktionelles Äquivalent von [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId  
 Nicht-funktionelles Äquivalent von [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="initialize"></a>  CNoWorkerThread::Initialize  
 Nicht-funktionelles Äquivalent von [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle  
 Nicht-funktionelles Äquivalent von [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown  
 Nicht-funktionelles Äquivalent von [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung, die von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.
