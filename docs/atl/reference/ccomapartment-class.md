---
title: CComApartment Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3fecd77e93c0c51a37d7363e6ec1472d157d6d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomapartment-class"></a>CComApartment-Klasse
Diese Klasse bietet Unterstützung für die Verwaltung einer Appartementnummer in einem Thread Pool EXE-Modul.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComApartment
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComApartment::CComApartment](#ccomapartment)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComApartment::Apartment](#apartment)|Markiert die Startadresse des Threads an.|  
|[CComApartment::GetLockCount](#getlockcount)|Gibt die aktuellen Sperren Threadanzahl zurück.|  
|[CComApartment::Lock](#lock)|Inkrementiert die Anzahl dem Thread-Sperre.|  
|[CComApartment::Unlock](#unlock)|Verringert die Sperrenanzahl des Threads.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Enthält die Thread-ID.|  
|[CComApartment::m_hThread](#m_hthread)|Enthält das Handle des Threads.|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Enthält die aktuellen Sperren Threadanzahl.|  
  
## <a name="remarks"></a>Hinweise  
 `CComApartment`Dient der [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) einem Apartment in einem Thread Pool EXE-Modul zu verwalten. `CComApartment`bietet Methoden zum Inkrementieren und Dekrementieren die Sperre für einen Thread zu zählen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="apartment"></a>CComApartment::Apartment  
 Markiert die Startadresse des Threads an.  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer 0.  
  
### <a name="remarks"></a>Hinweise  
 Automatisch festgelegt, während der [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).  
  
##  <a name="ccomapartment"></a>CComApartment::CComApartment  
 Der Konstruktor.  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComApartment` Datenmember [M_nLockCnt](#m_nlockcnt) und [M_hThread](#m_hthread).  
  
##  <a name="getlockcount"></a>CComApartment::GetLockCount  
 Gibt die aktuellen Sperren Threadanzahl zurück.  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Sperrenanzahl für den Thread.  
  
##  <a name="lock"></a>CComApartment::Lock  
 Inkrementiert die Anzahl dem Thread-Sperre.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Wird aufgerufen, indem [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Die Anzahl der Sperren für den Thread wird für statistische Zwecke verwendet.  
  
##  <a name="m_dwthreadid"></a>CComApartment::m_dwThreadID  
 Enthält die Thread-ID.  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="m_hthread"></a>CComApartment::m_hThread  
 Enthält das Handle des Threads.  
  
```
HANDLE m_hThread;
```  
  
##  <a name="m_nlockcnt"></a>CComApartment::m_nLockCnt  
 Enthält die aktuellen Sperren Threadanzahl.  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="unlock"></a>CComApartment::Unlock  
 Verringert die Sperrenanzahl des Threads.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Wird aufgerufen, indem [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Die Anzahl der Sperren für den Thread wird für statistische Zwecke verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
