---
title: Module-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module
- module/Microsoft::WRL::Module::Create
- module/Microsoft::WRL::Module::DecrementObjectCount
- module/Microsoft::WRL::Module::GetActivationFactory
- module/Microsoft::WRL::Module::GetClassObject
- module/Microsoft::WRL::Module::GetModule
- module/Microsoft::WRL::Module::GetObjectCount
- module/Microsoft::WRL::Module::IncrementObjectCount
- module/Microsoft::WRL::Module::Module
- module/Microsoft::WRL::Module::objectCount_Data
- module/Microsoft::WRL::Module::RegisterCOMObject
- module/Microsoft::WRL::Module::RegisterObjects
- module/Microsoft::WRL::Module::RegisterWinRTObject
- module/Microsoft::WRL::Module::releaseNotifier_
- module/Microsoft::WRL::Module::Terminate
- module/Microsoft::WRL::Module::~Module
- module/Microsoft::WRL::Module::UnregisterCOMObject
- module/Microsoft::WRL::Module::UnregisterObjects
- module/Microsoft::WRL::Module::UnregisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Module class
- Microsoft::WRL::Module::Create method
- Microsoft::WRL::Module::DecrementObjectCount method
- Microsoft::WRL::Module::GetActivationFactory method
- Microsoft::WRL::Module::GetClassObject method
- Microsoft::WRL::Module::GetModule method
- Microsoft::WRL::Module::GetObjectCount method
- Microsoft::WRL::Module::IncrementObjectCount method
- Microsoft::WRL::Module::Module, constructor
- Microsoft::WRL::Module::objectCount_ data member
- Microsoft::WRL::Module::RegisterCOMObject method
- Microsoft::WRL::Module::RegisterObjects method
- Microsoft::WRL::Module::RegisterWinRTObject method
- Microsoft::WRL::Module::releaseNotifier_ data member
- Microsoft::WRL::Module::Terminate method
- Microsoft::WRL::Module::~Module, destructor
- Microsoft::WRL::Module::UnregisterCOMObject method
- Microsoft::WRL::Module::UnregisterObjects method
- Microsoft::WRL::Module::UnregisterWinRTObject method
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2357790e3084c91011f16eb9f1f718948462f898
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059479"
---
# <a name="module-class"></a>Module-Klasse

Stellt eine Auflistung von zugehörigen Objekten dar.

## <a name="syntax"></a>Syntax

```cpp
template<ModuleType moduleType>
class Module;

template<>
class Module<InProc> : public Details::ModuleBase;

template<>
class Module<OutOfProc> : public Module<InProc>;
```

### <a name="parameters"></a>Parameter

*moduleType*<br/>
Eine Kombination aus einem oder mehreren [ModuleType](../windows/moduletype-enumeration.md) -Enumerationswerte fest.

## <a name="members"></a>Member

### <a name="protected-classes"></a>Geschützte Klassen

name                                                                                | Beschreibung
----------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------
[Module:: genericreleasenotifier](../windows/module-genericreleasenotifier-class.md) | Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler ist durch ein Lambda, Funktionselement oder Zeiger auf Funktion angegeben.
[Module:: methodreleasenotifier](../windows/module-methodreleasenotifier-class.md)   | Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler wird von einem Objekt und seine Member Zeiger-zu-Methode angegeben.
[Module:: releasenotifier](../windows/module-releasenotifier-class.md)               | Ruft einen Ereignishandler an, wenn das letzte Objekt in einem Modul veröffentlicht wird.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                             | Beschreibung
-------------------------------- | -----------------------------------------------------------
[Module:: ~ Module](#tilde-module) | Hebt die Initialisierung der aktuellen Instanz von der `Module` Klasse.

### <a name="protected-constructors"></a>Geschützte Konstruktoren

Name                      | Beschreibung
------------------------- | ---------------------------------------------------
[Module:: Module](#module) | Initialisiert eine neue Instanz der `Module`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                    | Beschreibung
------------------------------------------------------- | --------------------------------------------------------------------------------------------------
[Module:: Create](#create)                               | Erstellt eine Instanz eines Moduls.
[Module:: decrementobjectcount](#decrementobjectcount)   | Verringert die Anzahl der Objekte, die durch das Modul verfolgt wird.
[Module:: getactivationfactory](#getactivationfactory)   | Ruft eine aktivierungsfactory für das Modul ab.
[Module:: GetClassObject](#getclassobject)               | Ruft einen Cache von Klassenfactorys ab.
[Module:: GetModule](#getmodule)                         | Erstellt eine Instanz eines Moduls.
[Module:: getobjectcount](#getobjectcount)               | Ruft die Anzahl von Objekten, die von diesem Modul verwaltet.
[Module:: incrementobjectcount](#incrementobjectcount)   | Erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.
[Module:: registercomobject](#registercomobject)         | Registriert eine oder mehrere COM-Objekte an, damit andere Anwendungen eine Verbindung damit herstellen können.
[Module:: registerobjects](#registerobjects)             | COM- oder Windows-Runtime-Objekte registriert, damit andere Anwendungen eine Verbindung damit herstellen können.
[Module:: registerwinrtobject](#registerwinrtobject)     | Registriert ein oder mehrere Windows-Runtime-Objekte an, damit andere Anwendungen eine Verbindung damit herstellen können.
[Module:: Terminate](#terminate)                         | Bewirkt, dass alle Factorys, die durch das Modul zum Herunterfahren instanziiert.
[Module:: unregistercomobject](#unregistercomobject)     | Hebt die Registrierung für ein oder mehrere COM-Objekte, die verhindert, dass andere Anwendungen herstellen können.
[Module:: unregisterobjects](#unregisterobjects)         | Hebt die Registrierung auf die Objekte in das angegebene Modul, damit andere Anwendungen darauf keine Verbindung herstellen können.
[Module:: unregisterwinrtobject](#unregisterwinrtobject) | Hebt die Registrierung für ein oder mehrere Windows-Runtime-Objekte, damit andere Anwendungen darauf keine Verbindung herstellen können.

### <a name="protected-methods"></a>Geschützte Methoden

Name                      | Beschreibung
------------------------- | --------------------------------
[Module:: Create](#create) | Erstellt eine Instanz eines Moduls.

### <a name="protected-data-members"></a>Geschützte Datenmember

name                                         | Beschreibung
-------------------------------------------- | --------------------------------------------------------------------------------------------------------
[Module:: objectcount_](#objectcount)         | Behält Überblick darüber, wie viele Klassen erstellt wurden die [stellen](../windows/make-function.md) Funktion.
[Module:: releasenotifier_](#releasenotifier) | Enthält einen Zeiger auf eine `ReleaseNotifier` Objekt.

### <a name="macros"></a>Makros

Name | Beschreibung------| --- [ActivatableClass](../windows/activatableclass-macros.md) |  Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können. Dieses Makro gibt standardmäßig Factory und Gruppen-ID-Parameter an.
[ActivatableClassWithFactory](../windows/activatableclass-macros.md) | Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können. Mit diesem Makro können Sie einen bestimmtes Werk-Parameter angeben.
[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) | Füllt einen internen Cache, der eine Factory enthält, die eine Instanz der angegebenen Klasse erstellen können. Mit diesem Makro können Sie bestimmte Factory und Group-ID-Parameter angeben.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ModuleBase`

`Module`

`Module`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="tilde-module"></a>Module:: ~ Module

Hebt die Initialisierung der aktuellen Instanz von der `Module` Klasse.

```cpp
virtual ~Module();
```

## <a name="create"></a>Module:: Create

Erstellt eine Instanz eines Moduls.

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Modultyp.

*Rückruf*<br/>
Wird aufgerufen, wenn das letzte Instanzobjekt des Moduls freigegeben wird.

*object*<br/>
Die *Objekt* und *Methode* Parameter in Kombination verwendet werden. Verweist auf das letzte Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.

*Methode*<br/>
Die *Objekt* und *Methode* Parameter in Kombination verwendet werden. Zeigt auf die Methode des letzten Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.

### <a name="return-value"></a>Rückgabewert

Verweis auf das Modul.

## <a name="decrementobjectcount"></a>Module:: decrementobjectcount

Verringert die Anzahl der Objekte, die durch das Modul verfolgt wird.

```cpp
virtual long DecrementObjectCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der vor der dekrementvorgang werden soll.

## <a name="getactivationfactory"></a>Module:: getactivationfactory

Ruft eine aktivierungsfactory für das Modul ab.

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parameter

*pActivatibleClassId*<br/>
Die IID der von einer Runtime-Klasse.

*ppIFactory*<br/>
Die "iactivationfactory" für die angegebene Runtime-Klasse.

*ServerName*<br/>
Der Name einer Teilmenge von Klassenfactorys im aktuellen Modul. Geben Sie den Servernamen in verwendet die [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) -Makro, oder geben Sie `nullptr` um den Standardnamen für den Server zu erhalten.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls der HRESULT-Wert zurückgegeben, indem GetActivationFactory.

## <a name="getclassobject"></a>Module:: GetClassObject

Ruft einen Cache von Klassenfactorys.

```cpp
HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Klassen-ID.

*riid*<br/>
Schnittstellen-ID, die Sie anfordern.

*ppv*<br/>
Zeiger auf das zurückgegebene Objekt.

*ServerName*<br/>
Den Namen des Servers, der entweder angegeben ist die `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, oder `ActivatableClass` Makro; oder `nullptr` um den Standardnamen für den Server zu erhalten.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur für COM, nicht die Windows-Runtime. Diese Methode macht nur `IClassFactory` Methoden.

## <a name="getmodule"></a>Module:: GetModule

Erstellt eine Instanz eines Moduls.

```cpp
static Module& GetModule();
WRL_NOTHROW static Module& GetModule();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein Modul.

## <a name="getobjectcount"></a>Module:: getobjectcount

Ruft die Anzahl von Objekten, die von diesem Modul verwaltet.

```cpp
virtual long GetObjectCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Anzahl von Objekten, die von diesem Modul verwaltet.

## <a name="incrementobjectcount"></a>Module:: incrementobjectcount

Erhöht die Anzahl der Objekte, die vom Modul nachverfolgt.

```cpp
virtual long IncrementObjectCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der vor dem Inkrementieren negativ werden soll.

## <a name="module"></a>Module:: Module

Initialisiert eine neue Instanz der `Module`-Klasse.

```cpp
Module();
```

### <a name="remarks"></a>Hinweise

Dieser Konstruktor ist geschützt und kann nicht aufgerufen werden, mit der `new` Schlüsselwort. Rufen Sie stattdessen entweder [Module:: GetModule](#getmodule) oder [Module:: Create](#create).

## <a name="objectcount"></a>Module:: objectcount_

Behält Überblick darüber, wie viele Klassen erstellt wurden die [stellen](../windows/make-function.md) Funktion.

```cpp
volatile long objectCount_;
```

## <a name="registercomobject"></a>Module:: registercomobject

Registriert eine oder mehrere COM-Objekte an, damit andere Anwendungen eine Verbindung damit herstellen können.

```cpp
WRL_NOTHROW virtual HRESULT RegisterCOMObject(
   const wchar_t* serverName,
   IID* clsids,
   IClassFactory** factories,
   DWORD* cookies,
   unsigned int count);

```

### <a name="parameters"></a>Parameter

*ServerName*<br/>
Den vollqualifizierten Namen eines Servers.

*CLSIDs*<br/>
Ein Array von CLSID registrieren.

*Factorys*<br/>
Ein Array von IUnknown-Schnittstellen, der die Objekte der Klasse, deren Verfügbarkeit veröffentlicht wird.

*Cookies*<br/>
Wenn der Vorgang abgeschlossen ist, Objekte ein Array von Zeigern auf Werte, die die Klasse zu identifizieren, die registriert wurden. Diese Werte werden später verwendet werden. die Registrierung aufzuheben.

*count*<br/>
Die Anzahl der CLSID registrieren.

### <a name="return-value"></a>Rückgabewert

S_OK Wenn erfo; andernfalls ein HRESULT, z. B. CO_E_OBJISREG, der den Grund angibt. der Vorgang konnte nicht.

### <a name="remarks"></a>Hinweise

Die COM-Objekte werden bei der CLSCTX_LOCAL_SERVER-Enumerator, der die Enumeration CLSCTX registriert.

Die Art der Verbindung auf die registrierten Objekte wird durch eine Kombination aus dem aktuellen angegeben *Comflag* Template-Parameter und den REGCLS_SUSPENDED-Enumerator, der die REGCLS-Enumeration.

## <a name="registerobjects"></a>Module:: registerobjects

COM- oder Windows-Runtime-Objekte registriert, damit andere Anwendungen eine Verbindung damit herstellen können.

```cpp
HRESULT RegisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parameter

*module*<br/>
Ein Array von COM- oder Windows-Runtime-Objekte.

*ServerName*<br/>
Der Name des Servers, der die Objekte erstellt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, der den Grund angibt. der Vorgang konnte nicht.

## <a name="registerwinrtobject"></a>Module:: registerwinrtobject

Registriert ein oder mehrere Windows-Runtime-Objekte an, damit andere Anwendungen eine Verbindung damit herstellen können.

```cpp
HRESULT RegisterWinRTObject(const wchar_t* serverName,
   wchar_t** activatableClassIds,
   WINRT_REGISTRATION_COOKIE* cookie,
   unsigned int count)
```

### <a name="parameters"></a>Parameter

*ServerName*<br/>
Ein Name, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.

*activatableClassIds*<br/>
Ein Array von aktivierbare CLSIDs registrieren.

*Cookie*<br/>
Ein Wert, der die Objekte der Klasse identifiziert, die registriert wurden. Dieser Wert wird später verwendet, um die Registrierung aufzuheben.

*count*<br/>
Die Anzahl von Objekten zu registrieren.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, z. B. CO_E_OBJISREG, die den Grund angibt Fehler aufgetreten.

## <a name="releasenotifier"></a>Module:: releasenotifier_

Enthält einen Zeiger auf eine `ReleaseNotifier` Objekt.

```cpp
ReleaseNotifier *releaseNotifier_;
```

## <a name="terminate"></a>Module:: Terminate

Bewirkt, dass alle Factorys, die durch das Modul zum Herunterfahren instanziiert.

```cpp
void Terminate();
```

### <a name="remarks"></a>Hinweise

Gibt die Factorys im Cache frei.

## <a name="unregistercomobject"></a>Module:: unregistercomobject

Hebt die Registrierung für ein oder mehrere COM-Objekte, die verhindert, dass andere Anwendungen herstellen können.

```cpp
virtual HRESULT UnregisterCOMObject(
   const wchar_t* serverName,
   DWORD* cookies,
   unsigned int count
```

### <a name="parameters"></a>Parameter

*ServerName*<br/>
(Nicht verwendeten)

*Cookies*<br/>
Ein Array von Zeigern auf Werte, die identifizieren, Objekte der Klasse, deren Registrierung aufgehoben werden. Das Array erstellt wurde, indem die [RegisterCOMObject](#registercomobject) Methode.

*count*<br/>
Die Anzahl der Klassen zum Aufheben der Registrierung.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das den Grund angibt Fehler aufgetreten.

## <a name="unregisterobjects"></a>Module:: unregisterobjects

Hebt die Registrierung auf die Objekte in das angegebene Modul, damit andere Anwendungen darauf keine Verbindung herstellen können.

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parameter

*module*<br/>
Zeiger auf ein Modul.

*ServerName*<br/>
Einen qualifizierten Namen, der eine Teilmenge der von diesem Vorgang betroffenen Objekte angibt.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls Fehler Fehler HRESULT, das den Grund angibt, diesen Vorgang.

## <a name="unregisterwinrtobject"></a>Module:: unregisterwinrtobject

Hebt die Registrierung für ein oder mehrere Windows-Runtime-Objekte, damit andere Anwendungen darauf keine Verbindung herstellen können.

```cpp
virtual HRESULT UnregisterWinRTObject(
   unsigned int,
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie
);
```

### <a name="parameters"></a>Parameter

*Cookie*<br/>
Ein Zeiger auf ein Wert, der das Klassenobjekt identifiziert, dessen Registrierung aufgehoben werden.
