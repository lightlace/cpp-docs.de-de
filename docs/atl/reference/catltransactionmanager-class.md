---
title: Klasse CAtlTransactionManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: bc6162eaf1a4c8c3848a32e861019ff50e4f850c
ms.lasthandoff: 02/24/2017

---
# <a name="catltransactionmanager-class"></a>CAtlTransactionManager-Klasse
CAtlTransactionManager-Klasse stellt einen Wrapper für die Funktionen des Kerneltransaktions-Manager (KTM) bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CAtlTransactionManager;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager-Destruktor.|  
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager-Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Schließen](#close)|Schließt eine Transaktionshandle des.|  
|[Commit](#commit)|Fordert an, dass die Transaktion ein Commit ausgeführt werden.|  
|[Erstellen](#create)|Erstellt das Transaktionshandle.|  
|[CreateFile](#createfile)|Erstellt oder öffnet eine Datei, Datei-Stream oder Verzeichnis als ein Transaktiver Vorgang.|  
|[DeleteFile](#deletefile)|Löscht eine vorhandene Datei als ein Transaktiver Vorgang.|  
|[FindFirstFile](#findfirstfile)|Sucht in einem Verzeichnis für eine Datei oder ein Unterverzeichnis als ein Transaktiver Vorgang.|  
|[GetFileAttributes](#getfileattributes)|Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.|  
|[GetFileAttributesEx](#getfileattributesex)|Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.|  
|[GetHandle](#gethandle)|Gibt das Transaktionshandle an.|  
|[IsFallback](#isfallback)|Bestimmt, ob das fallback-Aufrufe aktiviert sind.|  
|[MoveFile](#movefile)|Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich seiner untergeordneten Elemente als ein Transaktiver Vorgang.|  
|[RegCreateKeyEx](#regcreatekeyex)|Erstellt den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion. Wenn der Schlüssel bereits vorhanden ist, wird er von die Funktion geöffnet.|  
|[RegDeleteKey](#regdeletekey)|Löscht einen Unterschlüssel und deren Werte aus der angegebenen plattformspezifische Ansicht der Registrierung als ein Transaktiver Vorgang.|  
|[Fehler bei RegOpenKeyEx](#regopenkeyex)|Öffnet den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion.|  
|[Rollback](#rollback)|Anforderungen, die die Transaktion ein Rollback ausgeführt werden.|  
|[SetFileAttributes](#setfileattributes)|Legt die Attribute für eine Datei oder ein Verzeichnis als ein Transaktiver Vorgang fest.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE`Wenn das Fallback unterstützt wird. `FALSE` andernfalls.|  
|[m_hTransaction](#m_htransaction)|Das Transaktionshandle an.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltransactionmanager.h  
  
##  <a name="dtor"></a>~ CAtlTransactionManager  
 CAtlTransactionManager-Destruktor.  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>Hinweise  
 Bei der normalen Verarbeitung wird die Transaktion automatisch ein Commit und geschlossen. Wenn bei einer Ausnahme Entladung der Destruktor aufgerufen wird, wird die Transaktion zurückgesetzt und geschlossen.  
  
##  <a name="catltransactionmanager"></a>CAtlTransactionManager  
 CAtlTransactionManager-Konstruktor.  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bFallback`  
 `TRUE`Gibt Unterstützung Fallback an. Wenn transaktive Funktion fehlschlägt, ruft die Klasse automatisch die Funktion "nicht transaktiven". `FALSE`gibt keine "fallback" Aufrufe an.  
  
 `bAutoCreateTransaction`  
 `TRUE`Gibt an, dass der Handler für die Transaktion automatisch im Konstruktor erstellt wird. `FALSE`Gibt an, dass es nicht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="close"></a>Schließen  
 Schließt das Transaktionshandle an.  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `CloseHandle` Funktion. Die Methode wird in der Destruktor automatisch aufgerufen.  
  
##  <a name="commit"></a>Commit  
 Fordert an, dass die Transaktion ein Commit ausgeführt werden.  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `CommitTransaction` Funktion. Die Methode wird in der Destruktor automatisch aufgerufen.  
  
##  <a name="create"></a>Erstellen  
 Erstellt das Transaktionshandle.  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `CreateTransaction` Funktion. Überprüfen Sie diesen  
  
##  <a name="createfile"></a>CreateFile  
 Erstellt oder öffnet eine Datei, Datei-Stream oder Verzeichnis als ein Transaktiver Vorgang.  
  
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
 `lpFileName`  
 Der Name eines Objekts erstellt oder geöffnet werden.  
  
 `dwDesiredAccess`  
 Der Zugriff auf das Objekt, das als lesen, schreiben, beide oder keines von beiden (null) zusammengefasst werden kann. Die am häufigsten verwendeten Werte werden GENERIC_READ und/oder GENERIC_WRITE: GENERIC_READ | GENERIC_WRITE.  
  
 `dwShareMode`  
 Ein Objekt, das Lesen, schreiben, beide werden kann, löschen, alle oder keine der Betriebsmodus: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.  
  
 `lpSecurityAttributes`  
 Ein Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die enthält einer optionale sicherheitsbeschreibungs an und legt fest, und zwar unabhängig davon, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Der Parameter kann sein `NULL`.  
  
 `dwCreationDisposition`  
 Eine Aktion auf Dateien angewendet, die vorhanden sein und sind nicht vorhanden. Dieser Parameter muss einer der folgenden Werte an, die kombiniert werden können: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING oder TRUNCATE_EXISTING.  
  
 `dwFlagsAndAttributes`  
 Die Dateiattribute und Flags. Dieser Parameter kann eine beliebige Kombination der verfügbaren Dateiattribute (FILE_ATTRIBUTE_ *) enthalten. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL. Dieser Parameter kann auch Kombinationen von Flags enthalten (FILE_FLAG_\*) Zugriff auf Pufferung Verhalten steuern, Modi und andere spezielle Flags. Diese kombinieren mit jeder FILE_ATTRIBUTE_\* Werte.  
  
 `hTemplateFile`  
 Ein gültiges Handle zu einer Vorlagendatei mit dem richtigen GENERIC_READ-Zugriff. Die Vorlagendatei liefert Dateiattribute und der erweiterten Attribute für die Datei, die erstellt wird. Dieser Parameter kann `NULL` sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle, das Zugriff auf das Objekt verwendet werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `CreateFileTransacted` Funktion.  
  
##  <a name="deletefile"></a>DeleteFile  
 Löscht eine vorhandene Datei als ein Transaktiver Vorgang.  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der zu löschenden Datei.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `DeleteFileTransacted` Funktion.  
  
##  <a name="findfirstfile"></a>FindFirstFile  
 Sucht in einem Verzeichnis für eine Datei oder ein Unterverzeichnis als ein Transaktiver Vorgang.  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Das Verzeichnis oder Pfad und den Dateinamen zu suchen. Dieser Parameter kann, z. B. ein Sternchen (*) oder ein Fragezeichen () enthalten.  
  
 `pNextInfo`  
 Ein Zeiger auf die WIN32_FIND_DATA-Struktur, die Informationen über eine gefundene Datei oder ein Unterverzeichnis empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ein Suchhandle, das in einem nachfolgenden Aufruf verwendet `FindNextFile` oder `FindClose`. Wenn die Funktion fehlschlägt, oder Suchen von Dateien aus der Suchzeichenfolge in nicht die `lpFileName` -Parameter, der Rückgabewert ist INVALID_HANDLE_VALUE.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `FindFirstFileTransacted` Funktion.  
  
##  <a name="getfileattributes"></a>GetFileAttributes  
 Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der Datei oder des Verzeichnisses.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `GetFileAttributesTransacted` Funktion.  
  
##  <a name="getfileattributesex"></a>GetFileAttributesEx  
 Ruft die Attribute des Dateisystems für eine angegebene Datei oder ein Verzeichnis als ein Transaktiver Vorgang ab.  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der Datei oder des Verzeichnisses.  
  
 `fInfoLevelId`  
 Die Ebene der Informationen abgerufen.  
  
 `lpFileInformation`  
 Ein Zeiger auf einen Puffer, der die Attributinformationen erhält. Der Typ des in diesem Puffer gespeicherten Attributinformationen wird bestimmt durch den Wert des `fInfoLevelId`. Wenn die `fInfoLevelId` Parameter GetFileExInfoStandard dann dieser Parameter verweist auf eine WIN32_FILE_ATTRIBUTE_DATA-Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `GetFileAttributesTransacted` Funktion.  
  
##  <a name="gethandle"></a>GetHandle  
 Gibt das Transaktionshandle an.  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Transaktionshandle für eine Klasse zurück. Gibt `NULL` Wenn der `CAtlTransactionManager` nicht an ein Handle zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isfallback"></a>IsFallback  
 Bestimmt, ob das fallback-Aufrufe aktiviert sind.  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` ist die Klasse unterstützt die fallback-Aufrufe. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bfallback"></a>m_bFallback  
 `TRUE`Wenn das Fallback unterstützt wird. `FALSE` andernfalls.  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_htransaction"></a>m_hTransaction  
 Das Transaktionshandle an.  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="movefile"></a>MoveFile  
 Verschiebt eine vorhandene Datei oder ein Verzeichnis, einschließlich seiner untergeordneten Elemente als ein Transaktiver Vorgang.  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpOldFileName`  
 Der aktuelle Name der Datei oder des Verzeichnisses auf dem lokalen Computer.  
  
 `lpNewFileName`  
 Der neue Name für die Datei oder das Verzeichnis. Dieser Name darf nicht bereits vorhanden sein. Auf einem anderen Dateisystem oder das Laufwerk möglicherweise eine neue Datei. Ein neues Verzeichnis muss sich auf dem gleichen Laufwerk befinden.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `MoveFileTransacted` Funktion.  
  
##  <a name="regcreatekeyex"></a>RegCreateKeyEx  
 Erstellt den angegebenen Registrierungsschlüssel, und ordnet sie einer Transaktion. Wenn der Schlüssel bereits vorhanden ist, wird er von die Funktion geöffnet.  
  
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
 `hKey`  
 Ein Handle für einen Registrierungsschlüssel.  
  
 `lpSubKey`  
 Der Name der Unterschlüssel, den diese Funktion wird geöffnet oder erstellt.  
  
 `dwReserved`  
 Dieser Parameter ist reserviert und muss&0; (null) sein.  
  
 `lpClass`  
 Die benutzerdefinierte Klasse dieses Schlüssels. Dieser Parameter kann ignoriert werden. Dieser Parameter kann NULL sein.  
  
 `dwOptions`  
 Dieser Parameter kann einen der folgenden Werte sein: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE oder REG_OPTION_VOLATILE.  
  
 `samDesired`  
 Eine Maske, die Zugriffsrechte für den Schlüssel angibt.  
  
 `lpSecurityAttributes`  
 Ein Zeiger auf eine SECURITY_ATTRIBUTES-Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Wenn `lpSecurityAttributes` ist `NULL`, das Handle kann nicht vererbt werden.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt. Wenn der Schlüssel nicht eine der vordefinierten Registrierungsschlüssel ist, rufen Sie die `RegCloseKey` funktionieren, nachdem Sie mit dem Handle abgeschlossen haben.  
  
 `lpdwDisposition`  
 Ein Zeiger auf eine Variable, die folgenden Werte für die Disposition empfängt: REG_CREATED_NEW_KEY oder REG_OPENED_EXISTING_KEY.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `RegCreateKeyTransacted` Funktion.  
  
##  <a name="regdeletekey"></a>RegDeleteKey  
 Löscht einen Unterschlüssel und deren Werte aus der angegebenen plattformspezifische Ansicht der Registrierung als ein Transaktiver Vorgang.  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`hKey`|Ein Handle für einen Registrierungsschlüssel.|  
|`lpSubKey`|Der Name des Schlüssels, der gelöscht werden.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `RegDeleteKeyTransacted` Funktion.  
  
##  <a name="regopenkeyex"></a>Fehler bei RegOpenKeyEx  
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
 `hKey`  
 Ein Handle für einen Registrierungsschlüssel.  
  
 `lpSubKey`  
 Der Name des Registrierungsunterschlüssels geöffnet werden.  
  
 `ulOptions`  
 Dieser Parameter ist reserviert und muss&0; (null) sein.  
  
 `samDesired`  
 Eine Maske, die Zugriffsrechte für den Schlüssel angibt.  
  
 `phkResult`  
 Ein Zeiger auf eine Variable, die ein Handle für den Schlüssel geöffnet oder erstellt empfängt. Wenn der Schlüssel nicht eine der vordefinierten Registrierungsschlüssel ist, rufen Sie die `RegCloseKey` funktionieren, nachdem Sie mit dem Handle abgeschlossen haben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null zeigt in Winerror.h definiert wird  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `RegOpenKeyTransacted` Funktion.  
  
##  <a name="rollback"></a>Rollback  
 Anforderungen, die die Transaktion ein Rollback ausgeführt werden.  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `RollbackTransaction` Funktion.  
  
##  <a name="setfileattributes"></a>SetFileAttributes  
 Legt die Attribute für eine Datei oder ein Verzeichnis als ein Transaktiver Vorgang fest.  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>Parameter  
 `lpFileName`  
 Der Name der Datei oder des Verzeichnisses.  
  
 `dwAttributes`  
 Die Dateiattribute für die Datei festlegen. Weitere Informationen finden Sie unter [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/linkid=158699).  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wrapper Aufrufe der `SetFileAttributesTransacted` Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)

