---
title: CRegKey-Klasse
ms.date: 11/04/2016
f1_keywords:
- CRegKey
- ATLBASE/ATL::CRegKey
- ATLBASE/ATL::CRegKey::CRegKey
- ATLBASE/ATL::CRegKey::Attach
- ATLBASE/ATL::CRegKey::Close
- ATLBASE/ATL::CRegKey::Create
- ATLBASE/ATL::CRegKey::DeleteSubKey
- ATLBASE/ATL::CRegKey::DeleteValue
- ATLBASE/ATL::CRegKey::Detach
- ATLBASE/ATL::CRegKey::EnumKey
- ATLBASE/ATL::CRegKey::Flush
- ATLBASE/ATL::CRegKey::GetKeySecurity
- ATLBASE/ATL::CRegKey::NotifyChangeKeyValue
- ATLBASE/ATL::CRegKey::Open
- ATLBASE/ATL::CRegKey::QueryBinaryValue
- ATLBASE/ATL::CRegKey::QueryDWORDValue
- ATLBASE/ATL::CRegKey::QueryGUIDValue
- ATLBASE/ATL::CRegKey::QueryMultiStringValue
- ATLBASE/ATL::CRegKey::QueryQWORDValue
- ATLBASE/ATL::CRegKey::QueryStringValue
- ATLBASE/ATL::CRegKey::QueryValue
- ATLBASE/ATL::CRegKey::RecurseDeleteKey
- ATLBASE/ATL::CRegKey::SetBinaryValue
- ATLBASE/ATL::CRegKey::SetDWORDValue
- ATLBASE/ATL::CRegKey::SetGUIDValue
- ATLBASE/ATL::CRegKey::SetKeySecurity
- ATLBASE/ATL::CRegKey::SetKeyValue
- ATLBASE/ATL::CRegKey::SetMultiStringValue
- ATLBASE/ATL::CRegKey::SetQWORDValue
- ATLBASE/ATL::CRegKey::SetStringValue
- ATLBASE/ATL::CRegKey::SetValue
- ATLBASE/ATL::CRegKey::m_hKey
- ATLBASE/ATL::CRegKey::m_pTM
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
ms.openlocfilehash: 1215c66f1f40cfbc96b813d4eb5084f07698bc01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278084"
---
# <a name="cregkey-class"></a>CRegKey-Klasse

Diese Klasse stellt Methoden zum Bearbeiten der Einträge in der systemregistrierung.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CRegKey
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CRegKey::CRegKey](#cregkey)|Der Konstruktor.|
|[CRegKey::~CRegKey](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRegKey::Attach](#attach)|Rufen Sie diese Methode, um eine zu öffnende HKEY Anfügen der `CRegKey` Objekt durch Festlegen der [M_hKey](#m_hkey) Member-Handle für `hKey`.|
|[CRegKey::Close](#close)|Rufen Sie diese Methode zum Freigeben der [M_hKey](#m_hkey) Element behandeln, und es auf NULL festgelegt.|
|[CRegKey::Create](#create)|Rufen Sie diese Methode zum Erstellen von des angegebenen Schlüssels aus, wenn er als der Unterschlüssel nicht vorhanden ist `hKeyParent`.|
|[CRegKey::DeleteSubKey](#deletesubkey)|Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung zu entfernen.|
|[CRegKey::DeleteValue](#deletevalue)|Rufen Sie diese Methode zum Entfernen eines Wertfelds aus [M_hKey](#m_hkey).|
|[CRegKey::Detach](#detach)|Rufen Sie diese Methode zum Trennen der [M_hKey](#m_hkey) Member-Handle aus der `CRegKey` Objekt, und legen `m_hKey` auf NULL.|
|[CRegKey::EnumKey](#enumkey)|Rufen Sie diese Methode zum Aufzählen der Unterschlüssel des Registrierungsschlüssels öffnen.|
|[CRegKey::Flush](#flush)|Rufen Sie diese Methode, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung zu schreiben.|
|[CRegKey::GetKeySecurity](#getkeysecurity)|Rufen Sie diese Methode, um eine Kopie der Sicherheitsbeschreibung, die Schutz der geöffneten Registrierungsschlüssels abzurufen.|
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Diese Methode benachrichtigt den Aufrufer über Änderungen an den Attributen oder den Inhalt des Registrierungsschlüssels öffnen.|
|[CRegKey::Open](#open)|Rufen Sie diese Methode, um den angegebenen Schlüssel zu öffnen, und legen [M_hKey](#m_hkey) an das Handle dieses Schlüssels.|
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Rufen Sie diese Methode zum Abrufen der binäre Daten für einen angegebenen Wert.|
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Rufen Sie diese Methode zum Abrufen der DWORD-Daten für einen angegebenen Wert.|
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Rufen Sie diese Methode zum Abrufen der GUID-Daten für einen angegebenen Wert.|
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Rufen Sie diese Methode zum Abrufen der mehrteilige Daten für einen angegebenen Wert.|
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Rufen Sie diese Methode zum Abrufen der QWORD-Daten für einen angegebenen Wert.|
|[CRegKey::QueryStringValue](#querystringvalue)|Rufen Sie diese Methode zum Abrufen der Zeichenfolgendaten für einen angegebenen Wert.|
|[CRegKey::QueryValue](#queryvalue)|Rufen Sie diese Methode zum Abrufen der Daten für das Feld mit dem angegebenen Wert [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und als ATL_DEPRECATED gekennzeichnet sind.|
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Rufen Sie diese Methode zum Entfernen des angegebenen Schlüssels aus der Registrierung und beliebige Unterschlüssel explizit entfernen.|
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Rufen Sie diese Methode, um den binären Wert des Registrierungsschlüssels festlegen.|
|[CRegKey::SetDWORDValue](#setdwordvalue)|Rufen Sie diese Methode, um den DWORD-Wert des Registrierungsschlüssels festlegen.|
|[CRegKey::SetGUIDValue](#setguidvalue)|Rufen Sie diese Methode, um den GUID-Wert des Registrierungsschlüssels festlegen.|
|[CRegKey::SetKeySecurity](#setkeysecurity)|Rufen Sie diese Methode, um die Sicherheit des Registrierungsschlüssels festgelegt werden.|
|[CRegKey::SetKeyValue](#setkeyvalue)|Rufen Sie diese Methode zum Speichern von Daten in einem Feld angegebenen Wert, der einem angegebenen Schlüssel.|
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Rufen Sie diese Methode, um die mehrteilige Zeichenfolge des Registrierungsschlüssels festgelegt.|
|[CRegKey::SetQWORDValue](#setqwordvalue)|Rufen Sie diese Methode aus, um den QWORD-Wert des Registrierungsschlüssels festzulegen.|
|[CRegKey::SetStringValue](#setstringvalue)|Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.|
|[CRegKey::SetValue](#setvalue)|Rufen Sie diese Methode zum Speichern von Daten in das Feld mit dem angegebenen Wert [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und als ATL_DEPRECATED gekennzeichnet sind.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CRegKey::operator HKEY](#operator_hkey)|Konvertiert eine `CRegKey` Objekt, das ein HKEY.|
|[CRegKey::operator =](#operator_eq)|Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|Ein Handle des zugeordneten Registrierungsschlüssels enthält den `CRegKey` Objekt.|
|[CRegKey::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|

## <a name="remarks"></a>Hinweise

`CRegKey` Stellt Methoden zum Erstellen und Löschen von Schlüsseln und Werten in der systemregistrierung. Die Registrierung enthält einen installationsspezifischen Satz mit Definitionen für die Systemkomponenten, z. B. softwareversionsnummern, logische, physische-Zuordnungen von installierten Hardware und COM-Objekte.

`CRegKey` Stellt eine Programmierschnittstelle für die Registrierung des Systems für einen bestimmten Computer an. Beispielsweise rufen Sie zum Öffnen eines bestimmten Registrierungsschlüssel statt `CRegKey::Open`. Rufen Sie zum Abrufen oder Ändern eines Datenwerts, `CRegKey::QueryValue` oder `CRegKey::SetValue`bzw. Rufen Sie zum Schließen eines Schlüssels `CRegKey::Close`.

Wenn Sie einen Schlüssel schließen, werden die Registrierungsdaten (geleert) auf die Festplatte geschrieben. Dieser Vorgang kann einige Sekunden dauern. Wenn Ihre Anwendung Registrierungsdaten explizit auf die Festplatte schreiben muss, können Sie rufen die [wurde von RegFlushKey](/windows/desktop/api/winreg/nf-winreg-regflushkey) Win32-Funktion. Allerdings `RegFlushKey` viele Systemressourcen verwendet und nur wenn unbedingt nötig aufgerufen werden soll.

> [!IMPORTANT]
>  Alle Methoden, mit denen den Aufrufer an einen Registrierungsspeicherort haben die Möglichkeit zum Lesen von Daten, die nicht vertrauenswürdig ist. Verwenden Sie die Methoden, mit denen der [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) sollten berücksichtigen, die diese Funktion nicht explizit Zeichenfolgen die NULL behandelt-terminiert sind. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="attach"></a>  CRegKey::Attach

Rufen Sie diese Methode, um eine zu öffnende HKEY Anfügen der `CRegKey` Objekt durch Festlegen der [M_hKey](#m_hkey) Member-Handle für *hKey*.

```
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Das Handle eines Registrierungsschlüssels.

### <a name="remarks"></a>Hinweise

`Attach` Wenn bestätigt `m_hKey` ungleich NULL ist.

##  <a name="close"></a>  CRegKey::Close

Rufen Sie diese Methode zum Freigeben der [M_hKey](#m_hkey) Element behandeln, und es auf NULL festgelegt.

```
LONG Close() throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS; Andernfalls wird einen Fehlerwert zurückgegeben.

##  <a name="create"></a>  CRegKey::Create

Rufen Sie diese Methode zum Erstellen von des angegebenen Schlüssels aus, wenn er als der Unterschlüssel nicht vorhanden ist *hKeyParent*.

```
LONG Create(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPTSTR lpszClass = REG_NONE,
    DWORD dwOptions = REG_OPTION_NON_VOLATILE,
    REGSAM samDesired = KEY_READ | KEY_WRITE,
    LPSECURITY_ATTRIBUTES lpSecAttr = NULL,
    LPDWORD lpdwDisposition = NULL) throw();
```

### <a name="parameters"></a>Parameter

*hKeyParent*<br/>
Das Handle des ein geöffneter Schlüssel.

*lpszKeyName*<br/>
Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des *hKeyParent*.

*lpszClass*<br/>
Gibt die Klasse des Schlüssels erstellt oder geöffnet werden. Der Standardwert ist REG_NONE.

*dwOptions*<br/>
Optionen für den Schlüssel. Der Standardwert ist REG_OPTION_NON_VOLATILE. Eine Liste der möglichen Werte und Beschreibungen, finden Sie unter ["RegCreateKeyEx" dienen](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) im Windows SDK.

*samDesired*<br/>
Der Sicherheitszugriff für den Schlüssel. Der Standardwert ist KEY_READ &#124; KEY_WRITE. Eine Liste der möglichen Werte und Beschreibungen, finden Sie unter `RegCreateKeyEx`.

*lpSecAttr*<br/>
Ein Zeiger auf eine [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die angibt, ob das Handle des Schlüssels von einem untergeordneten Prozess geerbt werden kann. Standardmäßig ist dieser Parameter NULL (d. h., die das Handle nicht geerbt werden kann).

*lpdwDisposition*<br/>
[out] Wenn nicht NULL ist, ruft Sie ab entweder REG_CREATED_NEW_KEY (wenn der Schlüssel nicht vorhanden war und erstellt wurde) oder REG_OPENED_EXISTING_KEY, (wenn der Schlüssel vorhanden war, und es geöffnet wurde).

### <a name="return-value"></a>Rückgabewert

Im Erfolgsfall gibt ERROR_SUCCESS und öffnet den Schlüssel. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

`Create` Legt die [M_hKey](#m_hkey) Member auf das Handle dieses Schlüssels.

##  <a name="cregkey"></a>  CRegKey::CRegKey

Der Konstruktor.

```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Ein Verweis auf ein `CRegKey`-Objekt.

*hKey*<br/>
Ein Handle für einen Registrierungsschlüssel.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Erstellt ein neues `CRegKey`-Objekt. Das Objekt kann erstellt werden, aus einer vorhandenen `CRegKey` -Objekt, oder aus einem Handle für einen Registrierungsschlüssel.

##  <a name="dtor"></a>  CRegKey::~CRegKey

Der Destruktor.

```
~CRegKey() throw();
```

### <a name="remarks"></a>Hinweise

Die Versionen der Destruktor `m_hKey`.

##  <a name="deletesubkey"></a>  CRegKey::DeleteSubKey

Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung zu entfernen.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Parameter

*lpszSubKey*<br/>
Gibt den Namen des Schlüssels zu löschen. Dieser Name muss ein Unterschlüssel des [M_hKey](#m_hkey).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

`DeleteSubKey` einen Schlüssel, der keine Unterschlüssel verfügt, können nur gelöscht werden. Wenn der Schlüssel Unterschlüssel verfügt, rufen Sie [RecurseDeleteKey](#recursedeletekey) stattdessen.

##  <a name="deletevalue"></a>  CRegKey::DeleteValue

Rufen Sie diese Methode zum Entfernen eines Wertfelds aus [M_hKey](#m_hkey).

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Parameter

*lpszValue*<br/>
Gibt das Wertfeld "zu entfernen.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

##  <a name="detach"></a>  CRegKey::Detach

Rufen Sie diese Methode zum Trennen der [M_hKey](#m_hkey) Member-Handle aus der `CRegKey` Objekt, und legen `m_hKey` auf NULL.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Der zu öffnende HKEY zugeordneten der `CRegKey` Objekt.

##  <a name="enumkey"></a>  CRegKey::EnumKey

Rufen Sie diese Methode zum Aufzählen der Unterschlüssel des Registrierungsschlüssels öffnen.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
Der Unterschlüssel Index. Dieser Parameter muss 0 (null), für den ersten Aufruf, und klicken Sie dann für nachfolgende Aufrufe erhöht.

*pszName*<br/>
Zeiger auf einen Puffer, der den Namen der Unterschlüssel, einschließlich des abschließenden Zeichens Null empfängt. Nur der Name des Unterschlüssels wird in den Puffer, die nicht die vollständige Hierarchie kopiert.

*pnNameLength*<br/>
Zeiger auf eine Variable, die die Größe in TCHARs, der vom angegebenen Puffer gibt an, die *PszName* Parameter. Diese Größe sollte das abschließende Nullzeichen enthalten. Wenn die Methode zurückgegeben, die Variable verweist *PnNameLength* enthält die Anzahl der Zeichen im Puffer gespeichert. Die Anzahl die zurückgegebenen schließt nicht das abschließende Nullzeichen.

*pftLastWriteTime*<br/>
Zeiger auf eine Variable, die die Zeit empfängt der aufgelistete Unterschlüssel des letzten Schreibvorgangs in.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Rufen Sie zum Aufzählen der Unterschlüssel `CRegKey::EnumKey` mit dem Index 0 (null). Erhöhen Sie den Indexwert, und wiederholen Sie, bis die Methode ERROR_NO_MORE_ITEMS zurückgibt. Weitere Informationen finden Sie unter [RegEnumKeyEx](/windows/desktop/api/winreg/nf-winreg-regenumkeyexa) im Windows SDK.

##  <a name="flush"></a>  CRegKey::Flush

Rufen Sie diese Methode, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung zu schreiben.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [RegEnumFlush](/windows/desktop/api/winreg/nf-winreg-regflushkey) im Windows SDK.

##  <a name="getkeysecurity"></a>  CRegKey::GetKeySecurity

Rufen Sie diese Methode, um eine Kopie der Sicherheitsbeschreibung, die Schutz der geöffneten Registrierungsschlüssels abzurufen.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Parameter

*si*<br/>
Die [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) -Wert, der die angeforderten Informationen an.

*psd*<br/>
Ein Zeiger auf einen Puffer, der eine Kopie der angeforderten Sicherheitsbeschreibung erhält.

*pnBytes*<br/>
Die Größe in Bytes, der die Puffer, der auf *Psd*.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich NULL in WINERROR definiert ist. H.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [RegGetKeySecurity](/windows/desktop/api/winreg/nf-winreg-reggetkeysecurity).

##  <a name="m_hkey"></a>  CRegKey::m_hKey

Ein Handle des zugeordneten Registrierungsschlüssels enthält den `CRegKey` Objekt.

```
HKEY m_hKey;
```

##  <a name="m_ptm"></a>  CRegKey::m_pTM

Zeiger auf eine `CAtlTransactionManager` Objekt.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Hinweise

##  <a name="notifychangekeyvalue"></a>  CRegKey::NotifyChangeKeyValue

Diese Methode benachrichtigt den Aufrufer über Änderungen an den Attributen oder den Inhalt des Registrierungsschlüssels öffnen.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>Parameter

*bWatchSubtree*<br/>
Gibt ein Flag, das angibt, ob Änderungen in den angegebenen Schlüssel und alle seine Unterschlüssel oder nur in den angegebenen Schlüssel zu melden. Wenn dieser Parameter TRUE ist, meldet die Methode Änderungen in den Schlüssel und dessen Unterschlüssel an. Wenn der Parameter auf "false" ist, meldet die Methode Änderungen ausschließlich in den Schlüssel an.

*dwNotifyFilter*<br/>
Gibt an, der ein Satz von Flags, die steuern, welche Änderungen gemeldet werden sollen. Dieser Parameter kann eine Kombination der folgenden Werte sein:

|Wert|Bedeutung|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|Benachrichtigen Sie den Aufrufer, wenn Sie ein Unterschlüssel hinzugefügt oder gelöscht wird.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|Benachrichtigt den Aufrufer der Änderungen auf die Attribute des Schlüssels, z. B. die Informationen der Sicherheitsbeschreibung.|
|REG_NOTIFY_CHANGE_LAST_SET|Benachrichtigt den Aufrufer der Änderungen auf einen Wert des Schlüssels an. Dies kann einschließen, hinzufügen oder Löschen einen Wert oder einen vorhandenen Wert ändern.|
|REG_NOTIFY_CHANGE_SECURITY|Benachrichtigt den Aufrufer der Änderungen an die Sicherheitsbeschreibung für den Schlüssel an.|

*hEvent*<br/>
Handle für ein Ereignis. Wenn die *bAsync* -Parameter ist "true", die Methode sofort zurückgegeben wird und Änderungen werden durch Signalisieren das Ereignis gemeldet. Wenn *bAsync* ist "false", *hEvent* wird ignoriert.

*bAsync*<br/>
Gibt ein Flag, das angibt, wie die Methode Änderungen meldet. Wenn dieser Parameter TRUE ist, wird die Methode sofort zurückgegeben, und meldet Änderungen durch das angegebene Ereignis zu signalisieren. Wenn dieser Parameter auf false festgelegt ist, wird die Methode nicht beendet, bis eine Änderung vorgenommen wurde. Wenn *hEvent* gibt kein gültiges Ereignis, das *bAsync* Parameter darf nicht "true" sein.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Methode benachrichtigt den Aufrufer nicht, wenn der angegebene Schlüssel gelöscht wird.

Weitere Informationen und ein Beispielprogramm, finden Sie unter [RegNotifyChangeKeyValue](/windows/desktop/api/winreg/nf-winreg-regnotifychangekeyvalue).

##  <a name="open"></a>  CRegKey::Open

Rufen Sie diese Methode, um den angegebenen Schlüssel zu öffnen, und legen [M_hKey](#m_hkey) an das Handle dieses Schlüssels.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>Parameter

*hKeyParent*<br/>
Das Handle des ein geöffneter Schlüssel.

*lpszKeyName*<br/>
Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des *hKeyParent*.

*samDesired*<br/>
Der Sicherheitszugriff für den Schlüssel. Der Standardwert ist KEY_ALL_ACCESS. Eine Liste der möglichen Werte und Beschreibungen, finden Sie unter ["RegCreateKeyEx" dienen](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS; Andernfalls definiert ein Fehlerwert ungleich NULL-in WINERROR. H.

### <a name="remarks"></a>Hinweise

Wenn die *LpszKeyName* -Parameter ist NULL oder verweist auf eine leere Zeichenfolge, `Open` öffnet ein neues Handle für den Schlüssel identifizierte *hKeyParent*, wird jeder zuvor geöffnete Handle nicht geschlossen.

Im Gegensatz zu [CRegKey::Create](#create), `Open` wird nicht den angegebenen Schlüssel erstellt, wenn er nicht vorhanden ist.

##  <a name="operator_hkey"></a>  CRegKey::operator HKEY

Konvertiert eine `CRegKey` Objekt, das ein HKEY.

```
operator HKEY() const throw();
```

##  <a name="operator_eq"></a>  CRegKey::operator =

Zuweisungsoperator.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüssel zu kopieren.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den neuen Schlüssel.

### <a name="remarks"></a>Hinweise

Dieser Operator wird *Schlüssel* aus der aktuellen Objekt und weist sie der `CRegKey` stattdessen Objekt.

##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue

Rufen Sie diese Methode zum Abrufen der binäre Daten für einen angegebenen Wert.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.

*pValue*<br/>
Zeiger auf einen Puffer, der den Wert der Daten empfängt.

*pnBytes*<br/>
Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt auf die von der *pValue* Parameter. Wenn die Methode zurückgibt, enthält diese Variable die Größe der Daten in den Puffer kopiert.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird die ERROR_SUCCESS zurückgegeben. Wenn die Methode zum Lesen eines Werts fehlschlägt, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, die auf die verwiesen wird, nicht vom Typ REG_BINARY ist, wird die ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Weitere Details.

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Funktion, die von dieser Methode verwendet nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue

Rufen Sie diese Methode zum Abrufen der DWORD-Daten für einen angegebenen Wert.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.

*dwValue*<br/>
Zeiger auf einen Puffer, der den DWORD-Wert empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird die ERROR_SUCCESS zurückgegeben. Wenn die Methode zum Lesen eines Werts fehlschlägt, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, die auf die verwiesen wird, nicht REG_DWORD-Datentyp ist, wird die ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Weitere Details.

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Funktion, die von dieser Methode verwendet nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue

Rufen Sie diese Methode zum Abrufen der GUID-Daten für einen angegebenen Wert.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.

*guidValue*<br/>
Zeiger auf eine Variable, die GUID empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird die ERROR_SUCCESS zurückgegeben. Wenn die Methode zum Lesen eines Werts fehlschlägt, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, die auf die verwiesen wird, keine gültige GUID ist, wird die ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `CRegKey::QueryStringValue` und konvertiert die Zeichenfolge in eine GUID mit [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring).

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist.

##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue

Rufen Sie diese Methode zum Abrufen der mehrteilige Daten für einen angegebenen Wert.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.

*pszValue*<br/>
Zeiger auf einen Puffer, der die mehrteilige Daten empfängt. Eine mehrteilige Zeichenfolge ist, ein Array mit Null endende Zeichenfolgen, durch zwei Null-Zeichen beendet wird.

*pnChars*<br/>
Die Größe in TCHARs, der die Puffer, der auf *PszValue*. Wenn die Methode zurückgibt, *PnChars* enthält die Größe in TCHARs, der die mehrteilige Zeichenfolge abgerufen, darunter ein abschließendes Nullzeichen.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird die ERROR_SUCCESS zurückgegeben. Wenn die Methode zum Lesen eines Werts fehlschlägt, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, die auf die verwiesen wird, nicht vom Typ REG_MULTI_SZ ist, wird die ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Weitere Details.

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Funktion, die von dieser Methode verwendet nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue

Rufen Sie diese Methode zum Abrufen der QWORD-Daten für einen angegebenen Wert.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.

*qwValue*<br/>
Zeiger auf einen Puffer, der als QWORD empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird die ERROR_SUCCESS zurückgegeben. Wenn die Methode zum Lesen eines Werts fehlschlägt, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, die auf die verwiesen wird, nicht vom Typ REG_QWORD ist, wird die ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Weitere Details.

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Funktion, die von dieser Methode verwendet nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue

Rufen Sie diese Methode zum Abrufen der Zeichenfolgendaten für einen angegebenen Wert.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.

*pszValue*<br/>
Zeiger auf einen Puffer, der die Zeichenfolgendaten empfängt.

*pnChars*<br/>
Die Größe in TCHARs, der die Puffer, der auf *PszValue*. Wenn die Methode zurückgibt, *PnChars* enthält die Größe in TCHARs, der die Zeichenfolge abgerufen, darunter ein abschließendes Nullzeichen.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird die ERROR_SUCCESS zurückgegeben. Wenn die Methode zum Lesen eines Werts fehlschlägt, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, die auf die verwiesen wird, nicht des Typs REG_SZ ist, wird die ERROR_INVALID_DATA zurückgegeben. Wenn der Methodenrückgabe ERROR_MORE_DATA zurück, *PnChars* gleich NULL, nicht die erforderliche Puffergröße in Byte.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Weitere Details.

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) Funktion, die von dieser Methode verwendet nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

##  <a name="queryvalue"></a>  CRegKey::QueryValue

Rufen Sie diese Methode zum Abrufen der Daten für das Feld mit dem angegebenen Wert [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und als ATL_DEPRECATED gekennzeichnet sind.

```
LONG QueryValue(
    LPCTSTR pszValueName,
    DWORD* pdwType,
    void* pData,
    ULONG* pnBytes) throw();

ATL_DEPRECATED LONG QueryValue(
    DWORD& dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG QueryValue(
    LPTSTR szValue,
    LPCTSTR lpszValueName,
    DWORD* pdwCount);
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage. Wenn *PszValueName* ist NULL oder eine leere Zeichenfolge "", die Methode ruft den Typ ab und Daten für den Schlüssel des unbenannte oder default-Wert, sofern vorhanden.

*pdwType*<br/>
Zeiger auf eine Variable, die einen Code, der angibt, der des Typs der in den angegebenen Wert gespeicherten Daten empfängt. Die *PdwType* Parameter kann NULL sein, wenn der Code nicht erforderlich ist.

*pData*<br/>
Zeiger auf einen Puffer, der den Wert der Daten empfängt. Dieser Parameter kann NULL sein, wenn die Daten nicht erforderlich ist.

*pnBytes*<br/>
Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt auf die von der *pData* Parameter. Wenn die Methode zurückgibt, wird diese Variable enthält die Größe der Daten kopiert *pData.*

*dwValue*<br/>
Der Wert des Felds numerische Daten.

*lpszValueName*<br/>
Gibt das Wertfeld "abgefragt werden.

*szValue*<br/>
Zeichenfolgendaten mit dem Wert des Felds.

*pdwCount*<br/>
Die Größe der Daten der Zeichenfolge. Sein Wert auf die Größe des ursprünglich festgelegt wird die *szValue einen* Puffer.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS; definiert, andernfalls ein Fehlercode ungleich NULL in WINERROR ein. H.

### <a name="remarks"></a>Hinweise

Die beiden ursprünglichen Versionen der `QueryValue` werden nicht mehr unterstützt und als ATL_DEPRECATED gekennzeichnet sind. Der Compiler gibt eine Warnung aus, wenn diese Formulare verwendet werden.

Die verbleibenden Methodenaufrufe RegQueryValueEx.

> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus behandelt die RegQueryValueEx-Funktion, die von dieser Methode verwendeten explizit Zeichenfolgen nicht die NULL-terminiert sind. Beide Bedingungen sollten vom aufrufenden Code überprüft werden.

##  <a name="recursedeletekey"></a>  CRegKey::RecurseDeleteKey

Rufen Sie diese Methode zum Entfernen des angegebenen Schlüssels aus der Registrierung und beliebige Unterschlüssel explizit entfernen.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Parameter

*lpszKey*<br/>
Gibt den Namen des Schlüssels zu löschen. Dieser Name muss ein Unterschlüssel des [M_hKey](#m_hkey).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS; Andernfalls definiert ein Fehlerwert ungleich NULL-in WINERROR. H.

### <a name="remarks"></a>Hinweise

Wenn der Schlüssel Unterschlüssel verfügt, müssen Sie diese Methode, um den Schlüssel löschen aufrufen.

##  <a name="setbinaryvalue"></a>  CRegKey::SetBinaryValue

Rufen Sie diese Methode, um den binären Wert des Registrierungsschlüssels festlegen.

```
LONG SetBinaryValue(
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*pValue*<br/>
Zeiger auf einen Puffer mit den Daten, die mit dem angegebenen Wertnamen gespeichert werden.

*nBytes*<br/>
Gibt die Größe in Bytes, die Informationen auf die von der *pValue* Parameter.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) auf den Wert in der Registrierung schreiben.

##  <a name="setdwordvalue"></a>  CRegKey::SetDWORDValue

Rufen Sie diese Methode, um den DWORD-Wert des Registrierungsschlüssels festlegen.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*dwValue*<br/>
Die DWORD-Daten mit dem angegebenen Wertnamen gespeichert werden muss.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) auf den Wert in der Registrierung schreiben.

##  <a name="setguidvalue"></a>  CRegKey::SetGUIDValue

Rufen Sie diese Methode, um den GUID-Wert des Registrierungsschlüssels festlegen.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*guidValue*<br/>
Verweis auf die GUID, der mit dem angegebenen Wertnamen gespeichert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode nutzt `CRegKey::SetStringValue` und konvertiert die GUID in eine Zeichenfolge mithilfe ["stringfromguid2"](/windows/desktop/api/combaseapi/nf-combaseapi-stringfromguid2).

##  <a name="setkeyvalue"></a>  CRegKey::SetKeyValue

Rufen Sie diese Methode zum Speichern von Daten in einem Feld angegebenen Wert, der einem angegebenen Schlüssel.

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>Parameter

*lpszKeyName*<br/>
Gibt den Namen des Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des [M_hKey](#m_hkey).

*lpszValue*<br/>
Gibt an, die Daten gespeichert werden. Dieser Parameter muss ungleich NULL sein.

*lpszValueName*<br/>
Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird sie hinzugefügt.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS; definiert, andernfalls ein Fehlercode ungleich NULL in WINERROR ein. H.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Erstellen oder öffnen Sie die *LpszKeyName* gedrückt, und speichern Sie die *LpszValue* Daten in die *LpszValueName* Feld "Wert".

##  <a name="setkeysecurity"></a>  CRegKey::SetKeySecurity

Rufen Sie diese Methode, um die Sicherheit des Registrierungsschlüssels festgelegt werden.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Parameter

*si*<br/>
Gibt die Komponenten der Sicherheitsbeschreibung fest. Der Wert eine Kombination der folgenden Werte sind möglich:

|Wert|Bedeutung|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Legt die DACL (des Schlüssels discretionary Access Control List) fest. Der Schlüssel muss über WRITE_DAC-Zugriff, oder der aufrufende Prozess muss den Besitzer des Objekts sein.|
|GROUP_SECURITY_INFORMATION|Legt fest, primäre Gruppe Sicherheits-ID (SID) des Schlüssels. Der Schlüssel muss WRITE_OWNER Zugriffsrechte besitzen, oder der aufrufende Prozess muss den Besitzer des Objekts sein.|
|OWNER_SECURITY_INFORMATION|Legt fest, Besitzer-SID des Schlüssels. Der Schlüssel muss WRITE_OWNER Zugriff, oder der aufrufende Prozess muss den Besitzer des Objekts oder die Berechtigung zum SE_TAKE_OWNERSHIP_NAME aktiviert.|
|SACL_SECURITY_INFORMATION|Legt fest, der mit dem Schlüssel System Access Control List (SACL). Der Schlüssel muss es sich um ACCESS_SYSTEM_SECURITY Zugriff haben. Der richtige Weg, um diesen Zugriff zu erhalten ist zum Aktivieren der SE_SECURITY_NAME [Berechtigungen](/windows/desktop/secauthz/privileges) in der aktuellen Zugriffstoken des Aufrufers, öffnen Sie das Handle für den ACCESS_SYSTEM_SECURITY Zugriff, und deaktivieren Sie die Berechtigung.|

*psd*<br/>
Zeiger auf eine [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-_security_descriptor) Struktur, die Attribute für die Sicherheit für den angegebenen Schlüssel festlegen angibt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Legt Attribute für die Sicherheit des Schlüssels fest. Finden Sie unter [RegSetKeySecurity](/windows/desktop/api/winreg/nf-winreg-regsetkeysecurity) Weitere Details.

##  <a name="setmultistringvalue"></a>  CRegKey::SetMultiStringValue

Rufen Sie diese Methode, um die mehrteilige Zeichenfolge des Registrierungsschlüssels festgelegt.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*pszValue*<br/>
Zeiger auf die mehrteilige Zeichenfolgen mit dem angegebenen Wertnamen zu speichernden Daten. Eine mehrteilige Zeichenfolge ist, ein Array mit Null endende Zeichenfolgen, durch zwei Null-Zeichen beendet wird.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) auf den Wert in der Registrierung schreiben.

##  <a name="setqwordvalue"></a>  CRegKey::SetQWORDValue

Rufen Sie diese Methode aus, um den QWORD-Wert des Registrierungsschlüssels festzulegen.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*qwValue*<br/>
Die QWORD-Daten mit dem angegebenen Wertnamen gespeichert werden muss.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) auf den Wert in der Registrierung schreiben.

##  <a name="setstringvalue"></a>  CRegKey::SetStringValue

Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.

```
LONG SetStringValue(
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*pszValue*<br/>
Zeiger zu den mit dem angegebenen Wertnamen zu speichernden Zeichenfolgendaten.

*dwType*<br/>
Der Typ der Zeichenfolge, die in die Registrierung geschrieben werden muss: entweder REG_SZ (Standard) oder REG_EXPAND_SZ (für mehrteiligen Zeichenfolgen).

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) auf den Wert in der Registrierung schreiben.

##  <a name="setvalue"></a>  CRegKey::SetValue

Rufen Sie diese Methode zum Speichern von Daten in das Feld mit dem angegebenen Wert [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und als ATL_DEPRECATED gekennzeichnet sind.

```
LONG SetValue(
    LPCTSTR pszValueName,
    DWORD dwType,
    const void* pValue,
    ULONG nBytes) throw();

static LONG WINAPI SetValue(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL);

ATL_DEPRECATED LONG SetValue(
    DWORD dwValue,
    LPCTSTR lpszValueName);

ATL_DEPRECATED LONG SetValue(
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL,
    bool bMulti = false,
    int nValueLen = -1);
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn Sie ein Wert mit diesem Namen nicht bereits im Schlüssel vorhanden ist, wird die Methode auf den Schlüssel. Wenn *PszValueName* ist NULL oder eine leere Zeichenfolge "", die-Methode legt den Typ und die Daten für den Schlüssel des unbenannten Werts oder Standardwerts.

*dwType*<br/>
Gibt einen Code, der angibt, der des Typs der Daten, verweist der *pValue* Parameter.

*pValue*<br/>
Zeiger auf einen Puffer mit den Daten, die mit dem angegebenen Wertnamen gespeichert werden.

*nBytes*<br/>
Gibt die Größe in Bytes, die Informationen auf die von der *pValue* Parameter. Wenn die Daten des Typs REG_SZ, REG_EXPAND_SZ oder REG_MULTI_SZ, *nBytes* muss die Größe des beendenden Null-Zeichens enthalten.

*hKeyParent*<br/>
Das Handle des ein geöffneter Schlüssel.

*lpszKeyName*<br/>
Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des *hKeyParent*.

*lpszValue*<br/>
Gibt an, die Daten gespeichert werden. Dieser Parameter muss ungleich NULL sein.

*lpszValueName*<br/>
Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird sie hinzugefügt.

*dwValue*<br/>
Gibt an, die Daten gespeichert werden.

*bMulti*<br/>
Wenn "false" gibt an, dass die Zeichenfolge des Typs REG_SZ. True gibt an, dass die Zeichenfolge eine mehrteilige Zeichenfolge vom Typ REG_MULTI_SZ ist.

*nValueLen*<br/>
Wenn *bMulti* ist "true" *nValueLen* die Länge der *LpszValue* Zeichenfolge in Zeichen. Wenn *bMulti* ist "false", der Wert-1 gibt an, dass die Methode die Länge automatisch berechnet wird.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS; definiert, andernfalls ein Fehlercode ungleich NULL in WINERROR ein. H.

### <a name="remarks"></a>Hinweise

Die beiden ursprünglichen Versionen der `SetValue` als ATL_DEPRECATED gekennzeichnet sind, und sollte nicht mehr verwendet werden. Der Compiler gibt eine Warnung aus, wenn diese Formulare verwendet werden.

Die dritte Methodenaufrufe [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa).

## <a name="see-also"></a>Siehe auch

[DCOM-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
