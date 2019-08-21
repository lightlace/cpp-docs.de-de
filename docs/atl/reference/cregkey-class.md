---
title: Klasse "-Schlüssel"
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
ms.openlocfilehash: bce5a16dd8d6564b6a0d3fa0344fe5cb2303764f
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915794"
---
# <a name="cregkey-class"></a>Klasse "-Schlüssel"

Diese Klasse stellt Methoden zum Bearbeiten von Einträgen in der Systemregistrierung bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

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
|[CRegKey::Attach](#attach)|Mit dieser Methode können Sie einen HKEY an das `CRegKey` -Objekt anfügen, indem Sie das `hKey` [m_hKey](#m_hkey) -Member-Handle auf festlegen.|
|[CRegKey::Close](#close)|Ruft diese Methode auf, um das [m_hKey](#m_hkey) -Element Handle freizugeben und auf NULL festzulegen.|
|[CRegKey::Create](#create)|Rufen Sie diese Methode auf, um den angegebenen Schlüssel zu erstellen, wenn er nicht als Unterschlüssel `hKeyParent`von vorhanden ist.|
|[CRegKey::DeleteSubKey](#deletesubkey)|Ruft diese Methode auf, um den angegebenen Schlüssel aus der Registrierung zu entfernen.|
|[CRegKey::DeleteValue](#deletevalue)|Diese Methode wird aufgerufen, um ein Wertfeld aus [m_hKey](#m_hkey)zu entfernen.|
|[CRegKey::Detach](#detach)|Diese Methode wird aufgerufen, um das [m_hKey](#m_hkey) -Member-Handle `CRegKey` vom-Objekt `m_hKey` zu trennen und auf NULL festzulegen.|
|[CRegKey::EnumKey](#enumkey)|Mit dieser Methode können Sie die Unterschlüssel des geöffneten Registrierungsschlüssels aufzählen.|
|[CRegKey::Flush](#flush)|Mit dieser Methode können Sie alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung schreiben.|
|[CRegKey::GetKeySecurity](#getkeysecurity)|Rufen Sie diese Methode auf, um eine Kopie der Sicherheits Beschreibung abzurufen, die den geöffneten Registrierungsschlüssel schützt.|
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Diese Methode benachrichtigt den Aufrufer über Änderungen an den Attributen oder Inhalten des geöffneten Registrierungsschlüssels.|
|[CRegKey::Open](#open)|Ruft diese Methode auf, um den angegebenen Schlüssel zu öffnen und [m_hKey](#m_hkey) auf das Handle dieses Schlüssels festzulegen.|
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Rufen Sie diese Methode auf, um die Binärdaten für einen angegebenen Wertnamen abzurufen.|
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Rufen Sie diese Methode auf, um die DWORD-Daten für einen angegebenen Wertnamen abzurufen.|
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Rufen Sie diese Methode auf, um die GUID-Daten für einen angegebenen Wertnamen abzurufen.|
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Rufen Sie diese Methode auf, um die multizeichenfolgen-Daten für einen angegebenen Wertnamen abzurufen.|
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Rufen Sie diese Methode auf, um die QWORD-Daten für einen angegebenen Wertnamen abzurufen.|
|[CRegKey::QueryStringValue](#querystringvalue)|Rufen Sie diese Methode auf, um die Zeichen folgen Daten für einen angegebenen Wertnamen abzurufen.|
|[CRegKey::QueryValue](#queryvalue)|Rufen Sie diese Methode auf, um die Daten für das angegebene Wertfeld von [m_hKey](#m_hkey)abzurufen. Frühere Versionen dieser Methode werden nicht mehr unterstützt und sind als ATL_DEPRECATED gekennzeichnet.|
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Ruft diese Methode auf, um den angegebenen Schlüssel aus der Registrierung zu entfernen und alle untergeordneten Schlüssel explizit zu entfernen.|
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Mit dieser Methode wird der binäre Wert des Registrierungsschlüssels festgelegt.|
|[CRegKey::SetDWORDValue](#setdwordvalue)|Mit dieser Methode wird der DWORD-Wert des Registrierungsschlüssels festgelegt.|
|[CRegKey::SetGUIDValue](#setguidvalue)|Mit dieser Methode können Sie den GUID-Wert des Registrierungsschlüssels festlegen.|
|[CRegKey::SetKeySecurity](#setkeysecurity)|Ruft diese Methode auf, um die Sicherheit des Registrierungsschlüssels festzulegen.|
|[CRegKey::SetKeyValue](#setkeyvalue)|Ruft diese Methode auf, um Daten in einem angegebenen Wertfeld eines angegebenen Schlüssels zu speichern.|
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Mit dieser Methode wird der mehrteilige Zeichen folgen Wert des Registrierungsschlüssels festgelegt.|
|[CRegKey::SetQWORDValue](#setqwordvalue)|Mit dieser Methode wird der QWORD-Wert des Registrierungsschlüssels festgelegt.|
|[CRegKey::SetStringValue](#setstringvalue)|Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.|
|[CRegKey::SetValue](#setvalue)|Ruft diese Methode auf, um Daten im angegebenen Wertfeld von [m_hKey](#m_hkey)zu speichern. Frühere Versionen dieser Methode werden nicht mehr unterstützt und sind als ATL_DEPRECATED gekennzeichnet.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|["Forgkey:: Operator"-HKEY](#operator_hkey)|Konvertiert ein `CRegKey` -Objekt in einen HKEY.|
|[CRegKey::operator =](#operator_eq)|Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CRegKey::m_hKey](#m_hkey)|Enthält ein Handle des dem- `CRegKey` Objekt zugeordneten Registrierungsschlüssels.|
|[CRegKey::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|

## <a name="remarks"></a>Hinweise

`CRegKey`stellt Methoden zum Erstellen und Löschen von Schlüsseln und Werten in der Systemregistrierung bereit. Die Registrierung enthält einen installationsspezifischen Satz von Definitionen für Systemkomponenten, z. b. Software Versionsnummern, logische und physische Zuordnungen von installierter Hardware und COM-Objekten.

`CRegKey`stellt eine Programmierschnittstelle für die Systemregistrierung für einen angegebenen Computer bereit. Um z `CRegKey::Open`. b. einen bestimmten Registrierungsschlüssel zu öffnen, geben Sie an. `CRegKey::QueryValue` Rufen`CRegKey::SetValue`Sie zum Abrufen oder Ändern eines Daten Werts bzw. auf. Um einen Schlüssel zu schließen, `CRegKey::Close`wird aufgerufen.

Wenn Sie einen Schlüssel schließen, werden die zugehörigen Registrierungsdaten auf die Festplatte geschrieben (geleert). Dieser Vorgang kann mehrere Sekunden dauern. Wenn Ihre Anwendung Registrierungsdaten explizit auf die Festplatte schreiben muss, können Sie die Win32-Funktion " [regflushkey](/windows/desktop/api/winreg/nf-winreg-regflushkey) " aufrufen. Verwendet jedoch `RegFlushKey` viele Systemressourcen und sollte nur aufgerufen werden, wenn dies unbedingt erforderlich ist.

> [!IMPORTANT]
>  Alle Methoden, mit denen der Aufrufer einen Registrierungs Speicherort angeben kann, können Daten lesen, die nicht vertrauenswürdig sind. Bei Methoden, die [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) verwenden, muss berücksichtigt werden, dass diese Funktion keine Zeichen folgen explizit behandelt, die NULL-Werte haben. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="attach"></a>"Kregkey:: Attach"

Mit dieser Methode können Sie einen HKEY an das `CRegKey` -Objekt anfügen, indem Sie das [m_hKey](#m_hkey) -Member-Handle auf *HKEY*festlegen.

```
void Attach(HKEY hKey) throw();
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Das Handle eines Registrierungsschlüssels.

### <a name="remarks"></a>Hinweise

`Attach`bestätigt, wenn `m_hKey` nicht NULL ist.

##  <a name="close"></a>"Kregkey:: Close"

Ruft diese Methode auf, um das [m_hKey](#m_hkey) -Element Handle freizugeben und auf NULL festzulegen.

```
LONG Close() throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. Andernfalls wird ein Fehlerwert zurückgegeben.

##  <a name="create"></a>Create-Key:: Create

Rufen Sie diese Methode auf, um den angegebenen Schlüssel zu erstellen, wenn er nicht als Unterschlüssel von *hkeyparent*vorhanden ist.

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
Das Handle eines geöffneten Schlüssels.

*lpszKeyName*<br/>
Gibt den Namen eines zu erstellenden oder zu öffnenden Schlüssels an. Dieser Name muss ein Unterschlüssel von *hkeyparent*sein.

*lpszClass*<br/>
Gibt die Klasse des zu erstellenden oder zu öffnenden Schlüssels an. Der Standardwert ist REG_NONE.

*dwOptions*<br/>
Optionen für den Schlüssel. Der Standardwert ist REG_OPTION_NON_VOLATILE. Eine Liste möglicher Werte und Beschreibungen finden Sie unter [regkreatekeyex](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) im Windows SDK.

*samDesired*<br/>
Der Sicherheits Zugriff für den Schlüssel. Der Standardwert ist KEY_READ &#124; KEY_WRITE. Eine Liste möglicher Werte und Beschreibungen finden `RegCreateKeyEx`Sie unter.

*lpSecAttr*<br/>
Ein Zeiger auf eine [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) -Struktur, die angibt, ob das Handle des Schlüssels von einem untergeordneten Prozess geerbt werden kann. Standardmäßig ist dieser Parameter NULL (was bedeutet, dass das Handle nicht vererbt werden kann).

*lpdwDisposition*<br/>
vorgenommen Wenn der Wert ungleich NULL ist, ruft entweder REG_CREATED_NEW_KEY (wenn der Schlüssel nicht vorhanden war und erstellt wurde) oder REG_OPENED_EXISTING_KEY auf (wenn der Schlüssel vorhanden war und geöffnet wurde).

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben und die Taste geöffnet. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

`Create`legt das [m_hKey](#m_hkey) -Element auf das Handle dieses Schlüssels fest.

##  <a name="cregkey"></a>"Kregkey:: up-Key"

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

Erstellt ein neues `CRegKey`-Objekt. Das-Objekt kann über ein vorhandenes `CRegKey` -Objekt oder ein Handle für einen Registrierungsschlüssel erstellt werden.

##  <a name="dtor"></a>"Kregkey:: ~ kregkey"

Der Destruktor.

```
~CRegKey() throw();
```

### <a name="remarks"></a>Hinweise

Die Dekonstruktor `m_hKey`Releases.

##  <a name="deletesubkey"></a>"Kregkey"::D eletesubkey

Ruft diese Methode auf, um den angegebenen Schlüssel aus der Registrierung zu entfernen.

```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```

### <a name="parameters"></a>Parameter

*lpszSubKey*<br/>
Gibt den Namen des zu löschenden Schlüssels an. Dieser Name muss ein Unterschlüssel von [m_hKey](#m_hkey)sein.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

`DeleteSubKey`ein Schlüssel, der keine Unterschlüssel enthält, kann nur gelöscht werden. Wenn der Schlüssel Unterschlüssel enthält, sollten Sie stattdessen [recursdeletekey](#recursedeletekey) aufrufen.

##  <a name="deletevalue"></a>Kregkey::D eletevalue

Diese Methode wird aufgerufen, um ein Wertfeld aus [m_hKey](#m_hkey)zu entfernen.

```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```

### <a name="parameters"></a>Parameter

*lpszValue*<br/>
Gibt das Wertfeld an, das entfernt werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

##  <a name="detach"></a>"Kregkey"::D Etach

Diese Methode wird aufgerufen, um das [m_hKey](#m_hkey) -Member-Handle `CRegKey` vom-Objekt `m_hKey` zu trennen und auf NULL festzulegen.

```
HKEY Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Der dem- `CRegKey` Objekt zugeordnete HKEY.

##  <a name="enumkey"></a>"Kregkey:: EnumKey"

Mit dieser Methode können Sie die Unterschlüssel des geöffneten Registrierungsschlüssels aufzählen.

```
LONG EnumKey(
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
Der Unterschlüssel Index. Dieser Parameter muss für den ersten Aufruf NULL sein und dann für nachfolgende Aufrufe inkrementiert werden.

*pszName*<br/>
Ein Zeiger auf einen Puffer, der den Namen des unter Schlüssels einschließlich des abschließenden NULL-Zeichens empfängt. Nur der Name des unter Schlüssels wird in den Puffer kopiert, nicht die vollständige Schlüssel Hierarchie.

*pnNameLength*<br/>
Ein Zeiger auf eine Variable, die die Größe des Puffers, der durch den *pszName* -Parameter angegeben wird, in tchars angibt. Diese Größe sollte das abschließende Null-Zeichen enthalten. Wenn die-Methode zurückgegeben wird, enthält die Variable, auf die von *pnnamelength* verwiesen wird, die Anzahl der im Puffer gespeicherten Zeichen. Die zurückgegebene Anzahl umfasst nicht das abschließende Null Zeichen.

*pftLastWriteTime*<br/>
Ein Zeiger auf eine Variable, die die Uhrzeit erhält, zu der der enumerierte Unterschlüssel zuletzt in geschrieben wurde.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Um die Unterschlüssel aufzulisten, müssen Sie `CRegKey::EnumKey` mit einem Index von 0 (null) aufzurufen. Erhöhen Sie den Indexwert, und wiederholen Sie den Vorgang, bis die Methode ERROR_NO_MORE_ITEMS Weitere Informationen finden Sie unter " [regenum KeyEx](/windows/desktop/api/winreg/nf-winreg-regenumkeyexa) " in der Windows SDK.

##  <a name="flush"></a>"Kregkey:: Flush"

Mit dieser Methode können Sie alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung schreiben.

```
LONG Flush() throw();
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter " [regenüberflush](/windows/desktop/api/winreg/nf-winreg-regflushkey) " in der Windows SDK.

##  <a name="getkeysecurity"></a>"Kregkey:: getkeysecurity"

Rufen Sie diese Methode auf, um eine Kopie der Sicherheits Beschreibung abzurufen, die den geöffneten Registrierungsschlüssel schützt.

```
LONG GetKeySecurity(
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```

### <a name="parameters"></a>Parameter

*si*<br/>
Der [SECURITY_INFORMATION](/windows/desktop/SecAuthZ/security-information) -Wert, der die angeforderten Sicherheitsinformationen angibt.

*psd*<br/>
Ein Zeiger auf einen Puffer, der eine Kopie der angeforderten Sicherheits Beschreibung empfängt.

*pnBytes*<br/>
Die Größe des Puffers in Byte, auf den von *PSD*gezeigt wird.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WinError definiert ist. Micha.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [reggetkeysecurity](/windows/desktop/api/winreg/nf-winreg-reggetkeysecurity).

##  <a name="m_hkey"></a>"Kregkey:: m_hKey"

Enthält ein Handle des dem- `CRegKey` Objekt zugeordneten Registrierungsschlüssels.

```
HKEY m_hKey;
```

##  <a name="m_ptm"></a>"Kregkey:: m_pTM"

Zeiger auf ein `CAtlTransactionManager` -Objekt.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Hinweise

##  <a name="notifychangekeyvalue"></a>  CRegKey::NotifyChangeKeyValue

Diese Methode benachrichtigt den Aufrufer über Änderungen an den Attributen oder Inhalten des geöffneten Registrierungsschlüssels.

```
LONG NotifyChangeKeyValue(
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```

### <a name="parameters"></a>Parameter

*bWatchSubtree*<br/>
Gibt ein Flag an, das angibt, ob Änderungen im angegebenen Schlüssel und allen zugehörigen unter Schlüsseln oder nur im angegebenen Schlüssel gemeldet werden sollen. Wenn dieser Parameter true ist, meldet die Methode Änderungen im Schlüssel und seinen unter Schlüsseln. Wenn der-Parameter false ist, meldet die-Methode nur Änderungen im-Schlüssel.

*dwNotifyFilter*<br/>
Gibt einen Satz von Flags an, die Steuern, welche Änderungen gemeldet werden sollen. Dieser Parameter kann eine Kombination der folgenden Werte sein:

|Wert|Bedeutung|
|-----------|-------------|
|REG_NOTIFY_CHANGE_NAME|Benachrichtigen des Aufrufers, wenn ein Unterschlüssel hinzugefügt oder gelöscht wird.|
|REG_NOTIFY_CHANGE_ATTRIBUTES|Benachrichtigen des Aufrufers über Änderungen an den Attributen des Schlüssels, z. b. Informationen zur Sicherheits Beschreibung.|
|REG_NOTIFY_CHANGE_LAST_SET|Benachrichtigen des Aufrufers über Änderungen an einem Wert des Schlüssels. Dies kann das Hinzufügen oder Löschen eines Werts oder das Ändern eines vorhandenen Werts einschließen.|
|REG_NOTIFY_CHANGE_SECURITY|Benachrichtigen des Aufrufers über Änderungen an der Sicherheits Beschreibung des Schlüssels.|

*hEvent*<br/>
Handle für ein Ereignis. Wenn der *basync* -Parameter true ist, gibt die Methode sofort zurück, und Änderungen werden gemeldet, indem dieses Ereignis signalisiert wird. Wenn *basync* den Wert false hat, wird *hevent* ignoriert.

*bAsync*<br/>
Gibt ein Flag an, das angibt, wie die-Methode Änderungen meldet. Wenn dieser Parameter true ist, gibt die Methode sofort zurück und meldet Änderungen, indem das angegebene Ereignis signalisiert wird. Wenn dieser Parameter false ist, wird die Methode erst zurückgegeben, wenn eine Änderung aufgetreten ist. Wenn *hevent* kein gültiges Ereignis angibt, kann der *basync* -Parameter nicht den Wert "true" aufweisen.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Methode benachrichtigt den Aufrufer nicht, wenn der angegebene Schlüssel gelöscht wird.

Weitere Informationen und ein Beispielprogramm finden Sie unter [RegNotifyChangeKeyValue](/windows/desktop/api/winreg/nf-winreg-regnotifychangekeyvalue).

##  <a name="open"></a>"Kregkey:: Open"

Ruft diese Methode auf, um den angegebenen Schlüssel zu öffnen und [m_hKey](#m_hkey) auf das Handle dieses Schlüssels festzulegen.

```
LONG Open(
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```

### <a name="parameters"></a>Parameter

*hKeyParent*<br/>
Das Handle eines geöffneten Schlüssels.

*lpszKeyName*<br/>
Gibt den Namen eines zu erstellenden oder zu öffnenden Schlüssels an. Dieser Name muss ein Unterschlüssel von *hkeyparent*sein.

*samDesired*<br/>
Der Sicherheits Zugriff für den Schlüssel. Der Standardwert ist KEY_ALL_ACCESS. Eine Liste möglicher Werte und Beschreibungen finden Sie unter [regkreatekeyex](/windows/desktop/api/winreg/nf-winreg-regcreatekeyexa) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. andernfalls ein Fehlerwert ungleich 0 (null), der in WinError definiert ist. Micha.

### <a name="remarks"></a>Hinweise

Wenn der *lpszkeyname* -Parameter NULL ist oder auf eine leere Zeichenfolge `Open` zeigt, wird von ein neues Handle des Schlüssels geöffnet, der von *hkeyparent*identifiziert wird, aber ein zuvor geöffnetes Handle wird nicht geschlossen.

Im Gegensatz zu [CRegKey::Create](#create) erstellt `Open` den angegebenen Schlüssel nicht, wenn dieser nicht vorhanden ist.

##  <a name="operator_hkey"></a>"Forgkey:: Operator"-HKEY

Konvertiert ein `CRegKey` -Objekt in einen HKEY.

```
operator HKEY() const throw();
```

##  <a name="operator_eq"></a>"Kregkey:: Operator ="

Zuweisungsoperator.

```
CRegKey& operator= (CRegKey& key) throw();
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Schlüssel, der kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf den neuen Schlüssel zurück.

### <a name="remarks"></a>Hinweise

Dieser Operator trennt den *Schlüssel* vom aktuellen-Objekt und weist ihn stattdessen dem `CRegKey` -Objekt zu.

##  <a name="querybinaryvalue"></a>  CRegKey::QueryBinaryValue

Rufen Sie diese Methode auf, um die Binärdaten für einen angegebenen Wertnamen abzurufen.

```
LONG QueryBinaryValue(
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält.

*pValue*<br/>
Zeiger auf einen Puffer, der die Daten des Werts empfängt.

*pnBytes*<br/>
Ein Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt, auf den der *pValue* -Parameter verweist. Wenn die-Methode zurückgegeben wird, enthält diese Variable die Größe der Daten, die in den Puffer kopiert werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode einen Wert nicht lesen kann, wird ein Fehlercode ungleich 0 (null), der in WinError definiert ist, zurückgegeben. Micha. Wenn die referenzierten Daten nicht vom Typ REG_BINARY sind, wird ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Weitere Informationen finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind. Außerdem behandelt die von dieser Methode verwendete [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) -Funktion nicht explizit Zeichen folgen, die auf Null enden. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

##  <a name="querydwordvalue"></a>  CRegKey::QueryDWORDValue

Rufen Sie diese Methode auf, um die DWORD-Daten für einen angegebenen Wertnamen abzurufen.

```
LONG QueryDWORDValue(
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält.

*dwValue*<br/>
Zeiger auf einen Puffer, der das DWORD empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode einen Wert nicht lesen kann, wird ein Fehlercode ungleich 0 (null), der in WinError definiert ist, zurückgegeben. Micha. Wenn die referenzierten Daten nicht vom Typ REG_DWORD sind, wird ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Weitere Informationen finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind. Außerdem behandelt die von dieser Methode verwendete [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) -Funktion nicht explizit Zeichen folgen, die auf Null enden. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

##  <a name="queryguidvalue"></a>  CRegKey::QueryGUIDValue

Rufen Sie diese Methode auf, um die GUID-Daten für einen angegebenen Wertnamen abzurufen.

```
LONG QueryGUIDValue(
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält.

*guidValue*<br/>
Ein Zeiger auf eine Variable, die die GUID empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode einen Wert nicht lesen kann, wird ein Fehlercode ungleich 0 (null), der in WinError definiert ist, zurückgegeben. Micha. Wenn die referenzierten Daten keine gültige GUID sind, wird ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet und konvertiert `CRegKey::QueryStringValue` die Zeichenfolge mithilfe von [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring)in eine GUID.

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind.

##  <a name="querymultistringvalue"></a>  CRegKey::QueryMultiStringValue

Rufen Sie diese Methode auf, um die multizeichenfolgen-Daten für einen angegebenen Wertnamen abzurufen.

```
LONG QueryMultiStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält.

*pszValue*<br/>
Ein Zeiger auf einen Puffer, der die Daten der mehrteiligen Zeichenfolge empfängt. Eine Multizeichenfolge ist ein Array von auf NULL endenden Zeichen folgen, die mit zwei NULL-Zeichen beendet werden.

*pnChars*<br/>
Die Größe des Puffers in tchars, auf den *pszValue*zeigt. Wenn die-Methode zurückgegeben wird, enthält *pnchars* die Größe der abgerufenen Multizeichenfolge in tchars, einschließlich eines abschließenden NULL-Zeichens.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode einen Wert nicht lesen kann, wird ein Fehlercode ungleich 0 (null), der in WinError definiert ist, zurückgegeben. Micha. Wenn die referenzierten Daten nicht vom Typ REG_MULTI_SZ sind, wird ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Weitere Informationen finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind. Außerdem behandelt die von dieser Methode verwendete [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) -Funktion nicht explizit Zeichen folgen, die auf Null enden. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

##  <a name="queryqwordvalue"></a>  CRegKey::QueryQWORDValue

Rufen Sie diese Methode auf, um die QWORD-Daten für einen angegebenen Wertnamen abzurufen.

```
LONG QueryQWORDValue(
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält.

*qwValue*<br/>
Zeiger auf einen Puffer, der das QWORD empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode einen Wert nicht lesen kann, wird ein Fehlercode ungleich 0 (null), der in WinError definiert ist, zurückgegeben. Micha. Wenn die referenzierten Daten nicht vom Typ REG_QWORD sind, wird ERROR_INVALID_DATA zurückgegeben.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Weitere Informationen finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind. Außerdem behandelt die von dieser Methode verwendete [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) -Funktion nicht explizit Zeichen folgen, die auf Null enden. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

##  <a name="querystringvalue"></a>  CRegKey::QueryStringValue

Rufen Sie diese Methode auf, um die Zeichen folgen Daten für einen angegebenen Wertnamen abzurufen.

```
LONG QueryStringValue(
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält.

*pszValue*<br/>
Zeiger auf einen Puffer, der die Zeichen folgen Daten empfängt.

*pnChars*<br/>
Die Größe des Puffers in tchars, auf den *pszValue*zeigt. Wenn die-Methode zurückgegeben wird, enthält *pnchars* die Größe der abgerufenen Zeichenfolge in tchars, einschließlich eines abschließenden NULL-Zeichens.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ausgeführt wird, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode einen Wert nicht lesen kann, wird ein Fehlercode ungleich 0 (null), der in WinError definiert ist, zurückgegeben. Micha. Wenn die referenzierten Daten nicht vom Typ REG_SZ sind, wird ERROR_INVALID_DATA zurückgegeben. Wenn die Methode ERROR_MORE_DATA zurückgibt, ist *pnchars* gleich 0 (null) und nicht die erforderliche Puffergröße in Bytes.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet `RegQueryValueEx` und bestätigt, dass der richtige Datentyp zurückgegeben wird. Weitere Informationen finden Sie unter [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) .

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind. Außerdem behandelt die von dieser Methode verwendete [RegQueryValueEx](/windows/desktop/api/winreg/nf-winreg-regqueryvalueexa) -Funktion nicht explizit Zeichen folgen, die auf Null enden. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

##  <a name="queryvalue"></a>  CRegKey::QueryValue

Rufen Sie diese Methode auf, um die Daten für das angegebene Wertfeld von [m_hKey](#m_hkey)abzurufen. Frühere Versionen dieser Methode werden nicht mehr unterstützt und sind als ATL_DEPRECATED gekennzeichnet.

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
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des abzufragende Werts enthält. Wenn *pszvaluename* NULL oder eine leere Zeichenfolge ("") ist, ruft die Methode den Typ und die Daten für den unbenannten oder Standardwert des Schlüssels ab, sofern vorhanden.

*pdwType*<br/>
Ein Zeiger auf eine Variable, die einen Code empfängt, der den Typ der im angegebenen Wert gespeicherten Daten angibt. Der *pdwtype* -Parameter kann NULL sein, wenn der Typcode nicht erforderlich ist.

*pData*<br/>
Zeiger auf einen Puffer, der die Daten des Werts empfängt. Dieser Parameter kann NULL sein, wenn die Daten nicht erforderlich sind.

*pnBytes*<br/>
Ein Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt, auf den der *pData* -Parameter verweist. Wenn die-Methode zurückgegeben wird, enthält diese Variable die Größe der Daten, die in *pData* kopiert werden.

*dwValue*<br/>
Die numerischen Daten des Wertfelds.

*lpszValueName*<br/>
Gibt das Wertfeld an, das abgefragt werden soll.

*szValue*<br/>
Die Zeichen folgen Daten des Wertfelds.

*pdwCount*<br/>
Die Größe der Zeichen folgen Daten. Der Wert ist anfänglich auf die Größe des *szvalue* -Puffers festgelegt.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. andernfalls ein Fehlercode ungleich 0 (null), der in WinError definiert ist. Micha.

### <a name="remarks"></a>Hinweise

Die beiden ursprünglichen Versionen von `QueryValue` werden nicht mehr unterstützt und sind als ATL_DEPRECATED gekennzeichnet. Der Compiler gibt eine Warnung aus, wenn diese Formulare verwendet werden.

Die verbleibende Methode ruft RegQueryValueEx auf.

> [!IMPORTANT]
>  Mit dieser Methode kann der Aufrufer beliebige Registrierungs Orte angeben und so möglicherweise Daten lesen, die nicht vertrauenswürdig sind. Außerdem behandelt die von dieser Methode verwendete RegQueryValueEx-Funktion nicht explizit Zeichen folgen, die auf Null enden. Beide Bedingungen sollten durch den aufrufenden Code geprüft werden.

##  <a name="recursedeletekey"></a>"Kregkey:: recurabdeletekey"

Ruft diese Methode auf, um den angegebenen Schlüssel aus der Registrierung zu entfernen und alle untergeordneten Schlüssel explizit zu entfernen.

```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```

### <a name="parameters"></a>Parameter

*lpszKey*<br/>
Gibt den Namen des zu löschenden Schlüssels an. Dieser Name muss ein Unterschlüssel von [m_hKey](#m_hkey)sein.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. andernfalls ein Fehlerwert ungleich 0 (null), der in WinError definiert ist. Micha.

### <a name="remarks"></a>Hinweise

Wenn der Schlüssel über Unterschlüssel verfügt, müssen Sie diese Methode zum Löschen des Schlüssels aufruft.

##  <a name="setbinaryvalue"></a>"Kregkey:: SetBinaryValue"

Mit dieser Methode wird der binäre Wert des Registrierungsschlüssels festgelegt.

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
Ein Zeiger auf einen Puffer, der die Daten enthält, die mit dem angegebenen Wertnamen gespeichert werden sollen.

*nBytes*<br/>
Gibt die Größe der Informationen, auf die der *pValue* -Parameter zeigt, in Bytes an.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) , um den Wert in die Registrierung zu schreiben.

##  <a name="setdwordvalue"></a>"Kregkey:: SetDWORDValue"

Mit dieser Methode wird der DWORD-Wert des Registrierungsschlüssels festgelegt.

```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*dwValue*<br/>
Die DWORD-Daten, die mit dem angegebenen Wertnamen gespeichert werden sollen.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) , um den Wert in die Registrierung zu schreiben.

##  <a name="setguidvalue"></a>"Kregkey:: setguidvalue"

Mit dieser Methode können Sie den GUID-Wert des Registrierungsschlüssels festlegen.

```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*guidValue*<br/>
Verweis auf die GUID, die mit dem angegebenen Wertnamen gespeichert werden soll.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet und konvertiert `CRegKey::SetStringValue` die GUID mithilfe von [StringFromGUID2](/windows/desktop/api/combaseapi/nf-combaseapi-stringfromguid2)in eine Zeichenfolge.

##  <a name="setkeyvalue"></a>"Kregkey:: SetKeyValue"

Ruft diese Methode auf, um Daten in einem angegebenen Wertfeld eines angegebenen Schlüssels zu speichern.

```
LONG SetKeyValue(
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```

### <a name="parameters"></a>Parameter

*lpszKeyName*<br/>
Gibt den Namen des zu erstellenden oder zu öffnenden Schlüssels an. Dieser Name muss ein Unterschlüssel von [m_hKey](#m_hkey)sein.

*lpszValue*<br/>
Gibt die zu speichernden Daten an. Dieser Parameter darf nicht NULL sein.

*lpszValueName*<br/>
Gibt das Wertfeld an, das festgelegt werden soll. Wenn ein Wertfeld mit diesem Namen nicht bereits im Schlüssel vorhanden ist, wird es hinzugefügt.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. andernfalls ein Fehlercode ungleich 0 (null), der in WinError definiert ist. Micha.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode auf, um den Schlüssel " *lpszkeyname* " zu erstellen oder zu öffnen und die *lpszvalue* -Daten im Feld " *lpszvaluename* " zu speichern.

##  <a name="setkeysecurity"></a>"Kregkey:: setkeysecurity"

Ruft diese Methode auf, um die Sicherheit des Registrierungsschlüssels festzulegen.

```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```

### <a name="parameters"></a>Parameter

*si*<br/>
Gibt die Komponenten der Sicherheits Beschreibung an, die festgelegt werden sollen. Der Wert kann eine Kombination der folgenden Werte sein:

|Wert|Bedeutung|
|-----------|-------------|
|DACL_SECURITY_INFORMATION|Legt die Zugriffs Steuerungs Liste (DACL) des Schlüssels für den Schlüssel fest. Der Schlüssel muss über WRITE_DAC Access verfügen, oder der aufrufende Prozess muss der Besitzer des Objekts sein.|
|GROUP_SECURITY_INFORMATION|Legt die primäre Gruppen Sicherheits Kennung (SID) des Schlüssels fest. Der Schlüssel muss über write_owner Access verfügen, oder der aufrufende Prozess muss der Besitzer des Objekts sein.|
|OWNER_SECURITY_INFORMATION|Legt die Besitzer-SID des Schlüssels fest. Der Schlüssel muss über write_owner Access verfügen, oder der aufrufende Prozess muss der Besitzer des Objekts sein, oder die SE_TAKE_OWNERSHIP_NAME-Berechtigung muss aktiviert sein.|
|SACL_SECURITY_INFORMATION|Legt die System Zugriffs Steuerungs Liste (SACL) des Schlüssels fest. Der Schlüssel muss über ACCESS_SYSTEM_SECURITY Access verfügen. Der richtige Weg, um diesen Zugriff zu erhalten, besteht darin, die SE_SECURITY_NAME- [Berechtigung](/windows/desktop/secauthz/privileges) im aktuellen Zugriffs Token des Aufrufers zu aktivieren, das Handle für ACCESS_SYSTEM_SECURITY Access zu öffnen und die Berechtigung zu deaktivieren.|

*psd*<br/>
Ein Zeiger auf eine [SECURITY_DESCRIPTOR](/windows/desktop/api/winnt/ns-winnt-security_descriptor) -Struktur, die die Sicherheits Attribute angibt, die für den angegebenen Schlüssel festgelegt werden sollen.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Legt die Sicherheits Attribute des Schlüssels fest. Weitere Informationen finden Sie unter [regsetkeysecurity](/windows/desktop/api/winreg/nf-winreg-regsetkeysecurity) .

##  <a name="setmultistringvalue"></a>"Kregkey:: SetMultiStringValue"

Mit dieser Methode wird der mehrteilige Zeichen folgen Wert des Registrierungsschlüssels festgelegt.

```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*pszValue*<br/>
Ein Zeiger auf die mehr Zeichen folgen Daten, die mit dem angegebenen Wertnamen gespeichert werden sollen. Eine Multizeichenfolge ist ein Array von auf NULL endenden Zeichen folgen, die mit zwei NULL-Zeichen beendet werden.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) , um den Wert in die Registrierung zu schreiben.

##  <a name="setqwordvalue"></a>"Kregkey:: SetQWORDValue"

Mit dieser Methode wird der QWORD-Wert des Registrierungsschlüssels festgelegt.

```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```

### <a name="parameters"></a>Parameter

*pszValueName*<br/>
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.

*qwValue*<br/>
Die QWORD-Daten, die mit dem angegebenen Wertnamen gespeichert werden sollen.

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.

### <a name="remarks"></a>Hinweise

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) , um den Wert in die Registrierung zu schreiben.

##  <a name="setstringvalue"></a>"Kregkey:: SetStringValue"

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

Diese Methode verwendet [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa) , um den Wert in die Registrierung zu schreiben.

##  <a name="setvalue"></a>"Kregkey:: SetValue"

Ruft diese Methode auf, um Daten im angegebenen Wertfeld von [m_hKey](#m_hkey)zu speichern. Frühere Versionen dieser Methode werden nicht mehr unterstützt und sind als ATL_DEPRECATED gekennzeichnet.

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
Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen im Schlüssel nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu. Wenn *pszvaluename* NULL oder eine leere Zeichenfolge ("") ist, legt die Methode den Typ und die Daten für den unbenannten oder Standardwert des Schlüssels fest.

*dwType*<br/>
Gibt einen Code an, der den Typ der Daten angibt, auf die durch den *pValue* -Parameter verwiesen wird.

*pValue*<br/>
Ein Zeiger auf einen Puffer, der die Daten enthält, die mit dem angegebenen Wertnamen gespeichert werden sollen.

*nBytes*<br/>
Gibt die Größe der Informationen, auf die der *pValue* -Parameter zeigt, in Bytes an. Wenn die Daten vom Typ REG_SZ, REG_EXPAND_SZ oder REG_MULTI_SZ sind, muss *nbytes* die Größe des abschließenden NULL-Zeichens einschließen.

*hKeyParent*<br/>
Das Handle eines geöffneten Schlüssels.

*lpszKeyName*<br/>
Gibt den Namen eines zu erstellenden oder zu öffnenden Schlüssels an. Dieser Name muss ein Unterschlüssel von *hkeyparent*sein.

*lpszValue*<br/>
Gibt die zu speichernden Daten an. Dieser Parameter darf nicht NULL sein.

*lpszValueName*<br/>
Gibt das Wertfeld an, das festgelegt werden soll. Wenn ein Wertfeld mit diesem Namen nicht bereits im Schlüssel vorhanden ist, wird es hinzugefügt.

*dwValue*<br/>
Gibt die zu speichernden Daten an.

*bMulti*<br/>
Der Wert false gibt an, dass die Zeichenfolge vom Typ REG_SZ ist. True gibt an, dass die Zeichenfolge eine Multizeichenfolge vom Typ REG_MULTI_SZ ist.

*nValueLen*<br/>
Wenn *bmultitrue* ist, ist *nvaluelen* die Länge der *lpszvalue* -Zeichenfolge in Zeichen. Wenn *bmultifalse* ist, gibt der Wert-1 an, dass die-Methode die Länge automatisch berechnet.

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, wird ERROR_SUCCESS zurückgegeben. andernfalls ein Fehlercode ungleich 0 (null), der in WinError definiert ist. Micha.

### <a name="remarks"></a>Hinweise

Die beiden ursprünglichen Versionen von `SetValue` werden als ATL_DEPRECATED gekennzeichnet und sollten nicht mehr verwendet werden. Der Compiler gibt eine Warnung aus, wenn diese Formulare verwendet werden.

Die dritte Methode ruft [RegSetValueEx](/windows/desktop/api/winreg/nf-winreg-regsetvalueexa)auf.

## <a name="see-also"></a>Siehe auch

[DCOM-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
