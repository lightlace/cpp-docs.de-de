---
title: CAtlTransactionManager-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 031d72903d72af77f6929072e4605d32d81585a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62260053"
---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager-Klasse

CAtlTransactionManager-Klasse stellt einen Wrapper für die Funktionen des Kerneltransaktions-Manager (KTM) bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CAtlTransactionManager;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[~CAtlTransactionManager](#dtor)|CAtlTransactionManager-Destruktor.|
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager-Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Schließen](#close)|Schließt eine Transaktionshandle des.|
|[Commit](#commit)|Fordert an, dass die Transaktion ein Commit ausgeführt werden.|
|[Erstellen](#create)|Erstellt das Transaktionshandle.|
|[CreateFile](#createfile)|Erstellt oder öffnet eine Datei, eine Datei-Stream oder ein Verzeichnis als ein Transaktiver Vorgang.|
|[DeleteFile](#deletefile)|Löscht eine vorhandene Datei als ein Transaktiver Vorgang an.|
|[FindFirstFile](#findfirstfile)|Durchsucht ein Verzeichnis für eine Datei oder ein Unterverzeichnis als ein Transaktiver Vorgang an.|
|[GetFileAttributes](#getfileattributes)|Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.|
|[GetFileAttributesEx](#getfileattributesex)|Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.|
|[GetHandle](#gethandle)|Gibt das Transaktionshandle zurück.|
|[IsFallback](#isfallback)|Bestimmt, ob die fallback-Aufrufe aktiviert sind.|
|[MoveFile](#movefile)|Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich der untergeordneten Elemente, wie ein Transaktiver Vorgang.|
|[RegCreateKeyEx](#regcreatekeyex)|Den angegebene Registrierungsschlüssel erstellt und verknüpft es mit einer Transaktion. Wenn der Schlüssel bereits vorhanden ist, wird Sie von die Funktion geöffnet.|
|[RegDeleteKey](#regdeletekey)|Löscht einen Unterschlüssel und ihre Werte aus der angegebenen Clientplattform-spezifische Ansicht der Registrierung als ein Transaktiver Vorgang.|
|[RegOpenKeyEx](#regopenkeyex)|Öffnet den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion.|
|[Rollback](#rollback)|Anforderungen, die die Transaktion ein Rollback ausgeführt werden.|
|[SetFileAttributes](#setfileattributes)|Legt die Attribute für eine Datei oder ein Verzeichnis als ein Transaktiver Vorgang fest.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|True, wenn das Fallback unterstützt wird. "False" andernfalls.|
|[m_hTransaction](#m_htransaction)|Das Transaktionshandle an.|

## <a name="remarks"></a>Hinweise

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** atltransactionmanager.h

##  <a name="dtor"></a>  ~ CAtlTransactionManager

CAtlTransactionManager-Destruktor.

```
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Hinweise

Bei der normalen Verarbeitung wird die Transaktion automatisch ein Commit ausgeführt und geschlossen. Wenn bei der eine Ausnahme Entladung der Destruktor aufgerufen wird, wird die Transaktion ein Rollback und geschlossen.

##  <a name="catltransactionmanager"></a>  CAtlTransactionManager

CAtlTransactionManager-Konstruktor.

```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Parameter

*bFallback*<br/>
TRUE gibt an, Unterstützung Fallback. Wenn transaktiven Funktion fehlschlägt, ruft die Klasse automatisch die Funktion "nicht transaktiven". FALSE gibt an, keine "fallback" Aufrufe.

*bAutoCreateTransaction*<br/>
TRUE gibt an, dass der Handler für die Transaktion automatisch im Konstruktor erstellt wird. FALSE gibt an, dass es nicht.

### <a name="remarks"></a>Hinweise

##  <a name="close"></a>  Schließen

Schließt das Transaktionshandle.

```
inline BOOL Close();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CloseHandle` Funktion. Die Methode wird im Destruktor automatisch aufgerufen.

##  <a name="commit"></a>  Commit

Fordert an, dass die Transaktion ein Commit ausgeführt werden.

```
inline BOOL Commit();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CommitTransaction` Funktion. Die Methode wird im Destruktor automatisch aufgerufen.

##  <a name="create"></a>  Erstellen

Erstellt das Transaktionshandle.

```
inline BOOL Create();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CreateTransaction` Funktion. Überprüfen Sie diesen

##  <a name="createfile"></a>  CreateFile

Erstellt oder öffnet eine Datei, eine Datei-Stream oder ein Verzeichnis als ein Transaktiver Vorgang.

```
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name eines Objekts erstellt oder geöffnet werden.

*dwDesiredAccess*<br/>
Der Zugriff auf das Objekt, das als lesen, schreiben, beide oder keines von beiden (null) zusammengefasst werden kann. Die am häufigsten verwendeten Werte sind GENERIC_READ, GENERIC_WRITE oder beides: GENERIC_READ &#124; GENERIC_WRITE.

*dwShareMode*<br/>
Die ein Objekt, das sein, lesen, schreiben, beide können, löschen, alle oder keine-Betriebsmodus: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*lpSecurityAttributes*<br/>
Ein Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die eine optionale Sicherheitsbeschreibung enthält und legt fest, und zwar unabhängig davon, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Der Parameter kann NULL sein.

*dwCreationDisposition*<br/>
Eine Aktion auf Dateien angewendet, die vorhanden sein und sind nicht vorhanden. Dieser Parameter muss eine der folgenden Werte an, die können nicht kombiniert werden: CREATE_ALWAYS CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING oder TRUNCATE_EXISTING.

*dwFlagsAndAttributes*<br/>
Die Dateiattribute und Flags. Dieser Parameter kann eine beliebige Kombination der verfügbaren Dateiattribute (FILE_ATTRIBUTE_ *) enthalten. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL. Dieser Parameter kann auch Kombinationen von Flags enthalten (FILE_FLAG_\*) Zugriff auf für die Steuerung von Pufferverhalten, Modi und andere spezielle Flags. Diese Anwendungen kombinieren, mit jedem FILE_ATTRIBUTE_\* Werte.

*hTemplateFile*<br/>
Ein gültiges Handle zu einer Vorlagendatei mit dem richtigen GENERIC_READ-Zugriff. Die Vorlagendatei stellt Dateiattribute und der erweiterten Attribute für die Datei, die erstellt wird. Dieser Parameter kann NULL sein.

### <a name="return-value"></a>Rückgabewert

Gibt ein Handle, das verwendet werden kann, um Zugriff auf das Objekt zurück.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `CreateFileTransacted` Funktion.

##  <a name="deletefile"></a>  DeleteFile

Löscht eine vorhandene Datei als ein Transaktiver Vorgang an.

```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der zu löschenden Datei.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `DeleteFileTransacted` Funktion.

##  <a name="findfirstfile"></a>  FindFirstFile

Durchsucht ein Verzeichnis für eine Datei oder ein Unterverzeichnis als ein Transaktiver Vorgang an.

```
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Das Verzeichnis oder Pfad und den Dateinamen für die Suche. Dieser Parameter kann Platzhalterzeichen, wie z. B. ein Sternchen (*) oder ein Fragezeichen (-) enthalten.

*pNextInfo*<br/>
Ein Zeiger auf die WIN32_FIND_DATA-Struktur, die Informationen über eine gefundene Datei oder ein Unterverzeichnis empfängt.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist eine Search-Handle, das in einem nachfolgenden Aufruf verwendet `FindNextFile` oder `FindClose`. Wenn die Funktion ein Fehler auftritt oder ein Fehler auftritt, Suchen von Dateien aus der Suchzeichenfolge in die *LpFileName* -Parameter, der Rückgabewert ist INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `FindFirstFileTransacted` Funktion.

##  <a name="getfileattributes"></a>  GetFileAttributes

Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.

```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der Datei oder des Verzeichnisses.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `GetFileAttributesTransacted` Funktion.

##  <a name="getfileattributesex"></a>  GetFileAttributesEx

Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.

```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der Datei oder des Verzeichnisses.

*fInfoLevelId*<br/>
Die Ebene der Informationen über Bildattribute abrufen.

*lpFileInformation*<br/>
Ein Zeiger auf einen Puffer, der Informationen über Bildattribute empfängt. Der Typ von Attributinformationen, die in diesen Puffer gespeichert ist richtet sich nach dem Wert der *fInfoLevelId*. Wenn die *fInfoLevelId* Parameter GetFileExInfoStandard dann dieser Parameter verweist auf eine WIN32_FILE_ATTRIBUTE_DATA-Struktur.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `GetFileAttributesTransacted` Funktion.

##  <a name="gethandle"></a>  GetHandle

Gibt das Transaktionshandle zurück.

```
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Transaktionshandle für eine Klasse zurück. Gibt NULL zurück, wenn die `CAtlTransactionManager` nicht an ein Handle angefügt ist.

### <a name="remarks"></a>Hinweise

##  <a name="isfallback"></a>  IsFallback

Bestimmt, ob die fallback-Aufrufe aktiviert sind.

```
BOOL IsFallback() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" ist die Klasse unterstützt die fallback-Aufrufe. "False" andernfalls.

### <a name="remarks"></a>Hinweise

##  <a name="m_bfallback"></a>  m_bFallback

True, wenn das Fallback unterstützt wird. "False" andernfalls.

```
BOOL m_bFallback;
```

### <a name="remarks"></a>Hinweise

##  <a name="m_htransaction"></a>  m_hTransaction

Das Transaktionshandle an.

```
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Hinweise

##  <a name="movefile"></a>  MoveFile

Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich der untergeordneten Elemente, wie ein Transaktiver Vorgang.

```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Parameter

*lpOldFileName*<br/>
Der aktuelle Name der vorhandenen Datei oder des Verzeichnisses auf dem lokalen Computer.

*lpNewFileName*<br/>
Der neue Name für das Verzeichnis oder Datei. Dieser Name darf nicht bereits vorhanden sein. Eine neue Datei kann auf einem anderen Dateisystem oder das Laufwerk sein. Ein neues Verzeichnis muss auf dem gleichen Laufwerk sein.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `MoveFileTransacted` Funktion.

##  <a name="regcreatekeyex"></a>  "RegCreateKeyEx" dienen

Den angegebene Registrierungsschlüssel erstellt und verknüpft es mit einer Transaktion. Wenn der Schlüssel bereits vorhanden ist, wird Sie von die Funktion geöffnet.

```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name der Unterschlüssel, den diese Funktion wird geöffnet oder erstellt.

*dwReserved*<br/>
Dieser Parameter ist reserviert und muss NULL sein.

*lpClass*<br/>
Die benutzerdefinierte Klasse dieses Schlüssels. Dieser Parameter kann ignoriert werden. Dieser Parameter kann NULL sein.

*dwOptions*<br/>
Dieser Parameter kann einen der folgenden Werte sein: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE oder REG_OPTION_VOLATILE.

*samDesired*<br/>
Eine Maske, die die Zugriffsrechte für den Schlüssel angibt.

*lpSecurityAttributes*<br/>
Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Wenn *LpSecurityAttributes* NULL ist, das Handle nicht geerbt werden.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt. Wenn der Schlüssel nicht eine der vordefinierten Registrierungsschlüssel ist, rufen Sie die `RegCloseKey` funktionieren, nachdem Sie abgeschlossen haben, mit dem Handle.

*lpdwDisposition*<br/>
Ein Zeiger auf eine Variable, die folgenden Werte für die Disposition empfängt: REG_CREATED_NEW_KEY oder REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RegCreateKeyTransacted` Funktion.

##  <a name="regdeletekey"></a>  RegDeleteKey

Löscht einen Unterschlüssel und ihre Werte aus der angegebenen Clientplattform-spezifische Ansicht der Registrierung als ein Transaktiver Vorgang.

```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*hKey*|Ein Handle für einen geöffneten Registrierungsschlüssel.|
|*lpSubKey*|Der Name des Schlüssels, der gelöscht werden.|

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RegDeleteKeyTransacted` Funktion.

##  <a name="regopenkeyex"></a>  "RegOpenKeyEx"

Öffnet den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion.

```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Parameter

*hKey*<br/>
Ein Handle für einen geöffneten Registrierungsschlüssel.

*lpSubKey*<br/>
Der Name des Registrierungsunterschlüssels geöffnet werden.

*ulOptions*<br/>
Dieser Parameter ist reserviert und muss NULL sein.

*samDesired*<br/>
Eine Maske, die die Zugriffsrechte für den Schlüssel angibt.

*phkResult*<br/>
Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt. Wenn der Schlüssel nicht eine der vordefinierten Registrierungsschlüssel ist, rufen Sie die `RegCloseKey` funktionieren, nachdem Sie abgeschlossen haben, mit dem Handle.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RegOpenKeyTransacted` Funktion.

##  <a name="rollback"></a>  Rollback

Anforderungen, die die Transaktion ein Rollback ausgeführt werden.

```
inline BOOL Rollback();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn erfolgreich, andernfalls FALSE.

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `RollbackTransaction` Funktion.

##  <a name="setfileattributes"></a>  SetFileAttributes

Legt die Attribute für eine Datei oder ein Verzeichnis als ein Transaktiver Vorgang fest.

```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Parameter

*lpFileName*<br/>
Der Name der Datei oder des Verzeichnisses.

*dwAttributes*<br/>
Die Dateiattribute, die für die Datei festgelegt. Weitere Informationen finden Sie unter [SetFileAttributesTransacted](/windows/desktop/api/winbase/nf-winbase-setfileattributestransacteda).

### <a name="remarks"></a>Hinweise

Dieser Wrapper Ruft die `SetFileAttributesTransacted` Funktion.

## <a name="see-also"></a>Siehe auch

[ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)
