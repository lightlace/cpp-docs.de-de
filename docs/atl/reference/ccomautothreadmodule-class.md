---
title: Der CComAutoThreadModule-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 07aaf6dc7029452fa6822c5f5f1ae09b724ddc8b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautothreadmodule-class"></a>Der CComAutoThreadModule-Klasse
Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>Parameter  
 `ThreadAllocator`  
 [in] Die Verwaltung von Thread-Auswahl-Klasse. Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|Wählt einen Thread, und klicken Sie dann im zugehörigen Apartment erstellt ein Objekt.|  
|[GetDefaultThreads](#getdefaultthreads)|(Statisch) Dynamisch berechnet die Anzahl der Threads für das Modul basierend auf der Anzahl der Prozessoren.|  
|[Init](#init)|Erstellt das Modul Threads.|  
|[Sperren](#lock)|Erhöht die Anzahl der Sperren für das Modul und für den aktuellen Thread.|  
|[Entsperren](#unlock)|Verringert die Sperrenanzahl für das Modul und für den aktuellen Thread.|  
  
### <a name="data-members"></a>Datenmember  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|Enthält den Bezeichner des aktuellen Threads.|  
|[m_Allocator](#m_allocator)|Verwaltet die Thread-Auswahl.|  
|[m_nThreads](#m_nthreads)|Enthält die Anzahl der Threads im Modul.|  
|[m_pApartments](#m_papartments)|Verwaltet das Modul Apartments.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Klasse ist veraltet, ersetzt, durch die [CComModule](../../atl/reference/catlautothreadmodule-class.md) und [von CAtlModule](../../atl/reference/catlmodule-class.md) abgeleiteten Klassen. Die folgenden Informationen werden für die Verwendung mit älteren Versionen von ATL  
  
 `CComAutoThreadModule`leitet sich von [CComModule](../../atl/reference/ccommodule-class.md) einen Thread Pool, Apartmentmodell COM-Server für die EXE-Dateien und Windows-Dienste zu implementieren. `CComAutoThreadModule`verwendet [CComApartment](../../atl/reference/ccomapartment-class.md) ein Apartment für jeden Thread im Modul zu verwalten.  
  
 Leiten Sie das Modul aus `CComAutoThreadModule` Wenn Sie Objekte in mehreren Apartments erstellen möchten. Sie umfasst auch die [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) Makro in die Klassendefinition für das Objekt an [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als ClassFactory.  
  
 Standardmäßig werden die ATL-COM-AppWizard (ATL-Projekt-Assistent in Visual Studio .NET) abgeleitet, das Modul aus `CComModule`. Mit `CComAutoThreadModule`, ändern Sie die Klassendefinition. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_AxHost&#2;](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
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
  
##  <a name="a-namecreateinstancea--ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Parameter  
 *pfnCreateInstance*  
 [in] Ein Zeiger auf eine Creator-Funktion.  
  
 `riid`  
 [in] Die IID der angeforderten Schnittstelle.  
  
 `ppvObj`  
 [out] Ein Zeiger auf den Schnittstellenzeiger vom `riid`. Wenn das Objekt diese Schnittstelle nicht unterstützt `ppvObj` auf NULL festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Wählt einen Thread, und klicken Sie dann im zugehörigen Apartment erstellt ein Objekt.  
  
##  <a name="a-namedwthreadida--ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>Hinweise  
 Enthält den Bezeichner des aktuellen Threads.  
  
##  <a name="a-namegetdefaultthreadsa--ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Threads im Modul exe-Datei erstellt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die statische Funktion berechnet dynamisch die maximale Anzahl von Threads für die EXE-Modul, basierend auf der Anzahl der Prozessoren. Standardmäßig wird dieser Rückgabewert an übergeben der [Init](#init) Methode, um die Threads zu erstellen.  
  
##  <a name="a-nameinita--ccomautothreadmoduleinit"></a><a name="init"></a>CComAutoThreadModule::Init  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 [in] Ein Zeiger auf ein Array von Objekt-Zuordnungseinträgen.  
  
 `h`  
 [in] Die `HINSTANCE` übergebenen **DLLMain** oder `WinMain`.  
  
 `plibid`  
 [in] Ein Zeiger auf die LIBID der Typbibliothek, die dem Projekt zugeordnet.  
  
 `nThreads`  
 [in] Die Anzahl der Threads erstellt werden. In der Standardeinstellung `nThreads` ist der zurückgegebene Wert [GetDefaultThreads](#getdefaultthreads).  
  
### <a name="remarks"></a>Hinweise  
 Datenmember initialisiert, und die Anzahl der Threads, die durch angegebene erstellt `nThreads`.  
  
##  <a name="a-namelocka--ccomautothreadmodulelock"></a><a name="lock"></a>CComAutoThreadModule::Lock  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Führt einen atomaren Inkrement auf die Anzahl der Sperren für das Modul und für den aktuellen Thread. `CComAutoThreadModule`verwendet die Sperrenanzahl des Moduls um zu bestimmen, ob alle Clients des Moduls zugreifen. Die Anzahl der Sperren für den aktuellen Thread wird für statistische Zwecke verwendet.  
  
##  <a name="a-namemallocatora--ccomautothreadmodulemallocator"></a><a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>Hinweise  
 Das Objekt, das Verwalten von Thread-Auswahl. In der Standardeinstellung die `ThreadAllocator` Klassenvorlagenparameter ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
##  <a name="a-namemnthreadsa--ccomautothreadmodulemnthreads"></a><a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>Hinweise  
 Enthält die Anzahl der Threads im EXE-Modul. Wenn [Init](#init) aufgerufen wird, `m_nThreads` wird festgelegt, um die `nThreads` Parameterwert. Zugeordnete Apartment des Threads erfolgt durch eine [CComApartment](../../atl/reference/ccomapartment-class.md) Objekt.  
  
##  <a name="a-namempapartmentsa--ccomautothreadmodulempapartments"></a><a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>Hinweise  
 Verweist auf ein Array von [CComApartment](../../atl/reference/ccomapartment-class.md) Objekte, von denen jedes ein Apartment im Modul verwaltet. Die Anzahl der Elemente im Array basiert auf der [M_nThreads](#m_nthreads) Element.  
  
##  <a name="a-nameunlocka--ccomautothreadmoduleunlock"></a><a name="unlock"></a>CComAutoThreadModule::Unlock  
 Zum Zeitpunkt der Erstellung ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für weitere Details.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der möglicherweise hilfreich für die Diagnose oder testen.  
  
### <a name="remarks"></a>Hinweise  
 Führt eine atomare verringern die Anzahl der Sperren für das Modul und für den aktuellen Thread. `CComAutoThreadModule`verwendet die Sperrenanzahl des Moduls um zu bestimmen, ob alle Clients des Moduls zugreifen. Die Anzahl der Sperren für den aktuellen Thread wird für statistische Zwecke verwendet.  
  
 Wenn die Anzahl der Sperren Modul&0; (null) erreicht, kann das Modul entladen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)

