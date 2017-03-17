---
title: Klasse CNoWorkerThread | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4c38d778849a31d55a657fc1022c2e9f4a370eec
ms.lasthandoff: 02/24/2017

---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread-Klasse
Verwenden Sie diese Klasse als Argument für die `MonitorClass` Vorlagenparameter Cacheklassen, wenn Sie dynamische Cache Wartung deaktivieren möchten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|Nicht funktionsfähige Entsprechung von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|  
|[CNoWorkerThread::AddTimer](#addtimer)|Nicht funktionsfähige Entsprechung von [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|Nicht funktionsfähige Entsprechung von [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|Nicht funktionsfähige Entsprechung von [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|  
|[CNoWorkerThread::Initialize](#initialize)|Nicht funktionsfähige Entsprechung von [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|Nicht funktionsfähige Entsprechung von [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).|  
|[CNoWorkerThread::Shutdown](#shutdown)|Nicht funktionsfähige Entsprechung von [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet die gleiche öffentliche Schnittstelle wie [CWorkerThread](../../atl/reference/cworkerthread-class.md). Diese Schnittstelle wird erwartet, dass die von bereitgestellt werden die `MonitorClass` Vorlagenparameter Cacheklassen.  
  
 Die Methoden in dieser Klasse werden implementiert, um den Vorgang. Die Methoden, die ein HRESULT, stets zurückgeben S_OK zurück, und die Methoden, eine HANDLE oder Thread-ID immer 0 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="addhandle"></a>CNoWorkerThread::AddHandle  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).  
  
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
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="addtimer"></a>CNoWorkerThread::AddTimer  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).  
  
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
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="getthreadhandle"></a>CNoWorkerThread::GetThreadHandle  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="getthreadid"></a>CNoWorkerThread::GetThreadId  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="initialize"></a>CNoWorkerThread::Initialize  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize).  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="removehandle"></a>CNoWorkerThread::RemoveHandle  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle).  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.  
  
##  <a name="shutdown"></a>CNoWorkerThread::Shutdown  
 Nicht funktionsfähige Entsprechung von [CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown).  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer S_OK zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Implementierung von dieser Klasse bereitgestellten wird keine Aktion ausgeführt.

