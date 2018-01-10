---
title: CRegKey Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dffc650c54c4a50fb4b3b1fe2c22ac82501b8b45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cregkey-class"></a>CRegKey-Klasse
Diese Klasse stellt Methoden zum Bearbeiten der Einträge in der systemregistrierung.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CRegKey
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|Der Konstruktor.|  
|[CRegKey:: ~ CRegKey](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|Rufen Sie diese Methode, um eine zu öffnende HKEY Anfügen der `CRegKey` Objekt durch Festlegen der [M_hKey](#m_hkey) Member-Handle für `hKey`.|  
|[CRegKey::Close](#close)|Rufen Sie diese Methode zum Freigeben der [M_hKey](#m_hkey) Datenmember behandeln, und legen Sie es auf NULL.|  
|[CRegKey::Create](#create)|Rufen Sie diese Methode zum Erstellen des angegebenen Schlüssels ein, wenn sie nicht vorhanden ist, als einen Unterschlüssel des Schlüssels `hKeyParent`.|  
|[CRegKey::DeleteSubKey](#deletesubkey)|Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung zu entfernen.|  
|[CRegKey::DeleteValue](#deletevalue)|Rufen Sie diese Methode zum Entfernen eines Wertfelds von [M_hKey](#m_hkey).|  
|[CRegKey::Detach](#detach)|Rufen Sie diese Methode zum Trennen der [M_hKey](#m_hkey) Member-Handle aus der `CRegKey` Objekt, und `m_hKey` auf NULL.|  
|[CRegKey::EnumKey](#enumkey)|Rufen Sie diese Methode zum Aufzählen der Unterschlüssel des Registrierungsschlüssels öffnen.|  
|[CRegKey::Flush](#flush)|Rufen Sie diese Methode, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung geschrieben.|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|Rufen Sie diese Methode, um eine Kopie der Sicherheitsbeschreibung, die Schutz der geöffneten Registrierungsschlüssels abzurufen.|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Diese Methode weist den Aufrufer über Änderungen auf die Attribute oder den Inhalt des Registrierungsschlüssels öffnen.|  
|[CRegKey::Open](#open)|Rufen Sie diese Methode zum Öffnen von des angegebenen Schlüssels und legen Sie [M_hKey](#m_hkey) an das Handle dieses Schlüssels.|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Rufen Sie diese Methode zum Abrufen der Binärdaten für einen angegebenen Wert.|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Rufen Sie diese Methode zum Abrufen der DWORD-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Rufen Sie diese Methode zum Abrufen der GUID-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Rufen Sie diese Methode zum Abrufen der Mehrfachzeichenfolge Daten für einen angegebenen Wert.|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Rufen Sie diese Methode zum Abrufen der QWORD-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryStringValue](#querystringvalue)|Rufen Sie diese Methode zum Abrufen der String-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryValue](#queryvalue)|Rufen Sie diese Methode zum Abrufen der Daten für das Feld angegebenen Wert des [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung entfernen und alle Unterschlüssel explizit entfernen.|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Rufen Sie diese Methode, um den binären Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|Rufen Sie diese Methode, um den DWORD-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetGUIDValue](#setguidvalue)|Rufen Sie diese Methode, um den GUID-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|Rufen Sie diese Methode, um die Sicherheit des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetKeyValue](#setkeyvalue)|Rufen Sie diese Methode zum Speichern von Daten in einem angegebenen Wertfeld eines angegebenen Schlüssels.|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Rufen Sie diese Methode, um den für mehrteilige Zeichenfolgen Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|Rufen Sie diese Methode, um den QWORD-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetStringValue](#setstringvalue)|Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetValue](#setvalue)|Rufen Sie diese Methode zum Speichern von Daten in das Feld angegebenen Wert des [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|Konvertiert eine `CRegKey` Objekt, das eine zu öffnende HKEY.|  
|[CRegKey::operator =](#operator_eq)|Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|Ein Handle des zugeordneten Registrierungsschlüssels enthält den `CRegKey` Objekt.|  
|[CRegKey::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|  
  
## <a name="remarks"></a>Hinweise  
 `CRegKey`Stellt Methoden zum Erstellen und Löschen von Schlüsseln und Werten in der systemregistrierung bereit. Die Registrierung enthält einen Satz Installation spezifischen Definitionen für Systemkomponenten, z. B. Software Versionsnummern, logische physische Zuordnungen von installierten Hardware und COM-Objekten.  
  
 `CRegKey`Stellt eine Programmierschnittstelle für die Registrierung für einen bestimmten Computer an. Aufrufen, um einen bestimmten Registrierungsschlüssel zu öffnen, z. B. `CRegKey::Open`. Rufen Sie zum Abrufen oder Ändern eines Datenwerts, `CRegKey::QueryValue` oder `CRegKey::SetValue`zugeordnet. Rufen Sie zum Schließen eines Schlüssels `CRegKey::Close`.  
  
 Beim Schließen eines Schlüssels werden die Registrierungsdaten (geleerten) auf die Festplatte geschrieben. Dies kann einige Sekunden dauern. Wenn Ihre Anwendung Registrierungsdaten explizit auf die Festplatte schreiben muss, können Sie rufen die [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32-Funktion. Allerdings **RegFlushKey** viele Systemressourcen verwendet und sollte aufgerufen werden, nur wenn unbedingt nötig.  
  
> [!IMPORTANT]
>  Alle Methoden, mit die den Aufrufer zum Angeben eines Speicherorts für die Registrierung können haben die Möglichkeit zum Lesen von Daten, die als vertrauenswürdig eingestuft werden. Verwenden Sie Methoden, die vereinfachen der [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) sollten berücksichtigen, die diese Funktion nicht explizit Zeichenfolgen die NULL behandelt-terminiert werden. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="attach"></a>CRegKey::Attach  
 Rufen Sie diese Methode, um eine zu öffnende HKEY Anfügen der `CRegKey` Objekt durch Festlegen der [M_hKey](#m_hkey) Member-Handle für `hKey`.  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Das Handle eines Registrierungsschlüssels.  
  
### <a name="remarks"></a>Hinweise  
 **Fügen Sie** übergeben wird, wenn `m_hKey` ungleich NULL ist.  
  
##  <a name="close"></a>CRegKey::Close  
 Rufen Sie diese Methode zum Freigeben der [M_hKey](#m_hkey) Datenmember behandeln, und legen Sie es auf NULL.  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS. andernfalls gibt einen Fehlerwert zurück.  
  
##  <a name="create"></a>CRegKey::Create  
 Rufen Sie diese Methode zum Erstellen des angegebenen Schlüssels ein, wenn sie nicht vorhanden ist, als einen Unterschlüssel des Schlüssels `hKeyParent`.  
  
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
 `hKeyParent`  
 Das Handle des ein geöffneter Schlüssel.  
  
 `lpszKeyName`  
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des Schlüssels sein `hKeyParent`.  
  
 `lpszClass`  
 Gibt die Klasse des Schlüssels erstellt oder geöffnet werden. Der Standardwert ist REG_NONE.  
  
 `dwOptions`  
 Optionen für den Schlüssel. Der Standardwert ist REG_OPTION_NON_VOLATILE. Eine Liste der möglichen Werte und Beschreibungen, finden Sie unter [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) im Windows SDK.  
  
 `samDesired`  
 Der Sicherheitszugriff für den Schlüssel. Der Standardwert ist KEY_READ &#124; KEY_WRITE. Eine Liste der möglichen Werte und Beschreibungen, finden Sie unter **RegCreateKeyEx**.  
  
 *lpSecAttr*  
 Ein Zeiger auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die angibt, ob das Handle des Schlüssels von einem untergeordneten Prozess geerbt werden kann. Dieser Parameter ist standardmäßig NULL (was bedeutet, dass das Handle nicht geerbt werden kann).  
  
 *lpdwDisposition*  
 [out] Wenn nicht NULL ist, ruft REG_CREATED_NEW_KEY (wenn der Schlüssel nicht vorhanden war und erstellt wurde) oder REG_OPENED_EXISTING_KEY (wenn der Schlüssel vorhanden war und geöffnet wurde).  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS und öffnet den Schlüssel. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** legt die [M_hKey](#m_hkey) Member an das Handle dieses Schlüssels.  
  
##  <a name="cregkey"></a>CRegKey::CRegKey  
 Der Konstruktor.  
  
```
CRegKey() throw();
CRegKey(CRegKey& key) throw();
explicit CRegKey(HKEY hKey) throw();
CRegKey(CAtlTransactionManager* pTM) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Ein Verweis auf ein `CRegKey`-Objekt.  
  
 `hKey`  
 Ein Handle für einen Registrierungsschlüssel.  
  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CRegKey`-Objekt. Das Objekt kann erstellt werden, aus einer vorhandenen `CRegKey` -Objekt, oder aus einem Handle für einen Registrierungsschlüssel.  
  
##  <a name="dtor"></a>CRegKey:: ~ CRegKey  
 Der Destruktor.  
  
```
~CRegKey() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor Versionen `m_hKey`.  
  
##  <a name="deletesubkey"></a>CRegKey::DeleteSubKey  
 Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung zu entfernen.  
  
```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSubKey`  
 Gibt den Namen des Schlüssels zu löschen. Dieser Name muss ein Unterschlüssel des Schlüssels sein [M_hKey](#m_hkey).  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS zurück. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 `DeleteSubKey`einen Schlüssel, der keine Unterschlüssel verfügt, können nur gelöscht werden. Wenn der Schlüssel Unterschlüssel hat, rufen Sie [RecurseDeleteKey](#recursedeletekey) stattdessen.  
  
##  <a name="deletevalue"></a>CRegKey::DeleteValue  
 Rufen Sie diese Methode zum Entfernen eines Wertfelds von [M_hKey](#m_hkey).  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszValue`  
 Gibt das Wertfeld zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS zurück. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
##  <a name="detach"></a>CRegKey::Detach  
 Rufen Sie diese Methode zum Trennen der [M_hKey](#m_hkey) Member-Handle aus der `CRegKey` Objekt, und `m_hKey` auf NULL.  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der zu öffnende HKEY zugeordneten der `CRegKey` Objekt.  
  
##  <a name="enumkey"></a>CRegKey::EnumKey  
 Rufen Sie diese Methode zum Aufzählen der Unterschlüssel des Registrierungsschlüssels öffnen.  
  
```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Der Registrierungsunterschlüssel Index. Dieser Parameter sollte 0 (null) für den ersten Aufruf und dann für nachfolgende Aufrufe inkrementiert.  
  
 `pszName`  
 Ein Zeiger auf einen Puffer, der Name des Unterschlüssels, einschließlich des abschließenden Null-Zeichens empfängt. Nur der Name des Unterschlüssels wird in den Puffer, nicht die vollständige Schlüsselhierarchie kopiert.  
  
 *pnNameLength*  
 Zeiger auf eine Variable, der angibt, die Größe in TCHARs, des Puffers gemäß der `pszName` Parameter. Diese Größe sollte das abschließende Nullzeichen enthalten. Wenn die Methode zurückgegeben, die Variable verweist, zu *PnNameLength* enthält die Anzahl der Zeichen im Puffer gespeichert. Die Anzahl die zurückgegebenen umfasst nicht das abschließende Nullzeichen.  
  
 *pftLastWriteTime*  
 Zeiger auf eine Variable, die Zeit empfängt, der aufgezählte Unterschlüssel des letzten Schreibvorgangs in.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Unterschlüssel auflisten, `CRegKey::EnumKey` mit dem Index 0 (null). Erhöhen Sie den Indexwert ab, und wiederholen Sie, bis die Methode ERROR_NO_MORE_ITEMS zurückgibt. Weitere Informationen finden Sie unter [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862) im Windows SDK.  
  
##  <a name="flush"></a>CRegKey::Flush  
 Rufen Sie diese Methode, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung geschrieben.  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867) im Windows SDK.  
  
##  <a name="getkeysecurity"></a>CRegKey::GetKeySecurity  
 Rufen Sie diese Methode, um eine Kopie der Sicherheitsbeschreibung, die Schutz der geöffneten Registrierungsschlüssels abzurufen.  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Die [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Wert, der die angeforderten Informationen angibt.  
  
 `psd`  
 Ein Zeiger auf einen Puffer, der eine Kopie der angeforderten Sicherheitsbeschreibung empfängt.  
  
 `pnBytes`  
 Die Größe in Bytes, des Puffers verweist `psd`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich NULL in WINERROR definiert ist. H.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [RegGetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379313).  
  
##  <a name="m_hkey"></a>CRegKey::m_hKey  
 Ein Handle des zugeordneten Registrierungsschlüssels enthält den `CRegKey` Objekt.  
  
```
HKEY m_hKey;
```  
  
##  <a name="m_ptm"></a>CRegKey::m_pTM  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="notifychangekeyvalue"></a>CRegKey::NotifyChangeKeyValue  
 Diese Methode weist den Aufrufer über Änderungen auf die Attribute oder den Inhalt des Registrierungsschlüssels öffnen.  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *bWatchSubtree*  
 Gibt ein Flag, das angibt, ob Änderungen in den angegebenen Schlüssel und alle seine Unterschlüssel oder nur in dem angegebenen Schlüssel zu melden. Wenn dieser Parameter auf "true" ist, meldet die Methode Änderungen in den Schlüssel und Unterschlüssel. Wenn der Parameter auf "false" ist, meldet die Methode ändert sich nur im Schlüssel.  
  
 *dwNotifyFilter*  
 Gibt an, dass eine Gruppe von Flags, die steuern, welche Änderungen gemeldet werden sollte. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|Benachrichtigen Sie der Aufrufer, wenn ein Unterschlüssel hinzugefügt oder gelöscht wird.|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|Benachrichtigen Sie der Aufrufer von Änderungen, die die Attribute des Schlüssels, z. B. die Sicherheitsbeschreibungsinformationen.|  
|REG_NOTIFY_CHANGE_LAST_SET|Den Aufrufer Änderungen auf einen Wert des Schlüssels zu benachrichtigen. Dies kann einschließen, hinzufügen oder Löschen einen Wert oder einen vorhandenen Wert ändern.|  
|REG_NOTIFY_CHANGE_SECURITY|Den Aufrufer Änderungen an der Sicherheitsbeschreibung des Schlüssels zu benachrichtigen.|  
  
 `hEvent`  
 Handle für ein Ereignis. Wenn die *bAsync* Parameter ist "true", die Methode sofort zurückgegeben, und Änderungen durch Signalisieren das Ereignis gemeldet werden. Wenn `bAsync` ist "false" `hEvent` wird ignoriert.  
  
 `bAsync`  
 Gibt ein Flag, das angibt, wie meldet die Methode ändert. Wenn dieser Parameter auf "true" ist, wird die Methode sofort zurückgegeben, und meldet Änderungen durch das angegebene Ereignis zu signalisieren. Wenn dieser Parameter auf "false" ist, gibt die Methode keinen zurück, bis eine Änderung aufgetreten ist. Wenn `hEvent` gibt keinen gültiges Ereignis, das `bAsync` Parameter darf nicht "true" sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nicht den Aufrufer benachrichtigen, wenn der angegebene Schlüssel gelöscht wird.  
  
 Weitere Informationen und ein Beispielprogramm finden Sie unter [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892).  
  
##  <a name="open"></a>CRegKey::Open  
 Rufen Sie diese Methode zum Öffnen von des angegebenen Schlüssels und legen Sie [M_hKey](#m_hkey) an das Handle dieses Schlüssels.  
  
```
LONG Open(  
    HKEY hKeyParent,
    LPCTSTR lpszKeyName,
    REGSAM samDesired = KEY_READ | KEY_WRITE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hKeyParent`  
 Das Handle des ein geöffneter Schlüssel.  
  
 `lpszKeyName`  
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des Schlüssels sein `hKeyParent`.  
  
 `samDesired`  
 Der Sicherheitszugriff für den Schlüssel. Der Standardwert ist KEY_ALL_ACCESS. Eine Liste der möglichen Werte und Beschreibungen, finden Sie unter [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS. Andernfalls definiert ein Fehlerwert ungleich NULL-in WINERROR. H.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `lpszKeyName` Parameter ist NULL oder verweist auf eine leere Zeichenfolge **öffnen** öffnet ein neues Handle für den Schlüssel identifizierte `hKeyParent`, alle zuvor geöffneten Handle wird nicht geschlossen.  
  
 Im Gegensatz zu [CRegKey::Create](#create), **öffnen** wird nicht den angegebenen Schlüssel erstellt, wenn er nicht vorhanden ist.  
  
##  <a name="operator_hkey"></a>CRegKey::operator HKEY  
 Konvertiert eine `CRegKey` Objekt, das eine zu öffnende HKEY.  
  
```  
operator HKEY() const throw();
```  
  
##  <a name="operator_eq"></a>CRegKey::operator =  
 Zuweisungsoperator.  
  
```
CRegKey& operator= (CRegKey& key) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `key`  
 Der Schlüssel zu kopieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf den neuen Schlüssel.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator trennt `key` vom aktuellen Objekt und weist sie der `CRegKey` stattdessen-Objekt.  
  
##  <a name="querybinaryvalue"></a>CRegKey::QueryBinaryValue  
 Rufen Sie diese Methode zum Abrufen der Binärdaten für einen angegebenen Wert.  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.  
  
 `pValue`  
 Ein Zeiger auf einen Puffer, der den Wert Daten empfängt.  
  
 `pnBytes`  
 Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt verweist die `pValue` Parameter. Wenn die Methode zurückkehrt, enthält diese Variable der Größe der Daten in den Puffer kopiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_BINARY ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **bei RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden. Darüber hinaus die [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion verwendet, die von dieser Methode nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
##  <a name="querydwordvalue"></a>CRegKey::QueryDWORDValue  
 Rufen Sie diese Methode zum Abrufen der DWORD-Daten für einen angegebenen Wert.  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.  
  
 `dwValue`  
 Ein Zeiger auf einen Puffer, der den DWORD-Wert empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_DWORD-Wert ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **bei RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden. Darüber hinaus die [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion verwendet, die von dieser Methode nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
##  <a name="queryguidvalue"></a>CRegKey::QueryGUIDValue  
 Rufen Sie diese Methode zum Abrufen der GUID-Daten für einen angegebenen Wert.  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.  
  
 `guidValue`  
 Ein Zeiger auf eine Variable, die GUID empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, auf die verwiesen wird, keine gültige GUID ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt `CRegKey::QueryStringValue` und konvertiert die Zeichenfolge in eine GUID mit [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589).  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden.  
  
##  <a name="querymultistringvalue"></a>CRegKey::QueryMultiStringValue  
 Rufen Sie diese Methode zum Abrufen der Mehrfachzeichenfolge Daten für einen angegebenen Wert.  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.  
  
 `pszValue`  
 Ein Zeiger auf einen Puffer, der die für mehrteilige Zeichenfolgen Daten empfängt. Eine Länge ist ein Array mit Null endende Zeichenfolgen, von zwei Null-Zeichen beendet.  
  
 `pnChars`  
 Die Größe in TCHARs, des Puffers verweist `pszValue`. Wenn die Methode zurückkehrt, `pnChars` enthält die Größe in TCHARs, der die Länge abgerufen, z. B. ein abschließendes Nullzeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_MULTI_SZ ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **bei RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden. Darüber hinaus die [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion verwendet, die von dieser Methode nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
##  <a name="queryqwordvalue"></a>CRegKey::QueryQWORDValue  
 Rufen Sie diese Methode zum Abrufen der QWORD-Daten für einen angegebenen Wert.  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.  
  
 `qwValue`  
 Ein Zeiger auf einen Puffer, der die QWORD empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_QWORD ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **bei RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden. Darüber hinaus die [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion verwendet, die von dieser Methode nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
##  <a name="querystringvalue"></a>CRegKey::QueryStringValue  
 Rufen Sie diese Methode zum Abrufen der String-Daten für einen angegebenen Wert.  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage.  
  
 `pszValue`  
 Ein Zeiger auf einen Puffer, der die Zeichenfolgendaten empfängt.  
  
 `pnChars`  
 Die Größe in TCHARs, des Puffers verweist `pszValue`. Wenn die Methode zurückkehrt, `pnChars` enthält die Größe in TCHARs, der die Zeichenfolge abgerufen, z. B. ein abschließendes Nullzeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definierten zurückgegeben. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_SZ ist, wird ERROR_INVALID_DATA zurückgegeben. Wenn der ERROR_MORE_DATA zurück, der Methodenrückgabe `pnChars` gleich 0 (null), nicht die erforderliche Puffergröße in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **bei RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden. Darüber hinaus die [bei RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion verwendet, die von dieser Methode nicht explizit behandelt den Zeichenfolgen, die NULL-terminiert werden. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
##  <a name="queryvalue"></a>CRegKey::QueryValue  
 Rufen Sie diese Methode zum Abrufen der Daten für das Feld angegebenen Wert des [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.  
  
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
 `pszValueName`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen des Werts, der Abfrage. Wenn `pszValueName` ist NULL oder eine leere Zeichenfolge "", die Methode ruft den Typ ab und Daten für den Schlüssel der unbenannten, oder Standardwert, sofern vorhanden.  
  
 `pdwType`  
 Ein Zeiger auf eine Variable, die einen Code, der angibt, der des Typs der in den angegebenen Wert gespeicherten Daten empfängt. Die `pdwType` Parameter kann NULL sein, wenn der Code nicht erforderlich ist.  
  
 `pData`  
 Ein Zeiger auf einen Puffer, der den Wert Daten empfängt. Dieser Parameter kann NULL sein, wenn die Daten nicht erforderlich ist.  
  
 `pnBytes`  
 Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt verweist die `pData` Parameter. Wenn die Methode zurückkehrt, wird diese Variable enthält die Größe der Daten in kopiert *pData.*  
  
 `dwValue`  
 Der Wert des Felds numerische Daten.  
  
 `lpszValueName`  
 Gibt das Wertfeld "abgefragt werden.  
  
 `szValue`  
 Zeichenfolgendaten mit dem Wert des Felds.  
  
 `pdwCount`  
 Die Größe der Zeichenfolge. Ihr Wert wird anfangs festgelegt, auf die Größe des der `szValue` Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS. andernfalls ein Fehlercode ungleich NULL in WINERROR definiert sind. H.  
  
### <a name="remarks"></a>Hinweise  
 Die beiden ursprünglichen Versionen der `QueryValue` werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**. Der Compiler wird eine Warnmeldung ausgegeben, wenn diese Formen verwendet werden.  
  
 Die übrigen Methodenaufrufe bei RegQueryValueEx.  
  
> [!IMPORTANT]
>  Diese Methode kann der Aufrufer an alle Registrierungsspeicherort potenziell Lesen von Daten, die als vertrauenswürdig eingestuft werden. Darüber hinaus die RegQueryValueEx-Funktion verwendet, die von dieser Methode explizit verarbeitet keine Zeichenfolgen sind `NULL` beendet. Beide Bedingungen sollte auf der aufrufende Code überprüft werden.  
  
##  <a name="recursedeletekey"></a>CRegKey::RecurseDeleteKey  
 Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung entfernen und alle Unterschlüssel explizit entfernen.  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszKey*  
 Gibt den Namen des Schlüssels zu löschen. Dieser Name muss ein Unterschlüssel des Schlüssels sein [M_hKey](#m_hkey).  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS. Andernfalls definiert ein Fehlerwert ungleich NULL-in WINERROR. H.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Schlüssel Unterschlüssel verfügt, müssen Sie diese Methode, um den Schlüssel löschen aufrufen.  
  
##  <a name="setbinaryvalue"></a>CRegKey::SetBinaryValue  
 Rufen Sie diese Methode, um den binären Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetBinaryValue(  
    LPCTSTR pszValueName,
    const void* pValue,
    ULONG nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `pValue`  
 Ein Zeiger auf einen Puffer, die mit dem angegebenen Wertnamen zu speichernden Daten enthält.  
  
 `nBytes`  
 Gibt die Größe in Bytes, der Informationen, die durch die `pValue` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) den Wert in die Registrierung geschrieben.  
  
##  <a name="setdwordvalue"></a>CRegKey::SetDWORDValue  
 Rufen Sie diese Methode, um den DWORD-Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `dwValue`  
 DWORD-Daten mit dem angegebenen Wertnamen gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) den Wert in die Registrierung geschrieben.  
  
##  <a name="setguidvalue"></a>CRegKey::SetGUIDValue  
 Rufen Sie diese Methode, um den GUID-Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `guidValue`  
 Verweis auf die GUID mit dem angegebenen Wertnamen gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt `CRegKey::SetStringValue` und konvertiert die GUID in eine Zeichenfolge mit [StringFromGUID2](http://msdn.microsoft.com/library/windows/desktop/ms683893).  
  
##  <a name="setkeyvalue"></a>CRegKey::SetKeyValue  
 Rufen Sie diese Methode zum Speichern von Daten in einem angegebenen Wertfeld eines angegebenen Schlüssels.  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszKeyName`  
 Gibt den Namen des Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des Schlüssels sein [M_hKey](#m_hkey).  
  
 `lpszValue`  
 Gibt die Daten gespeichert werden soll. Dieser Parameter muss ungleich NULL sein.  
  
 `lpszValueName`  
 Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird er hinzugefügt.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS. andernfalls ein Fehlercode ungleich NULL in WINERROR definiert sind. H.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Erstellen oder öffnen Sie die `lpszKeyName` Schlüssel und speichern Sie die `lpszValue` Daten in die `lpszValueName` Feld "Wert".  
  
##  <a name="setkeysecurity"></a>CRegKey::SetKeySecurity  
 Rufen Sie diese Methode, um die Sicherheit des Registrierungsschlüssels festzulegen.  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Gibt die Komponenten der Sicherheitsbeschreibung fest. Der Wert kann eine Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|Der Schlüssel discretionary Access Control-Liste (DACL) fest. Der Schlüssel muss WRITE_DAC Zugriff haben, oder der aufrufende Prozess muss den Besitzer des Objekts sein.|  
|GROUP_SECURITY_INFORMATION|Legt fest, primäre Gruppe Sicherheits-ID (SID) des Schlüssels. Der Schlüssel muss WRITE_OWNER Zugriff haben, oder der aufrufende Prozess muss den Besitzer des Objekts sein.|  
|OWNER_SECURITY_INFORMATION|Legt den Schlüssel Besitzer SID fest. Der Schlüssel muss WRITE_OWNER Zugriff haben, oder der aufrufende Prozess muss den Besitzer des Objekts oder die Berechtigung SE_TAKE_OWNERSHIP_NAME aktiviert.|  
|SACL_SECURITY_INFORMATION|Legt den Schlüssel System Access Control List (SACL) an. Der Schlüssel muss es sich um ACCESS_SYSTEM_SECURITY Zugriff haben. Die richtige Methode zum Abrufen dieser Zugriff wird so aktivieren Sie die SE_SECURITY_NAME [Berechtigung](http://msdn.microsoft.com/library/windows/desktop/aa379306) im aktuellen Zugriffstoken des Aufrufers, öffnen Sie das Handle für den ACCESS_SYSTEM_SECURITY Zugriff, und deaktivieren Sie die Berechtigung.|  
  
 `psd`  
 Zeiger auf eine [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) -Struktur, die die Sicherheitsattribute für den angegebenen Schlüssel festlegen angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Legt die Sicherheitsattribute für den Schlüssel fest. Finden Sie unter [RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314) Weitere Details.  
  
##  <a name="setmultistringvalue"></a>CRegKey::SetMultiStringValue  
 Rufen Sie diese Methode, um den für mehrteilige Zeichenfolgen Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `pszValue`  
 Zeiger auf die Daten für mehrteilige Zeichenfolgen mit dem angegebenen Wertnamen gespeichert werden. Eine Länge ist ein Array mit Null endende Zeichenfolgen, von zwei Null-Zeichen beendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) den Wert in die Registrierung geschrieben.  
  
##  <a name="setqwordvalue"></a>CRegKey::SetQWORDValue  
 Rufen Sie diese Methode, um den QWORD-Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `qwValue`  
 Die QWORD-Daten mit dem angegebenen Wertnamen gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) den Wert in die Registrierung geschrieben.  
  
##  <a name="setstringvalue"></a>CRegKey::SetStringValue  
 Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetStringValue(  
    LPCTSTR pszValueName,
    LPCTSTR pszValue,
    DWORD dwType = REG_SZ) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `pszValue`  
 Zeiger zu den mit dem angegebenen Wertnamen zu speichernden Zeichenfolgendaten.  
  
 `dwType`  
 Der Typ der Zeichenfolge, die in die Registrierung geschrieben werden muss: entweder REG_SZ (Standard) oder REG_EXPAND_SZ (für mehrteiligen Zeichenfolgen).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923\(v=vs.85\).aspx) den Wert in die Registrierung geschrieben.  
  
##  <a name="setvalue"></a>CRegKey::SetValue  
 Rufen Sie diese Methode zum Speichern von Daten in das Feld angegebenen Wert des [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.  
  
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
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht im Schlüssel vorhanden ist, fügt die Methode das auf den Schlüssel. Wenn `pszValueName` ist NULL oder eine leere Zeichenfolge "", die-Methode legt den Typ und Daten für den Schlüssel des nicht benannt ist, oder Standardwert.  
  
 `dwType`  
 Gibt den Code, der angibt, der des Typs der Daten, die durch die `pValue` Parameter.  
  
 `pValue`  
 Ein Zeiger auf einen Puffer, die mit dem angegebenen Wertnamen zu speichernden Daten enthält.  
  
 `nBytes`  
 Gibt die Größe in Bytes, der Informationen, die durch die `pValue` Parameter. Wenn die Daten des Typs REG_SZ, REG_EXPAND_SZ oder REG_MULTI_SZ, `nBytes` muss die Größe des abschließenden Null-Zeichens enthalten.  
  
 `hKeyParent`  
 Das Handle des ein geöffneter Schlüssel.  
  
 `lpszKeyName`  
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss ein Unterschlüssel des Schlüssels sein `hKeyParent`.  
  
 `lpszValue`  
 Gibt die Daten gespeichert werden soll. Dieser Parameter muss ungleich NULL sein.  
  
 `lpszValueName`  
 Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird er hinzugefügt.  
  
 `dwValue`  
 Gibt die Daten gespeichert werden soll.  
  
 `bMulti`  
 Wenn "false" gibt an, dass die Zeichenfolge des Typs REG_SZ. Wenn "true" gibt an, dass die Zeichenfolge eine Länge des Typs REG_MULTI_SZ ist.  
  
 `nValueLen`  
 Wenn `bMulti` ist "true" `nValueLen` ist die Länge der *LpszValue* Zeichenfolge in Zeichen. Wenn `bMulti` lautet "false", der Wert-1 gibt an, dass die Methode die Länge automatisch berechnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt ERROR_SUCCESS. andernfalls ein Fehlercode ungleich NULL in WINERROR definiert sind. H.  
  
### <a name="remarks"></a>Hinweise  
 Die beiden ursprünglichen Versionen der `SetValue` werden als **ATL_DEPRECATED** und sollte nicht mehr verwendet werden. Der Compiler wird eine Warnmeldung ausgegeben, wenn diese Formen verwendet werden.  
  
 Ruft die dritte Methode [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923).  
  
## <a name="see-also"></a>Siehe auch  
 [DCOM-Beispiel](../../visual-cpp-samples.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
