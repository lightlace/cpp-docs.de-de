---
title: CAtlDllModuleT-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: be42915c6c2e941bc5fc1de78c5c7ac26ccca6e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247099"
---
# <a name="catldllmodulet-class"></a>CAtlDllModuleT-Klasse

Diese Klasse stellt das Modul für eine DLL.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse abgeleitet `CAtlDllModuleT`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Der Konstruktor.|
|[CAtlDllModuleT::~CAtlDllModuleT](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlDllModuleT::DllCanUnloadNow](#dllcanunloadnow)|Testet, ob die DLL entladen werden kann.|
|[CAtlDllModuleT::DllGetClassObject](#dllgetclassobject)|Gibt eine Klassenfactory zurück.|
|[CAtlDllModuleT::DllMain](#dllmain)|Der optionale Einstiegspunkt in einer Dynamic Link Library (DLL).|
|[CAtlDllModuleT::DllRegisterServer](#dllregisterserver)|Fügt Einträge in die systemregistrierung für Objekte in der DLL hinzu.|
|[CAtlDllModuleT::DllUnregisterServer](#dllunregisterserver)|Entfernt die Einträge in der systemregistrierung für Objekte in der DLL.|
|[CAtlDllModuleT::GetClassObject](#getclassobject)|Gibt eine Klassenfactory zurück. Aufgerufen durch [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Hinweise

`CAtlDllModuleT` das Modul für eine Dynamic Link Library (DLL) darstellt, und bietet Funktionen, die von allen DLL-Projekten verwendet wird. Diese Spezialisierung [CAtlModuleT](../../atl/reference/catlmodulet-class.md) Klasse bietet Unterstützung für die Registrierung.

Weitere Informationen zu Modulen in ATL, finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="catldllmodulet"></a>  CAtlDllModuleT::CAtlDllModuleT

Der Konstruktor.

```
CAtlDllModuleT() throw();
```

##  <a name="dtor"></a>  CAtlDllModuleT:: ~ CAtlDllModuleT

Der Destruktor.

```
~CAtlDllModuleT() throw();
```

##  <a name="dllcanunloadnow"></a>  CAtlDllModuleT::DllCanUnloadNow

Testet, ob die DLL entladen werden kann.

```
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück, wenn die DLL entladen werden kann, oder S_FALSE zurück, wenn dies nicht möglich.

##  <a name="dllgetclassobject"></a>  CAtlDllModuleT::DllGetClassObject

Gibt die Klassenfactory zurück.

```
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parameter

*rclsid*<br/>
Die CLSID des Objekts erstellt werden.

*riid*<br/>
Die IID der angeforderten Schnittstelle.

*ppv*<br/>
Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *Ppv* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="dllmain"></a>  CAtlDllModuleT::DllMain

Der optionale Einstiegspunkt in einer Dynamic Link Library (DLL).

```
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parameter

*dwReason*<br/>
Wenn auf DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH und DLL_THREAD_DETACH Benachrichtigungsaufrufe deaktiviert sind.

*lpReserved*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt immer "true" zurück.

### <a name="remarks"></a>Hinweise

Deaktivieren die DLL_THREAD_ATTACH und DLL_THREAD_DETACH Benachrichtigung, dass Aufrufe eine nützliche Optimierung für Multithread-Anwendungen werden können, die viele DLLs, die häufig erstellen und Löschen von Threads und, dessen DLLs ist nicht erforderlich, diese Benachrichtigungen auf Threadebene der Anlage/trennen.

##  <a name="dllregisterserver"></a>  CAtlDllModuleT::DllRegisterServer

Fügt Einträge in die systemregistrierung für Objekte in der DLL hinzu.

```
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parameter

*bRegTypeLib*<br/>
True, wenn die Typbibliothek registriert werden. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="dllunregisterserver"></a>  CAtlDllModuleT::DllUnregisterServer

Entfernt die Einträge in der systemregistrierung für Objekte in der DLL.

```
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parameter

*bUnRegTypeLib*<br/>
True, wenn die Typbibliothek aus der Registrierung entfernt werden soll. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="getclassobject"></a>  CAtlDllModuleT::GetClassObject

Erstellt ein Objekt der angegebenen CLSID.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parameter

*rclsid*<br/>
Die CLSID des Objekts erstellt werden.

*riid*<br/>
Die IID der angeforderten Schnittstelle.

*ppv*<br/>
Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *Ppv* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, indem [CAtlDllModuleT::DllGetClassObject](#dllgetclassobject) und wird aus Gründen der Abwärtskompatibilität.

## <a name="see-also"></a>Siehe auch

[CAtlModuleT-Klasse](../../atl/reference/catlmodulet-class.md)<br/>
[CAtlExeModuleT-Klasse](../../atl/reference/catlexemodulet-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Modulklassen](../../atl/atl-module-classes.md)
