---
title: Klasse CAtlAutoThreadModuleT | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT
- ATLBASE/ATL::CAtlAutoThreadModuleT::GetDefaultThreads
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModuleT class
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 86b35f0a6a3ab43c170ee710838ec9ba0e2fc5b0
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT-Klasse
Diese Klasse stellt Methoden zum Implementieren eines COM‑Servers in einem Thread-Pool, Apartment-Modell.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse, die die COM-Server implementiert werden.  
  
 `ThreadAllocator`  
 Die Verwaltung von Thread-Auswahl-Klasse. Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Gibt das Timeoutintervall in Millisekunden. Der Standardwert ist UNENDLICH, d.h. Timeoutintervall für die Methode nie ablaufen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Die statische Funktion dynamisch berechnet und gibt die maximale Anzahl von Threads für die EXE-Modul, basierend auf der Anzahl der Prozessoren.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse [CComModule](../../atl/reference/catlautothreadmodule-class.md) abgeleitet `CAtlAutoThreadModuleT` um ein COM-Server in einem Thread-Pool, Apartment-Modell zu implementieren. Ersetzt die veraltete Klasse [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Diese Klasse sollte nicht in einer DLL verwendet werden, als Standardwert `dwWait` Wert INFINITE bewirkt einen Deadlock, wenn die DLL entladen wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>CAtlAutoThreadModuleT::GetDefaultThreads  
 Die statische Funktion dynamisch berechnet und gibt die maximale Anzahl von Threads für die EXE-Modul, basierend auf der Anzahl der Prozessoren.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Threads im Modul exe-Datei erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie eine andere Methode verwenden, für die Anzahl von Threads berechnen möchten. Standardmäßig basiert die Anzahl der Threads auf die Anzahl der Prozessoren.  
  
## <a name="see-also"></a>Siehe auch  
 [IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
 [Modulklassen](../../atl/atl-module-classes.md)

