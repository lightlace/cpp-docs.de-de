---
title: CComAutoThreadModule Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
- ATLBASE/ATL::CComAutoThreadModule
- ATLBASE/ATL::CreateInstance
- ATLBASE/ATL::GetDefaultThreads
- ATLBASE/ATL::Init
- ATLBASE/ATL::Lock
- ATLBASE/ATL::Unlock
- ATLBASE/ATL::dwThreadID
- ATLBASE/ATL::m_Allocator
- ATLBASE/ATL::m_nThreads
- ATLBASE/ATL::m_pApartments
dev_langs:
- C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 094d10069b854d122e835f7d12f9ef095775db2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule-Klasse
Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>Parameter  
 `ThreadAllocator`  
 [in] Die Verwaltung von Threads Auswahl-Klasse. Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|Wählt einen Thread, und klicken Sie dann im zugehörigen Apartment erstellt ein Objekt.|  
|[GetDefaultThreads](#getdefaultthreads)|(Statisch) Dynamisch berechnet die Anzahl der Threads für das Modul basierend auf der Anzahl der Prozessoren ein.|  
|[Init](#init)|Erstellt das Modul Threads.|  
|[Sperre](#lock)|Erhöht die Anzahl der Sperren für das Modul und für den aktuellen Thread.|  
|[Entsperren](#unlock)|Verringert die Sperrenanzahl für das Modul und für den aktuellen Thread.|  
  
### <a name="data-members"></a>Datenmember  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|Enthält den Bezeichner des aktuellen Threads.|  
|[m_Allocator](#m_allocator)|Verwaltet die Thread-Auswahl.|  
|[m_nThreads](#m_nthreads)|Enthält die Anzahl der Threads im Modul an.|  
|[m_pApartments](#m_papartments)|Verwaltet das Modul Apartments an.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Klasse ist veraltet, ersetzt, durch die [CComModule](../../atl/reference/catlautothreadmodule-class.md) und [von CAtlModule](../../atl/reference/catlmodule-class.md) abgeleitete Klassen. Die folgenden Informationen wird für die Verwendung mit älteren Versionen von ATL  
  
 `CComAutoThreadModule`leitet sich von [CComModule](../../atl/reference/ccommodule-class.md) einen Thread Pool, Apartmentmodell COM-Server für die EXE-Dateien und Windows-Dienste implementiert. `CComAutoThreadModule`verwendet [CComApartment](../../atl/reference/ccomapartment-class.md) einem Apartment für jeden Thread im Modul zu verwalten.  
  
 Leiten Sie das Modul aus `CComAutoThreadModule` beim Erstellen von Objekten in mehreren Apartments werden sollen. Sie umfasst auch die [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Makro in die Objektklassendefinition an [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als ClassFactory.  
  
 Standardmäßig wird der ATL-COM-AppWizard (ATL-Projekt-Assistenten in Visual Studio .NET) leiten Sie das Modul aus `CComModule`. Mit `CComAutoThreadModule`, ändern Sie die Definition der Klasse. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [Von CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Parameter  
 *pfnCreateInstance*  
 [in] Ein Zeiger auf eine erstellerfunktion.  
  
 `riid`  
 [in] Die IID der angeforderten Schnittstelle.  
  
 `ppvObj`  
 [out] Ein Zeiger auf den Schnittstellenzeiger, der durch `riid`. Wenn das Objekt nicht über diese Schnittstelle unterstützt `ppvObj` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wählt einen Thread, und klicken Sie dann im zugehörigen Apartment erstellt ein Objekt.  
  
##  <a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>Hinweise  
 Enthält den Bezeichner des aktuellen Threads.  
  
##  <a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Threads an, die im Modul exe-Datei erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese statische Funktion berechnet dynamisch die maximale Anzahl von Threads für die EXE-Modul, basierend auf der Anzahl der Prozessoren. Dieser Rückgabewert wird standardmäßig zum Übergeben der [Init](#init) Methode, um Threads zu erstellen.  
  
##  <a name="init"></a>CComAutoThreadModule::Init  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Ein Zeiger auf ein Array von Objekt-Zuordnungseinträge.  
  
 `h`  
 [in] Die `HINSTANCE` übergeben **DLLMain** oder `WinMain`.  
  
 `plibid`  
 [in] Ein Zeiger auf die LIBID der Typbibliothek, die dem Projekt zugeordnet.  
  
 `nThreads`  
 [in] Die Anzahl der Threads an, die erstellt werden. Standardmäßig `nThreads` ist der zurückgegebene Wert [GetDefaultThreads](#getdefaultthreads).  
  
### <a name="remarks"></a>Hinweise  
 Datenmember initialisiert und erstellt die Anzahl der Threads, die vom angegebenen `nThreads`.  
  
##  <a name="lock"></a>CComAutoThreadModule::Lock  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Führt atomic erhöht die Anzahl der Sperren für das Modul und für den aktuellen Thread. `CComAutoThreadModule`verwendet die Anzahl der Module Sperre um zu bestimmen, ob alle Clients auf das Modul zugreifen. Die Anzahl der Sperren für den aktuellen Thread wird für statistische Zwecke verwendet.  
  
##  <a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>Hinweise  
 Das Objekt, das Verwalten von Threads Auswahl. Wird standardmäßig die `ThreadAllocator` Klassenvorlagenparameter ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
##  <a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>Hinweise  
 Enthält die Anzahl der Threads im Modul exe-Datei an. Wenn [Init](#init) aufgerufen wird, `m_nThreads` festgelegt ist, um die `nThreads` Parameterwert. Zugeordnete Apartment des Threads wird von verwaltet eine [CComApartment](../../atl/reference/ccomapartment-class.md) Objekt.  
  
##  <a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>Hinweise  
 Verweist auf ein Array von [CComApartment](../../atl/reference/ccomapartment-class.md) Objekte, von denen jeder einem Apartment im Modul verwaltet. Die Anzahl der Elemente im Array basiert auf der [M_nThreads](#m_nthreads) Member.  
  
##  <a name="unlock"></a>CComAutoThreadModule::Unlock  
 Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Führt einen atomarischen Dekrement auf die Anzahl der Sperren für das Modul und für den aktuellen Thread. `CComAutoThreadModule`verwendet die Anzahl der Module Sperre um zu bestimmen, ob alle Clients auf das Modul zugreifen. Die Anzahl der Sperren für den aktuellen Thread wird für statistische Zwecke verwendet.  
  
 Wenn die Anzahl der Sperren Modul 0 (null) erreicht, kann das Modul entladen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)
