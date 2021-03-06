---
title: Klasse von "Klasse"
ms.date: 11/04/2016
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
ms.openlocfilehash: 798e94aed3bbd98108866ce0a1810485bd68699b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497753"
---
# <a name="catlmodule-class"></a>Klasse von "Klasse"

Diese Klasse stellt Methoden bereit, die von mehreren ATL-Modul Klassen verwendet werden.

## <a name="syntax"></a>Syntax

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|["":](#catlmodule)|Der Konstruktor.|
|["-Module":: ~ "Module"](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|Überschreiben Sie diese Methode, um der Registrierungs Komponente der ATL-Registrierungs Komponente Parameter hinzuzufügen.|
|[CAtlModule::AddTermFunc](#addtermfunc)|Fügt eine neue Funktion hinzu, die aufgerufen wird, wenn das Modul beendet wird.|
|[CAtlModule::GetGITPtr](#getgitptr)|Gibt den globalen Schnittstellen Zeiger zurück.|
|[CAtlModule::GetLockCount](#getlockcount)|Gibt die Sperrenanzahl zurück.|
|[""-Modul ""](#lock)|Erhöht die Sperrenanzahl.|
|["":](#term)|Gibt alle Datenmember frei.|
|["-Module":: Unlock](#unlock)|Verringert die Sperrenanzahl.|
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|Führt das in einer angegebenen Ressource enthaltene Skript aus, um ein Objekt zu registrieren oder die Registrierung aufzuheben.|
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|Diese Methode wird von `UpdateRegistryFromResourceD` aufgerufen, um das Registrierungs Update auszuführen.|
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|Führt das in einer angegebenen Ressource enthaltene Skript aus, um ein Objekt zu registrieren oder die Registrierung aufzuheben. Diese Methode verknüpft statisch mit der ATL-Registrierungs Komponente.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|["-Module":: m_libid](#m_libid)|Enthält die GUID des aktuellen Moduls.|
|[CAtlModule::m_pGIT](#m_pgit)|Zeiger auf die globale Schnittstellen Tabelle.|

## <a name="remarks"></a>Hinweise

Diese Klasse [wird von der](../../atl/reference/catldllmodulet-class.md)Klasse "" der Klasse "-Klasse", der Klasse "-Klasse" und der [Klasse](../../atl/reference/catlservicemodulet-class.md) "-Klasse" [verwendet, um](../../atl/reference/catlexemodulet-class.md)Unterstützung für dll-Anwendungen, exe-Anwendungen und Windows-Dienste bereitzustellen.

Weitere Informationen zu Modulen in ATL finden Sie unter [ATL-Modul Klassen](../../atl/atl-module-classes.md).

Diese Klasse ersetzt die veraltete [CComModule-Klasse](../../atl/reference/ccommodule-class.md) , die in früheren Versionen von ATL verwendet wurde.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="addcommonrgsreplacements"></a>"" Für "": addcommonrgserersetzungen

Überschreiben Sie diese Methode, um der Registrierungs Komponente der ATL-Registrierungs Komponente Parameter hinzuzufügen.

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>Parameter

*pRegistrar*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ersetzbare Parameter ermöglichen es dem Client der Registrierungsstelle, Laufzeitdaten anzugeben. Zu diesem Zweck behält die Registrierungsstelle eine Ersatz Zuordnung bei, in die Sie die Werte eingibt, die den ersetzbaren Parametern in Ihrem Skript zugeordnet sind. Diese Einträge werden von der Registrierungsstelle zur Laufzeit erstellt.

Weitere Informationen finden [Sie im Thema Verwenden von ersetzbaren Parametern (Präprozessor der Registrierungsstelle)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) .

##  <a name="addtermfunc"></a>"-Module":: addtermfunc

Fügt eine neue Funktion hinzu, die aufgerufen wird, wenn das Modul beendet wird.

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>Parameter

*pFunc*<br/>
Ein Zeiger auf die hinzu zufügende Funktion.

*dw*<br/>
Benutzerdefinierte Daten, die an die Funktion übermittelt werden.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="catlmodule"></a>"":

Der Konstruktor.

```
CAtlModule() throw();
```

### <a name="remarks"></a>Hinweise

Initialisiert Datenmember und initiiert einen kritischen Abschnitt um den Thread des Moduls.

##  <a name="dtor"></a>"-Module":: ~ "Module"

Der Destruktor.

```
~CAtlModule() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle Datenmember frei.

##  <a name="getgitptr"></a>"Update Module:: getgitptr"

Ruft einen Zeiger auf die globale Schnittstellen Tabelle ab.

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>Parameter

*ppGIT*<br/>
Ein Zeiger auf die Variable, die den Zeiger auf die globale Schnittstellen Tabelle empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen Fehlercode bei einem Fehler zurück. E_POINTER wird zurückgegeben, wenn *ppgit* gleich NULL ist.

### <a name="remarks"></a>Hinweise

Wenn das Table-Objekt der globalen Schnittstelle nicht vorhanden ist, wird es erstellt, und seine Adresse wird in der [Element Variablen "](#m_pgit)", "", "", "".

In Debugbuilds tritt ein Fehler auf, wenn *ppgit* gleich NULL ist oder wenn der globale Schnittstellen Tabellen Zeiger nicht abgerufen werden kann.

Informationen zur globalen Schnittstellen Tabelle finden Sie unter [iglobalinterfaketable](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable) .

##  <a name="getlockcount"></a>"Chanlmodule:: GetLockCount"

Gibt die Sperrenanzahl zurück.

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Sperrenanzahl zurück. Dieser Wert kann bei der Diagnose und beim Debuggen hilfreich sein.

##  <a name="lock"></a>""-Modul ""

Erhöht die Sperrenanzahl.

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>Rückgabewert

Erhöht die Sperrenanzahl und gibt den aktualisierten Wert zurück. Dieser Wert kann bei der Diagnose und beim Debuggen hilfreich sein.

##  <a name="m_libid"></a>"-Module":: m_libid

Enthält die GUID des aktuellen Moduls.

```
static GUID m_libid;
```

##  <a name="m_pgit"></a>"-Module":: m_pGIT

Zeiger auf die globale Schnittstellen Tabelle.

```
IGlobalInterfaceTable* m_pGIT;
```

##  <a name="term"></a>"":

Gibt alle Datenmember frei.

```
void Term() throw();
```

### <a name="remarks"></a>Hinweise

Gibt alle Datenmember frei. Diese Methode wird vom Dekonstruktor aufgerufen.

##  <a name="unlock"></a>"-Module":: Unlock

Verringert die Sperrenanzahl.

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>Rückgabewert

Verringert die Sperrenanzahl und gibt den aktualisierten Wert zurück. Dieser Wert kann bei der Diagnose und beim Debuggen hilfreich sein.

##  <a name="updateregistryfromresourced"></a>"Update Module:: UpdateRegistryFromResource"

Führt das in einer angegebenen Ressource enthaltene Skript aus, um ein Objekt zu registrieren oder die Registrierung aufzuheben.

```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parameter

*lpszRes*<br/>
Ein Ressourcen Name.

*nResID*<br/>
Eine Ressourcen-ID.

*bRegister*<br/>
TRUE, wenn das Objekt registriert werden soll. Andernfalls false.

*pmapentries*<br/>
Ein Zeiger auf die Ersatz Zuordnung, die Werte speichert, die den ersetzbaren Parametern des Skripts zugeordnet sind. ATL verwendet automatisch% Module%. Informationen zur Verwendung zusätzlicher ersetzbarer Parameter [finden Sie](#addcommonrgsreplacements)unter "". Andernfalls verwenden Sie den Standardwert NULL.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Führt das Skript aus, das in der durch *lpszres oder nresid*angegebenen Ressource enthalten ist. Wenn *bregister* den Wert true hat, registriert diese Methode das Objekt in der Systemregistrierung. Andernfalls wird das Objekt aus der Registrierung entfernt.

Informationen zur statischen Verknüpfung mit der ATL-Registrierungs Komponente (Registrierungs Komponente, Registrierungs Komponente [) finden Sie](#updateregistryfromresources)unter "".

Diese [Methode ruft "](#updateregistryfromresourcedhelper) " "" "" "", "", "" für " [".](iregistrar-class.md#resourceunregister)

##  <a name="updateregistryfromresourcedhelper"></a>Skript Modul:: updateregistryfromresourcedhelper

Diese Methode wird von `UpdateRegistryFromResourceD` aufgerufen, um das Registrierungs Update auszuführen.

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parameter

*lpszRes*<br/>
Ein Ressourcen Name.

*bRegister*<br/>
Gibt an, ob das Objekt registriert werden soll.

*pmapentries*<br/>
Ein Zeiger auf die Ersatz Zuordnung, die Werte speichert, die den ersetzbaren Parametern des Skripts zugeordnet sind. ATL verwendet automatisch% Module%. Informationen zur Verwendung zusätzlicher ersetzbarer Parameter [finden Sie](#addcommonrgsreplacements)unter "". Andernfalls verwenden Sie den Standardwert NULL.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Diese Methode bietet die [Implementierung von "](#updateregistryfromresourced)" für "".

##  <a name="updateregistryfromresources"></a>Skript Modul:: updateregistryfromresources

Führt das in einer angegebenen Ressource enthaltene Skript aus, um ein Objekt zu registrieren oder die Registrierung aufzuheben. Diese Methode verknüpft statisch mit der ATL-Registrierungs Komponente.

```
HRESULT WINAPI UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>Parameter

*nResID*<br/>
Eine Ressourcen-ID.

*lpszRes*<br/>
Ein Ressourcen Name.

*bRegister*<br/>
Gibt an, ob das Ressourcen Skript registriert werden soll.

*pmapentries*<br/>
Ein Zeiger auf die Ersatz Zuordnung, die Werte speichert, die den ersetzbaren Parametern des Skripts zugeordnet sind. ATL verwendet automatisch% Module%. Informationen zur Verwendung zusätzlicher ersetzbarer Parameter [finden Sie](#addcommonrgsreplacements)unter "". Andernfalls verwenden Sie den Standardwert NULL.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ähnlich wie bei "" von "" mit "" ("") `CAtlModule::UpdateRegistryFromResourceS` ": [UpdateRegistryFromResource](#updateregistryfromresourced) " mit Ausnahme von erstellt einen statischen Link zur ATL-Registrierungs Komponente

## <a name="see-also"></a>Siehe auch

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[Modul Klassen](../../atl/atl-module-classes.md)<br/>
[Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md)
