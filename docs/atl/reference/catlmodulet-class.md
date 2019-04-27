---
title: CAtlModuleT-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: 2cd207038a92b944bf95575f0e0c820b8f09d615
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260148"
---
# <a name="catlmodulet-class"></a>CAtlModuleT-Klasse

Diese Klasse implementiert ein ATL-Modul.

## <a name="syntax"></a>Syntax

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse abgeleitet `CAtlModuleT`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlModuleT::InitLibId](#initlibid)|Initialisiert den Datenmember, die mit der GUID des aktuellen Moduls.|
|[CAtlModuleT::RegisterAppId](#registerappid)|Die EXE-Datei hinzugefügt zur Registrierung.|
|[CAtlModuleT::RegisterServer](#registerserver)|Fügt den Dienst in der Registrierung.|
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|Entfernt die EXE-Datei aus der Registrierung.|
|[CAtlModuleT::UnregisterServer](#unregisterserver)|Entfernt den Dienst aus der Registrierung.|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|Aktualisiert die EXE-Informationen in der Registrierung.|

## <a name="remarks"></a>Hinweise

`CAtlModuleT`, abgeleitet [CAtlModule](../../atl/reference/catlmodule-class.md), implementiert eine ausführbare Datei (EXE) oder einem Dienst (EXE), ATL-Modul. Ein ausführbares Modul ist eine lokale, Out-of-Process-Server, während ein Dienstmodul einer Windows-Anwendung, die im Hintergrund ausgeführt wird ist, wenn Windows gestartet wird.

`CAtlModuleT` bietet Unterstützung für die Initialisierung, Registrierung und Aufheben der Registrierung des Moduls.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="catlmodulet"></a>  CAtlModuleT::CAtlModuleT

Der Konstruktor.

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlModuleT::InitLibId](#initlibid).

##  <a name="initlibid"></a>  CAtlModuleT::InitLibId

Initialisiert den Datenmember, die mit der GUID des aktuellen Moduls.

```
static void InitLibId() throw();
```

### <a name="remarks"></a>Hinweise

Wird aufgerufen, durch den Konstruktor [CAtlModuleT::CAtlModuleT](#catlmodulet).

##  <a name="registerappid"></a>  CAtlModuleT::RegisterAppId

Die EXE-Datei hinzugefügt zur Registrierung.

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="registerserver"></a>  CAtlModuleT::RegisterServer

Fügt den Dienst in der Registrierung.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parameter

*bRegTypeLib*<br/>
True, wenn die Typbibliothek registriert werden. Der Standardwert ist "false".

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das registriert werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung registriert wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="unregisterappid"></a>  CAtlModuleT::UnregisterAppId

Entfernt die EXE-Datei aus der Registrierung.

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="unregisterserver"></a>  CAtlModuleT::UnregisterServer

Entfernt den Dienst aus der Registrierung.

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parameter

*bUnRegTypeLib*<br/>
"True", wenn die Bibliothek auch aufgehoben werden soll.

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung aufgehoben.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="updateregistryappid"></a>  CAtlModuleT::UpdateRegistryAppId

Aktualisiert die EXE-Informationen in der Registrierung.

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>Parameter

*bRegister*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

## <a name="see-also"></a>Siehe auch

[CAtlModule-Klasse](../../atl/reference/catlmodule-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[Modulklassen](../../atl/atl-module-classes.md)
