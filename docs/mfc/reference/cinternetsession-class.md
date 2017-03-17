---
title: CInternetSession Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
dev_langs:
- C++
helpviewer_keywords:
- CInternetSession class
- Internet sessions
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
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
ms.openlocfilehash: caec3ae416dc82d49fc0051f0d9d1d2e021e0ba5
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetsession-class"></a>CInternetSession-Klasse
Erstellt und initialisiert einzelne oder mehrere gleichzeitige Internetsitzungen und beschreibt ggf. die Verbindung mit einem Proxyserver.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInternetSession : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetSession::CInternetSession](#cinternetsession)|Erstellt ein `CInternetSession`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetSession::Close](#close)|Schließt die Verbindung zum Internet, wenn die Internet-Sitzung beendet wird.|  
|[CInternetSession:: EnableStatusCallback](#enablestatuscallback)|Richtet eine Status-Callback-Routine.|  
|[CInternetSession::GetContext](#getcontext)|Schließt die Verbindung zum Internet, wenn die Internet-Sitzung beendet wird.|  
|[CInternetSession::GetCookie](#getcookie)|Cookies zurückgegeben für die angegebene URL und alle übergeordneten URLs.|  
|[CInternetSession::GetCookieLength](#getcookielength)|Ruft die Variable, die die Länge des Cookies im Puffer gespeichert.|  
|[CInternetSession:: GetFTPConnection](#getftpconnection)|Öffnet eine FTP-Sitzung mit einem Server. Meldet sich der Benutzer an.|  
|[CInternetSession:: GetGopherConnection](#getgopherconnection)|Öffnet einen Gopher-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|  
|[CInternetSession:: GetHttpConnection](#gethttpconnection)|Öffnet einen HTTP-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|  
|[CInternetSession:: OnStatusCallback](#onstatuscallback)|Aktualisiert den Status eines Vorgangs, wenn Statusrückruf aktiviert ist.|  
|[OpenURL](#openurl)|Analysiert und eine URL geöffnet.|  
|[CInternetSession::SetCookie](#setcookie)|Legt ein Cookie für die angegebene URL fest.|  
|[CInternetSession:: SetOption](#setoption)|Legt Optionen für die Internet-Sitzung.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Ein Handle für die aktuelle Internet-Sitzung.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Ihre Internet-Verbindung für die Dauer einer Anwendung verwaltet werden muss, erstellen Sie eine `CInternetSession` Member der Klasse [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Nachdem Sie eine Internet-Sitzung hergestellt haben, können Sie aufrufen [OpenURL](#openurl). `CInternetSession`Klicken Sie dann die URL für Sie durch Aufrufen der globalen Funktion analysiert [AfxParseURL](http://msdn.microsoft.com/library/505c717e-aa52-4106-8522-eedff3d9bbae). Unabhängig vom Protokolltyp `CInternetSession` interpretiert die URL, und es für Sie verwaltet. Sie können Anforderungen für lokale Dateien mit der URL-Ressource "file://" identifiziert behandeln. `OpenURL`Gibt einen Zeiger auf eine [CStdioFile](../../mfc/reference/cstdiofile-class.md) -Objekt, wenn Sie ihr den Namen übergeben, ist eine lokale Datei.  
  
 Wenn Sie eine URL auf einem Server mit Internet öffnen `OpenURL`, erhalten Sie Informationen von der Website. Wenn Sie dienstspezifische (z. B. HTTP, FTP oder Gopher) Aktionen auf Dateien auf einem Server ausführen möchten, müssen Sie die entsprechende Verbindung mit dem Server einrichten. Um eine bestimmte Art von Verbindung direkt mit einem bestimmten Dienst zu öffnen, verwenden Sie eine der folgenden Memberfunktionen:  
  
- [GetGopherConnection](#getgopherconnection) zum Öffnen einer Verbindung zu einem Gopher-Dienst.  
  
- [GetHttpConnection hergestellt](#gethttpconnection) zum Öffnen einer Verbindung zu einem HTTP-Dienst.  
  
- [GetFtpConnection](#getftpconnection) zum Öffnen einer Verbindung mit einem FTP-Dienst.  
  
 [SetOption](#setoption) ermöglicht es Ihnen, Ihre Sitzung, z. B. Timeoutwerte, Anzahl der Wiederholungsversuche, die Abfrageoptionen festlegen und so weiter.  
  
 `CInternetSession`Memberfunktionen [SetCookie](#setcookie), [GetCookie](#getcookie), und [GetCookieLength](#getcookielength) bieten die Möglichkeit, eine Win32-Cookie Datenbank zu verwalten, über den Server und Skripts Statusinformationen über die Client-Arbeitsstation verwalten.  
  
 Weitere Informationen zu grundlegenden Internet Programmieraufgaben, finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md). Allgemeine Informationen zur Verwendung der MFC-WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
> `CInternetSession`Löst ein [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) für nicht unterstützte Datentypen. Nur die folgenden Diensttypen werden derzeit unterstützt: FTP, HTTP, Gopher und Datei.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cinternetsession"></a>CInternetSession::CInternetSession  
 Diese Member-Funktion wird aufgerufen, wenn ein `CInternetSession` Objekt erstellt wird.  
  
```  
CInternetSession(
    LPCTSTR pstrAgent = NULL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,  
    LPCTSTR pstrProxyName = NULL,  
    LPCTSTR pstrProxyBypass = NULL,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrAgent`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen der Anwendung oder der verbundenen Entität Aufrufen der Internet-Funktionen (z. B. "Microsoft Internet Browser") bezeichnet. Wenn `pstrAgent` ist **NULL** (Standard) festgelegt ist, ruft das Framework die globale Funktion [AfxGetAppName](application-information-and-management.md#afxgetappname), die eine Null-terminierte Zeichenfolge, die mit einer Anwendung Namen zurückgibt. Einige Protokolle verwenden Sie diese Zeichenfolge zum Identifizieren Ihrer Anwendung auf dem Server.  
  
 `dwContext`  
 Die Kontext-ID für den Vorgang. `dwContext`identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](#onstatuscallback). Der Standardwert ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und die Arbeit ist, werden dieser Kontext-ID zugeordnet werden.  
  
 `dwAccessType`  
 Die Art des Zugriffs, die erforderlich sind. Die folgenden sind Werte gültig, von denen genau, die eines ausgeliefert werden:  
  
- **INTERNET_OPEN_TYPE_PRECONFIG** Verbinden mit vorkonfigurierten Einstellungen in der Registrierung. Dieser Art wird als Standard festgelegt. Verbindung über ein TIS-Proxy legen `dwAccessType` mit diesem Wert; Sie dann die Registrierung entsprechend festgelegt.  
  
- `INTERNET_OPEN_TYPE_DIRECT`Direkt mit dem Internet verbinden.  
  
- `INTERNET_OPEN_TYPE_PROXY`Verbinden Sie über einen CERN-Proxy.  
  
 Informationen zum Herstellen einer Verbindung mit verschiedenen Typen von Proxys finden Sie unter [Schritte in einer Typischen FTP-Clientanwendung](../../mfc/steps-in-a-typical-ftp-client-application.md).  
  
 *pstrProxyName*  
 Der Name des bevorzugten CERN-Proxy Wenn `dwAccessType` festgelegt ist, als `INTERNET_OPEN_TYPE_PROXY`. Der Standardwert ist **NULL**.  
  
 *pstrProxyBypass*  
 Ein Zeiger auf eine Zeichenfolge, die eine optionale Liste von Adressen für Server enthält. Bei Verwendung des Proxyzugriffs, können diese Adressen umgangen werden. Wenn ein **NULL** -Wert angegeben ist, wird die Umgehungsliste aus der Registrierung gelesen werden. Dieser Parameter hat nur dann, wenn `dwAccessType` Wert `INTERNET_OPEN_TYPE_PROXY`.  
  
 `dwFlags`  
 Gibt verschiedene Optionen zum Zwischenspeichern. Der Standardwert ist auf 0 festgelegt. Mögliche Werte sind:  
  
- `INTERNET_FLAG_DONT_CACHE`Die Daten sollten nicht zwischengespeichert werden, entweder lokal oder in einen beliebigen Gatewayserver.  
  
- `INTERNET_FLAG_OFFLINE`Download-Vorgänge über den persistenten Cache nur zufrieden sind. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechende Fehlercode zurückgegeben. Dieses Flag kann mit einer bitweisen kombiniert werden `OR` ( **|**) Operator.  
  
### <a name="remarks"></a>Hinweise  
 **CInternetSession** die erste Internet-Funktion, die von einer Anwendung aufgerufen wird. Interne Datenstrukturen initialisiert und für zukünftige Aufrufe der Anwendung wird vorbereitet.  
  
 Wenn keine Verbindung zum Internet geöffnet werden kann, `CInternetSession` löst ein [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="close"></a>CInternetSession::Close  
 Rufen Sie diese Memberfunktion Beendigung die Anwendung mithilfe der `CInternetSession` Objekt.  
  
```  
virtual void Close();
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="enablestatuscallback"></a>CInternetSession:: EnableStatusCallback  
 Rufen Sie diese Memberfunktion zum Rückruf zu aktivieren.  
  
```  
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob der Rückruf aktiviert oder deaktiviert ist. Der Standardwert ist **TRUE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Beim Rückruf zu behandeln, können Sie Statusinformationen über den Fortschritt des Vorgangs (z. B. Auflösen von Namen, um eine Verbindung zum Server usw.) in der Statusleiste der Anwendung bereitstellen. Anzeigen des Vorgangsstatus ist insbesondere während eines langfristigen Vorgangs.  
  
 Da während der Verarbeitung der Anforderung Rückrufe ausgeführt werden, sollte die Anwendung so wenig Zeit wie möglich in der Rückruf, der eine Verringerung der Datendurchsatz mit dem Netzwerk zu verhindern, dass verbringen. Beispielsweise ein Dialogfeld einen Rückruf bereitstellen solcher eines längeren Vorgangs möglicherweise, dass der Server die Anforderung beendet wird.  
  
 Der Rückruf kann nicht entfernt werden, solange die Rückrufe ausstehen.  
  
 Behandeln Sie alle Vorgänge asynchron müssen Sie einen eigenen Thread erstellen oder verwenden Sie die WinInet-Funktionen ohne MFC.  
  
##  <a name="getcontext"></a>CInternetSession::GetContext  
 Rufen Sie diese Memberfunktion, um den Kontext für eine bestimmte anwendungssitzung nutzen.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der anwendungsspezifische-Kontext Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 [OnStatusCallback](#onstatuscallback) verwendet, die die Kontext-ID, die von zurückgegebenen **GetContext** um den Status einer bestimmten Anwendung melden. Wenn ein Benutzer eine internetanforderung aktiviert, bei der Rückgabe von Statusinformationen, verwendet der Statusrückruf die Kontext-ID Statusberichte z. B. auf diese bestimmte Anforderung. Wenn der Benutzer zwei Separate aktiviert Internet angefordert wird, dass in beiden Fällen Rückgabe von Statusinformationen, `OnStatusCallback` die Kontext-IDs verwendet, über die entsprechenden Anforderungen zurück. Daher wird die Kontext-ID für alle Status Rückrufvorgänge verwendet, und die Sitzung, bis die Sitzung beendet wird, zugeordnet ist.  
  
 Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="getcookie"></a>CInternetSession::GetCookie  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPTSTR pstrCookieData,  
    DWORD dwBufLen);

 
static BOOL GetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    CString& strCookieData);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrUrl`  
 Ein Zeiger auf eine Zeichenfolge mit der URL.  
  
 `pstrCookieName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Cookies, das für die angegebene URL abrufen.  
  
 `pstrCookieData`  
 In der ersten Überladung ist ein Zeiger auf eine Zeichenfolge, die die Adresse des Puffers, der die Cookiedaten empfängt. Dieser Wert kann **NULL**. In der zweiten Überladung, die einen Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die Cookiedaten zu empfangen.  
  
 `dwBufLen`  
 Die Variable angeben der Größe der `pstrCookieData` Puffer. Wenn die Funktion erfolgreich ist, empfängt der Puffer die Menge der Daten, die in kopiert die `pstrCookieData` Puffer. Wenn `pstrCookieData` ist **NULL**, diesen Parameter erhält einen Wert, der angibt, die Größe des Puffers erforderlich, um die Cookiedaten kopieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** im Erfolgsfall oder **FALSE** andernfalls. Wenn der Aufruf fehlschlägt, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) die Ursache des Fehlers bestimmen. Die folgenden Fehlerwerte gelten:  
  
- **ERROR_NO_MORE_ITEMS** kein Cookie für die angegebene URL und alle übergeordneten vorhanden ist.  
  
- **ERROR_INSUFFICIENT_BUFFER** der übergebene Wert `dwBufLen` ausreicht, um die Cookiedaten kopieren. Der zurückgegebene Wert in `dwBufLen` ist die Größe des Puffers zum Abrufen aller Daten.  
  
### <a name="remarks"></a>Hinweise  
 In der zweiten Überladung ruft MFC die Cookiedaten in die angegebene `CString` Objekt.  
  
##  <a name="getcookielength"></a>CInternetSession::GetCookieLength  
 Rufen Sie diese Memberfunktion zum Abrufen der Länge des Cookies im Puffer gespeichert.  
  
```  
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrUrl`  
 Ein Zeiger auf eine Zeichenfolge mit der URL  
  
 `pstrCookieName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Cookies enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der die Länge des Cookies, die im Puffer gespeichert. NULL, wenn kein Cookie mit dem Namen erkennbar `pstrCookieName` vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird verwendet, indem [GetCookie](#getcookie).  
  
##  <a name="getftpconnection"></a>CInternetSession:: GetFTPConnection  
 Rufen Sie diese Memberfunktion auf, um eine FTP-Verbindung herzustellen, und ermitteln einen Zeiger auf ein `CFtpConnection` Objekt.  
  
```  
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den FTP-Servernamen enthält.  
  
 `pstrUserName`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers an, Anmeldung angibt. Wenn **NULL**, der Standardwert ist anonymous.  
  
 `pstrPassword`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Kennwort für die Anmeldung verwenden. Wenn beide `pstrPassword` und `pstrUserName` sind **NULL**, das anonyme Standardkennwort lautet die e-Mail-Namen des Benutzers. Wenn `pstrPassword` ist **NULL** (oder eine leere Zeichenfolge), aber `pstrUserName` nicht **NULL**, ein leeres Kennwort verwendet wird. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der `pstrUserName` und `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP-Server gesendeten Benutzernamen|Kennwort zum FTP-Server gesendet wird.|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** oder ""|**NULL** oder ""|"Anonym"|Die e-Mail-Namen des Benutzers|  
|Nicht- **NULL** Zeichenfolge|**NULL** oder ""|`pstrUserName`|" "|  
|**NULL** nicht **NULL** Zeichenfolge|**FEHLER**|**FEHLER**||  
|Nicht- **NULL** Zeichenfolge|Nicht- **NULL** Zeichenfolge|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port an, auf dem Server identifiziert.  
  
 `bPassive`  
 Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn auf festgelegt **TRUE**, wird die Win32-API- `dwFlag` auf **INTERNET_FLAG_PASSIVE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CFtpConnection](../../mfc/reference/cftpconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `GetFtpConnection`eine Verbindung mit einem FTP-Server erstellt und gibt einen Zeiger auf eine **CFTPConnection** Objekt. Jeder bestimmte Vorgänge auf dem Server wird nicht ausgeführt. Wenn Sie beabsichtigen, lesen oder Schreiben von Dateien, zum Beispiel müssen Sie diese Vorgänge als separate Schritte ausführen. Finden Sie unter [CFtpConnection](../../mfc/reference/cftpconnection-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) für Informationen zum Suchen nach Dateien, Öffnen von Dateien, und das Lesen oder Schreiben von Dateien. Finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md) für Schritte in Ausführen häufig anfallender Aufgaben der FTP-Verbindung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="getgopherconnection"></a>CInternetSession:: GetGopherConnection  
 Rufen Sie diese Memberfunktion auf, um eine neue Gopherverbindung herstellen, und ermitteln einen Zeiger auf ein `CGopherConnection` Objekt.  
  
```  
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Gopher-Servers enthält.  
  
 `pstrUserName`  
 Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.  
  
 `pstrPassword`  
 Ein Zeiger auf eine Zeichenfolge, die das Kennwort enthält.  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port an, auf dem Server identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `GetGopherConnection`eine Verbindung mit einem Gopher-Server her und erstellt und gibt einen Zeiger auf ein `CGopherConnection` Objekt. Jeder bestimmte Vorgänge auf dem Server wird nicht ausgeführt. Wenn Sie Daten lesen oder schreiben möchten, müssen Sie z. B. diese Operationen als separate Schritte ausführen. Finden Sie unter [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), und [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) für Informationen zum Suchen nach Dateien, Öffnen von Dateien, und das Lesen oder Schreiben von Dateien. Informationen zu eine FTP-Site durchsuchen, finden Sie unter der Memberfunktion [OpenURL](#openurl). Finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md) für Schritte in Ausführen von häufigen Aufgaben von Gopher-Verbindung.  
  
##  <a name="gethttpconnection"></a>CInternetSession:: GetHttpConnection  
 Rufen Sie diese Memberfunktion auf, um eine HTTP-Verbindung herzustellen, und ermitteln einen Zeiger auf ein `CHttpConnection` Objekt.  
  
```  
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);

 
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des HTTP-Servers enthält.  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port an, auf dem Server identifiziert.  
  
 `pstrUserName`  
 Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.  
  
 `pstrPassword`  
 Ein Zeiger auf eine Zeichenfolge, die das Kennwort enthält.  
  
 *dwFlags*  
 Eine beliebige Kombination der **INTERNET_ FLAG_\* ** Flags. Siehe die Tabelle in der **Hinweise** im Abschnitt [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) eine Beschreibung der `dwFlags` Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CHttpConnection](../../mfc/reference/chttpconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `GetHttpConnection`eine Verbindung mit einem HTTP-Server her und erstellt und gibt einen Zeiger auf ein `CHttpConnection` Objekt. Jeder bestimmte Vorgänge auf dem Server wird nicht ausgeführt. Wenn Sie beabsichtigen, einen HTTP-Header Abfragen, z. B. müssen Sie diesen Vorgang als separater Schritt ausführen. Finden Sie unter [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CHttpFile](../../mfc/reference/chttpfile-class.md) Informationen zu Vorgängen können Sie mithilfe von eine Verbindung mit einem HTTP-Server ausführen. Informationen zu eine HTTP-Site durchsuchen, finden Sie unter der Memberfunktion [OpenURL](#openurl). Finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritte bei der Ausführung von Aufgaben für HTTP-Verbindung.  
  
##  <a name="onstatuscallback"></a>CInternetSession:: OnStatusCallback  
 Diese Memberfunktion wird von dem Framework, um den Status zu aktualisieren, wenn Statusrückruf aktiviert ist und ein Vorgang noch wird aufgerufen.  
  
```  
virtual void OnStatusCallback(
    DWORD_PTR dwContext,  
    DWORD dwInternetStatus,  
    LPVOID lpvStatusInformation,  
    DWORD dwStatusInformationLength);
```  
  
### <a name="parameters"></a>Parameter  
 `dwContext`  
 Der Kontextwert von der Anwendung bereitgestellt.  
  
 `dwInternetStatus`  
 Einen Statuscode gibt an, warum der Rückruf erfolgt. Finden Sie unter **Hinweise** für eine Tabelle mit möglichen Werten.  
  
 `lpvStatusInformation`  
 Ein Zeiger auf einen Puffer mit Informationen zu diesen Rückruf.  
  
 `dwStatusInformationLength`  
 Die Größe von `lpvStatusInformation`.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen zuerst Aufrufen [EnableStatusCallback](#enablestatuscallback) Statusrückruf nutzen.  
  
 Die `dwInternetStatus` Parameter gibt die auszuführende Operation an und bestimmt, welche den Inhalt des `lpvStatusInformation` werden. `dwStatusInformationLength`Gibt die Länge der in enthaltenen Daten `lpvStatusInformation`. Die folgenden Statuswerte für `dwInternetStatus` wie folgt definiert:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`INTERNET_STATUS_RESOLVING_NAME`|Der Name in die IP-Adresse nachschlagen `lpvStatusInformation`.|  
|`INTERNET_STATUS_NAME_RESOLVED`|Der Name in die IP-Adresse gefunden `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|Herstellen einer Verbindung mit der Socketadresse ( [SOCKADDR](../../mfc/reference/sockaddr-structure.md)) auf den `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|Verbindung mit der Socketadresse ( `SOCKADDR`) auf den `lpvStatusInformation`.|  
|`INTERNET_STATUS_SENDING_REQUEST`|Die Anforderung an den Server gesendet. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|**INTERNET_STATUS_ REQUEST_SENT**|Die Anforderung wird erfolgreich an den Server gesendet. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_RECEIVING_RESPONSE`|Warten, bis der Server eine Anforderung antworten. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_RESPONSE_RECEIVED`|Erfolgreich empfangen eine Antwort vom Server. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_CLOSING_CONNECTION`|Schließen die Verbindung mit dem Server. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_CONNECTION_CLOSED`|Die Verbindung mit dem Server erfolgreich geschlossen. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_HANDLE_CREATED`|Von der Win32-API-Funktion verwendete [InternetConnect erhalten](http://msdn.microsoft.com/library/windows/desktop/aa384363) um anzugeben, dass das neue Handle erstellt wurde. Auf diese Weise können die Anwendung Aufrufen der Win32-Funktion [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) von einem anderen Thread auf, wenn die Verbindung zu lange dauert. Finden Sie unter den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]für Weitere Informationen zu diesen Funktionen.|  
|`INTERNET_STATUS_HANDLE_CLOSING`|Dieser Handlewert beendet erfolgreich.|  
  
 Überschreiben Sie diese Memberfunktion, um eine Aktion erfordern, bevor eine Status-Callback-Routine ausgeführt wird.  
  
> [!NOTE]
>  Status Rückrufe werden Thread-Status-Schutz benötigen. Wenn Sie MFC in einer freigegebenen Bibliothek verwenden, fügen Sie die folgende Zeile am Anfang der außer Kraft setzen:  
  
 [!code-cpp[NVC_MFCHtmlHttp&#8;](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]  
  
 Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="openurl"></a>OpenURL  
 Rufen Sie bei diesem Member-Funktion die angegebene Anforderung an den HTTP-Server senden und MIME-Client zum Angeben zusätzlicher RFC822 oder HTTP-Header mit der Anforderung zu senden.  
  
```  
CStdioFile* OpenURL(
    LPCTSTR pstrURL,  
    DWORD_PTR dwContext = 1,  
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,  
    LPCTSTR pstrHeaders = NULL,  
    DWORD dwHeadersLength = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrURL*  
 Ein Zeiger auf den Namen der URL gelesen werden soll. Nur URLs Datei ab:, ftp:, Gopher:, oder http: werden unterstützt. **ASSERTIONEN** Wenn *PszURL* ist **NULL**.  
  
 `dwContext`  
 Ein anwendungsdefinierter Wert mit dem Rückruf zurückgegebene Handle übergeben.  
  
 `dwFlags`  
 Die Flags, die beschreiben, wie diese Verbindung zu behandeln. Finden Sie unter **Hinweise** Weitere Informationen zu gültigen Flags. Gültige Flags sind:  
  
- **INTERNET_FLAG_TRANSFER_ASCII** die Standardeinstellung. Übertragen Sie die Datei als ASCII-Text.  
  
- **INTERNET_FLAG_TRANSFER_BINARY** übertragen Sie die Datei als Binärdatei.  
  
- `INTERNET_FLAG_RELOAD`Rufen Sie Daten aus der Übertragung, selbst wenn er lokal zwischengespeichert wird.  
  
- `INTERNET_FLAG_DONT_CACHE`Die Daten sollten nicht zwischengespeichert werden, entweder lokal oder im Gateways.  
  
- `INTERNET_FLAG_SECURE`Dieses Flag gilt nur für HTTP-Anforderungen. Fordert die sichere Transaktionen bei der Übertragung mit Secure Sockets Layer oder Prozent  
  
- **INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT** Wenn möglich, Wiederverwendung die vorhandenen Verbindungen mit dem Server für neue Anforderungen, die von generierten **OpenUrl** statt für jede verbindungsanforderung eine neue Sitzung erstellen.  
  
- **INTERNET_FLAG_PASSIVE** für eine FTP-Site verwendet. Verwendet die passive FTP-Semantik. Mit verwendete [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) von `OpenURL`.  
  
 `pstrHeaders`  
 Ein Zeiger auf eine Zeichenfolge mit den Headern, die an den HTTP-Server gesendet werden.  
  
 *dwHeadersLength*  
 Die Länge in Zeichen, der zusätzliche Header. Ist dies-1 L und `pstrHeaders` nicht **NULL**, dann `pstrHeaders` wird davon ausgegangen, dass&0; (null) beendet, und die Länge wird berechnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Dateihandle für FTP, GOPHER, HTTP und Dateitypen Internet-Dienste. Gibt **NULL** wenn Analyse nicht erfolgreich war.  
  
 Der Zeiger, `OpenURL` gibt hängt *PszURL*der Typ des Diensts. Die nachfolgende Tabelle zeigt die möglichen Zeiger `OpenURL` zurückgeben können.  
  
|URL-Typ|Rückgabe|  
|--------------|-------------|  
|file://|**CStdioFile\***|  
|http://|**CHttpFile\***|  
|Gopher://|**CGopherFile\***|  
|FTP: / /|**CInternetFile\***|  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `dwFlags` umfasst entweder **INTERNET_FLAG_TRANSFER_ASCII** oder **INTERNET_FLAG_TRANSFER_BINARY**, aber nicht beide. Die übrigen Flags können kombiniert werden, mit einer bitweisen `OR` Operator ( **|**).  
  
 `OpenURL`, die die Win32-Funktion umschließt **InternetOpenURL**, können nur herunterladen, abrufen und Lesen der Daten von einem Internetserver. `OpenURL`kann keine Datei an einem Remotestandort daher keine benötigt [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) Objekt.  
  
 Verbindungsspezifische verwenden (d. h. protokollspezifische) Funktionen, wie z. B. das Schreiben in eine Datei, müssen Sie eine Sitzung zu öffnen, klicken Sie dann öffnen Sie eine bestimmte Art von Verbindung und dann mithilfe dieser Verbindung Öffnen einer Datei in den gewünschten Modus. Finden Sie unter `CInternetConnection` Weitere Informationen zu Verbindungs-spezifische Funktionen.  
  
##  <a name="operator_hinternet"></a>CInternetSession::operator HINTERNET  
 Verwenden Sie diesen Operator, um das Windows-Handle für die aktuelle Sitzung mit Internet abzurufen.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="setcookie"></a>CInternetSession::SetCookie  
 Legt ein Cookie für die angegebene URL fest.  
  
```  
static BOOL SetCookie(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName,  
    LPCTSTR pstrCookieData);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrUrl`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die die URL gibt an, für die das Cookie festgelegt werden soll.  
  
 `pstrCookieName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Cookies enthält.  
  
 `pstrCookieData`  
 Ein Zeiger auf eine Zeichenfolge, die die eigentlichen Zeichenfolgendaten, die URL zugeordnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** im Erfolgsfall oder **FALSE** andernfalls. Rufen Sie zum Abrufen des Fehlercode **GetLastError.**  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setoption"></a>CInternetSession:: SetOption  
 Rufen Sie diese Memberfunktion zum Festlegen von Optionen für die Internet-Sitzung.  
  
```  
BOOL SetOption(
    DWORD dwOption,  
    LPVOID lpBuffer,  
    DWORD dwBufferLength,  
    DWORD dwFlags = 0);

 
BOOL SetOption(
    DWORD dwOption,  
    DWORD dwValue,  
    DWORD dwFlags = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `dwOption`  
 Die Internet-Option festgelegt werden soll. Finden Sie unter [Optionsflags](http://msdn.microsoft.com/library/windows/desktop/aa385328) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]eine Liste der möglichen Optionen.  
  
 `lpBuffer`  
 Ein Puffer, der die Einstellung der Option enthält.  
  
 *dwBufferLength*  
 Die Länge des `lpBuffer` oder die Größe des `dwValue`.  
  
 `dwValue`  
 Ein `DWORD` , der die Einstellung der Option enthält.  
  
 `dwFlags`  
 Gibt verschiedene Optionen zum Zwischenspeichern. Der Standardwert ist auf 0 festgelegt. Mögliche Werte sind:  
  
- `INTERNET_FLAG_DONT_CACHE`Die Daten sollten nicht zwischengespeichert werden, entweder lokal oder in einen beliebigen Gatewayserver.  
  
- `INTERNET_FLAG_OFFLINE`Download-Vorgänge über den persistenten Cache nur zufrieden sind. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechende Fehlercode zurückgegeben. Dieses Flag kann mit einer bitweisen kombiniert werden `OR` ( **|**) Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Vorgang erfolgreich, und war der Wert **TRUE** zurückgegeben wird. Wenn ein Fehler aufgetreten ist, der Wert **FALSE** zurückgegeben wird. Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)   
 [CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)   
 [CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)

