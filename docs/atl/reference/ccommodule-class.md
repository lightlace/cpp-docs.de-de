---
title: CComModule-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
ms.openlocfilehash: 6d95460902c44ff058a4c7b90c810ab44489d952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259273"
---
# <a name="ccommodule-class"></a>CComModule-Klasse

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComModule::GetClassObject](#getclassobject)|Erstellt ein Objekt der angegebenen CLSID. Für nur-DLLs.|
|[CComModule::GetModuleInstance](#getmoduleinstance)|Gibt `m_hInst`zurück.|
|[CComModule::GetResourceInstance](#getresourceinstance)|Gibt `m_hInstResource`zurück.|
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|Gibt `m_hInstTypeLib`zurück.|
|[CComModule::Init](#init)|Initialisiert die Datenmember.|
|[CComModule::RegisterClassHelper](#registerclasshelper)|Gibt die standard-klassenregistrierung eines Objekts in der systemregistrierung.|
|[CComModule::RegisterClassObjects](#registerclassobjects)|Registriert das Klassenobjekt. Für EXE-Dateien nur.|
|[CComModule::RegisterServer](#registerserver)|Die Registrierung des Systems für jedes Objekt in der objektzuordnung wird aktualisiert.|
|[CComModule::RegisterTypeLib](#registertypelib)|Registriert eine Typbibliothek.|
|[CComModule::RevokeClassObjects](#revokeclassobjects)|Widerruft das Klassenobjekt. Für EXE-Dateien nur.|
|[CComModule::Term](#term)|Gibt die Datenmember frei.|
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|Entfernt ein Objekt des standard-klassenregistrierung aus der systemregistrierung.|
|[CComModule::UnregisterServer](#unregisterserver)|Hebt die Registrierung jedes Objekt in der objektzuordnung.|
|[CComModule::UpdateRegistryClass](#updateregistryclass)|Registriert, oder hebt die Registrierung für die standard-klassenregistrierung eines Objekts.|
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das Skript in einer angegebenen Ressource für das Registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.|
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Statisch mit der ATL-Registrierungskomponente verknüpft. Führt das Skript in einer angegebenen Ressource für das Registrieren oder Aufheben der Registrierung eines Objekts enthalten sind.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComModule::m_csObjMap](#m_csobjmap)|Wird die synchronisierten Zugriff auf die Informationen des Objekt-Zuordnung sichergestellt.|
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|Stellt sicher synchronisierten Zugriff auf die Typinformationen für die Bibliothek aus.|
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|Stellt sicher synchronisierten Zugriff auf die fensterklasseninformationen sowie aus statischen Daten, die während der Erstellung verwendet werden soll.|
|[CComModule::m_hInst](#m_hinst)|Das Handle für die Modulinstanz enthält.|
|[CComModule::m_hInstResource](#m_hinstresource)|Standardmäßig enthält das Handle für die Modulinstanz.|
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|Standardmäßig enthält das Handle für die Modulinstanz.|
|[CComModule::m_pObjMap](#m_pobjmap)|Zeigt auf der objektzuordnung, die von der Modulinstanz verwaltet.|

## <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Klasse ist veraltet, und verwenden Sie den schemagenerierungs-Assistenten von ATL-Code nun die [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) und [CAtlModule](../../atl/reference/catlmodule-class.md) abgeleiteten Klassen. Finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) für Weitere Informationen. Die folgenden Informationen, die für die Verwendung mit Anwendungen, die mit älteren Versionen von ATL erstellt wird `CComModule` ist immer noch Teil der ATL für Abwärtskompatibilität Funktion.

`CComModule` implementiert ein COM-Server-Modul, einen Client den Zugriff auf die Modul Komponenten zulassen. `CComModule` unterstützt (in-Process)-DLL und EXE-Datei (local)-Module.

Ein `CComModule` -Instanz eine objektzuordnung verwendet, um einen Satz von Objektdefinitionen Klasse verwalten. Dieses objektzuordnung wird als ein Array von implementiert `_ATL_OBJMAP_ENTRY` strukturiert und enthält Informationen für:

- Eingeben, und Entfernen von Beschreibungen der Ergebnisobjekte in der systemregistrierung.

- Instanziieren von Objekten, die über eine Klassenfactory.

- Beim Herstellen der Kommunikation zwischen einem Client und das Stammobjekt in der Komponente.

- Verwaltung des Lebenszyklus von Klassenobjekten wird durchgeführt.

Wenn Sie die ATL-COM-AppWizard ausführen, der Assistent generiert automatisch `_Module`, eine globale Instanz des `CComModule` oder eine Klasse abgeleitet wird. Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

Zusätzlich zu `CComModule`, ATL stellt [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), die ein Modul Apartment-Modell für EXE-Dateien und Windows-Dienste implementiert. Ableiten des Moduls aus `CComAutoThreadModule` beim Erstellen von Objekten in mehreren Apartments werden sollen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="getclassobject"></a>  CComModule::GetClassObject

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parameter

*rclsid*<br/>
[in] Die CLSID des Objekts erstellt werden.

*riid*<br/>
[in] Die IID der angeforderten Schnittstelle.

*ppv*<br/>
[out] Ein Zeiger auf den Schnittstellenzeiger vom *Riid*. Wenn das Objekt nicht über diese Schnittstelle unterstützt *Ppv* auf NULL festgelegt ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Erstellt ein Objekt der angegebenen CLSID und einen Schnittstellenzeiger für dieses Objekt abgerufen.

`GetClassObject` ist nur auf DLLs verfügbar.

##  <a name="getmoduleinstance"></a>  CComModule::GetModuleInstance

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>Rückgabewert

Das HINSTANCE, die dieses Modul identifiziert.

### <a name="remarks"></a>Hinweise

Gibt die [M_hInst](#m_hinst) -Datenmember.

##  <a name="getresourceinstance"></a>  CComModule::GetResourceInstance

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein HINSTANCE.

### <a name="remarks"></a>Hinweise

Gibt die [M_hInstResource](#m_hinstresource) -Datenmember.

##  <a name="gettypelibinstance"></a>  CComModule::GetTypeLibInstance

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>Rückgabewert

Ein HINSTANCE.

### <a name="remarks"></a>Hinweise

Gibt die [M_hInstTypeLib](#m_hinsttypelib) -Datenmember.

##  <a name="init"></a>  CComModule

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] Ein Zeiger auf ein Array von Objekt-Zuordnungseinträge.

*h*<br/>
[in] Das HINSTANCE, die an `DLLMain` oder `WinMain`.

*plibid*<br/>
[in] Ein Zeiger auf die LIBID der Typbibliothek, die dem Projekt zugeordnet.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Initialisiert alle Datenmember.

##  <a name="m_csobjmap"></a>  CComModule::m_csObjMap

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>Hinweise

Wird die synchronisierten Zugriff auf die objektzuordnung sichergestellt.

##  <a name="m_cstypeinfoholder"></a>  CComModule::m_csTypeInfoHolder

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>Hinweise

Stellt sicher synchronisierten Zugriff auf die Typbibliothek.

##  <a name="m_cswindowcreate"></a>  CComModule::m_csWindowCreate

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>Hinweise

Stellt sicher synchronisierten Zugriff fensterklasseninformationen und statische Daten, die während der Erstellung verwendet werden soll.

##  <a name="m_hinst"></a>  CComModule::m_hInst

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>Hinweise

Das Handle für die Modulinstanz enthält.

Die [Init](#init) Methode legt `m_hInst` an das Handle übergeben `DLLMain` oder `WinMain`.

##  <a name="m_hinstresource"></a>  CComModule::m_hInstResource

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>Hinweise

Standardmäßig enthält das Handle für die Modulinstanz.

Die [Init](#init) Methode legt `m_hInstResource` an das Handle übergeben `DLLMain` oder `WinMain`. Sie können explizit festlegen `m_hInstResource` auf das Handle für eine Ressource.

Die [GetResourceInstance](#getresourceinstance) Methode gibt das Handle in gespeicherten `m_hInstResource`.

##  <a name="m_hinsttypelib"></a>  CComModule::m_hInstTypeLib

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>Hinweise

Standardmäßig enthält das Handle für die Modulinstanz.

Die [Init](#init) Methode legt `m_hInstTypeLib` an das Handle übergeben `DLLMain` oder `WinMain`. Sie können explizit festlegen `m_hInstTypeLib` auf den Ziehpunkt in eine Typbibliothek.

Die [GetTypeLibInstance](#gettypelibinstance) Methode gibt das Handle in gespeicherten `m_hInstTypeLib`.

##  <a name="m_pobjmap"></a>  CComModule::m_pObjMap

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>Hinweise

Zeigt auf der objektzuordnung, die von der Modulinstanz verwaltet.

##  <a name="registerclasshelper"></a>  CComModule::RegisterClassHelper

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
[in] Die CLSID des Objekts, die registriert werden.

*lpszProgID*<br/>
[in] Die ProgID, die dem Objekt zugeordnet wird.

*lpszVerIndProgID*<br/>
[in] Die versionsunabhängigen-ProgID, die dem Objekt zugeordnet.

*nDescID*<br/>
[in] Der Bezeichner des eine Zeichenfolgenressource für die Beschreibung des Objekts.

*dwFlags*<br/>
[in] Gibt das Threadingmodell an, in der Registrierung einzugeben. Mögliche Werte sind THREADFLAGS_APARTMENT THREADFLAGS_BOTH oder AUTPRXFLAG.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Gibt die standard-klassenregistrierung eines Objekts in der systemregistrierung.

Die [UpdateRegistryClass](#updateregistryclass) Methodenaufrufe `RegisterClassHelper`.

##  <a name="registerclassobjects"></a>  CComModule::RegisterClassObjects

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>Parameter

*dwClsContext*<br/>
[in] Gibt den Kontext, in dem das Klassenobjekt ist, ausgeführt werden. Mögliche Werte sind CLSCTX_INPROC_SERVER CLSCTX_INPROC_HANDLER oder CLSCTX_LOCAL_SERVER. Eine Beschreibung dieser Werte finden Sie in [CLSCTX](/windows/desktop/api/wtypesbase/ne-wtypesbase-tagclsctx) im Windows SDK.

*dwFlags*<br/>
[in] Bestimmt die Art der Verbindung mit dem Klassenobjekt. Mögliche Werte sind REGCLS_SINGLEUSE REGCLS_MULTIPLEUSE oder REGCLS_MULTI_SEPARATE. Eine Beschreibung dieser Werte finden Sie in [REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Ein Klassenobjekt exe-Datei registriert mit OLE, damit andere Anwendungen hergestellt werden können. Diese Methode ist nur für EXE-Dateien verfügbar.

##  <a name="registerserver"></a>  CComModule::RegisterServer

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>Parameter

*bRegTypeLib*<br/>
[in] Gibt an, ob die Typbibliothek registriert wird. Der Standardwert ist "false".

*pCLSID*<br/>
[in] Zeigt auf die CLSID des Objekts, das registriert werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung registriert wird.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Je nachdem auf die *pCLSID* Parameter aktualisiert, die Registrierung des Systems für ein Objekt der Klasse oder für alle Objekte in der objektzuordnung.

Wenn *bRegTypeLib* ist "true", die Typinformationen für die Bibliothek wird auch aktualisiert werden.

Finden Sie unter [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) Informationen zum Hinzufügen eines Eintrags zur objektzuordnung.

`RegisterServer` wird automatisch aufgerufen, `DLLRegisterServer` für eine DLL oder durch `WinMain` eine EXE-Datei führen Sie mit der `/RegServer` -Befehlszeilenoption.

##  <a name="registertypelib"></a>  CComModule::RegisterTypeLib

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>Parameter

*lpszIndex*<br/>
[in] Zeichenfolge im Format `"\\N"`, wobei `N` ist der ganzzahlige Index der TYPELIB-Ressourcen.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Fügt Informationen über eine Typbibliothek in die systemregistrierung.

Wenn die Modulinstanz mehrere Bibliotheken enthält, verwenden Sie die zweite Version dieser Methode, um anzugeben, welche Typbibliothek verwendet werden soll.

##  <a name="revokeclassobjects"></a>  CComModule::RevokeClassObjects

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Entfernt das Klassenobjekt. Diese Methode ist nur für EXE-Dateien verfügbar.

##  <a name="term"></a>  CComModule:: Term.

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
void Term() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle Datenmember frei.

##  <a name="unregisterclasshelper"></a>  CComModule::UnregisterClassHelper

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
[in] Die CLSID des Objekts, deren Registrierung aufgehoben werden.

*lpszProgID*<br/>
[in] Die ProgID, die dem Objekt zugeordnet wird.

*lpszVerIndProgID*<br/>
[in] Die versionsunabhängigen-ProgID, die dem Objekt zugeordnet.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Entfernt ein Objekt des standard-klassenregistrierung aus der systemregistrierung.

Die [UpdateRegistryClass](#updateregistryclass) Methodenaufrufe `UnregisterClassHelper`.

##  <a name="unregisterserver"></a>  CComModule::UnregisterServer

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>Parameter

*bUnRegTypeLib*<br/>
Bei "true", wird die Bibliothek auch aufgehoben werden.

*pCLSID*<br/>
Zeigt auf die CLSID des Objekts, das nicht aufgehoben werden. Wenn NULL (Standardwert), alle Objekte in der objektzuordnung aufgehoben.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Je nachdem auf die *pCLSID* Parameter hebt die Registrierung für ein Objekt der Klasse oder alle Objekte in der objektzuordnung.

`UnregisterServer` wird automatisch aufgerufen, `DLLUnregisterServer` für eine DLL oder durch `WinMain` eine EXE-Datei führen Sie mit der `/UnregServer` -Befehlszeilenoption.

Finden Sie unter [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) Informationen zum Hinzufügen eines Eintrags zur objektzuordnung.

##  <a name="updateregistryclass"></a>  CComModule::UpdateRegistryClass

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```

### <a name="parameters"></a>Parameter

*clsid*<br/>
Die CLSID des Objekts, registriert oder deren Registrierung aufgehoben werden soll.

*lpszProgID*<br/>
Die ProgID, die dem Objekt zugeordnet wird.

*lpszVerIndProgID*<br/>
Die versionsunabhängigen-ProgID, die dem Objekt zugeordnet.

*nDescID*<br/>
Der Bezeichner der Zeichenfolgenressource für die Beschreibung des Objekts.

*szDesc*<br/>
Eine Zeichenfolge, die die Beschreibung des Objekts enthält.

*dwFlags*<br/>
Gibt das Threadingmodell an, in der Registrierung einzugeben. Mögliche Werte sind THREADFLAGS_APARTMENT THREADFLAGS_BOTH oder AUTPRXFLAG.

*bRegister*<br/>
Gibt an, ob das Objekt registriert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn *bRegistrieren Sie sich* "true", wird diese Methode gibt die standard-klassenregistrierung des Objekts in der Registrierung des Systems.

Wenn *bRegistrieren Sie sich* false festgelegt ist, wird das Objekt in der Registrierung entfernt.

Abhängig vom Wert *bRegistrieren Sie sich*, `UpdateRegistryClass` Ruft entweder [RegisterClassHelper](#registerclasshelper) oder [UnregisterClassHelper](#unregisterclasshelper).

Durch Angabe der [DECLARE_REGISTRY](registry-macros.md#declare_registry) Makro `UpdateRegistryClass` wird automatisch aufgerufen, wenn die objektzuordnung verarbeitet wird.

##  <a name="updateregistryfromresourced"></a>  CComModule::UpdateRegistryFromResourceD

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
virtual HRESULT UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```

### <a name="parameters"></a>Parameter

*lpszRes*<br/>
[in] Ein Ressourcenname.

*nResID*<br/>
[in] Eine Ressourcen-ID

*bRegister*<br/>
[in] Gibt an, ob das Objekt registriert werden soll.

*pMapEntries*<br/>
[in] Ein Zeiger auf die Ersatz-Zuordnung ersetzbare Parameter des Skripts zugeordneten Werte zu speichern. ATL verwendet, automatisch `%MODULE%`. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter den Hinweisen zu den Details. Verwenden Sie andernfalls den Standardwert NULL.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Führt das Skript in die Ressource anhand des enthaltenen *LpszRes* oder *nResID*.

Wenn *bRegistrieren Sie sich* "true", wird diese Methode registriert das Objekt in der systemregistrierung; anderenfalls Es hebt die Registrierung des Objekts.

Durch Angabe der [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) oder [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) Makro `UpdateRegistryFromResourceD` wird automatisch aufgerufen, wenn die objektzuordnung verarbeitet wird.

> [!NOTE]
>  Um Ersatzwerte zur Laufzeit zu ersetzen, geben Sie das Makro DECLARE_REGISTRY_RESOURCE oder DECLARE_REGISTRY_RESOURCEID nicht. Erstellen Sie stattdessen ein Array von `_ATL_REGMAP_ENTRIES` Strukturen, von denen jeder Eintrag einen Variable Platzhalter enthält mit dem Wert ersetzt den Platzhalter zur Laufzeit zugeordnet. Rufen Sie anschließend `UpdateRegistryFromResourceD`, übergeben das Array für die *pMapEntries* Parameter. Dadurch werden die Ersatzwerte in der `_ATL_REGMAP_ENTRIES` Strukturen, um die Registrierungsstelle Ersatz-Zuordnung.

> [!NOTE]
>  Um statisch mit der ATL-Registrierungskomponente (Registrar) zu verknüpfen, finden Sie unter [UpdateRegistryFromResourceS](#updateregistryfromresources).

Weitere Informationen zu ersetzbare Parameter und Skripts finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).

##  <a name="updateregistryfromresources"></a>  CComModule::UpdateRegistryFromResourceS

Zum Zeitpunkt der ATL 7.0 `CComModule` ist veraltet: finden Sie unter [ATL-Modulklassen](../../atl/atl-module-classes.md) Weitere Details.

```
virtual HRESULT UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parameter

*lpszRes*<br/>
[in] Ein Ressourcenname.

*nResID*<br/>
[in] Eine Ressourcen-ID

*bRegister*<br/>
[in] Gibt an, ob das Ressourcenskript registriert werden soll.

*pMapEntries*<br/>
[in] Ein Zeiger auf die Ersatz-Zuordnung ersetzbare Parameter des Skripts zugeordneten Werte zu speichern. ATL verwendet, automatisch `%MODULE%`. Um zusätzliche ersetzbare Parameter verwenden zu können, finden Sie unter den Hinweisen zu den Details. Verwenden Sie andernfalls den Standardwert NULL.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Ähnlich wie [UpdateRegistryFromResourceD](#updateregistryfromresourced) außer `UpdateRegistryFromResourceS` erstellt einen statischen Link zu der ATL-Registrierungskomponente (Registrar).

`UpdateRegistryFromResourceS` wird aufgerufen, automatisch bei Ihrer objektzuordnung verarbeitet wurde, vorausgesetzt Sie hinzufügen, `#define _ATL_STATIC_REGISTRY` auf Ihre "stdafx.h".

> [!NOTE]
>  Um Ersatzwerte zur Laufzeit zu ersetzen, geben Sie nicht die [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) oder [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) Makro. Erstellen Sie stattdessen ein Array von `_ATL_REGMAP_ENTRIES` Strukturen, von denen jeder Eintrag einen Variable Platzhalter enthält mit dem Wert ersetzt den Platzhalter zur Laufzeit zugeordnet. Rufen Sie anschließend `UpdateRegistryFromResourceS`, übergeben das Array für die *pMapEntries* Parameter. Dadurch werden die Ersatzwerte in der `_ATL_REGMAP_ENTRIES` Strukturen, um die Registrierungsstelle Ersatz-Zuordnung.

Weitere Informationen zu ersetzbare Parameter und Skripts finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
