---
title: Klasse CComApartment | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComApartment
- CComApartment
- ATL.CComApartment
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 9359e2ab8c4a84ab66441e3eb8cfd39520fd4e8d
ms.lasthandoff: 02/24/2017

---
# <a name="ccomapartment-class"></a>CComApartment-Klasse
Diese Klasse bietet Unterstützung für die Verwaltung einer Appartementnummer in einem Thread Pool EXE-Modul.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComApartment
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComApartment::CComApartment](#ccomapartment)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComApartment::Apartment](#apartment)|Markiert die Startadresse des Threads.|  
|[CComApartment::GetLockCount](#getlockcount)|Gibt die aktuellen Sperren Threadanzahl zurück.|  
|[CComApartment::Lock](#lock)|Erhöht die Anzahl der Sperren des Threads.|  
|[CComApartment::Unlock](#unlock)|Verringert die Sperrenanzahl des Threads.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Der Thread-ID enthält.|  
|[CComApartment::m_hThread](#m_hthread)|Enthält das Handle des Threads.|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Enthält die aktuellen Sperren Threadanzahl.|  
  
## <a name="remarks"></a>Hinweise  
 `CComApartment`werden [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) ein Apartment in einem Thread Pool EXE-Modul zu verwalten. `CComApartment`Stellt Methoden zum Inkrementieren und Dekrementieren die Sperre für einen Thread zählen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameapartmenta--ccomapartmentapartment"></a><a name="apartment"></a>CComApartment::Apartment  
 Markiert die Startadresse des Threads.  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer 0.  
  
### <a name="remarks"></a>Hinweise  
 Automatisch festgelegt, während der [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).  
  
##  <a name="a-nameccomapartmenta--ccomapartmentccomapartment"></a><a name="ccomapartment"></a>CComApartment::CComApartment  
 Der Konstruktor.  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>Hinweise  
 Initialisiert die `CComApartment` Datenmember [M_nLockCnt](#m_nlockcnt) und [M_hThread](#m_hthread).  
  
##  <a name="a-namegetlockcounta--ccomapartmentgetlockcount"></a><a name="getlockcount"></a>CComApartment::GetLockCount  
 Gibt die aktuellen Sperren Threadanzahl zurück.  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Sperren für den Thread.  
  
##  <a name="a-namelocka--ccomapartmentlock"></a><a name="lock"></a>CComApartment::Lock  
 Erhöht die Anzahl der Sperren des Threads.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Aufgerufen von [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Die Anzahl der Sperren für den Thread wird für statistische Zwecke verwendet.  
  
##  <a name="a-namemdwthreadida--ccomapartmentmdwthreadid"></a><a name="m_dwthreadid"></a>CComApartment::m_dwThreadID  
 Der Thread-ID enthält.  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="a-namemhthreada--ccomapartmentmhthread"></a><a name="m_hthread"></a>CComApartment::m_hThread  
 Enthält das Handle des Threads.  
  
```
HANDLE m_hThread;
```  
  
##  <a name="a-namemnlockcnta--ccomapartmentmnlockcnt"></a><a name="m_nlockcnt"></a>CComApartment::m_nLockCnt  
 Enthält die aktuellen Sperren Threadanzahl.  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="a-nameunlocka--ccomapartmentunlock"></a><a name="unlock"></a>CComApartment::Unlock  
 Verringert die Sperrenanzahl des Threads.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Aufgerufen von [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Die Anzahl der Sperren für den Thread wird für statistische Zwecke verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

