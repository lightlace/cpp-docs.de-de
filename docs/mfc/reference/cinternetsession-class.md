---
title: Cinternetzession-Klasse
ms.date: 06/20/2018
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
ms.openlocfilehash: c9b8eaf51820dfcd08c1390c8645978fa403931d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505844"
---
# <a name="cinternetsession-class"></a>Cinternetzession-Klasse

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
|[CInternetSession::Close](#close)|Schließt die Internetverbindung, wenn die Internet Sitzung beendet wird.|
|[CInternetSession::EnableStatusCallback](#enablestatuscallback)|Legt eine Status Rückruf Routine fest.|
|[CInternetSession::GetContext](#getcontext)|Schließt die Internetverbindung, wenn die Internet Sitzung beendet wird.|
|[CInternetSession::GetCookie](#getcookie)|Gibt Cookies für die angegebene URL und alle zugehörigen übergeordneten URLs zurück.|
|[CInternetSession::GetCookieLength](#getcookielength)|Ruft die Variable ab, die die Länge des Cookies angibt, das im Puffer gespeichert ist.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Öffnet eine FTP-Sitzung mit einem Server. Protokolliert den Benutzer.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Öffnet einen Gopher-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Öffnet einen HTTP-Server für eine Anwendung, die versucht, eine Verbindung zu öffnen.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Aktualisiert den Status eines Vorgangs, wenn der Status Rückruf aktiviert ist.|
|[CInternetSession::OpenURL](#openurl)|Analysiert und öffnet eine URL.|
|[CInternetSession::SetCookie](#setcookie)|Legt ein Cookie für die angegebene URL fest.|
|[CInternetSession::SetOption](#setoption)|Legt Optionen für die Internet Sitzung fest.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Cinternetzession:: Operator HINTERNET](#operator_hinternet)|Ein Handle für die aktuelle Internet Sitzung.|

## <a name="remarks"></a>Hinweise

Wenn Ihre Internet Verbindung für die Dauer einer Anwendung beibehalten werden muss, können Sie ein `CInternetSession` Mitglied der [CWinApp](../../mfc/reference/cwinapp-class.md)-Klasse erstellen.

Nachdem Sie eine Internet Sitzung eingerichtet haben, können Sie [OpenURL](#openurl)aufzurufen. `CInternetSession`analysiert dann die URL für Sie, indem Sie die globale Funktion [afxparser URL](internet-url-parsing-globals.md#afxparseurl)aufrufen. Unabhängig vom Protokolltyp `CInternetSession` interpretiert die URL und verwaltet diese für Sie. Er kann Anforderungen für lokale Dateien verarbeiten, die durch die URL-Ressource "file://" identifiziert werden. `OpenURL`Gibt einen Zeiger auf ein [CStdioFile](../../mfc/reference/cstdiofile-class.md) -Objekt zurück, wenn der Name, den Sie übergeben, eine lokale Datei ist.

Wenn Sie mithilfe `OpenURL`von eine URL auf einem Internet Server öffnen, können Sie Informationen von der Website lesen. Wenn Sie Dienst spezifische Aktionen (z. b. http-, FTP-oder Gopher-Aktionen) für Dateien auf einem Server ausführen möchten, müssen Sie die entsprechende Verbindung mit diesem Server herstellen. Verwenden Sie eine der folgenden Member-Funktionen, um eine bestimmte Art von Verbindung direkt mit einem bestimmten Dienst zu öffnen:

- [GetGopherConnection](#getgopherconnection) , um eine Verbindung mit einem Gopher-Dienst zu öffnen.

- [GetHttpConnection](#gethttpconnection) , um eine Verbindung mit einem HTTP-Dienst zu öffnen.

- [GetFtpConnection](#getftpconnection) , um eine Verbindung mit einem FTP-Dienst zu öffnen.

Mithilfe von " [SetOption](#setoption) " können Sie die Abfrage Optionen der Sitzung festlegen, z. b. Timeout Werte, Anzahl der Wiederholungen usw.

`CInternetSession`die Member-Funktionen [setcookie](#setcookie), [GetCookie](#getcookie)und [getcookielength](#getcookielength) bieten die Möglichkeit, eine Win32-cookendatenbank zu verwalten, über die Server und Skripts Zustandsinformationen über die Client Arbeitsstation erhalten.

Weitere Informationen zu grundlegenden Internet Programmierungsaufgaben finden Sie im [Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md). Allgemeine Informationen zum Verwenden der MFC-WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

> [!NOTE]
> `CInternetSession`löst eine [afxthrownotsupportedexception](exception-processing.md#afxthrownotsupportedexception) für nicht unterstützte Dienst Typen aus. Zurzeit werden nur die folgenden Dienst Typen unterstützt: FTP, http, Gopher und Datei.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

## <a name="cinternetsession"></a>Cinternetzession:: cinternetzession

Diese Member-Funktion wird aufgerufen, `CInternetSession` wenn ein-Objekt erstellt wird.

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

*pstrAgent*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen der Anwendung oder Entität identifiziert, die die Internet Funktionen aufrufen (z. b. "Microsoft Internet Browser"). Wenn *pstragent* den Wert NULL (Standard) hat, ruft das Framework die globale Funktion [afxgetappname](application-information-and-management.md#afxgetappname)auf, die eine mit NULL endenden Zeichenfolge zurückgibt, die den Namen einer Anwendung enthält. Einige Protokolle verwenden diese Zeichenfolge, um die Anwendung auf dem Server zu identifizieren.

*dwContext*<br/>
Der Kontext Bezeichner für den Vorgang. *dwcontext* identifiziert die von [cinternetzession:: OnStatusCallback](#onstatuscallback)zurückgegebenen Statusinformationen des Vorgangs. Der Standardwert wird auf 1 festgelegt. Sie können jedoch explizit eine bestimmte Kontext-ID für den Vorgang zuweisen. Das-Objekt und alle Aufgaben, die es durchführt, werden mit dieser Kontext-ID verknüpft.

*dwAccessType*<br/>
Der erforderliche Zugriffstyp. Im folgenden finden Sie gültige Werte, von denen genau eine bereitgestellt werden kann:

- INTERNET_OPEN_TYPE_PRECONFIG verbinden Sie sich mithilfe vorkonfigurierter Einstellungen in der Registrierung. Dieser Zugriffstyp wird als Standard festgelegt. Zum Herstellen einer Verbindung über einen tis-Proxy legen Sie *dwaccesstype* auf diesen Wert fest. Anschließend legen Sie die Registrierung entsprechend fest.

- INTERNET_OPEN_TYPE_DIRECT verbinden Sie sich direkt mit dem Internet.

- INTERNET_OPEN_TYPE_PROXY stellen Sie eine Verbindung über einen CERN-Proxy her.

Informationen zum Herstellen einer Verbindung mit verschiedenen Typen von Proxys finden Sie unter [Schritte in einer typischen FTP-Client Anwendung](../../mfc/steps-in-a-typical-ftp-client-application.md).

*pstrProxyName*<br/>
Der Name des bevorzugten CERN-Proxys, wenn *dwaccesstype* als INTERNET_OPEN_TYPE_PROXY festgelegt ist. Der Standardwert ist NULL.

*pstrProxyBypass*<br/>
Ein Zeiger auf eine Zeichenfolge, die eine optionale Liste von Serveradressen enthält. Diese Adressen können bei Verwendung des Proxy Zugriffs umgangen werden. Wenn ein NULL-Wert angegeben wird, wird die Umgehungs Liste aus der Registrierung gelesen. Dieser Parameter ist nur dann von Bedeutung, wenn *dwaccesstype* auf INTERNET_OPEN_TYPE_PROXY festgelegt ist.

*dwFlags*<br/>
Gibt verschiedene zwischen Speicherungs Optionen an. Der Standardwert wird auf 0 festgelegt. Folgende Werte sind möglich:

- INTERNET_FLAG_DONT_CACHE speichern Sie die Daten weder lokal noch auf Gatewayservern.

- INTERNET_FLAG_OFFLINE-Download Vorgänge werden nur über den persistenten Cache erfüllt. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechender Fehlercode zurückgegeben. Dieses Flag kann mit dem bitweisen **or** ( **&#124;** )-Operator kombiniert werden.

### <a name="remarks"></a>Hinweise

`CInternetSession`ist die erste Internet Funktion, die von einer Anwendung aufgerufen wird. Sie initialisiert interne Datenstrukturen und bereitet zukünftige Aufrufe von der Anwendung vor.

Wenn keine Internet Verbindung geöffnet werden kann, `CInternetSession` löst eine [afxthrowinternettexception](internet-url-parsing-globals.md#afxthrowinternetexception)aus.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="close"></a>Cinternetzession:: Close

Diese Member-Funktion wird aufgerufen, wenn die Anwendung die `CInternetSession` Verwendung des-Objekts beendet hat.

```cpp
virtual void Close();
```

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="enablestatuscallback"></a>Cinternetzession:: enablestatus Callback

Rufen Sie diese Element Funktion auf, um den Status Rückruf zu aktivieren.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
Gibt an, ob der Rückruf aktiviert oder deaktiviert ist. Der Standardwert ist "true".

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

### <a name="remarks"></a>Hinweise

Wenn Sie den Status Rückruf verarbeiten, können Sie den Status des Vorgangs (z. b. das Auflösen von Namen, das Herstellen einer Verbindung mit dem Server usw.) in der Statusleiste der Anwendung angeben. Die Anzeige des Vorgangs Status ist bei einem langfristigen Vorgang besonders wünschenswert.

Da bei der Verarbeitung der Anforderung Rückrufe auftreten, sollte die Anwendung so wenig Zeit wie möglich für den Rückruf aufwenden, um eine Herabstufung des Daten Durchsatzes im Netzwerk zu verhindern. Beispielsweise kann ein Dialogfeld in einem Rückruf ein solcher längerer Vorgang sein, bei dem der Server die Anforderung beendet.

Der Status Rückruf kann nicht entfernt werden, solange alle Rückrufe ausstehend sind.

Zum asynchronen verarbeiten von Vorgängen müssen Sie entweder ihren eigenen Thread erstellen oder die WinInet-Funktionen ohne MFC verwenden.

## <a name="getcontext"></a>Cinternetzession:: GetContext

Mit dieser Member-Funktion können Sie den Kontextwert für eine bestimmte Anwendungs Sitzung abrufen.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Rückgabewert

Der von der Anwendung definierte Kontext Bezeichner.

### <a name="remarks"></a>Hinweise

[OnStatusCallback](#onstatuscallback) verwendet die von `GetContext` zurückgegebene Kontext-ID, um den Status einer bestimmten Anwendung zu melden. Wenn ein Benutzer beispielsweise eine Internet Anforderung aktiviert, die Statusinformationen zurückgibt, verwendet der Status Rückruf die Kontext-ID, um den Status für diese bestimmte Anforderung zu melden. Wenn der Benutzer zwei separate Internet Anforderungen aktiviert, die beide die Rückgabe von Status `OnStatusCallback` Informationen einschließen, verwendet die Kontext Bezeichner, um den Status der entsprechenden Anforderungen zurückzugeben. Folglich wird der Kontext Bezeichner für alle Status Rückruf Vorgänge verwendet und der Sitzung zugeordnet, bis die Sitzung beendet wird.

Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internet First Steps: WinInet](../../mfc/wininet-basics.md).

## <a name="getcookie"></a>Cinternetzession:: GetCookie

Diese Member-Funktion implementiert das Verhalten der Win32-Funktion [InternetGetCookie](/windows/win32/api/wininet/nf-wininet-internetgetcookiew), wie im Windows SDK beschrieben.

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

*pstrUrl*<br/>
Ein Zeiger auf eine Zeichenfolge, die die URL enthält.

*pstrCookieName*<br/>
Ein Zeiger auf eine Zeichenfolge mit dem Namen des Cookies, das für die angegebene URL angezeigt werden soll.

*pstrCookieData*<br/>
In der ersten Überladung ein Zeiger auf eine Zeichenfolge, die die Adresse des Puffers enthält, der die Cookie-Daten empfängt. Dieser Wert kann NULL sein. In der zweiten Überladung ein Verweis auf ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, um die Cookie-Daten zu empfangen.

*dwBufLen*<br/>
Die Variable, die die Größe des *pstrincookiedata* -Puffers angibt. Wenn die Funktion erfolgreich ausgeführt wird, empfängt der Puffer die Menge der Daten, die in den *pstrincookiedata* -Puffer kopiert werden. Wenn *pstrincookiedata* NULL ist, erhält dieser Parameter einen Wert, der die Größe des Puffers angibt, der zum Kopieren aller Cookiedaten erforderlich ist.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich, andernfalls false. Wenn der-Befehl fehlschlägt, rufen Sie die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) auf, um die Ursache des Fehlers zu ermitteln. Die folgenden Fehler Werte gelten:

- ERROR_NO_MORE_ITEMS es gibt kein Cookie für die angegebene URL und alle zugehörigen übergeordneten Elemente.

- ERROR_INSUFFICIENT_BUFFER der in *dwbuflen* über gegebene Wert reicht nicht aus, um alle Cookie-Daten zu kopieren. Der in *dwbuflen* zurückgegebene Wert ist die Größe des Puffers, der zum erhalten aller Daten erforderlich ist.

### <a name="remarks"></a>Hinweise

In der zweiten Überladung ruft MFC die Cookie-Daten in das angegebene `CString` -Objekt ab.

## <a name="getcookielength"></a>Cinternetzession:: getcookielength

Mit dieser Member-Funktion können Sie die Länge des Cookies abrufen, das im Puffer gespeichert ist.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Parameter

*pstrUrl*<br/>
Ein Zeiger auf eine Zeichenfolge, die die URL enthält.

*pstrCookieName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Cookies enthält.

### <a name="return-value"></a>Rückgabewert

Ein DWORD-Wert, der die Länge des Cookies angibt, das im Puffer gespeichert ist. 0 (null), wenn kein Cookie mit dem von *pstrincookiename* gekennzeichneten Namen vorhanden ist.

### <a name="remarks"></a>Hinweise

Dieser Wert wird von [GetCookie](#getcookie)verwendet.

## <a name="getftpconnection"></a>Cinternetzession:: GetFtpConnection

Mit dieser Member-Funktion können Sie eine FTP-Verbindung herstellen und einen Zeiger `CFtpConnection` auf ein-Objekt abrufen.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Parameter

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den FTP-Servernamen enthält.

*pstrUserName*<br/>
Zeiger auf eine mit NULL endenden Zeichenfolge, die den Namen des Benutzers angibt, der angemeldet werden soll. Wenn der Wert NULL ist, ist der Standardwert Anonymous.

*pstrPassword*<br/>
Ein Zeiger auf eine mit NULL endende Zeichenfolge, die das Kennwort für die Anmeldung angibt. Wenn sowohl *pstraupassword* als auch *pstrusername* NULL sind, ist das anonyme Standard Kennwort der e-Mail-Name des Benutzers. Wenn *pstraupassword* NULL (oder eine leere Zeichenfolge) ist, aber *pstrusername* nicht NULL ist, wird ein leeres Kennwort verwendet. In der folgenden Tabelle wird das Verhalten der vier möglichen Einstellungen von *pstrusername* und *pstrinpassword*beschrieben:

| *pstrUserName*  | *pstrPassword*  | An FTP-Server gesendeter Benutzername | Kennwort an FTP-Server gesendet |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL oder ""   |   NULL oder ""   |         Anonymous         |      E-Mail-Name des Benutzers      |
| Zeichenfolge ungleich NULL |   NULL oder ""   |       *pstrUserName*        |             " "             |
|      NULL       | Zeichenfolge ungleich NULL |            Fehler            |            Fehler            |
| Zeichenfolge ungleich NULL | Zeichenfolge ungleich NULL |       *pstrUserName*        |       *pstrPassword*        |

*nPort*<br/>
Eine Zahl, die den auf dem Server zu verwendenden TCP/IP-Port identifiziert.

*bPassive*<br/>
Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn der Wert auf true festgelegt ist, wird `dwFlag` die Win32-API auf INTERNET_FLAG_PASSIVE festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CFtpConnection](../../mfc/reference/cftpconnection-class.md) -Objekt. Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

### <a name="remarks"></a>Hinweise

`GetFtpConnection`stellt eine Verbindung mit einem FTP-Server her und erstellt einen Zeiger auf `CFTPConnection` ein-Objekt und gibt diesen zurück. Auf dem Server wird kein bestimmter Vorgang durchgeführt. Wenn Sie z. b. beabsichtigen, Dateien zu lesen oder in Dateien zu schreiben, müssen Sie diese Vorgänge in separaten Schritten ausführen. Informationen zum Suchen nach Dateien, zum Öffnen von Dateien und zum Lesen oder Schreiben von Dateien finden Sie in den Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) . Schritte zum Durchführen allgemeiner FTP-Verbindungs Aufgaben finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md) .

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="getgopherconnection"></a>Cinternetzession:: GetGopherConnection

Mit dieser Member-Funktion können Sie eine neue Gopher-Verbindung einrichten und einen Zeiger `CGopherConnection` auf ein-Objekt abrufen.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parameter

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Gopher-Servernamen enthält.

*pstrUserName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.

*pstrPassword*<br/>
Ein Zeiger auf eine Zeichenfolge, die das Zugriffs Kennwort enthält.

*nPort*<br/>
Eine Zahl, die den auf dem Server zu verwendenden TCP/IP-Port identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) -Objekt. Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

### <a name="remarks"></a>Hinweise

`GetGopherConnection`stellt eine Verbindung mit einem Gopher-Server her und erstellt einen Zeiger auf `CGopherConnection` ein-Objekt und gibt diesen zurück. Auf dem Server wird kein bestimmter Vorgang durchgeführt. Wenn Sie z. b. Daten lesen oder schreiben möchten, müssen Sie diese Vorgänge in separaten Schritten ausführen. Informationen zum Suchen nach Dateien, zum Öffnen von Dateien und zum Lesen oder Schreiben von Dateien finden Sie in den Klassen [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md)und [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) . Weitere Informationen zum Durchsuchen einer FTP-Site finden Sie unter " [OpenURL](#openurl)" der Member-Funktion. Schritte zum Durchführen allgemeiner Gopher-Verbindungs Aufgaben finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md) .

## <a name="gethttpconnection"></a>Cinternetzzession:: GetHttpConnection

Mit dieser Member-Funktion können Sie eine HTTP-Verbindung herstellen und einen Zeiger `CHttpConnection` auf ein-Objekt abrufen.

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

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den HTTP-Servernamen enthält.

*nPort*<br/>
Eine Zahl, die den auf dem Server zu verwendenden TCP/IP-Port identifiziert.

*pstrUserName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Benutzernamen enthält.

*pstrPassword*<br/>
Ein Zeiger auf eine Zeichenfolge, die das Zugriffs Kennwort enthält.

*dwflags*<br/>
Eine beliebige Kombination `INTERNET_FLAG_*` der Flags. Eine Beschreibung von *dwFlags* -Werten finden Sie in der Tabelle im Abschnitt " **Hinweise** " unter [CHttpConnection:: openrequest](../../mfc/reference/chttpconnection-class.md#openrequest) .

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein [CHttpConnection](../../mfc/reference/chttpconnection-class.md) -Objekt. Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

### <a name="remarks"></a>Hinweise

`GetHttpConnection`stellt eine Verbindung mit einem HTTP-Server her und erstellt einen Zeiger auf `CHttpConnection` ein-Objekt und gibt diesen zurück. Auf dem Server wird kein bestimmter Vorgang durchgeführt. Wenn Sie z. b. einen HTTP-Header Abfragen möchten, müssen Sie diesen Vorgang in einem separaten Schritt ausführen. Informationen zu Vorgängen, die Sie mithilfe einer Verbindung mit einem HTTP-Server ausführen können, finden Sie in den Klassen " [CHttpConnection](../../mfc/reference/chttpconnection-class.md) " und " [CHttpFile](../../mfc/reference/chttpfile-class.md) ". Weitere Informationen zum Durchsuchen einer HTTP-Website finden Sie unter " [OpenURL](#openurl)" der Member-Funktion. Schritte zum Durchführen allgemeiner HTTP-Verbindungs Aufgaben finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md) .

## <a name="onstatuscallback"></a>Cinternetzession:: OnStatus Callback

Diese Member-Funktion wird vom Framework aufgerufen, um den Status zu aktualisieren, wenn der Status Rückruf aktiviert ist und ein Vorgang aussteht.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Parameter

*dwContext*<br/>
Der von der Anwendung bereitgestellte Kontextwert.

*dwInternetStatus*<br/>
Ein Statuscode, der angibt, warum der Rückruf durchgeführt wird. Eine Tabelle mit möglichen Werten finden Sie unter " **Hinweise** ".

*lpvStatusInformation*<br/>
Ein Zeiger auf einen Puffer, der Informationen enthält, die für diesen Rückruf relevant sind.

*dwStatusInformationLength*<br/>
Die Größe von *lpvstatusinformation*.

### <a name="remarks"></a>Hinweise

Sie müssen zuerst [EnableStatusCallback](#enablestatuscallback) aufrufen, um den Status Rückruf zu nutzen.

Der *dwinternetstatus* -Parameter gibt den Vorgang an, der ausgeführt wird, und bestimmt, wie der Inhalt von *lpvstatusinformation* sein wird. *dwstatusinformationlength* gibt die Länge der Daten an, die in *lpvstatusinformation*enthalten sind. Die folgenden Statuswerte für *dwinternetstatus* werden wie folgt definiert:

|Wert|Bedeutung|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|Suchen Sie nach der IP-Adresse des in *lpvstatusinformation*enthaltenen Namens.|
|INTERNET_STATUS_NAME_RESOLVED|Die IP-Adresse des in " *lpvstatusinformation*" enthaltenen namens wurde gefunden.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|Herstellen einer Verbindung mit der Socketadresse ([sockaddr](/windows/win32/winsock/sockaddr-2)), auf die von *lpvstatusinformation*verwiesen wird.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|Die Verbindung mit der Socketadresse (sockaddr), auf die von *lpvstatusinformation*verwiesen wird, wurde erfolgreich hergestellt.|
|INTERNET_STATUS_SENDING_REQUEST|Die Informationsanforderung wird an den Server gesendet. Der *lpvstatusinformation* -Parameter ist NULL.|
|INTERNET_STATUS_ REQUEST_SENT|Die Informationsanforderung wurde erfolgreich an den Server gesendet. Der *lpvstatusinformation* -Parameter ist NULL.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Es wird darauf gewartet, dass der Server auf eine Anforderung antwortet. Der *lpvstatusinformation* -Parameter ist NULL.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Es wurde erfolgreich eine Antwort vom Server empfangen. Der *lpvstatusinformation* -Parameter ist NULL.|
|INTERNET_STATUS_CLOSING_CONNECTION|Die Verbindung mit dem Server wird beendet. Der *lpvstatusinformation* -Parameter ist NULL.|
|INTERNET_STATUS_CONNECTION_CLOSED|Die Verbindung mit dem Server wurde erfolgreich geschlossen. Der *lpvstatusinformation* -Parameter ist NULL.|
|INTERNET_STATUS_HANDLE_CREATED|Wird von der Win32-API-Funktion [InternetConnect](/windows/win32/api/wininet/nf-wininet-internetconnectw) verwendet, um anzugeben, dass das neue Handle erstellt wurde. Dadurch kann die Anwendung die Win32-Funktion [internetclosehandle](/windows/win32/api/wininet/nf-wininet-internetclosehandle) von einem anderen Thread aus abrufen, wenn die Verbindung zu lange dauert. Weitere Informationen zu diesen Funktionen finden Sie unter Windows SDKfor.|
|INTERNET_STATUS_HANDLE_CLOSING|Dieser handle-Wert wurde erfolgreich beendet.|

Überschreiben Sie diese Member-Funktion, um eine Aktion anzufordern, bevor eine Status Rückruf Routine ausgeführt wird.

> [!NOTE]
> Status Rückrufe benötigen einen Thread Zustands Schutz. Wenn Sie MFC in einer freigegebenen Bibliothek verwenden, fügen Sie die folgende Zeile am Anfang der außer Kraft Setzung ein:

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Weitere Informationen zu asynchronen Vorgängen finden Sie im Artikel [Internet First Steps: WinInet](../../mfc/wininet-basics.md).

## <a name="openurl"></a>Cinternetzession:: OpenURL

Mit dieser Member-Funktion wird die angegebene Anforderung an den HTTP-Server gesendet, und der Client kann weitere RFC822-, MIME-oder http-Header angeben, die zusammen mit der Anforderung gesendet werden sollen.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Parameter

*pstrURL*<br/>
Ein Zeiger auf den Namen der URL, die gelesen werden soll. Es werden nur URLs unterstützt, die mit "file:, FTP:, Gopher:" oder "http:" beginnen. Bestätigt, ob *pstrinurl* NULL ist.

*dwContext*<br/>
Ein von der Anwendung definierter Wert, der mit dem zurückgegebenen Handle in Callback übermittelt wurde.

*dwFlags*<br/>
Die Flags, die beschreiben, wie diese Verbindung behandelt werden soll. Weitere Informationen zu den gültigen Flags finden Sie unter " **Hinweise** ". Gültige Flags:

- INTERNET_FLAG_TRANSFER_ASCII die Standardeinstellung. Übertragen Sie die Datei als ASCII-Text.

- INTERNET_FLAG_TRANSFER_BINARY übertragen Sie die Datei als Binärdatei.

- INTERNET_FLAG_RELOAD die Daten aus dem Netzwerk auch dann, wenn Sie lokal zwischengespeichert werden.

- INTERNET_FLAG_DONT_CACHE speichern Sie die Daten weder lokal noch in Gateways.

- INTERNET_FLAG_SECURE dieses Flag gilt nur für HTTP-Anforderungen. Mit Secure Sockets Layer oder PCT werden sichere Transaktionen angefordert.

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT verwenden Sie nach Möglichkeit die vorhandenen Verbindungen mit dem Server für neue Anforderungen, die `OpenUrl` von generiert wurden, anstatt eine neue Sitzung für jede Verbindungsanforderung zu erstellen.

- INTERNET_FLAG_PASSIVE wird für eine FTP-Site verwendet. Verwendet passive FTP-Semantik. Wird mit [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) von `OpenURL`verwendet.

*pstrHeaders*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Header enthält, die an den HTTP-Server gesendet werden sollen.

*dwHeadersLength*<br/>
Die Länge der zusätzlichen Header in Zeichen. Wenn dies-1L und *pstrinheaders* nicht NULL ist, wird davon ausgegangen , dass die Länge 0 (null) endet und die Länge berechnet wird.

### <a name="return-value"></a>Rückgabewert

Gibt nur ein Datei Handle für FTP-, Gopher-, http-und File-Type-Internet Dienste zurück. Gibt NULL zurück, wenn die Verarbeitung nicht erfolgreich war.

Der Zeiger, `OpenURL` der zurückgibt, hängt vom Typ des Typs von *pstrinurl*ab. In der folgenden Tabelle wird veranschaulicht, `OpenURL` welche möglichen Zeiger zurückgeben können.

|URL-Typ|Rückgabewert|
|--------------|-------------|
|file://|`CStdioFile*`|
|http://|`CHttpFile*`|
|gopher://|`CGopherFile*`|
|ftp://|`CInternetFile*`|

### <a name="remarks"></a>Hinweise

Der Parameter " *dwFlags* " muss entweder "INTERNET_FLAG_TRANSFER_ASCII" oder "INTERNET_FLAG_TRANSFER_BINARY" enthalten, jedoch nicht beide. Die verbleibenden Flags können mit dem bitweisen **or** -Operator ( **&#124;** ) kombiniert werden.

`OpenURL`, das die Win32-Funktion `InternetOpenURL`umschließt, erlaubt nur das herunterladen, abrufen und Lesen von Daten von einem Internet Server. `OpenURL`ermöglicht keine Dateibearbeitung an einem Remote Speicherort, sodass kein [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) -Objekt erforderlich ist.

Wenn Sie Verbindungs spezifische (d. h. Protokoll spezifische) Funktionen verwenden möchten, z. b. das Schreiben in eine Datei, müssen Sie eine-Sitzung öffnen, eine bestimmte Art von Verbindung öffnen und dann diese Verbindung verwenden, um eine Datei im gewünschten Modus zu öffnen. Weitere `CInternetConnection` Informationen zu Verbindungs spezifischen Funktionen finden Sie unter.

## <a name="operator_hinternet"></a>Cinternetzession:: Operator HINTERNET

Verwenden Sie diesen Operator, um das Windows-Handle für die aktuelle Internet Sitzung zu erhalten.

```cpp
operator HINTERNET() const;
```

## <a name="setcookie"></a>Cinternetzession:: setcookie

Legt ein Cookie für die angegebene URL fest.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Parameter

*pstrUrl*<br/>
Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die die URL angibt, für die das Cookie festgelegt werden soll.

*pstrCookieName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Cookies enthält.

*pstrCookieData*<br/>
Ein Zeiger auf eine Zeichenfolge, die die eigentlichen Zeichen folgen Daten enthält, die der URL zugeordnet werden sollen.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn erfolgreich, andernfalls false. Um den spezifischen Fehlercode abzurufen, müssen Sie`GetLastError.`

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [InternetSetCookie](/windows/win32/api/wininet/nf-wininet-internetsetcookiew), wie im Windows SDK beschrieben.

## <a name="setoption"></a>Cinternetzzession:: SetOption

Mit dieser Member-Funktion können Sie Optionen für die Internet Sitzung festlegen.

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

*dwOption*<br/>
Die festzulegende Internet Option. Weitere Informationen finden Sie unter [Optionsflags](/windows/win32/WinInet/option-flags) in der Windows SDKfor a-Liste der möglichen Optionen.

*lpBuffer*<br/>
Ein Puffer, der die Options Einstellung enthält.

*dwBufferLength*<br/>
Die Länge von *lpBuffer* oder die Größe von *dwValue*.

*dwValue*<br/>
Ein DWORD, das die Options Einstellung enthält.

*dwFlags*<br/>
Gibt verschiedene zwischen Speicherungs Optionen an. Der Standardwert wird auf 0 festgelegt. Folgende Werte sind möglich:

- INTERNET_FLAG_DONT_CACHE speichern Sie die Daten weder lokal noch auf Gatewayservern.

- INTERNET_FLAG_OFFLINE-Download Vorgänge werden nur über den persistenten Cache erfüllt. Wenn das Element nicht im Cache vorhanden ist, wird ein entsprechender Fehlercode zurückgegeben. Dieses Flag kann mit dem bitweisen **or** ( **&#124;** )-Operator kombiniert werden.

### <a name="return-value"></a>Rückgabewert

Wenn der Vorgang erfolgreich war, wird der Wert true zurückgegeben. Wenn ein Fehler aufgetreten ist, wird der Wert false zurückgegeben. Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)<br/>
[CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)<br/>
[CGopherConnection-Klasse](../../mfc/reference/cgopherconnection-class.md)
