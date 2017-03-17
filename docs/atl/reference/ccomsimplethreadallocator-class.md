---
title: Klasse CComSimpleThreadAllocator | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 377e7f2fa6d8377d46e98b52e9c8f075b10956a8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator-Klasse
Diese Klasse verwaltet die Thread-Auswahl für die Klasse `CComAutoThreadModule`.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|Wählt einen Thread.|  
  
## <a name="remarks"></a>Hinweise  
 `CComSimpleThreadAllocator`verwaltet die Thread-Auswahl für [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`einfach durch jeden Thread und gibt das nächste in der Sequenz zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Wählt einen Thread durch Angabe des nächsten Threads in der Sequenz.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Parameter  
 `pApt`  
 In ATL Standard-Implementierung verwendet nicht.  
  
 `nThreads`  
 Die maximale Anzahl von Threads in der EXE-Modul.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl zwischen 0 (null) und ( `nThreads` – 1). Identifiziert einen der Threads in der EXE-Modul.  
  
### <a name="remarks"></a>Hinweise  
 Sie überschreiben können `GetThread` eine andere Methode der Auswahl oder stellen verwenden die `pApt` Parameter.  
  
 `GetThread`wird aufgerufen, indem [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>Siehe auch  
 [CComApartment-Klasse](../../atl/reference/ccomapartment-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

