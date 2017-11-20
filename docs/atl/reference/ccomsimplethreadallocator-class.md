---
title: CComSimpleThreadAllocator Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs: C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 150abb28f84d31e1ef6785f9109844529f10276d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
 `CComSimpleThreadAllocator`verwaltet die Auswahl der Thread [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`einfach durchläuft jeden Thread, und gibt den nächsten in der Sequenz zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Wählt einen Thread durch Angabe des nächsten Threads in der Sequenz.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Parameter  
 `pApt`  
 In der Standardimplementierung von ATL verwendet nicht.  
  
 `nThreads`  
 Die maximale Anzahl von Threads in der EXE-Modul.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl zwischen 0 (null) und ( `nThreads` - 1). Identifiziert einen Threads in der EXE-Modul.  
  
### <a name="remarks"></a>Hinweise  
 Sie überschreiben können `GetThread` , geben Sie eine andere Methode der Auswahl sowie zum vornehmen von verwenden die `pApt` Parameter.  
  
 `GetThread`wird aufgerufen, indem [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>Siehe auch  
 [CComApartment-Klasse](../../atl/reference/ccomapartment-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
