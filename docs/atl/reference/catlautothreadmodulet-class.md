---
title: CAtlAutoThreadModuleT Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a012494365745d40d98c0f65ee9eff6b5e9502da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="catlautothreadmodulet-class"></a>CAtlAutoThreadModuleT-Klasse
Diese Klasse stellt Methoden zum Implementieren eines COM‑Servers in einem Thread-Pool, Apartmentmodell bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, 
         class ThreadAllocator = CComSimpleThreadAllocator,
         DWORD dwWait = INFINITE>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT : public IAtlAutoThreadModule
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse, die COM-Server implementiert werden.  
  
 `ThreadAllocator`  
 Die Verwaltung von Threads Auswahl-Klasse. Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Gibt das Timeoutintervall in Millisekunden an. Der Standardwert ist UNBEGRENZT, womit Timeoutintervall der Methode nie ablaufen.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](#getdefaultthreads)|Diese statische Funktion dynamisch berechnet und gibt die maximale Anzahl von Threads für die EXE-Modul, basierend auf der Anzahl der Prozessoren.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse [CComModule](../../atl/reference/catlautothreadmodule-class.md) leitet sich von `CAtlAutoThreadModuleT` um einen Thread Pool, Apartmentmodell COM-Server zu implementieren. Er ersetzt die veraltete Klasse [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
> [!NOTE]
>  Diese Klasse sollte nicht in einer DLL verwendet werden, als Standard `dwWait` Wert INFINITE wird einen Deadlock verursachen, wenn die DLL entladen wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="getdefaultthreads"></a>  CAtlAutoThreadModuleT::GetDefaultThreads  
 Diese statische Funktion dynamisch berechnet und gibt die maximale Anzahl von Threads für die EXE-Modul, basierend auf der Anzahl der Prozessoren.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Threads an, die im Modul exe-Datei erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie eine andere Methode für die Berechnung der Anzahl der Threads verwenden möchten. Standardmäßig basiert die Anzahl der Threads auf die Anzahl der Prozessoren.  
  
## <a name="see-also"></a>Siehe auch  
 [IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule-Klasse](../../atl/reference/iatlautothreadmodule-class.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
