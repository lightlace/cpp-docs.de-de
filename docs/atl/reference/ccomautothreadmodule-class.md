---
title: CComAutoThreadModule-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
ms.openlocfilehash: 805227144887b29d85b1948f62060ffe9eb2d0e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50435687"
---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule-Klasse

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class ThreadAllocator = CComSimpleThreadAllocator>
class CComAutoThreadModule : public CComModule
```

#### <a name="parameters"></a>Parameter

*ThreadAllocator*<br/>
[in] Die Verwaltung von threadauswahl-Klasse. Der Standardwert ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CreateInstance](#createinstance)|Wählt einen Thread aus, und erstellt dann ein Objekt im zugeordneten Apartment.|
|[GetDefaultThreads](#getdefaultthreads)|(Statisch) Dynamisch berechnet die Anzahl der Threads für das Modul, das basierend auf der Anzahl der Prozessoren ein.|
|[Init](#init)|Erstellt das Modul des Threads.|
|[Sperre](#lock)|Erhöht die Sperrenanzahl des Moduls und für den aktuellen Thread.|
|[Entsperren](#unlock)|Verringert die Sperrenanzahl des Moduls und für den aktuellen Thread.|

### <a name="data-members"></a>Datenmember

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[dwThreadID](#dwthreadid)|Enthält den Bezeichner des aktuellen Threads.|
|[m_Allocator](#m_allocator)|Verwaltet die threadauswahl.|
|[m_nThreads](#m_nthreads)|Enthält die Anzahl der Threads im Modul an.|
|[m_pApartments](#m_papartments)|Verwaltet die Modul Apartments an.|

## <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Klasse ist veraltet, ersetzt, durch die [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) und [CAtlModule](../../atl/reference/catlmodule-class.md) abgeleiteten Klassen. Die folgenden Informationen wird für die Verwendung mit älteren Versionen von ATL

`CComAutoThreadModule` leitet sich von [CComModule](../../atl/reference/ccommodule-class.md) einen Thread Pooling, Apartment-Modell COM-Server für EXE-Dateien und Windows-Dienste zu implementieren. `CComAutoThreadModule` verwendet [CComApartment](../../atl/reference/ccomapartment-class.md) eine Wohnung für jeden Thread im Modul zu verwalten.

Ableiten des Moduls aus `CComAutoThreadModule` beim Erstellen von Objekten in mehreren Apartments werden sollen. Sie müssen auch einschließen der [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) Makro in Definition der Klasse des Objekts an [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) als die Klassenfactory.

Standardmäßig wird der ATL-COM-AppWizard (ATL-Projekt-Assistent in Visual Studio .NET) des Moduls aus abgeleitet `CComModule`. Verwendung von `CComAutoThreadModule`, ändern Sie die Definition der Klasse. Zum Beispiel:

[!code-cpp[NVC_ATL_AxHost#2](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`IAtlAutoThreadModule`

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

[CComModule](../../atl/reference/ccommodule-class.md)

`CComAutoThreadModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="createinstance"></a>  CComAutoThreadModule::CreateInstance

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```

### <a name="parameters"></a>Parameter

*pfnCreateInstance*<br/>
[in] Ein Zeiger auf eine Creator-Funktion.

*riid*<br/>
[in] Die IID der angeforderten Schnittstelle.

*ppvObj*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *PpvObj* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wählt einen Thread aus, und erstellt dann ein Objekt im zugeordneten Apartment.

##  <a name="dwthreadid"></a>  CComAutoThreadModule::dwThreadID

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
DWORD dwThreadID;
```

### <a name="remarks"></a>Hinweise

Enthält den Bezeichner des aktuellen Threads.

##  <a name="getdefaultthreads"></a>  CComAutoThreadModule::GetDefaultThreads

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
static int GetDefaultThreads();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Threads im Modul exe-Datei erstellt werden.

### <a name="remarks"></a>Hinweise

Diese statischen Funktion berechnet dynamisch die maximale Anzahl von Threads für die EXE-Modul, das basierend auf der Anzahl der Prozessoren. Dieser Rückgabewert wird standardmäßig zum Übergeben der [Init](#init) Methode, um Threads zu erstellen.

##  <a name="init"></a>  CComAutoThreadModule::Init

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Ein Zeiger auf ein Array von Objekt-Zuordnungseinträge.

*h*<br/>
[in] Das HINSTANCE, die an `DLLMain` oder `WinMain`.

*plibid*<br/>
[in] Ein Zeiger auf die LIBID der Typbibliothek, die dem Projekt zugeordnet.

*nThreads*<br/>
[in] Die Anzahl der Threads erstellt werden. In der Standardeinstellung *nThreads* ist der Rückgabewert von [GetDefaultThreads](#getdefaultthreads).

### <a name="remarks"></a>Hinweise

Datenmember initialisiert und erstellt die Anzahl der Threads, die anhand des *nThreads*.

##  <a name="lock"></a>  CComAutoThreadModule::Lock

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
LONG Lock();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

### <a name="remarks"></a>Hinweise

Führt eine atomische Inkrementoperation die Sperrenanzahl für das Modul und für den aktuellen Thread. `CComAutoThreadModule` verwendet die Sperrenanzahl des Moduls um zu bestimmen, ob alle Clients auf das Modul zugreifen. Die Anzahl der Sperren für den aktuellen Thread wird für statistische Zwecke verwendet.

##  <a name="m_allocator"></a>  CComAutoThreadModule::m_Allocator

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
ThreadAllocator  m_Allocator;
```

### <a name="remarks"></a>Hinweise

Das Objekt, das Verwalten von threadauswahl. In der Standardeinstellung die `ThreadAllocator` Klassenvorlagenparameter ist [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).

##  <a name="m_nthreads"></a>  CComAutoThreadModule::m_nThreads

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
int m_nThreads;
```

### <a name="remarks"></a>Hinweise

Enthält die Anzahl der Threads in der EXE-Modul. Wenn [Init](#init) aufgerufen wird, `m_nThreads` nastaven NA hodnotu der *nThreads* Parameterwert. Zugeordnete Apartment des Threads wird von verwaltet eine [CComApartment](../../atl/reference/ccomapartment-class.md) Objekt.

##  <a name="m_papartments"></a>  CComAutoThreadModule::m_pApartments

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
CComApartment* m_pApartments;
```

### <a name="remarks"></a>Hinweise

Verweist auf ein Array von [CComApartment](../../atl/reference/ccomapartment-class.md) Objekte, von denen jede eine Wohnung im Modul verwaltet. Die Anzahl der Elemente im Array basiert auf der [M_nThreads](#m_nthreads) Member.

##  <a name="unlock"></a>  CComAutoThreadModule::Unlock

Zum Zeitpunkt der ATL 7.0 `CComAutoThreadModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
LONG Unlock();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der möglicherweise bei der Diagnose hilfreich oder testen.

### <a name="remarks"></a>Hinweise

Führt eine atomische Dekrementoperation die Sperrenanzahl für das Modul und für den aktuellen Thread. `CComAutoThreadModule` verwendet die Sperrenanzahl des Moduls um zu bestimmen, ob alle Clients auf das Modul zugreifen. Die Anzahl der Sperren für den aktuellen Thread wird für statistische Zwecke verwendet.

Wenn die Sperrenanzahl des Moduls auf 0 (null) erreicht, kann das Modul entladen werden.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Modulklassen](../../atl/atl-module-classes.md)
