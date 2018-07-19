---
title: CInternetSession-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
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
- CInternetSession [MFC], CInternetSession
- CInternetSession [MFC], Close
- CInternetSession [MFC], EnableStatusCallback
- CInternetSession [MFC], GetContext
- CInternetSession [MFC], GetCookie
- CInternetSession [MFC], GetCookieLength
- CInternetSession [MFC], GetFtpConnection
- CInternetSession [MFC], GetGopherConnection
- CInternetSession [MFC], GetHttpConnection
- CInternetSession [MFC], OnStatusCallback
- CInternetSession [MFC], OpenURL
- CInternetSession [MFC], SetCookie
- CInternetSession [MFC], SetOption
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8eb030bb6827fd8df5a7f4826c4c1e4b3b47b5a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337169"
---
# <a name="cinternetsession-class"></a>CInternetSession-Klasse

Erstellt und initialisiert einzelne oder mehrere gleichzeitige Internetsitzungen und beschreibt ggf. die Verbindung mit einem Proxyserver.

## <a name="syntax"></a>Syntax

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|Erstellt ein `CInternetSession`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CInternetSession::Close](#close)|Schließt die Internetverbindung, wenn die Internet-Sitzung beendet wird.|
|[CInternetSession:: EnableStatusCallback](#enablestatuscallback)|Stellt eine Rückrufroutine Status her.|
|[CInternetSession::GetContext](#getcontext)|Schließt die Internetverbindung, wenn die Internet-Sitzung beendet wird.|
|[CInternetSession::GetCookie](#getcookie)|Cookies zurückgegeben für die angegebene URL und alle übergeordneten URLs.|
|[CInternetSession::GetCookieLength](#getcookielength)|Ruft ab, die Variable, die die Länge des Cookies, die im Puffer gespeichert.|
|[CInternetSession:: GetFTPConnection](#getftpconnection)|Öffnet eine FTP-Sitzung mit einem Server an. Protokolle für den Benutzer.|
|[CInternetSession:: GetGopherConnection](#getgopherconnection)|Öffnet einen Gopher-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|
|[CInternetSession:: GetHttpConnection](#gethttpconnection)|Öffnet einen HTTP-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|
|[CInternetSession:: OnStatusCallback](#onstatuscallback)|Aktualisiert den Status eines Vorgangs an, wenn Statusrückruf aktiviert ist.|
|[OpenURL](#openurl)|Analysiert und eine URL geöffnet.|
|[CInternetSession::SetCookie](#setcookie)|Erstellt ein Cookie für die angegebene URL.|
|[CInternetSession:: SetOption](#setoption)|Legt Optionen für die Internet-Sitzung fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetSession::operator HINTERNET](#operator_hinternet)|Ein Handle für die aktuelle Internet-Sitzung.|

## <a name="remarks"></a>Hinweise

Wenn Ihre Internetverbindung für die Dauer einer Anwendung verwaltet werden muss, können Sie erstellen eine `CInternetSession` Member der Klasse [CWinApp](../../mfc/reference/cwinapp-class.md).

Wenn Sie eine internetsitzung eingerichtet haben, können Sie aufrufen [OpenURL](#openurl). `CInternetSession` Klicken Sie dann die URL für Sie durch Aufrufen der globalen Funktion analysiert [AfxParseURL](internet-url-parsing-globals.md#afxparseurl). Unabhängig von der Protokolltyp `CInternetSession` interpretiert die URL ein, und es für Sie verwaltet. Sie können Anforderungen für lokale Dateien, die mit der URL-Ressource "file://" identifiziert behandeln. `OpenURL` Gibt einen Zeiger auf eine [CStdioFile](../../mfc/reference/cstdiofile-class.md) -Objekt, wenn Sie ihr den Namen übergeben, ist eine lokale Datei.

Wenn Sie eine auf einem Server mit Internet-URL öffnen `OpenURL`, erhalten Sie Informationen von der Website. Wenn Sie dienstspezifische (z. B. HTTP, FTP oder Gopher)-Aktionen auf Dateien auf einem Server ausführen möchten, müssen Sie die entsprechende Verbindung mit dem Server herstellen. Um eine bestimmte Art von Verbindung direkt mit einem bestimmten Dienst zu öffnen, gehen Sie die folgenden Memberfunktionen:

- [GetGopherConnection](#getgopherconnection) zum Öffnen einer Verbindung zu einem Gopher-Dienst.

- [GetHttpConnection hergestellt](#gethttpconnection) zum Öffnen einer Verbindung mit einem HTTP-Dienst.

- [GetFtpConnection](#getftpconnection) zum Öffnen einer Verbindung mit einem FTP-Dienst.

[SetOption](#setoption) ermöglicht es Ihnen, die Abfrageoptionen der Sitzung, wie Timeoutwerte, Anzahl von Wiederholungen, festlegen und so weiter.

`CInternetSession` Memberfunktionen [SetCookie](#setcookie), [GetCookie](#getcookie), und [GetCookieLength](#getcookielength) bieten die Möglichkeit zum Verwalten von einer Win32-Cookie-Datenbank, über den Server und -Skripts verwalten Statusinformationen über den die Clientarbeitsstation.

Weitere Informationen zu grundlegenden Internet Programmieraufgaben erledigen, finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md). Allgemeine Informationen zur Verwendung der MFC-WinInet-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

> [!NOTE]
> `CInternetSession` Löst ein [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) für nicht unterstützte Diensttypen. Nur die folgenden Diensttypen werden derzeit unterstützt: FTP, HTTP, Gopher und Datei.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)  
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

## <a name="cinternetsession"></a> CInternetSession::CInternetSession

Diese Memberfunktion wird aufgerufen, wenn eine `CInternetSession` Objekt erstellt wird.

```cpp
CInternetSession(
    LPCTSTR pstrAgent = NULL,
    DWORD_PTR dwContext = 1,
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,
    LPCTSTR pstrProxyName = NULL,
    LPCTSTR pstrProxyBypass = NULL,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parameter

*pstrAgent*  
Ein Zeiger auf eine Zeichenfolge, die den Namen der Anwendung oder der verbundenen Entität Aufrufen der Internet-Funktionen (z. B. "Microsoft Internet Browser") bezeichnet. Wenn *PstrAgent* ist NULL (Standard), das Framework Ruft die globale Funktion [AfxGetAppName](application-information-and-management.md#afxgetappname), die eine Null-terminierte Zeichenfolge, die mit einer Anwendung-Namen zurückgibt. Einige Protokolle verwenden Sie diese Zeichenfolge zum Identifizieren Ihrer Anwendung auf dem Server.

*dwContext*  
Der Kontextbezeichner für den Vorgang. *DwContext* identifiziert des Vorgangs der vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](#onstatuscallback). Der Standardwert ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und Arbeit ist, werden diese Kontext-ID zugeordnet werden.

*dwAccessType*  
Der Typ des Zugriffs, die erforderlich sind. Die folgenden sind Werte gültig, von denen genau, die eines kann angegeben werden:

- Verbinden von INTERNET_OPEN_TYPE_PRECONFIG mithilfe von vorkonfigurierten Einstellungen in der Registrierung. Dieser Art wird als Standard festgelegt. Legen Sie zum Verbinden über einen Proxy TIS *DwAccessType* auf diesen Wert; klicken Sie dann die Registrierung wie gewünscht festgelegt.

- INTERNET_OPEN_TYPE_PROXY direkt mit dem Internet verbinden.

- INTERNET_OPEN_TYPE_DIRECT verbinden über einen CERN-Proxy.

Informationen zum Herstellen einer Verbindung mit verschiedenen Typen von Proxys finden Sie unter [Schritte in einer Typischen FTP-Clientanwendung](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*  
Der Name des bevorzugten CERN-Proxy Wenn *DwAccessType* als INTERNET_OPEN_TYPE_DIRECT festgelegt ist. Der Standardwert ist NULL.

*pstrProxyBypass*  
Ein Zeiger auf eine Zeichenfolge, die eine optionale Liste mit Serveradressen enthält. Bei Verwendung des Proxyzugriffs, können diese Adressen umgangen werden. Wenn ein NULL-Wert angegeben wird, wird der Umgehungsliste aufgeführt, aus der Registrierung gelesen werden. Dieser Parameter hat nur dann, wenn *DwAccessType* auf INTERNET_OPEN_TYPE_DIRECT festgelegt ist.

*dwFlags*  
Gibt an, verschiedene Cacheoptionen. Der Standardwert ist auf 0 festgelegt. Die möglichen Werte sind:

- INTERNET_FLAG_DONT_CACHE Zwischenspeichern nicht der Daten, entweder lokal oder in einen beliebigen Gatewayserver.

- Vorgänge INTERNET_FLAG_OFFLINE herunterladen, die über den persistenten Cache nur erfüllt werden. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechender Fehlercode zurückgegeben. Dieses Flag kann kombiniert werden, mit dem bitweisen **oder** ( **&#124;**) Operator.

### <a name="remarks"></a>Hinweise

`CInternetSession` die erste Internet-Funktion wird von einer Anwendung aufgerufen werden. Interne Datenstrukturen initialisiert und für zukünftige Aufrufe von der Anwendung wird vorbereitet.

Wenn keine Verbindung zum Internet geöffnet werden kann, `CInternetSession` löst eine [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="close"></a>  CInternetSession::Close

Diese Memberfunktion aufrufen, wenn Ihre Anwendung mit der `CInternetSession` Objekt.

```cpp
virtual void Close();
```

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="enablestatuscallback"></a>  CInternetSession:: EnableStatusCallback

Rufen Sie diese Memberfunktion zum Statusrückruf zu aktivieren.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*  
Gibt an, ob der Rückruf aktiviert oder deaktiviert ist. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Bei der Behandlung von Statusrückruf können Sie den Status über den Fortschritt des Vorgangs (z. B. Auflösen von Namen, eine Verbindung mit Server usw.) in der Statusleiste der Anwendung bereitstellen. Anzeigen des Status des Vorgangs ist während eines langfristigen Vorgangs besonders wünschenswert.

Da Rückrufe während der Verarbeitung der Anforderung ausgeführt werden, sollten Sie die Anwendung so wenig Zeit wie möglich in der Rückruf, der Beeinträchtigung der Datendurchsatz mit dem Netzwerk zu verhindern, dass sorgfältig Bedenken. Z. B. einfügen, wird ein Dialogfeld, in einem Rückruf solche einen langwierigen Vorgang möglicherweise, dass der Server die Anforderung beendet wird.

Der Statusrückruf kann nicht entfernt werden, solange alle Rückrufe ausstehen.

Um alle Vorgänge asynchron zu behandeln, müssen Sie einen eigenen Thread erstellen oder verwenden, die ohne MFC-WinInet-Funktionen.

## <a name="getcontext"></a>  CInternetSession::GetContext

Rufen Sie diese Memberfunktion um den Kontextwert für eine bestimmte Anwendung-Sitzung abzurufen.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Rückgabewert

Der Anwendung definierte-Kontext Bezeichner.

### <a name="remarks"></a>Hinweise

[OnStatusCallback](#onstatuscallback) verwendet, die die Kontext-ID zurückgegeben werden, indem `GetContext` um den Status einer bestimmten Anwendung melden. Wenn ein Benutzer auf eine internetanforderung aktiviert, bei der Rückgabe von Statusinformationen, verwendet der Statusrückruf z. B. die Kontext-ID, um den Status für diese bestimmte Anforderung. Wenn der Benutzer zwei Separate aktiviert Internet fordert an, dass in beiden Fällen die Rückgabe von Statusinformationen, `OnStatusCallback` verwendet die Kontext-IDs, Status über die entsprechenden Anforderungen zurückzugeben. Daher wird die Kontext-ID wird für alle Status Rückrufvorgänge verwendet, und es bezieht sich auf die Sitzung, bis die Sitzung beendet wird.

Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>  CInternetSession::GetCookie

Diese Memberfunktion auf, die das Verhalten der Win32-Funktion [InternetGetCookie](http://msdn.microsoft.com/library/windows/desktop/aa384710), wie im Windows SDK beschrieben.

```cpp
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

*pstrUrl*  
Ein Zeiger auf eine Zeichenfolge, die die URL enthält.

*pstrCookieName*  
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Cookies, das für die angegebene URL zu erhalten.

*pstrCookieData*  
In der ersten Überladung ist ein Zeiger auf eine Zeichenfolge, enthält die Adresse des Puffers, der die Cookiedaten empfängt. Dieser Wert kann NULL sein. In der zweiten Überladung ist ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, um die Cookiedaten zu erhalten.

*dwBufLen*  
Die Variable angeben der Größe der *PstrCookieData* Puffer. Wenn die Funktion erfolgreich ist, empfängt der Puffer die Menge der Daten kopiert werden, um die *PstrCookieData* Puffer. Wenn *PstrCookieData* NULL ist, diesen Parameter einen Wert, der angibt, die Größe des Puffers erforderlich, um die Cookiedaten kopieren empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich, oder "false" andernfalls. Wenn der Aufruf fehlschlägt, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) um die Ursache des Fehlers zu bestimmen. Die folgenden Fehlerwerte gelten:

- ERROR_NO_MORE_ITEMS besteht kein Cookie für die angegebene URL und alle übergeordneten.

- ERROR_INSUFFICIENT_BUFFER der übergebene Wert *DwBufLen* ist nicht ausreichend, um die Cookiedaten zu kopieren. Der zurückgegebene Wert in *DwBufLen* muss die Größe des Puffers zum Abrufen aller Daten.

### <a name="remarks"></a>Hinweise

In der zweiten Überladung ist ruft MFC die Cookiedaten in die angegebene `CString` Objekt.

## <a name="getcookielength"></a>  CInternetSession::GetCookieLength

Rufen Sie diese Memberfunktion zum Abrufen der Länge des Cookies, die im Puffer gespeichert.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Parameter

*pstrUrl*  
Ein Zeiger auf eine Zeichenfolge, die mit der URL

*pstrCookieName*  
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Cookies.

### <a name="return-value"></a>Rückgabewert

Ein DWORD-Wert, der angibt, der Länge des Cookies, die im Puffer gespeichert werden. NULL, wenn kein Cookie mit dem Namen erkennbar *PstrCookieName* vorhanden ist.

### <a name="remarks"></a>Hinweise

Dieser Wert wird verwendet, indem [GetCookie](#getcookie).

## <a name="getftpconnection"></a>  CInternetSession:: GetFTPConnection

Rufen Sie diese Memberfunktion zum Herstellen einer FTP-Verbindung und einen Zeiger auf eine `CFtpConnection` Objekt.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Parameter

*pstrServer*  
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des FTP-Server.

*pstrUserName*  
Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers für die Anmeldung angibt. Wenn der Wert NULL ist, ist die Standardeinstellung anonym.

*pstrPassword*  
Ein Zeiger auf eine auf Null endende Zeichenfolge, die das Kennwort für die Anmeldung angibt. Wenn beide *PstrPassword* und *PstrUserName* NULL sind, die das anonymen Standard-Kennwort wird den e-Mail-Adresse des Benutzers. Wenn *PstrPassword* ist NULL (oder eine leere Zeichenfolge), aber *PstrUserName* ist nicht NULL ist, wird ein leeres Kennwort verwendet. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der *PstrUserName* und *PstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP-Server gesendeten Benutzernamen|Kennwort für FTP-Server gesendet wird.|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL oder ""|NULL oder ""|"Anonym"|Die e-Mail-Adresse des Benutzers|
|Nicht-NULL-Zeichenfolge|NULL oder ""|*pstrUserName*|" "|
|NULL|Nicht-NULL-Zeichenfolge|FEHLER|FEHLER||
|Nicht-NULL-Zeichenfolge|Nicht-NULL-Zeichenfolge|*pstrUserName*|*pstrPassword*|

*%nPort*  
Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.

*bPassive*  
Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn Sie auf "true" festgelegt, die Win32-API wird `dwFlag` zu INTERNET_FLAG_PASSIVE.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CFtpConnection](../../mfc/reference/cftpconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

### <a name="remarks"></a>Hinweise

`GetFtpConnection` eine Verbindung mit einem FTP-Server her und erstellt und gibt einen Zeiger auf eine `CFTPConnection` Objekt. Es führt kein bestimmten Vorgang auf dem Server. Wenn Sie beabsichtigen, zu lesen oder Schreiben in Dateien, beispielsweise müssen Sie diese Vorgänge als separate Schritte ausführen. Finden Sie unter den Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) Informationen nach Dateien suchen, Öffnen von Dateien, und das Lesen oder Schreiben in Dateien. Finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritte bei der Ausführung von Aufgaben für FTP-Verbindung.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="getgopherconnection"></a>  CInternetSession:: GetGopherConnection

Rufen Sie diese Memberfunktion, um eine neue Gopherverbindung herstellen und erhalten Sie einen Zeiger auf eine `CGopherConnection` Objekt.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parameter

*pstrServer*  
Ein Zeiger auf eine Zeichenfolge, die den Namen des Gopher-Servers enthält.

*pstrUserName*  
Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.

*pstrPassword*  
Ein Zeiger auf eine Zeichenfolge, enthält das Zugriffskennwort.

*%nPort*  
Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

### <a name="remarks"></a>Hinweise

`GetGopherConnection` eine Verbindung mit einem Gopher-Server her und erstellt und gibt einen Zeiger auf eine `CGopherConnection` Objekt. Es führt kein bestimmten Vorgang auf dem Server. Wenn Sie Daten lesen oder schreiben möchten, müssen Sie z. B. diese Vorgänge als separate Schritte ausführen. Finden Sie unter den Klassen [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md), und [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) Informationen nach Dateien suchen, Öffnen von Dateien, und das Lesen oder Schreiben in Dateien. Informationen zum Durchsuchen einer FTP-Site finden Sie auf die Member-Funktion [OpenURL](#openurl). Finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritte bei der Ausführung von Aufgaben für Gopher-Verbindung.

## <a name="gethttpconnection"></a>  CInternetSession:: GetHttpConnection

Rufen Sie diese Memberfunktion, um eine HTTP-Verbindung herzustellen, und erhalten einen Zeiger auf eine `CHttpConnection` Objekt.

```cpp
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

*pstrServer*  
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des HTTP-Server.

*%nPort*  
Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.

*pstrUserName*  
Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.

*pstrPassword*  
Ein Zeiger auf eine Zeichenfolge, enthält das Zugriffskennwort.

*dwFlags*  
Eine beliebige Kombination der `INTERNET_FLAG_*` Flags. Finden Sie in der Tabelle in der **"Hinweise"** Abschnitt [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) eine Beschreibung der *DwFlags* Werte.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CHttpConnection](../../mfc/reference/chttpconnection-class.md) Objekt. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

### <a name="remarks"></a>Hinweise

`GetHttpConnection` eine Verbindung mit einem HTTP-Server her und erstellt und gibt einen Zeiger auf eine `CHttpConnection` Objekt. Es führt kein bestimmten Vorgang auf dem Server. Wenn Sie beabsichtigen, einen HTTP-Header Abfragen, z. B. müssen Sie diesen Vorgang als separater Schritt ausführen. Finden Sie unter den Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CHttpFile](../../mfc/reference/chttpfile-class.md) Informationen zu Vorgängen, die Sie mit der eine Verbindung mit einem HTTP-Server ausführen können. Informationen zum Durchsuchen einer HTTP-Website finden Sie auf die Member-Funktion [OpenURL](#openurl). Finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md) Schritte bei der Ausführung von Aufgaben für HTTP-Verbindung.

## <a name="onstatuscallback"></a>  CInternetSession:: OnStatusCallback

Diese Memberfunktion wird aufgerufen, durch das Framework, um den Status zu aktualisieren, wenn Statusrückruf aktiviert ist, und ein Vorgang aussteht.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Parameter

*dwContext*  
Der Kontextwert, der von der Anwendung bereitgestellt wird.

*dwInternetStatus*  
Ein Statuscode gibt an, warum der Rückruf vorgenommen wird. Finden Sie unter **"Hinweise"** für eine Tabelle der möglichen Werte.

*lpvStatusInformation*  
Ein Zeiger auf einen Puffer, die Informationen zu diesen Rückruf enthält.

*dwStatusInformationLength*  
Die Größe des *LpvStatusInformation*.

### <a name="remarks"></a>Hinweise

Sie müssen zuerst Aufrufen [EnableStatusCallback](#enablestatuscallback) Statusrückruf nutzen.

Die *DwInternetStatus* Parameter gibt den Vorgang ausgeführt wird und bestimmt, welche den Inhalt der *LpvStatusInformation* werden. *DwStatusInformationLength* gibt die Länge der Daten *LpvStatusInformation*. Die Status der folgende Werte für *DwInternetStatus* sind wie folgt definiert:

|Wert|Bedeutung|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|Die IP-Adresse mit dem Namen, die in enthaltenen Nachschlagen *LpvStatusInformation*.|
|INTERNET_STATUS_NAME_RESOLVED|Die IP-Adresse mit dem Namen, die in enthaltenen gefunden *LpvStatusInformation*.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|Herstellen einer Verbindung mit der Socketadresse ([SOCKADDR](../../mfc/reference/sockaddr-structure.md)) verweist *LpvStatusInformation*.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|Verbindung erfolgreich hergestellt, um die Socketadresse (SOCKADDR) verweist *LpvStatusInformation*.|
|INTERNET_STATUS_SENDING_REQUEST|Die informationsanforderung an den Server gesendet. Die *LpvStatusInformation* Parameter NULL ist.|
|INTERNET_STATUS_ REQUEST_SENT|Die informationsanforderung erfolgreich an den Server gesendet werden. Die *LpvStatusInformation* Parameter NULL ist.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Warten auf den Server, auf eine Anforderung zu reagieren. Die *LpvStatusInformation* Parameter NULL ist.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Erfolgreich empfangen eine Antwort vom Server. Die *LpvStatusInformation* Parameter NULL ist.|
|INTERNET_STATUS_CLOSING_CONNECTION|Das Schließen der Verbindung mit dem Server. Die *LpvStatusInformation* Parameter NULL ist.|
|INTERNET_STATUS_CONNECTION_CLOSED|Die Verbindung an den Server erfolgreich geschlossen. Die *LpvStatusInformation* Parameter NULL ist.|
|INTERNET_STATUS_HANDLE_CREATED|Der Win32-API-Funktion verwendet [InternetConnect erhalten](http://msdn.microsoft.com/library/windows/desktop/aa384363) , um anzugeben, dass sie das neue Handle erstellt wurde. Dadurch können die Anwendung Aufruf der Win32-Funktion [InternetCloseHandle](http://msdn.microsoft.com/library/windows/desktop/aa384350) aus einem anderen Thread auf, wenn die Verbindung zu lange dauert. Finden Sie weitere Informationen zu diesen Funktionen in der Windows-SDKfor.|
|INTERNET_STATUS_HANDLE_CLOSING|Erfolgreich beendet diese Handlewert.|

Überschreiben Sie diese Memberfunktion, um eine Aktion erfordern, bevor eine Rückrufroutine Status ausgeführt wird.

> [!NOTE]
> Status-Rückrufe benötigen Threadzustand Schutz. Wenn Sie MFC in einer freigegebenen Bibliothek verwenden, fügen Sie die folgende Zeile am Anfang Ihrer außer Kraft setzen:

 [!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>  OpenURL

Rufen Sie diesen Member, Funktion, die die angegebene Anforderung an den HTTP-Server senden, und ermöglichen es dem Client zusätzlichen "RFC822", an der MIME- oder HTTP-Header, zusammen mit der Anforderung senden.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Parameter

*pstrURL*  
Ein Zeiger auf den Namen der URL gelesen werden soll. Nur URLs, die Datei ab:, ftp:, Gopher:, oder http: werden unterstützt. Bestätigt, wenn *PstrURL* ist NULL.

*dwContext*  
Ein Anwendung definierte Wert wurde mit das zurückgegebene Handle im Rückruf.

*dwFlags*  
Die Flags, die beschreibt, wie diese Verbindung zu behandeln. Finden Sie unter **"Hinweise"** Informationen die gültigen Flags. Die gültigen Flags sind:

- INTERNET_FLAG_TRANSFER_ASCII die Standardeinstellung. Übertragen Sie die Datei als ASCII-Text.

- INTERNET_FLAG_TRANSFER_BINARY übertragen Sie die Datei als Binärdatei.

- INTERNET_FLAG_RELOAD rufen Sie Daten aus der Übertragung, auch wenn es lokal zwischengespeichert werden.

- INTERNET_FLAG_DONT_CACHE Zwischenspeichern nicht der Daten, entweder lokal oder in der Gateways.

- INTERNET_FLAG_SECURE dieses Flag gilt nur für HTTP-Anforderungen. Sichere Transaktionen bei der Übertragung mit Secure Sockets Layer "oder" Prozent angefordert

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT Wenn möglich, wiederverwenden, die vorhandenen Verbindungen mit dem Server für neue Anforderungen, die vom `OpenUrl` anstatt eine neue Sitzung für jede verbindungsanforderung zu erstellen.

- INTERNET_FLAG_PASSIVE, die für eine FTP-Site verwendet werden. Wird verwendet, passive FTP-Semantik. Mit verwendet [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) von `OpenURL`.

*pstrHeaders*  
Ein Zeiger auf eine Zeichenfolge mit den Headern, die an den HTTP-Server gesendet werden.

*dwHeadersLength*  
Die Länge in Zeichen, der zusätzliche Header. Ist dies-1 L und *PstrHeaders* ist nicht NULL ist, dann *PstrHeaders* wird davon ausgegangen, dass 0 (null) beendet, und die Länge berechnet wird.

### <a name="return-value"></a>Rückgabewert

Gibt ein Dateihandle für FTP, GOPHER, HTTP und Dateityp Internet Dienste zurück. Gibt NULL zurück, wenn die Analyse nicht erfolgreich war.

Der Zeiger, `OpenURL` gibt hängt *PstrURL*den Typ des Diensts. In der folgenden Tabelle veranschaulicht die möglichen Zeiger `OpenURL` zurückgeben können.

|URL-Typ|Rückgabe|
|--------------|-------------|
|file://|`CStdioFile*`|
|http://|`CHttpFile*`|
|Gopher://|`CGopherFile*`|
|FTP: / /|`CInternetFile*`|

### <a name="remarks"></a>Hinweise

Der Parameter *DwFlags* muss entweder INTERNET_FLAG_TRANSFER_ASCII oder INTERNET_FLAG_TRANSFER_BINARY, jedoch nicht beides enthalten. Die übrigen Flags können kombiniert werden, mit dem bitweisen **oder** Operator ( **&#124;**).

`OpenURL`, die die Win32-Funktion umschließt `InternetOpenURL`, ermöglicht es, nur herunterladen, abrufen und Lesen von Daten aus einem Internetserver. `OpenURL` können Sie keine dateibearbeitung an einem Remotestandort, deshalb sie keine müssen [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) Objekt.

Verbindungsspezifische verwenden (d. h. protokollspezifische) Funktionen, wie z. B. das Schreiben in eine Datei, müssen Sie eine Sitzung zu öffnen, klicken Sie dann öffnen Sie eine bestimmte Art von Verbindung und anschließend verwenden Sie die Verbindung zum Öffnen einer Datei in den gewünschten Modus. Finden Sie unter `CInternetConnection` für Weitere Informationen zu Verbindungs-spezifischen Funktionen.

## <a name="operator_hinternet"></a>  CInternetSession::operator HINTERNET

Verwenden Sie diesen Operator, um das Windows-Handle für die aktuelle Sitzung von Internet abzurufen.

```cpp
operator HINTERNET() const;
```

## <a name="setcookie"></a>  CInternetSession::SetCookie

Erstellt ein Cookie für die angegebene URL.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Parameter

*pstrUrl*  
Ein Zeiger auf eine auf Null endende Zeichenfolge, die die URL gibt an, für die das Cookie festgelegt werden soll.

*pstrCookieName*  
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Cookies.

*pstrCookieData*  
Ein Zeiger auf eine Zeichenfolge, enthält die eigentlichen Zeichenfolgendaten, die URL zugeordnet werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich, oder "false" andernfalls. Um den spezifischen Fehlercode abzurufen, rufen `GetLastError.`

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [InternetSetCookie](http://msdn.microsoft.com/library/windows/desktop/aa385107), wie im Windows SDK beschrieben.

## <a name="setoption"></a>  CInternetSession:: SetOption

Rufen Sie diese Memberfunktion zum Festlegen von Optionen für die Internet-Sitzung.

```cpp
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

*dwOption*  
Die Internet-Option festgelegt werden soll. Finden Sie unter [Optionsflags](http://msdn.microsoft.com/library/windows/desktop/aa385328) in der Windows-SDKfor eine Liste der möglichen Optionen.

*lpBuffer*  
Ein Puffer, der die Einstellung der Option enthält.

*dwBufferLength*  
Die Länge des *LpBuffer* oder die Größe der *DwValue*.

*dwValue*  
Ein DWORD, das die Einstellung der Option enthält.

*dwFlags*  
Gibt an, verschiedene Cacheoptionen. Der Standardwert ist auf 0 festgelegt. Die möglichen Werte sind:

- INTERNET_FLAG_DONT_CACHE Zwischenspeichern nicht der Daten, entweder lokal oder in einen beliebigen Gatewayserver.

- Vorgänge INTERNET_FLAG_OFFLINE herunterladen, die über den persistenten Cache nur erfüllt werden. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechender Fehlercode zurückgegeben. Dieses Flag kann kombiniert werden, mit dem bitweisen **oder** ( **&#124;**) Operator.

### <a name="return-value"></a>Rückgabewert

Wenn der Vorgang erfolgreich war, wird der Wert "true" zurückgegeben. Wenn ein Fehler aufgetreten ist, wird der Wert "false" zurückgegeben. Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)  
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)  
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)  
[CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)  
[CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)  
[CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)  
