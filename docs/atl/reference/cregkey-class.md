---
title: Klasse CRegKey | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRegKey
- ATL::CRegKey
- ATL.CRegKey
dev_langs:
- C++
helpviewer_keywords:
- CRegKey class
- ATL, registry
- registry, deleting values
- registry, writing to
- registry, deleting keys
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
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
ms.openlocfilehash: d0ab2a2a0c74ed3d6b48297cc052ebbf09bd3291
ms.lasthandoff: 02/24/2017

---
# <a name="cregkey-class"></a>CRegKey-Klasse
Diese Klasse stellt Methoden zum Bearbeiten von Einträgen in der Registrierung.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CRegKey
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::CRegKey](#cregkey)|Der Konstruktor.|  
|[CRegKey:: ~ CRegKey](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::Attach](#attach)|Rufen Sie diese Methode, um eine zu öffnende HKEY Anfügen der `CRegKey` Objekt durch Festlegen der [M_hKey](#m_hkey) Member-Handle für `hKey`.|  
|[CRegKey::Close](#close)|Rufen Sie diese Methode zum Freigeben der [M_hKey](#m_hkey) Member behandeln, und legen Sie es auf NULL.|  
|[CRegKey::Create](#create)|Rufen Sie diese Methode zum Erstellen des angegebenen Schlüssels, wenn er als der Unterschlüssel nicht vorhanden ist `hKeyParent`.|  
|[CRegKey::DeleteSubKey](#deletesubkey)|Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung zu entfernen.|  
|[CRegKey::DeleteValue](#deletevalue)|Rufen Sie diese Methode zum Entfernen eines Wertfelds von [M_hKey](#m_hkey).|  
|[CRegKey::Detach](#detach)|Rufen Sie diese Methode zum Trennen der [M_hKey](#m_hkey) Element Handle aus der `CRegKey` Objekt, und legen `m_hKey` auf NULL.|  
|[CRegKey::EnumKey](#enumkey)|Rufen Sie diese Methode, um die Unterschlüssel des geöffneten Registrierungsschlüssels aufgelistet werden.|  
|[CRegKey::Flush](#flush)|Rufen Sie diese Methode, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung schreiben.|  
|[CRegKey::GetKeySecurity](#getkeysecurity)|Rufen Sie diese Methode zum Abrufen einer Kopie des Sicherheitsdeskriptors schützt das Öffnen des Registrierungsschlüssels.|  
|[CRegKey::NotifyChangeKeyValue](#notifychangekeyvalue)|Diese Methode benachrichtigt den Aufrufer zu Änderungen an den Attributen oder den Inhalt des Registrierungsschlüssels öffnen.|  
|[CRegKey::Open](#open)|Rufen Sie diese Methode, um den angegebenen Schlüssel öffnen und legen Sie [M_hKey](#m_hkey) auf das Handle des Schlüssels.|  
|[CRegKey::QueryBinaryValue](#querybinaryvalue)|Rufen Sie diese Methode zum Abrufen der binären Daten für einen angegebenen Wert.|  
|[CRegKey::QueryDWORDValue](#querydwordvalue)|Rufen Sie diese Methode zum Abrufen der DWORD-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryGUIDValue](#queryguidvalue)|Rufen Sie diese Methode zum Abrufen der GUID-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryMultiStringValue](#querymultistringvalue)|Rufen Sie diese Methode zum Abrufen der mehrteilige Daten für einen angegebenen Wert.|  
|[CRegKey::QueryQWORDValue](#queryqwordvalue)|Rufen Sie diese Methode zum Abrufen der QWORD-Daten für einen angegebenen Wert.|  
|[CRegKey::QueryStringValue](#querystringvalue)|Rufen Sie diese Methode zum Abrufen der Zeichenfolgendaten für einen angegebenen Wert.|  
|[CRegKey::QueryValue](#queryvalue)|Rufen Sie diese Methode zum Abrufen der Daten für das Feld angegebenen Wert der [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](#recursedeletekey)|Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung entfernen und Unterschlüssel explizit entfernen.|  
|[CRegKey::SetBinaryValue](#setbinaryvalue)|Rufen Sie diese Methode, um den binären Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetDWORDValue](#setdwordvalue)|Rufen Sie diese Methode, um den DWORD-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetGUIDValue](#setguidvalue)|Rufen Sie diese Methode, um den GUID-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetKeySecurity](#setkeysecurity)|Rufen Sie diese Methode, um die Sicherheit für den Registrierungsschlüssel festgelegt werden.|  
|[CRegKey::SetKeyValue](#setkeyvalue)|Rufen Sie diese Methode zum Speichern von Daten in einem Feld angegebenen Wert, der einem angegebenen Schlüssel.|  
|[CRegKey::SetMultiStringValue](#setmultistringvalue)|Rufen Sie diese Methode, um den Mehrfachzeichenfolge Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetQWORDValue](#setqwordvalue)|Rufen Sie diese Methode, um den QWORD-Wert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetStringValue](#setstringvalue)|Rufen Sie diese Methode auf, um den Zeichenfolgenwert des Registrierungsschlüssels festzulegen.|  
|[CRegKey::SetValue](#setvalue)|Rufen Sie diese Methode zum Speichern von Daten in das Feld angegebenen Wert eines [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::operator HKEY](#operator_hkey)|Konvertiert ein `CRegKey` Objekt, das eine zu öffnende HKEY.|  
|[CRegKey::operator =](#operator_eq)|Zuweisungsoperator.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRegKey::m_hKey](#m_hkey)|Ein Handle für den zugeordneten Registrierungsschlüssel enthält die `CRegKey` Objekt.|  
|[CRegKey::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|  
  
## <a name="remarks"></a>Hinweise  
 `CRegKey`Stellt Methoden zum Erstellen und Löschen von Schlüsseln und Werten in der Registrierung. Die Registrierung enthält einen Installation spezifischen Satz von Definitionen für Systemkomponenten, wie z. B. Software-Versionsnummern, logische, physische Zuordnung der installierten Hardware und COM-Objekte.  
  
 `CRegKey`Stellt eine Programmierschnittstelle für die Registrierung für einen bestimmten Computer an. Rufen Sie z. B. zum Öffnen eines bestimmten Registrierungsschlüssel statt `CRegKey::Open`. Rufen Sie zum Abrufen oder ändern einen Datenwert, `CRegKey::QueryValue` oder `CRegKey::SetValue`bzw.. Rufen Sie zum Schließen eines Schlüssels `CRegKey::Close`.  
  
 Wenn Sie einen Schlüssel schließen, werden die Registrierungsdaten (geleert) auf die Festplatte geschrieben. Dieser Vorgang kann einige Sekunden dauern. Wenn die Anwendung explizit Registrierungsdaten auf die Festplatte schreiben muss, können Sie Aufrufen der [wurde von RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32-Funktion. Allerdings **wurde von RegFlushKey** viele Systemressourcen verwendet und sollte nur aufgerufen, wenn dies absolut notwendig.  
  
> [!IMPORTANT]
>  Alle Methoden, mit denen den Aufrufer ein Registrierungsspeicherort angeben haben die Möglichkeit zum Lesen von Daten, die nicht vertrauenswürdig ist. Methoden, die Stellen verwenden [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) sollten berücksichtigen, die diese Funktion nicht explizit Zeichenfolgen die NULL behandelt-terminiert sind. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameattacha--cregkeyattach"></a><a name="attach"></a>CRegKey::Attach  
 Rufen Sie diese Methode, um eine zu öffnende HKEY Anfügen der `CRegKey` Objekt durch Festlegen der [M_hKey](#m_hkey) Member-Handle für `hKey`.  
  
```
void Attach(HKEY hKey) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `hKey`  
 Das Handle eines Registrierungsschlüssels.  
  
### <a name="remarks"></a>Hinweise  
 **Fügen Sie** wenn bestätigt `m_hKey` ungleich NULL ist.  
  
##  <a name="a-nameclosea--cregkeyclose"></a><a name="close"></a>CRegKey::Close  
 Rufen Sie diese Methode zum Freigeben der [M_hKey](#m_hkey) Member behandeln, und legen Sie es auf NULL.  
  
```
LONG Close() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung gibt ERROR_SUCCESS zurück. andernfalls gibt einen Fehlerwert zurück.  
  
##  <a name="a-namecreatea--cregkeycreate"></a><a name="create"></a>CRegKey::Create  
 Rufen Sie diese Methode zum Erstellen des angegebenen Schlüssels, wenn er als der Unterschlüssel nicht vorhanden ist `hKeyParent`.  
  
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
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss einem Unterschlüssel des `hKeyParent`.  
  
 `lpszClass`  
 Gibt die Klasse des Schlüssels erstellt oder geöffnet werden. Der Standardwert ist REG_NONE.  
  
 `dwOptions`  
 Optionen für den Schlüssel. Der Standardwert ist REG_OPTION_NON_VOLATILE. Eine Liste der möglichen Werte und eine Beschreibung, finden Sie unter [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `samDesired`  
 Der Sicherheitszugriff für den Schlüssel. Der Standardwert ist KEY_READ | KEY_WRITE. Eine Liste der möglichen Werte und eine Beschreibung, finden Sie unter **RegCreateKeyEx**.  
  
 *lpSecAttr*  
 Ein Zeiger auf eine [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die angibt, ob das Handle des Schlüssels von einem untergeordneten Prozess geerbt werden kann. Dieser Parameter ist standardmäßig NULL (d. h., der das Handle nicht geerbt werden kann).  
  
 *lpdwDisposition*  
 [out] Wenn nicht NULL ist, ruft REG_CREATED_NEW_KEY (wenn der Schlüssel nicht vorhanden war und erstellt wurde) oder REG_OPENED_EXISTING_KEY (wenn der Schlüssel vorhanden war und geöffnet wurde).  
  
### <a name="return-value"></a>Rückgabewert  
 Bei einem erfolgreichen ERROR_SUCCESS zurückgibt, und öffnet den Schlüssel. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 **Erstellen Sie** legt die [M_hKey](#m_hkey) Member auf das Handle des Schlüssels.  
  
##  <a name="a-namecregkeya--cregkeycregkey"></a><a name="cregkey"></a>CRegKey::CRegKey  
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
  
##  <a name="a-namedtora--cregkeycregkey"></a><a name="dtor"></a>CRegKey:: ~ CRegKey  
 Der Destruktor.  
  
```
~CRegKey() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Der Destruktor Versionen `m_hKey`.  
  
##  <a name="a-namedeletesubkeya--cregkeydeletesubkey"></a><a name="deletesubkey"></a>CRegKey::DeleteSubKey  
 Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung zu entfernen.  
  
```
LONG DeleteSubKey(LPCTSTR lpszSubKey) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSubKey`  
 Gibt den Namen des Schlüssels zu löschen. Dieser Name muss einem Unterschlüssel des [M_hKey](#m_hkey).  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 `DeleteSubKey`kann nur einen Schlüssel löschen, der keine Unterschlüssel. Wenn der Schlüssel Unterschlüssel hat, rufen Sie [RecurseDeleteKey](#recursedeletekey) stattdessen.  
  
##  <a name="a-namedeletevaluea--cregkeydeletevalue"></a><a name="deletevalue"></a>CRegKey::DeleteValue  
 Rufen Sie diese Methode zum Entfernen eines Wertfelds von [M_hKey](#m_hkey).  
  
```
LONG DeleteValue(LPCTSTR lpszValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszValue`  
 Gibt das Wertfeld "zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
##  <a name="a-namedetacha--cregkeydetach"></a><a name="detach"></a>CRegKey::Detach  
 Rufen Sie diese Methode zum Trennen der [M_hKey](#m_hkey) Element Handle aus der `CRegKey` Objekt, und legen `m_hKey` auf NULL.  
  
```
HKEY Detach() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der zu öffnende HKEY zugeordneten der `CRegKey` Objekt.  
  
##  <a name="a-nameenumkeya--cregkeyenumkey"></a><a name="enumkey"></a>CRegKey::EnumKey  
 Rufen Sie diese Methode, um die Unterschlüssel des geöffneten Registrierungsschlüssels aufgelistet werden.  
  
```
LONG EnumKey(  
    DWORD iIndex,
    LPTSTR pszName,
    LPDWORD pnNameLength,
    FILETIME* pftLastWriteTime = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `iIndex`  
 Der Registrierungsunterschlüssel Index. Dieser Parameter muss&0; (null) für den ersten Aufruf und dann für nachfolgende Aufrufe erhöht.  
  
 `pszName`  
 Ein Zeiger auf einen Puffer, der Name des Unterschlüssels, einschließlich des abschließenden Null-Zeichens empfängt. Nur der Name des Unterschlüssels wird in den Puffer, nicht die vollständige Hierarchie kopiert.  
  
 *pnNameLength*  
 Zeiger auf eine Variable, die die Größe in TCHARs, des angegebenen Puffers angibt, die `pszName` Parameter. Diese Größe sollte das abschließende Nullzeichen enthalten. Wenn die Methode zurückgibt, die auf die Variable *PnNameLength* enthält die Anzahl der Zeichen im Puffer gespeichert. Die zurückgegebene Anzahl schließt nicht das abschließende Nullzeichen.  
  
 *pftLastWriteTime*  
 Zeiger auf eine Variable, die Zeit empfängt, der aufgelistete Unterschlüssel des letzten Schreibvorgangs.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Auflisten der Unterschlüssel `CRegKey::EnumKey` mit einem Index&0; (null). Erhöhen Sie den Indexwert, und wiederholen Sie, bis die Methode ERROR_NO_MORE_ITEMS zurückgibt. Weitere Informationen finden Sie unter [RegEnumKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724862) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameflusha--cregkeyflush"></a><a name="flush"></a>CRegKey::Flush  
 Rufen Sie diese Methode, um alle Attribute des geöffneten Registrierungsschlüssels in die Registrierung schreiben.  
  
```
LONG Flush() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [RegEnumFlush](http://msdn.microsoft.com/library/windows/desktop/ms724867) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetkeysecuritya--cregkeygetkeysecurity"></a><a name="getkeysecurity"></a>CRegKey::GetKeySecurity  
 Rufen Sie diese Methode zum Abrufen einer Kopie des Sicherheitsdeskriptors schützt das Öffnen des Registrierungsschlüssels.  
  
```
LONG GetKeySecurity(  
    SECURITY_INFORMATION si,
    PSECURITY_DESCRIPTOR psd,
    LPDWORD pnBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Die [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) Wert, der die angeforderten Sicherheitsinformationen angibt.  
  
 `psd`  
 Ein Zeiger auf einen Puffer, der eine Kopie der angeforderten Sicherheitsdeskriptor empfängt.  
  
 `pnBytes`  
 Die Größe in Bytes, der die Puffer, die auf `psd`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich NULL in WINERROR definiert. H.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [RegGetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379313).  
  
##  <a name="a-namemhkeya--cregkeymhkey"></a><a name="m_hkey"></a>CRegKey::m_hKey  
 Ein Handle für den zugeordneten Registrierungsschlüssel enthält die `CRegKey` Objekt.  
  
```
HKEY m_hKey;
```  
  
##  <a name="a-namemptma--cregkeymptm"></a><a name="m_ptm"></a>CRegKey::m_pTM  
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namenotifychangekeyvaluea--cregkeynotifychangekeyvalue"></a><a name="notifychangekeyvalue"></a>CRegKey::NotifyChangeKeyValue  
 Diese Methode benachrichtigt den Aufrufer zu Änderungen an den Attributen oder den Inhalt des Registrierungsschlüssels öffnen.  
  
```
LONG NotifyChangeKeyValue(  
    BOOL bWatchSubtree,
    DWORD dwNotifyFilter,
    HANDLE hEvent,
    BOOL bAsync = TRUE) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *bWatchSubtree*  
 Gibt ein Flag, das angibt, ob die Änderungen in den angegebenen Schlüssel und dessen Unterschlüssel oder nur in den angegebenen Schlüssel zu melden. Wenn dieser Parameter auf "true" ist, meldet die Methode ändert sich in den Schlüssel und dessen Unterschlüssel. Wenn der Parameter auf false festgelegt ist, meldet die Methode ändert sich nur im Schlüssel.  
  
 *dwNotifyFilter*  
 Gibt an, dass ein Satz von Flags, die steuern, welche Änderungen gemeldet werden sollen. Dieser Parameter kann eine Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|REG_NOTIFY_CHANGE_NAME|Benachrichtigen Sie den Aufrufer, wenn ein Unterschlüssel hinzugefügt oder gelöscht wird.|  
|REG_NOTIFY_CHANGE_ATTRIBUTES|Den Aufrufer von Änderungen an den Attributen des Schlüssels, z. B. die Sicherheitsbeschreibungsinformationen zu benachrichtigen.|  
|REG_NOTIFY_CHANGE_LAST_SET|Den Aufrufer Änderungen auf einen Wert des Schlüssels zu benachrichtigen. Dazu kann gehören, hinzufügen oder Löschen eines Wertes oder Ändern eines vorhandenen Werts.|  
|REG_NOTIFY_CHANGE_SECURITY|Den Aufrufer Änderungen an den Sicherheitsdeskriptor des Schlüssels zu benachrichtigen.|  
  
 `hEvent`  
 Handle für ein Ereignis. Wenn die *bAsync* -Parameter ist "true", die Methode kehrt sofort zurück und ändert sich durch Signalisieren dieses Ereignis gemeldet. Wenn `bAsync` ist FALSE, `hEvent` wird ignoriert.  
  
 `bAsync`  
 Gibt ein Flag, das angibt, wie die-Methode Änderungen meldet. Wenn dieser Parameter auf "true" ist, wird die Methode kehrt sofort zurück und meldet Änderungen durch das angegebene Ereignis zu signalisieren. Wenn dieser Parameter auf false festgelegt ist, wird die Methode nicht beendet, bis eine Änderung vorgenommen wurde. Wenn `hEvent` gibt kein gültiges Ereignis, das `bAsync` Parameter darf nicht "true" sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode benachrichtigt nicht den Aufrufer, wenn der angegebene Schlüssel gelöscht wird.  
  
 Weitere Informationen und ein Beispielprogramm, finden Sie unter [RegNotifyChangeKeyValue](http://msdn.microsoft.com/library/windows/desktop/ms724892).  
  
##  <a name="a-nameopena--cregkeyopen"></a><a name="open"></a>CRegKey::Open  
 Rufen Sie diese Methode, um den angegebenen Schlüssel öffnen und legen Sie [M_hKey](#m_hkey) auf das Handle des Schlüssels.  
  
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
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss einem Unterschlüssel des `hKeyParent`.  
  
 `samDesired`  
 Der Sicherheitszugriff für den Schlüssel. Der Standardwert ist KEY_ALL_ACCESS. Eine Liste der möglichen Werte und eine Beschreibung, finden Sie unter [RegCreateKeyEx](http://msdn.microsoft.com/library/windows/desktop/ms724844) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung gibt ERROR_SUCCESS zurück. Andernfalls definiert ein Fehlerwert ungleich NULL-in WINERROR. H.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `lpszKeyName` Parameter ist NULL oder verweist auf eine leere Zeichenfolge, **öffnen** öffnet ein neues Handle für den Schlüssel identifizierte `hKeyParent`, schließt jedoch keine zuvor geöffneten Handles.  
  
 Im Gegensatz zu [CRegKey::Create](#create), **Open** den angegebenen Schlüssel nicht erstellen, wenn er nicht vorhanden ist.  
  
##  <a name="a-nameoperatorhkeya--cregkeyoperator-hkey"></a><a name="operator_hkey"></a>CRegKey::operator HKEY  
 Konvertiert ein `CRegKey` Objekt, das eine zu öffnende HKEY.  
  
```  
operator HKEY() const throw();
```  
  
##  <a name="a-nameoperatoreqa--cregkeyoperator-"></a><a name="operator_eq"></a>CRegKey::operator =  
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
 Dieser Operator wird getrennt `key` aus dem aktuellen Objekt und weist sie dem `CRegKey` -Objekt stattdessen.  
  
##  <a name="a-namequerybinaryvaluea--cregkeyquerybinaryvalue"></a><a name="querybinaryvalue"></a>CRegKey::QueryBinaryValue  
 Rufen Sie diese Methode zum Abrufen der binären Daten für einen angegebenen Wert.  
  
```
LONG QueryBinaryValue(  
    LPCTSTR pszValueName,
    void* pValue,
    ULONG* pnBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage.  
  
 `pValue`  
 Ein Zeiger auf einen Puffer, der den Wert empfängt.  
  
 `pnBytes`  
 Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt auf die von der `pValue` Parameter. Wenn die Methode zurückgibt, enthält die Variable die Größe der Daten in den Puffer kopiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definiert. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_BINARY ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion, die von dieser Methode verwendeten behandelt nicht explizit Zeichenfolgen, die NULL-terminiert werden. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
##  <a name="a-namequerydwordvaluea--cregkeyquerydwordvalue"></a><a name="querydwordvalue"></a>CRegKey::QueryDWORDValue  
 Rufen Sie diese Methode zum Abrufen der DWORD-Daten für einen angegebenen Wert.  
  
```
LONG QueryDWORDValue(  
    LPCTSTR pszValueName,
    DWORD& dwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage.  
  
 `dwValue`  
 Ein Zeiger auf einen Puffer, der den DWORD-Wert erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definiert. H. Wenn die Daten, auf die verwiesen wird, nicht REG_DWORD-Datentyp ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion, die von dieser Methode verwendeten behandelt nicht explizit Zeichenfolgen, die NULL-terminiert werden. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
##  <a name="a-namequeryguidvaluea--cregkeyqueryguidvalue"></a><a name="queryguidvalue"></a>CRegKey::QueryGUIDValue  
 Rufen Sie diese Methode zum Abrufen der GUID-Daten für einen angegebenen Wert.  
  
```
LONG QueryGUIDValue(  
    LPCTSTR pszValueName,
    GUID& guidValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage.  
  
 `guidValue`  
 Ein Zeiger auf eine Variable, die GUID empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definiert. H. Wenn die Daten, auf die verwiesen wird, keine gültige GUID ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt `CRegKey::QueryStringValue` und konvertiert die Zeichenfolge in eine GUID mit [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589).  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist.  
  
##  <a name="a-namequerymultistringvaluea--cregkeyquerymultistringvalue"></a><a name="querymultistringvalue"></a>CRegKey::QueryMultiStringValue  
 Rufen Sie diese Methode zum Abrufen der mehrteilige Daten für einen angegebenen Wert.  
  
```
LONG QueryMultiStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage.  
  
 `pszValue`  
 Ein Zeiger auf einen Puffer, der die mehrteilige Daten empfängt. Eine mehrteilige Zeichenfolge ist ein Array mit Null endende Zeichenfolgen, von zwei Null-Zeichen beendet wird.  
  
 `pnChars`  
 Die Größe in TCHARs, des Puffers auf den `pszValue`. Wenn die Methode zurückkehrt, `pnChars` enthält die Größe in TCHARs, der die mehrteilige Zeichenfolge abgerufen, einschließlich des abschließenden Null-Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definiert. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_MULTI_SZ ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion, die von dieser Methode verwendeten behandelt nicht explizit Zeichenfolgen, die NULL-terminiert werden. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
##  <a name="a-namequeryqwordvaluea--cregkeyqueryqwordvalue"></a><a name="queryqwordvalue"></a>CRegKey::QueryQWORDValue  
 Rufen Sie diese Methode zum Abrufen der QWORD-Daten für einen angegebenen Wert.  
  
```
LONG QueryQWORDValue(  
    LPCTSTR pszValueName,
    ULONGLONG& qwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage.  
  
 `qwValue`  
 Ein Zeiger auf einen Puffer, der QWORD empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definiert. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ REG_QWORD ist, wird ERROR_INVALID_DATA zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion, die von dieser Methode verwendeten behandelt nicht explizit Zeichenfolgen, die NULL-terminiert werden. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
##  <a name="a-namequerystringvaluea--cregkeyquerystringvalue"></a><a name="querystringvalue"></a>CRegKey::QueryStringValue  
 Rufen Sie diese Methode zum Abrufen der Zeichenfolgendaten für einen angegebenen Wert.  
  
```
LONG QueryStringValue(  
    LPCTSTR pszValueName,
    LPTSTR pszValue,
    ULONG* pnChars) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage.  
  
 `pszValue`  
 Ein Zeiger auf einen Puffer, der die Zeichenfolgendaten empfängt.  
  
 `pnChars`  
 Die Größe in TCHARs, des Puffers auf den `pszValue`. Wenn die Methode zurückkehrt, `pnChars` enthält die Größe in TCHARs, der die Zeichenfolge abgerufen, einschließlich des abschließenden Null-Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird ERROR_SUCCESS zurückgegeben. Wenn die Methode fehlschlägt, einen Wert zu lesen, wird einen Fehlercode ungleich Null zeigt in WINERROR definiert. H. Wenn die Daten, auf die verwiesen wird, nicht vom Typ "REG_SZ" ist, wird ERROR_INVALID_DATA zurückgegeben. Wenn die Methode ERROR_MORE_DATA zurück, gibt `pnChars` gleich&0; (null), nicht die erforderliche Puffergröße in Byte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt **RegQueryValueEx** und bestätigt, dass der richtige Datentyp zurückgegeben wird. Finden Sie unter [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) für weitere Details.  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) Funktion, die von dieser Methode verwendeten behandelt nicht explizit Zeichenfolgen, die NULL-terminiert werden. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
##  <a name="a-namequeryvaluea--cregkeyqueryvalue"></a><a name="queryvalue"></a>CRegKey::QueryValue  
 Rufen Sie diese Methode zum Abrufen der Daten für das Feld angegebenen Wert der [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.  
  
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
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen des Werts, der Abfrage. Wenn `pszValueName` ist NULL oder eine leere Zeichenfolge "", die Methode ruft den Typ ab und Daten für den Schlüssel des unbenannten oder default-Wert, falls vorhanden.  
  
 `pdwType`  
 Ein Zeiger auf eine Variable, die einen Code, der den Typ der Daten aus dem angegebenen Wert empfängt. Die `pdwType` Parameter kann NULL sein, wenn der Code nicht erforderlich ist.  
  
 `pData`  
 Ein Zeiger auf einen Puffer, der den Wert empfängt. Dieser Parameter kann NULL sein, wenn die Daten nicht erforderlich ist.  
  
 `pnBytes`  
 Zeiger auf eine Variable, die die Größe des Puffers in Bytes angibt auf die von der `pData` Parameter. Wenn die Methode zurückkehrt, wird diese Variable enthält die Größe der Daten, die kopiert werden sollen *pData.*  
  
 `dwValue`  
 Der Wert des Felds numerische Daten.  
  
 `lpszValueName`  
 Gibt das Wertfeld abgefragt werden.  
  
 `szValue`  
 Der Wert des Felds Zeichenfolgendaten.  
  
 `pdwCount`  
 Die Größe der Zeichenfolge. Sein Wert wird anfangs festgelegt, der Größe der `szValue` Puffer.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung gibt ERROR_SUCCESS zurück. andernfalls ein Fehlercode ungleich NULL in WINERROR definiert. H.  
  
### <a name="remarks"></a>Hinweise  
 Die beiden ursprünglichen Versionen der `QueryValue` werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**. Der Compiler wird eine Warnung ausgegeben, wenn diese Formulare verwendet werden.  
  
 Die übrigen Methodenaufrufe RegQueryValueEx.  
  
> [!IMPORTANT]
>  Diese Methode ermöglicht den Aufrufer, geben Sie Registrierung an, die möglicherweise beim Lesen der Daten, die nicht vertrauenswürdig ist. Darüber hinaus die RegQueryValueEx-Funktion, die von dieser Methode verwendet nicht explizit behandelt Zeichenfolgen diese `NULL` wurde beendet. In beiden Fällen sollte der aufrufende Code überprüft werden.  
  
##  <a name="a-namerecursedeletekeya--cregkeyrecursedeletekey"></a><a name="recursedeletekey"></a>CRegKey::RecurseDeleteKey  
 Rufen Sie diese Methode, um den angegebenen Schlüssel aus der Registrierung entfernen und Unterschlüssel explizit entfernen.  
  
```
LONG RecurseDeleteKey(LPCTSTR lpszKey) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszKey*  
 Gibt den Namen des Schlüssels zu löschen. Dieser Name muss einem Unterschlüssel des [M_hKey](#m_hkey).  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung gibt ERROR_SUCCESS zurück. Andernfalls definiert ein Fehlerwert ungleich NULL-in WINERROR. H.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Schlüssel Unterschlüssel verfügt, müssen Sie diese Methode, um den Schlüssel löschen aufrufen.  
  
##  <a name="a-namesetbinaryvaluea--cregkeysetbinaryvalue"></a><a name="setbinaryvalue"></a>CRegKey::SetBinaryValue  
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
 Ein Zeiger auf einen Puffer, der mit dem angegebenen Wertnamen zu speichernden Daten enthält.  
  
 `nBytes`  
 Gibt die Größe in Bytes, der auf den Informationen der `pValue` Parameter.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) auf den Wert in der Registrierung schreiben.  
  
##  <a name="a-namesetdwordvaluea--cregkeysetdwordvalue"></a><a name="setdwordvalue"></a>CRegKey::SetDWORDValue  
 Rufen Sie diese Methode, um den DWORD-Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetDWORDValue(LPCTSTR pszValueName, DWORD dwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `dwValue`  
 DWORD-Daten mit dem angegebenen Wertnamen gespeichert werden muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) auf den Wert in der Registrierung schreiben.  
  
##  <a name="a-namesetguidvaluea--cregkeysetguidvalue"></a><a name="setguidvalue"></a>CRegKey::SetGUIDValue  
 Rufen Sie diese Methode, um den GUID-Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetGUIDValue(LPCTSTR pszValueName, REFGUID guidValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `guidValue`  
 Verweis auf die GUID mit dem angegebenen Wertnamen gespeichert werden muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode nutzt `CRegKey::SetStringValue` und die GUID in eine Zeichenfolge konvertiert ["stringfromguid2"](http://msdn.microsoft.com/library/windows/desktop/ms683893).  
  
##  <a name="a-namesetkeyvaluea--cregkeysetkeyvalue"></a><a name="setkeyvalue"></a>CRegKey::SetKeyValue  
 Rufen Sie diese Methode zum Speichern von Daten in einem Feld angegebenen Wert, der einem angegebenen Schlüssel.  
  
```
LONG SetKeyValue(  
    LPCTSTR lpszKeyName,
    LPCTSTR lpszValue,
    LPCTSTR lpszValueName = NULL) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszKeyName`  
 Gibt den Namen des Schlüssels erstellt oder geöffnet werden. Dieser Name muss einem Unterschlüssel des [M_hKey](#m_hkey).  
  
 `lpszValue`  
 Gibt die Daten gespeichert werden. Dieser Parameter muss ungleich NULL sein.  
  
 `lpszValueName`  
 Gibt das Wertfeld festgelegt werden. Wenn ein Wertfeld mit diesem Namen in der Schlüssel nicht bereits vorhanden ist, wird er hinzugefügt.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung gibt ERROR_SUCCESS zurück. andernfalls ein Fehlercode ungleich NULL in WINERROR definiert. H.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Erstellen oder öffnen die `lpszKeyName` Schlüssel und speichern Sie die `lpszValue` Daten in der `lpszValueName` Feld "Wert".  
  
##  <a name="a-namesetkeysecuritya--cregkeysetkeysecurity"></a><a name="setkeysecurity"></a>CRegKey::SetKeySecurity  
 Rufen Sie diese Methode, um die Sicherheit für den Registrierungsschlüssel festgelegt werden.  
  
```
LONG SetKeySecurity(SECURITY_INFORMATION si, PSECURITY_DESCRIPTOR psd) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `si`  
 Gibt die Komponenten des Sicherheitsdeskriptors festlegen. Der Wert kann eine Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|DACL_SECURITY_INFORMATION|Legt den Schlüssel discretionary Access Control (List, DACL). Der Schlüssel muss über WRITE_DAC-Zugriff haben, oder der aufrufende Prozess muss den Besitzer des Objekts sein.|  
|GROUP_SECURITY_INFORMATION|Legt den Schlüssel primäre Gruppe Sicherheits-ID (SID). Der Schlüssel muss WRITE_OWNER Zugriff haben, oder der aufrufende Prozess muss den Besitzer des Objekts sein.|  
|OWNER_SECURITY_INFORMATION|Legt fest, der Besitzer des Schlüssels SID. Die Schlüssel muss WRITE_OWNER Zugriff, oder der aufrufende Prozess muss den Besitzer des Objekts oder die Berechtigung SE_TAKE_OWNERSHIP_NAME aktiviert.|  
|SACL_SECURITY_INFORMATION|Legt den Schlüssel System Access Control List (SACL). Der Schlüssel muss es sich um ACCESS_SYSTEM_SECURITY Zugriff haben. Die richtige Methode zum Abrufen dieser Zugriff wird zum Aktivieren der SE_SECURITY_NAME [Berechtigung](http://msdn.microsoft.com/library/windows/desktop/aa379306) im aktuellen Zugriffstoken des Aufrufers, öffnen Sie das Handle für den ACCESS_SYSTEM_SECURITY Zugriff, und deaktivieren Sie die Berechtigung.|  
  
 `psd`  
 Zeiger auf eine [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) -Struktur, die die Sicherheitsattribute für den angegebenen Schlüssel festlegen angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Legt die Sicherheitsattribute für den Schlüssel fest. Finden Sie unter [RegSetKeySecurity](http://msdn.microsoft.com/library/windows/desktop/aa379314) Weitere Details.  
  
##  <a name="a-namesetmultistringvaluea--cregkeysetmultistringvalue"></a><a name="setmultistringvalue"></a>CRegKey::SetMultiStringValue  
 Rufen Sie diese Methode, um den Mehrfachzeichenfolge Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetMultiStringValue(LPCTSTR pszValueName, LPCTSTR pszValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `pszValue`  
 Ein Zeiger auf die mehrteilige Zeichenfolgen mit dem angegebenen Wertnamen zu speichernden Daten. Eine mehrteilige Zeichenfolge ist ein Array mit Null endende Zeichenfolgen, von zwei Null-Zeichen beendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) auf den Wert in der Registrierung schreiben.  
  
##  <a name="a-namesetqwordvaluea--cregkeysetqwordvalue"></a><a name="setqwordvalue"></a>CRegKey::SetQWORDValue  
 Rufen Sie diese Methode, um den QWORD-Wert des Registrierungsschlüssels festzulegen.  
  
```
LONG SetQWORDValue(LPCTSTR pszValueName, ULONGLONG qwValue) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `pszValueName`  
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits vorhanden ist, fügt die Methode ihn dem Schlüssel hinzu.  
  
 `qwValue`  
 Die QWORD-Daten mit dem angegebenen Wertnamen gespeichert werden muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923) auf den Wert in der Registrierung schreiben.  
  
##  <a name="a-namesetstringvaluea--cregkeysetstringvalue"></a><a name="setstringvalue"></a>CRegKey::SetStringValue  
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
 Wenn die Methode erfolgreich ist, ist der Rückgabewert ERROR_SUCCESS. Wenn die Methode fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich&0; (null), der in WINERROR.H definiert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923\(v=vs.85\).aspx) auf den Wert in der Registrierung schreiben.  
  
##  <a name="a-namesetvaluea--cregkeysetvalue"></a><a name="setvalue"></a>CRegKey::SetValue  
 Rufen Sie diese Methode zum Speichern von Daten in das Feld angegebenen Wert eines [M_hKey](#m_hkey). Frühere Versionen dieser Methode werden nicht mehr unterstützt und werden als **ATL_DEPRECATED**.  
  
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
 Zeiger zu einer Zeichenfolge, die den Namen des festzulegenden Wert enthält. Wenn ein Wert mit diesem Namen nicht bereits im Schlüssel vorhanden ist, fügt die-Methode auf den Schlüssel. Wenn `pszValueName` ist NULL oder eine leere Zeichenfolge "", die-Methode legt den Typ und Daten für den Schlüssel des unbenannten oder default-Wert.  
  
 `dwType`  
 Gibt einen Code, der angibt, auf den Datentyp der `pValue` Parameter.  
  
 `pValue`  
 Ein Zeiger auf einen Puffer, der mit dem angegebenen Wertnamen zu speichernden Daten enthält.  
  
 `nBytes`  
 Gibt die Größe in Bytes, der auf den Informationen der `pValue` Parameter. Wenn die Daten des Typs REG_SZ oder REG_EXPAND_SZ REG_MULTI_SZ, `nBytes` muss die Größe des beendenden Null-Zeichen enthalten.  
  
 `hKeyParent`  
 Das Handle des ein geöffneter Schlüssel.  
  
 `lpszKeyName`  
 Gibt den Namen eines Schlüssels erstellt oder geöffnet werden. Dieser Name muss einem Unterschlüssel des `hKeyParent`.  
  
 `lpszValue`  
 Gibt die Daten gespeichert werden. Dieser Parameter muss ungleich NULL sein.  
  
 `lpszValueName`  
 Gibt das Wertfeld festgelegt werden. Wenn ein Wertfeld mit diesem Namen in der Schlüssel nicht bereits vorhanden ist, wird er hinzugefügt.  
  
 `dwValue`  
 Gibt die Daten gespeichert werden.  
  
 `bMulti`  
 Bei false gibt an, dass die Zeichenfolge vom Typ "REG_SZ" ist. True gibt an, dass die Zeichenfolge eine mehrteilige Zeichenfolge des Typs REG_MULTI_SZ ist.  
  
 `nValueLen`  
 Wenn `bMulti` true ist, `nValueLen` ist die Länge der *LpszValue* Zeichenfolge in Zeichen. Wenn `bMulti` false ist, der Wert-1 gibt an, dass die Methode die Länge automatisch berechnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei erfolgreicher Ausführung gibt ERROR_SUCCESS zurück. andernfalls ein Fehlercode ungleich NULL in WINERROR definiert. H.  
  
### <a name="remarks"></a>Hinweise  
 Die beiden ursprünglichen Versionen der `SetValue` werden als **ATL_DEPRECATED** und sollte nicht mehr verwendet werden. Der Compiler wird eine Warnung ausgegeben, wenn diese Formulare verwendet werden.  
  
 Ruft die dritte Methode [RegSetValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724923).  
  
## <a name="see-also"></a>Siehe auch  
 [DCOM-Beispiel](../../visual-cpp-samples.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

