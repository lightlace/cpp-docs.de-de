---
title: CInternetSession Klasse | Microsoft Docs
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 1bc8f21cd68741a4b0560ea3e1cb678be50dcf89
ms.lasthandoff: 04/12/2017

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
|[CInternetSession::Close](#close)|Schließt die Internet-Verbindung an, wenn die Internet-Sitzung beendet wird.|  
|[CInternetSession:: EnableStatusCallback](#enablestatuscallback)|Stellt einen Status Abbruchroutine her.|  
|[CInternetSession::GetContext](#getcontext)|Schließt die Internet-Verbindung an, wenn die Internet-Sitzung beendet wird.|  
|[CInternetSession::GetCookie](#getcookie)|Cookies zurückgegeben URLs für die angegebene URL und seinem übergeordneten Element.|  
|[CInternetSession::GetCookieLength](#getcookielength)|Ruft die Variable, die die Länge des Cookies, die im Puffer gespeichert.|  
|[CInternetSession:: GetFTPConnection](#getftpconnection)|Öffnet eine FTP-Sitzung mit einem Server an. Protokolle für den Benutzer.|  
|[CInternetSession:: GetGopherConnection](#getgopherconnection)|Öffnet einen Gopher-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|  
|[CInternetSession:: GetHttpConnection](#gethttpconnection)|Öffnet einen HTTP-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|  
|[CInternetSession:: OnStatusCallback](#onstatuscallback)|Aktualisiert den Status eines Vorgangs an, wenn Statusrückruf aktiviert ist.|  
|[OpenURL](#openurl)|Analysiert und öffnet eine URL.|  
|[CInternetSession::SetCookie](#setcookie)|Legt ein Cookie für die angegebene URL fest.|  
|[CInternetSession:: SetOption](#setoption)|Legt Optionen für die Internet-Sitzung.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Ein Handle für die aktuelle Internet-Sitzung.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Ihre Internet-Verbindung für die Dauer einer Anwendung verwaltet werden muss, können Sie erstellen eine `CInternetSession` Member der Klasse [CWinApp](../../mfc/reference/cwinapp-class.md).  
  
 Sobald Sie eine Internet-Sitzung eingerichtet haben, können Sie aufrufen [OpenURL](#openurl). `CInternetSession`Klicken Sie dann die URL für Sie durch Aufrufen der globalen Funktion analysiert [AfxParseURL](internet-url-parsing-globals.md#afxparseurl). Unabhängig vom Protokolltyp `CInternetSession` interpretiert die URL, und es für Sie verwaltet. Sie können Anforderungen für lokale Dateien identifiziert, mit der URL-Ressource "file://" verarbeiten. `OpenURL`Gibt zurück, einen Zeiger auf eine [CStdioFile](../../mfc/reference/cstdiofile-class.md) -Objekt, wenn Sie den Namen übergeben wird, eine lokale Datei.  
  
 Wenn Sie eine URL auf dem ein Internet Server öffnen `OpenURL`, lesen Sie Informationen von der Website. Wenn Sie die dienstspezifischen (z. B. HTTP, FTP oder Gopher) Aktionen für eine Datei auf einem Server ausführen möchten, müssen Sie die entsprechende Verbindung mit diesem Server einrichten. Um eine bestimmte Art von Verbindung direkt mit einem bestimmten Dienst zu öffnen, verwenden Sie eine der folgenden Memberfunktionen:  
  
- [GetGopherConnection](#getgopherconnection) zum Öffnen einer Verbindung zu einem Gopher-Dienst.  
  
- [GetHttpConnection hergestellt](#gethttpconnection) zum Öffnen einer Verbindung mit einem HTTP-Dienst.  
  
- [GetFtpConnection](#getftpconnection) zum Öffnen einer Verbindung mit einem FTP-Dienst.  
  
 [SetOption](#setoption) können Sie die Abfrageoptionen der Sitzung, wie Timeoutwerte, Anzahl der Wiederholungsversuche, festlegen und so weiter.  
  
 `CInternetSession`Memberfunktionen [SetCookie](#setcookie), [GetCookie](#getcookie), und [GetCookieLength](#getcookielength) bieten die Möglichkeit, eine Win32-Cookie-Datenbank zu verwalten, über den Server und Skripts Statusinformationen über den die Clientarbeitsstation verwalten.  
  
 Weitere Informationen zu grundlegenden Internet Programmieraufgaben erledigen, finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md). Allgemeine Informationen zum Verwenden der MFC-WinInet-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
> [!NOTE]
> `CInternetSession`Löst ein [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) für nicht unterstützte Diensttypen. Nur die folgenden Diensttypen werden derzeit unterstützt: FTP, HTTP, Gopher und Datei.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetSession`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cinternetsession"></a>CInternetSession::CInternetSession  
 Diese Memberfunktion wird aufgerufen, wenn ein `CInternetSession` Objekt erstellt wird.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die den Namen der Anwendung oder der verbundenen Entität, die Internet-Funktionen aufrufen (z. B. "Microsoft Internet-Browser") bezeichnet. Wenn `pstrAgent` ist **NULL** (Standard), das Framework Ruft die globale Funktion [AfxGetAppName](application-information-and-management.md#afxgetappname), die eine Null-terminierte Zeichenfolge, die mit einer Anwendung Namen zurückgibt. Einige Protokolle verwenden diese Zeichenfolge zum Identifizieren Ihrer Anwendung mit dem Server.  
  
 `dwContext`  
 Der Kontextbezeichner für den Vorgang. `dwContext`identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](#onstatuscallback). Die Standardeinstellung ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und jede Arbeit, die es ausführt, werden dieser Kontext-ID zugeordnet werden.  
  
 `dwAccessType`  
 Der Typ des erforderlichen Zugriffsrechte. Die folgenden sind Werte gültig, von denen genau, die eines angegeben werden kann:  
  
- **INTERNET_OPEN_TYPE_PRECONFIG** Verbinden mit vorkonfigurierten Einstellungen in der Registrierung. Dieser Art wird als Standard festgelegt. Legen Sie für die Verbindung über einen Proxy TIS `dwAccessType` mit diesem Wert; Sie dann die Registrierung entsprechend festgelegt.  
  
- `INTERNET_OPEN_TYPE_DIRECT`Direkt mit dem Internet verbinden.  
  
- `INTERNET_OPEN_TYPE_PROXY`Verbinden Sie über einen Proxy CERN.  
  
 Informationen zum Herstellen einer Verbindung mit verschiedenen Typen von Proxys finden Sie unter [Schritte in einer Typischen FTP-Clientanwendung](../../mfc/steps-in-a-typical-ftp-client-application.md).  
  
 *pstrProxyName*  
 Der Name des bevorzugten CERN Proxys Wenn `dwAccessType` festgelegt ist, als `INTERNET_OPEN_TYPE_PROXY`. Die Standardeinstellung ist **NULL**.  
  
 *pstrProxyBypass*  
 Ein Zeiger auf eine Zeichenfolge, enthält eine optionale Liste von Serveradressen. Diese Adressen möglicherweise umgangen werden, wenn Proxyzugriffs verwenden. Wenn eine **NULL** Wert angegeben ist, wird die Umgehungsliste wird aus der Registrierung gelesen werden. Dieser Parameter hat nur, wenn `dwAccessType` festgelegt ist, um `INTERNET_OPEN_TYPE_PROXY`.  
  
 `dwFlags`  
 Gibt verschiedene Cacheoptionen an. Die Standardeinstellung ist auf 0 festgelegt. Mögliche Werte:  
  
- `INTERNET_FLAG_DONT_CACHE`Die Daten nicht zwischengespeichert, entweder lokal oder in einen beliebigen Gatewayserver.  
  
- `INTERNET_FLAG_OFFLINE`Download-Vorgänge über den persistenten Cache nur erfüllt sind. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechende Fehlercode zurückgegeben. Dieses Flag kann mit dem bitweisen kombiniert werden `OR` ( **|**) Operator.  
  
### <a name="remarks"></a>Hinweise  
 **CInternetSession** die erste Internet-Funktion, die von einer Anwendung aufgerufen wird. Interne Datenstrukturen initialisiert, und für zukünftige Aufrufe von der Anwendung wird vorbereitet.  
  
 Wenn keine Verbindung zum Internet geöffnet werden kann, `CInternetSession` löst ein [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="close"></a>CInternetSession::Close  
 Diese Memberfunktion aufgerufen wird, wenn Ihre Anwendung nicht mehr benötigt hat die `CInternetSession` Objekt.  
  
```  
virtual void Close();
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="enablestatuscallback"></a>CInternetSession:: EnableStatusCallback  
 Rufen Sie diese Memberfunktion zum Statusrückruf zu aktivieren.  
  
```  
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob der Rückruf aktiviert oder deaktiviert ist. Die Standardeinstellung ist **"true"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Behandlung von Statusrückruf können Sie den Status über den Fortschritt des Vorgangs (z. B. Auflösen von Namen, eine Verbindung mit Server usw.) in der Statusleiste der Anwendung bereitstellen. Vorgangsstatus für die Anzeige ist während eines langfristigen Vorgangs besonders wünschenswert.  
  
 Da Rückrufe während der Verarbeitung der Anforderung ausgeführt werden, sollte die Anwendung so wenig Zeit wie möglich den Rückruf zur Verringerung des Datendurchsatzes mit dem Netzwerk zu verhindern, dass auseinandersetzen. Z. B. einfügen, wird ein Dialogfeld, in einem Rückruf solche eines längeren Vorgangs möglicherweise, dass der Server die Anforderung beendet wird.  
  
 Der Statusrückruf kann nicht entfernt werden, solange die Rückrufe ausstehen.  
  
 Um alle Vorgänge asynchron zu verarbeiten, müssen Sie entweder Erstellen eigener threadverwaltungsarten oder die ohne MFC-WinInet-Funktionen.  
  
##  <a name="getcontext"></a>CInternetSession::GetContext  
 Rufen Sie diese Memberfunktion um den Kontextwert für eine bestimmte Anwendung-Sitzung zu erhalten.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der anwendungsspezifische-Kontext Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 [OnStatusCallback](#onstatuscallback) verwendet, die die Kontext-ID zurückgegebenes **GetContext** um den Status einer bestimmten Anwendung melden. Wenn ein Benutzer auf eine internetanforderung aktiviert, bei der Rückgabe von Statusinformationen, verwendet der Statusrückruf z. B. die Kontext-ID, um den Berichtstatus auf diese bestimmte Anforderung. Wenn der Benutzer zwei Separate aktiviert Internet angefordert wird, dass in beiden Fällen geht Rückgabe von Statusinformationen, `OnStatusCallback` verwendet die Kontext-IDs, Status zu ihren entsprechenden Anforderungen zurückzugeben. Daher der Kontextbezeichner wird für alle Status Rückrufvorgänge verwendet, und er bezieht sich auf die Sitzung, bis die Sitzung beendet wird.  
  
 Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="getcookie"></a>CInternetSession::GetCookie  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 Ein Zeiger auf eine Zeichenfolge, die die URL enthält.  
  
 `pstrCookieName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Cookies für die angegebene URL abgerufen werden soll.  
  
 `pstrCookieData`  
 In der ersten Überladung ist ein Zeiger auf eine Zeichenfolge, enthält die Adresse des Puffers, der die Cookiedaten empfängt. Mögliche Werte sind **NULL**. In der zweiten Überladung ist ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das die Cookiedaten zu empfangen.  
  
 `dwBufLen`  
 Die Variable angeben der Größe der `pstrCookieData` Puffer. Wenn die Funktion erfolgreich ausgeführt wird, empfängt der Puffer die Menge der Daten in kopiert die `pstrCookieData` Puffer. Wenn `pstrCookieData` ist **NULL**, dieser Parameter erhält einen Wert, der die Größe des Puffers erforderlich, kopieren Sie die Cookiedaten angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** im Erfolgsfall oder **"false"** andernfalls. Wenn der Aufruf fehlschlägt, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um die Ursache des Fehlers zu bestimmen. Die folgenden Fehlerwerte gelten:  
  
- **ERROR_NO_MORE_ITEMS** kein Cookie für die angegebene URL und alle übergeordneten Elemente vorhanden ist.  
  
- **ERROR_INSUFFICIENT_BUFFER** der übergebene Wert `dwBufLen` ausreicht, um die Cookiedaten kopieren. Der zurückgegebene Wert in `dwBufLen` ist die Größe des Puffers erforderlich, um alle Daten zu erhalten.  
  
### <a name="remarks"></a>Hinweise  
 In der zweiten Überladung MFC die Cookiedaten in das angegebene abruft `CString` Objekt.  
  
##  <a name="getcookielength"></a>CInternetSession::GetCookieLength  
 Rufen Sie diese Memberfunktion zum Abrufen der Länge des Cookies, die im Puffer gespeichert.  
  
```  
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,  
    LPCTSTR pstrCookieName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrUrl`  
 Ein Zeiger auf eine Zeichenfolge, die die URL enthält.  
  
 `pstrCookieName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Cookies.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der angibt, der Länge des Cookies, die im Puffer gespeichert. NULL, wenn kein Cookie mit dem Namen erkennbar `pstrCookieName` vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wird verwendet, indem [GetCookie](#getcookie).  
  
##  <a name="getftpconnection"></a>CInternetSession:: GetFTPConnection  
 Rufen Sie diese Memberfunktion zum Einrichten der FTP-Verbindung verwenden und einen Zeiger auf eine `CFtpConnection` Objekt.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die den Namen des FTP-Server enthält.  
  
 `pstrUserName`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers anmelden angibt. Wenn **NULL**, der Standardwert ist anonymous.  
  
 `pstrPassword`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Kennwort zur Anmeldung verwenden. Wenn beide `pstrPassword` und `pstrUserName` sind **NULL**, das anonymen Standard-Kennwort ist die e-Mail-Namen des Benutzers. Wenn `pstrPassword` ist **NULL** (oder eine leere Zeichenfolge), aber `pstrUserName` nicht **NULL**, ein leeres Kennwort verwendet. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der `pstrUserName` und `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP-Server gesendeten Benutzernamen|Kennwort mit FTP-Server gesendet wird.|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** oder ""|**NULL** oder ""|"Anonym"|Die e-Mail-Namen des Benutzers|  
|Nicht- **NULL** Zeichenfolge|**NULL** oder ""|`pstrUserName`|" "|  
|**NULL** nicht- **NULL** Zeichenfolge|**FEHLER**|**FEHLER**||  
|Nicht- **NULL** Zeichenfolge|Nicht- **NULL** Zeichenfolge|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.  
  
 `bPassive`  
 Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn auf festgelegt **"true"**, wird die Win32-API `dwFlag` auf **INTERNET_FLAG_PASSIVE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CFtpConnection](../../mfc/reference/cftpconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `GetFtpConnection`eine Verbindung mit einem FTP-Server her und erstellt und gibt einen Zeiger auf eine **CFTPConnection** Objekt. Es führt kein bestimmten Vorgang auf dem Server. Wenn Sie beabsichtigen, Lese- und Schreibvorgänge für Dateien, z. B. müssen Sie diese Vorgänge als separate Schritte ausführen. Finden Sie in den Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) für Informationen zum Suchen nach Dateien, Öffnen von Dateien, und das Lesen oder Schreiben in Dateien. Finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritten ausführen von häufigen Aufgaben von FTP-Verbindung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).  
  
##  <a name="getgopherconnection"></a>CInternetSession:: GetGopherConnection  
 Rufen Sie diese Memberfunktion auf, um eine neue Gopherverbindung herstellen und ermitteln einen Zeiger auf eine `CGopherConnection` Objekt.  
  
```  
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den Gopher-Servernamen enthält.  
  
 `pstrUserName`  
 Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.  
  
 `pstrPassword`  
 Ein Zeiger auf eine Zeichenfolge, enthält das Zugriffskennwort.  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `GetGopherConnection`eine Verbindung mit einem Gopher-Server her und erstellt und gibt einen Zeiger auf eine `CGopherConnection` Objekt. Es führt kein bestimmten Vorgang auf dem Server. Wenn Sie Daten lesen oder schreiben möchten, müssen Sie z. B. Operationen als separate Schritte ausführen. Finden Sie in den Klassen [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), und [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) für Informationen zum Suchen nach Dateien, Öffnen von Dateien, und das Lesen oder Schreiben in Dateien. Informationen zum Durchsuchen einer FTP-Site finden Sie in der Memberfunktion [OpenURL](#openurl). Finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritten ausführen von häufigen Aufgaben von Gopher-Verbindung.  
  
##  <a name="gethttpconnection"></a>CInternetSession:: GetHttpConnection  
 Rufen Sie diese Memberfunktion zum Herstellen einer HTTP-Verbindungs verwenden und einen Zeiger auf eine `CHttpConnection` Objekt.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die den Namen der HTTP-Server enthält.  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.  
  
 `pstrUserName`  
 Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.  
  
 `pstrPassword`  
 Ein Zeiger auf eine Zeichenfolge, enthält das Zugriffskennwort.  
  
 *dwFlags*  
 Eine beliebige Kombination der **INTERNET_ FLAG_\*** Flags. Finden Sie in der Tabelle in der **"Hinweise"** Abschnitt [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) eine Beschreibung der `dwFlags` Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CHttpConnection](../../mfc/reference/chttpconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `GetHttpConnection`eine Verbindung mit einem HTTP-Server her und erstellt und gibt einen Zeiger auf eine `CHttpConnection` Objekt. Es führt kein bestimmten Vorgang auf dem Server. Wenn Sie beabsichtigen, einen HTTP-Header Abfragen, z. B. müssen Sie diesen Vorgang als separater Schritt ausführen. Finden Sie in den Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CHttpFile](../../mfc/reference/chttpfile-class.md) Informationen zu Vorgängen, die Sie mit der eine Verbindung mit einem HTTP-Server ausführen können. Informationen zum Durchsuchen einer HTTP-Website finden Sie die Memberfunktion [OpenURL](#openurl). Finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritte bei der Ausführung von Aufgaben für HTTP-Verbindung.  
  
##  <a name="onstatuscallback"></a>CInternetSession:: OnStatusCallback  
 Diese Memberfunktion wird aufgerufen, durch das Framework der Status aktualisiert, wenn Statusrückruf aktiviert ist und ein Vorgang zur Verfügung steht.  
  
```  
virtual void OnStatusCallback(
    DWORD_PTR dwContext,  
    DWORD dwInternetStatus,  
    LPVOID lpvStatusInformation,  
    DWORD dwStatusInformationLength);
```  
  
### <a name="parameters"></a>Parameter  
 `dwContext`  
 Der Kontextwert von der Anwendung bereitgestellt wird.  
  
 `dwInternetStatus`  
 Einen Statuscode gibt an, warum der Rückruf erfolgt. Finden Sie unter **"Hinweise"** für eine Tabelle mit möglichen Werten.  
  
 `lpvStatusInformation`  
 Ein Zeiger auf einen Puffer mit den Informationen zu diesem Rückruf.  
  
 `dwStatusInformationLength`  
 Die Größe von `lpvStatusInformation`.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen zuerst Aufrufen [EnableStatusCallback](#enablestatuscallback) Statusrückruf nutzen.  
  
 Die `dwInternetStatus` Parameter gibt die auszuführende Operation an und bestimmt, welche den Inhalt der `lpvStatusInformation` werden. `dwStatusInformationLength`Gibt die Länge der Daten `lpvStatusInformation`. Der Status der folgenden Werte für `dwInternetStatus` wie folgt definiert:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|`INTERNET_STATUS_RESOLVING_NAME`|Die IP-Adresse mit dem Namen, die in enthaltenen Nachschlagen `lpvStatusInformation`.|  
|`INTERNET_STATUS_NAME_RESOLVED`|Die IP-Adresse mit dem Namen enthalten, die erfolgreich gefunden `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTING_TO_SERVER`|Herstellen einer Verbindung mit der Socketadresse ( [SOCKADDR](../../mfc/reference/sockaddr-structure.md)) verweist, zu `lpvStatusInformation`.|  
|`INTERNET_STATUS_CONNECTED_TO_SERVER`|Erfolgreich mit Socketadresse verbunden ( `SOCKADDR`) verweist, zu `lpvStatusInformation`.|  
|`INTERNET_STATUS_SENDING_REQUEST`|Die Anforderung an den Server gesendet. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|**INTERNET_STATUS_ REQUEST_SENT**|Die Anforderung wird erfolgreich an den Server gesendet. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_RECEIVING_RESPONSE`|Es wird darauf gewartet, dass des Servers auf eine Anforderung reagiert. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_RESPONSE_RECEIVED`|Erfolgreich empfangen eine Antwort vom Server. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_CLOSING_CONNECTION`|Schließen die Verbindung mit dem Server. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_CONNECTION_CLOSED`|Erfolgreich geschlossen, die Verbindung mit dem Server. Die `lpvStatusInformation` Parameter ist **NULL**.|  
|`INTERNET_STATUS_HANDLE_CREATED`|Von der Win32-API-Funktion verwendeten [InternetConnect erhalten](http://msdn.microsoft.com/library/windows/desktop/aa384363) , um anzugeben, dass sie das neue Handle erstellt wurde. Auf diese Weise können die Anwendung Aufruf der Win32-Funktion [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) aus einem anderen Thread auf, wenn die Verbindung zu lange dauert. Finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]für Weitere Informationen zu diesen Funktionen.|  
|`INTERNET_STATUS_HANDLE_CLOSING`|Erfolgreich beendet diese Handlewert.|  
  
 Überschreiben Sie diese Memberfunktion, um eine Aktion erfordern, bevor Rückrufroutine Status ausgeführt wird.  
  
> [!NOTE]
>  Status Rückrufe benötigen Threadzustand Schutz. Wenn Sie MFC in einer freigegebenen Bibliothek verwenden, fügen Sie die folgende Zeile am Anfang der Außerkraftsetzung aus:  
  
 [!code-cpp[NVC_MFCHtmlHttp #8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]  
  
 Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md).  
  
##  <a name="openurl"></a>OpenURL  
 Rufen Sie bei diesem Member-Funktion die angegebene Anforderung an den HTTP-Server senden und ermöglichen es dem Client an zusätzliche RFC822 MIME- oder HTTP-Header mit der Anforderung zu senden.  
  
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
 Ein Zeiger auf den Namen der URL gelesen werden soll. Nur URLs mit der Datei ab:, ftp:, Gopher:, oder http: werden unterstützt. **ASSERTIONEN** Wenn *PszURL* ist **NULL**.  
  
 `dwContext`  
 Ein anwendungsdefinierten Wert, die mit das zurückgegebene Handle Rückruf übergeben werden.  
  
 `dwFlags`  
 Die Flags, die beschreiben, wie diese Verbindung zu behandeln. Finden Sie unter **"Hinweise"** für Weitere Informationen über die gültigen Flags. Die gültigen Flags sind:  
  
- **INTERNET_FLAG_TRANSFER_ASCII** die Standardeinstellung. Übertragen Sie die Datei als ASCII-Text.  
  
- **INTERNET_FLAG_TRANSFER_BINARY** übertragen Sie die Datei als Binärdatei.  
  
- `INTERNET_FLAG_RELOAD`Rufen Sie Daten aus der Übertragung, auch wenn diese lokal zwischengespeichert wird.  
  
- `INTERNET_FLAG_DONT_CACHE`Die Daten nicht zwischengespeichert, entweder lokal oder in Gateways.  
  
- `INTERNET_FLAG_SECURE`Dieses Flag gilt nur für HTTP-Anforderungen zur Verfügung. Sichere Transaktionen bei der Übertragung mit Secure Sockets Layer "oder" Prozent fordert  
  
- **INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT** wiederverwenden Wenn möglich, alle bestehenden Verbindungen mit dem Server neue Anforderungen von generierten **OpenUrl** statt zu eine neue Sitzung für jede verbindungsanforderung erstellen.  
  
- **INTERNET_FLAG_PASSIVE** für eine FTP-Site verwendet. Wird verwendet, passive FTP-Semantik. Mit verwendet [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) von `OpenURL`.  
  
 `pstrHeaders`  
 Ein Zeiger auf eine Zeichenfolge, enthält der Header an den HTTP-Server gesendet werden.  
  
 *dwHeadersLength*  
 Die Länge in Zeichen, der zusätzliche Header. Ist dies-1 L und `pstrHeaders` nicht **NULL**, klicken Sie dann `pstrHeaders` wird davon ausgegangen, dass 0 (null) beendet und die Länge berechnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Dateihandle für FTP, GOPHER, HTTP und Dateityp Internet-Dienste. Gibt **NULL** Wenn die Analyse nicht erfolgreich war.  
  
 Der Zeiger, `OpenURL` gibt hängt *PszURL*des Typ des Diensts. Die nachfolgende Tabelle veranschaulicht die möglichen Zeiger `OpenURL` zurückgeben kann.  
  
|URL-Typ|Rückgabe|  
|--------------|-------------|  
|file://|**CStdioFile\***|  
|http://|**CHttpFile\***|  
|Gopher://|**CGopherFile\***|  
|FTP: / /|**CInternetFile\***|  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter `dwFlags` umfasst entweder **INTERNET_FLAG_TRANSFER_ASCII** oder **INTERNET_FLAG_TRANSFER_BINARY**, aber nicht beides. Die übrigen Flags können kombiniert werden, mit einer bitweisen `OR` Operator ( **|**).  
  
 `OpenURL`, die dient als Wrapper für der Win32-Funktion **InternetOpenURL**, ermöglicht, nur herunterladen, abrufen und das Lesen von Daten aus einem Internetserver. `OpenURL`ermöglicht keine dateibearbeitung an einem Remotestandort befinden, daher keine erforderlich [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) Objekt.  
  
 Verbindungsspezifischen verwenden (d. h. protokollspezifische) Funktionen, z. B. in eine Datei schreiben, müssen öffnen Sie eine Sitzung, klicken Sie dann eine bestimmte Art von Verbindung öffnen Sie diese Verbindung verwenden, um das Öffnen einer Datei in den gewünschten Modus. Finden Sie unter `CInternetConnection` für Weitere Informationen zum Verbindungs-spezifischen Funktionen.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Cookies.  
  
 `pstrCookieData`  
 Ein Zeiger auf eine Zeichenfolge, enthält die eigentlichen Zeichenfolgendaten, die URL zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** im Erfolgsfall oder **"false"** andernfalls. Um den spezifischen Fehlercode abzurufen, rufen **GetLastError.**  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 Ein `DWORD` , die die Einstellung der Option enthält.  
  
 `dwFlags`  
 Gibt verschiedene Cacheoptionen an. Die Standardeinstellung ist auf 0 festgelegt. Mögliche Werte:  
  
- `INTERNET_FLAG_DONT_CACHE`Die Daten nicht zwischengespeichert, entweder lokal oder in einen beliebigen Gatewayserver.  
  
- `INTERNET_FLAG_OFFLINE`Download-Vorgänge über den persistenten Cache nur erfüllt sind. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechende Fehlercode zurückgegeben. Dieses Flag kann mit dem bitweisen kombiniert werden `OR` ( **|**) Operator.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Vorgang erfolgreich war, einen Wert von **"true"** wird zurückgegeben. Wenn ein Fehler aufgetreten ist, einen Wert von **"false"** wird zurückgegeben. Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)   
 [CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)   
 [CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)

