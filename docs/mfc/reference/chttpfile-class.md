---
title: CHttpFile-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
helpviewer_keywords:
- CHttpFile [MFC], CHttpFile
- CHttpFile [MFC], AddRequestHeaders
- CHttpFile [MFC], EndRequest
- CHttpFile [MFC], GetFileURL
- CHttpFile [MFC], GetObject
- CHttpFile [MFC], GetVerb
- CHttpFile [MFC], QueryInfo
- CHttpFile [MFC], QueryInfoStatusCode
- CHttpFile [MFC], SendRequest
- CHttpFile [MFC], SendRequestEx
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
ms.openlocfilehash: a637ef8feb28396b1427341c8174e9a7adaa69a9
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503494"
---
# <a name="chttpfile-class"></a>CHttpFile-Klasse

Stellt die Funktionalität bereit, um Dateien auf einem HTTP-Server anfordern und zu lesen.

## <a name="syntax"></a>Syntax

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHttpFile::CHttpFile](#chttpfile)|Erstellt ein `CHttpFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Die Anforderung ein HTTP-Server an werden Header hinzugefügt.|
|[CHttpFile::EndRequest](#endrequest)|Beendet eine Anforderung gesendet, um einen HTTP-Server mit der [SendRequestEx](#sendrequestex) Member-Funktion.|
|[CHttpFile::GetFileURL](#getfileurl)|Ruft die URL für die angegebene Datei.|
|[CHttpFile::GetObject](#getobject)|Ruft das Zielobjekt des Verbs in einer Anforderung eines HTTP-Servers ab.|
|[CHttpFile::GetVerb](#getverb)|Ruft das Verb, das in einer Anforderung an einen HTTP-Server verwendet wurde.|
|[CHttpFile::QueryInfo](#queryinfo)|Gibt die Antwort oder Anforderung-Header der HTTP-Server zurück.|
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Ruft den Statuscode einer HTTP-Anforderung zugeordnet ist, und platziert sie in der angegebenen `dwStatusCode` Parameter.|
|[CHttpFile::SendRequest](#sendrequest)|Sendet eine Anforderung an einen HTTP-Server.|
|[CHttpFile::SendRequestEx](#sendrequestex)|Sendet eine Anforderung an eine HTTP-Server mit der [schreiben](../../mfc/reference/cinternetfile-class.md#write) oder [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) Methoden `CInternetFile`.|

## <a name="remarks"></a>Hinweise

Wenn es sich bei die Internet-Sitzung Daten aus einem HTTP-Server liest, müssen Sie eine Instanz von erstellen `CHttpFile`.

Weitere Informationen finden Sie `CHttpFile` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="addrequestheaders"></a>  CHttpFile:: AddRequestHeaders

Rufen Sie diese Memberfunktion zum Hinzufügen oder weitere HTTP-Anforderungsheader in der HTTP-Anforderung verarbeiten.

```
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,
    int dwHeadersLen = -1);

BOOL AddRequestHeaders(
    CString& str,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```

### <a name="parameters"></a>Parameter

*pstrHeaders*<br/>
Ein Zeiger auf eine Zeichenfolge mit der Kopf- oder der Header, um die Anforderung angefügt werden soll. Jeder Header muss durch ein CR/LF-Paar beendet werden.

*dwFlags*<br/>
Ändert die Semantik der neuen Header an. Einer der folgenden Werte ist möglich:

- Führt HTTP_ADDREQ_FLAG_COALESCE-Header mit dem gleichen Namen, die mithilfe des Flags, die den ersten Header finden Sie auf den nachfolgenden Header hinzufügen. Z. B. "annehmen: Text /\*" gefolgt von "Accept: audio /\*" führt die Bildung von den einmaligen Header "annehmen: Text /\*, audio /\*". Es ist Aufgabe der aufrufenden Anwendung ein, um sicherzustellen, dass ein zusammenhängender Schema in Bezug auf die Daten vom mit zusammengeführte oder separate-Headern gesendeten Anforderungen empfangen werden.

- HTTP_ADDREQ_FLAG_REPLACE führt eine entfernen und Ersetzen Sie den aktuellen Header hinzuzufügen. So entfernen Sie den aktuellen Headerausgabestream der Headernamen verwendet werden, und der vollständige Wert wird verwendet werden, um die neuen Header hinzuzufügen. Wenn der Header-Wert leer ist, und der Header gefunden wird, wird sie entfernt. Wenn dies nicht leer ist, wird der Header-Wert ersetzt.

- Fügt den Header nur HTTP_ADDREQ_FLAG_ADD_IF_NEW hinzu, wenn es nicht bereits vorhanden ist. Wenn eine vorhanden ist, wird ein Fehler zurückgegeben.

- HTTP_ADDREQ_FLAG_ADD mit ersetzen verwendet. Fügt den Header an, wenn er nicht vorhanden.

*dwHeadersLen*<br/>
Die Länge in Zeichen des *PstrHeaders*. Wenn dies-1 L, dann ist *PstrHeaders* wird davon ausgegangen, dass 0 (null) beendet werden und die Länge berechnet wird.

*str*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, enthält der Anforderungsheader oder einen Header hinzugefügt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

`AddRequestHeaders` fügt zusätzliche, freiem Header an das Handle des HTTP-Anforderung an. Es ist für die Verwendung durch komplexe Clients vorgesehen, die detaillierte Kontrolle über die genaue Anforderung an den HTTP-Server gesendet.

> [!NOTE]
>  Leitet die Anwendung kann mehrere Header in *PstrHeaders* oder *str* für eine `AddRequestHeaders` rufen mit HTTP_ADDREQ_FLAG_ADD oder HTTP_ADDREQ_FLAG_ADD_IF_NEW. Wenn die Anwendung versucht, entfernen oder Ersetzen Sie einen Header mithilfe HTTP_ADDREQ_FLAG_REMOVE oder HTTP_ADDREQ_FLAG_REPLACE, kann nur einen Header angegeben werden, *LpszHeaders*.

##  <a name="chttpfile"></a>  CHttpFile::CHttpFile

Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CHttpFile` Objekt.

```
CHttpFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrObject,
    LPCTSTR pstrServer,
    LPCTSTR pstrVerb,
    DWORD_PTR dwContext);

CHttpFile(
    HINTERNET hFile,
    LPCTSTR pstrVerb,
    LPCTSTR pstrObject,
    CHttpConnection* pConnection);
```

### <a name="parameters"></a>Parameter

*hFile*<br/>
Ein Handle für eine Internetdatei.

*hSession*<br/>
Ein Handle für eine internetsitzung.

*pstrObject*<br/>
Ein Zeiger auf eine Zeichenfolge mit der `CHttpFile` Objekt.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Servers.

*pstrVerb*<br/>
Ein Zeiger auf eine Zeichenfolge, enthält die Methode, die beim Senden der Anforderung verwendet werden. POST, HEAD, werden oder abrufen können.

*dwContext*<br/>
Der Kontextbezeichner für den `CHttpFile` Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu diesem Parameter.

*pConnection*<br/>
Ein Zeiger auf eine [CHttpConnection](../../mfc/reference/chttpconnection-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CHttpFile` direkt, sondern rufen [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) stattdessen.

Der Standardwert für `dwContext` wird gesendet, von MFC über die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) -Objekt, das erstellt die `CHttpFile` Objekt. Beim Aufruf `CInternetSession::OpenURL` oder `CHttpConnection` zum Erstellen einer `CHttpFile` Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zu Status für das Objekt mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

##  <a name="endrequest"></a>  CHttpFile::EndRequest

Rufen Sie diese Memberfunktion zum Beenden einer Anforderung gesendet, um einen HTTP-Server mit der [SendRequestEx](#sendrequestex) Member-Funktion.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Flags, die den Vorgang beschreiben. Eine Liste mit den geeigneten Flags, finden Sie unter [HttpEndRequest](/windows/desktop/api/wininet/nf-wininet-httpendrequesta) im Windows SDK.

*lpBuffIn*<br/>
Zeiger auf ein initialisiertes [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-_internet_buffersa) , beschreibt den Eingabepuffer für den Vorgang verwendet.

*dwContext*<br/>
Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Der Standardwert für *DwContext* wird gesendet, von MFC über die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) -Objekt, das erstellt die `CHttpFile` Objekt. Beim Aufruf [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen einer `CHttpFile` Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zu Status für das Objekt mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

##  <a name="getfileurl"></a>  CHttpFile::GetFileURL

Rufen Sie diese Memberfunktion zum Abrufen des Namens der HTTP-Datei als URL verwendet wird.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das eine URL verweisen auf die Ressource hat diese Datei enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf ["SendRequest"](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getobject"></a>  CHttpFile::GetObject

Rufen Sie diese Memberfunktion zum Abrufen des Namens des zugeordneten Objekts `CHttpFile`.

```
CString GetObject() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Namen des Objekts enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf ["SendRequest"](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="getverb"></a>  CHttpFile::GetVerb

Rufen Sie diese Memberfunktion rufen Sie die HTTP-Verb (oder Methode) zugeordneten `CHttpFile`.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Namen der HTTP-Verb (oder Methode) enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf ["SendRequest"](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

##  <a name="queryinfo"></a>  CHttpFile::QueryInfo

Rufen Sie diese Memberfunktion zum Zurückgeben der Antwort oder Header für die Anforderung von einer HTTP-Anforderung.

```
BOOL QueryInfo(
    DWORD dwInfoLevel,
    LPVOID lpvBuffer,
    LPDWORD lpdwBufferLength,
    LPDWORD lpdwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    CString& str,
    LPDWORD dwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    SYSTEMTIME* pSysTime,
    LPDWORD dwIndex = NULL) const;
```

### <a name="parameters"></a>Parameter

*dwInfoLevel*<br/>
Eine Kombination des Attributs, Abfrage und die folgenden Flags, die den Typ der angeforderten Informationen angeben:

- HTTP_QUERY_CUSTOM sucht nach den Headernamen an und gibt diesen Wert in der *LpvBuffer* bei der Ausgabe. HTTP_QUERY_CUSTOM löst eine Assertion aus, wenn der Header nicht gefunden wird.

- Die Anwendung fragt HTTP_QUERY_FLAG_REQUEST_HEADERS in der Regel die Header der Antwort, aber eine Anwendung kann auch die Anforderungsheader Abfragen, indem Sie die Verwendung dieses Flags.

- HTTP_QUERY_FLAG_SYSTEMTIME für Header, dessen Wert ein Datum/Uhrzeit-Zeichenfolge, z. B. "Last-Modified-Zeit," dieses Flag gibt den Headerwert als eine standardmäßige Win32- [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) -Struktur, die keine die Anwendung erforderlich ist die Daten analysieren. Wenn Sie dieses Flag verwenden, sollten Sie verwenden die `SYSTEMTIME` außer Kraft setzen, der Funktion.

- HTTP_QUERY_FLAG_NUMBER für Header, dessen Wert eine Zahl, z. B. der Statuscode ist, dieses Flag die Daten als 32-Bit-Zahl zurückgegeben.

Finden Sie unter den **"Hinweise"** Abschnitt eine Liste der möglichen Werte.

*lpvBuffer*<br/>
Ein Zeiger auf den Puffer, der die Informationen empfängt.

*lpdwBufferLength*<br/>
Bei einem Eintrag verweist dies auf einen Wert, der die Länge des Datenpuffers in Anzahl von Zeichen oder Bytes enthält. Finden Sie unter den **"Hinweise"** im Abschnitt Weitere ausführliche Informationen zu diesem Parameter.

*lpdwIndex*<br/>
Ein Zeiger auf eine nullbasierte Headerindex. NULL kann sein. Verwenden Sie dieses Flag, um mehrere Header mit dem gleichen Namen aufgelistet. Bei Eingabe *LpdwIndex* gibt den Index des angegebenen Headers zurückgegeben. Bei der Ausgabe *LpdwIndex* gibt den Index des nächsten-Header. Wenn der nächste Index kann nicht gefunden werden, wird die ERROR_HTTP_HEADER_NOT_FOUND zurückgegeben.

*str*<br/>
Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt empfangen die zurückgegebene Informationen.

*dwIndex*<br/>
Ein Indexwert. Finden Sie unter *LpdwIndex*.

*pSysTime*<br/>
Ein Zeiger auf eine Win32- [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf ["SendRequest"](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

Sie können die folgenden Arten von Daten aus abrufen `QueryInfo`:

- Zeichenfolgen (Standard)

- `SYSTEMTIME` (für "Daten:" "läuft ab:" usw., Header)

- DWORD (für STATUS_CODE, CONTENT_LENGTH usw.)

Wenn eine Zeichenfolge in den Puffer geschrieben wird, und die Member-Funktion erfolgreich ist, `lpdwBufferLength` enthält die Länge der Zeichen minus 1 für das abschließende NULL-Zeichen in der Zeichenfolge.

Die möglichen *DwInfoLevel* Werte sind:

- HTTP_QUERY_MIME_VERSION

- HTTP_QUERY_CONTENT_TYPE

- HTTP_QUERY_CONTENT_TRANSFER_ENCODING

- HTTP_QUERY_CONTENT_ID

- HTTP_QUERY_CONTENT_DESCRIPTION

- HTTP_QUERY_CONTENT_LENGTH

- HTTP_QUERY_ALLOWED_METHODS

- HTTP_QUERY_PUBLIC_METHODS

- HTTP_QUERY_DATE

- HTTP_QUERY_EXPIRES

- HTTP_QUERY_LAST_MODIFIED

- HTTP_QUERY_MESSAGE_ID

- HTTP_QUERY_URI

- HTTP_QUERY_DERIVED_FROM

- HTTP_QUERY_LANGUAGE

- HTTP_QUERY_COST

- HTTP_QUERY_WWW_LINK

- HTTP_QUERY_PRAGMA

- HTTP_QUERY_VERSION

- HTTP_QUERY_STATUS_CODE

- HTTP_QUERY_STATUS_TEXT

- HTTP_QUERY_RAW_HEADERS

- HTTP_QUERY_RAW_HEADERS_CRLF

##  <a name="queryinfostatuscode"></a>  CHttpFile::QueryInfoStatusCode

Rufen Sie diese Memberfunktion rufen Sie den Statuscode einer HTTP-Anforderung zugeordnet ist, und platzieren Sie sie in der angegebenen *DwStatusCode* Parameter.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Parameter

*dwStatusCode*<br/>
Ein Verweis auf einen Statuscode. Statuscodes geben an, den Erfolg oder Misserfolg des angeforderten Ereignisses. Finden Sie unter **"Hinweise"** für eine Reihe von statusbeschreibungen-Code.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf ["SendRequest"](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

HTTP-Statuscodes werden in Gruppen, der angibt, den Erfolg oder Misserfolg der Anforderung. In den folgenden Tabellen werden die Status-Codegruppen und am häufigsten verwendeten HTTP-Statuscodes beschrieben.

|Gruppieren|Bedeutung|
|-----------|-------------|
|200-299|Erfolgreich|
|300-399|Information|
|400-499|Anforderungsfehler|
|500-599|Serverfehler|

Allgemeine HTTP-Statuscodes:

|Statuscode:|Bedeutung|
|-----------------|-------------|
|200|URL befindet, folgt der Übertragung|
|400|Unzulässige Anforderung|
|404|Angeforderte URL nicht gefunden.|
|405|Server unterstützt nicht die angeforderte Methode|
|500|Unbekannter Serverfehler|
|503|Server-Kapazität erreicht|

##  <a name="sendrequest"></a>  CHttpFile:: SendRequest

Rufen Sie diese Memberfunktion zum Senden einer Anforderung an einen HTTP-Server.

```
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLen = 0,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);

BOOL SendRequest(
    CString& strHeaders,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);
```

### <a name="parameters"></a>Parameter

*pstrHeaders*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Header zum Senden.

*dwHeadersLen*<br/>
Die Länge der Header identifizierte *PstrHeaders*.

*lpOptional*<br/>
Optionale Daten unmittelbar nach dem Header der Anforderung zu senden. Dies wird im Allgemeinen für Post- und PUT-Vorgänge verwendet. Dies kann NULL sein, wenn keine optionalen Daten senden.

*dwOptionalLen*<br/>
Die Länge des *LpOptional*.

*strHeaders*<br/>
Eine Zeichenfolge, die mit dem Namen der Header für die Anforderung gesendet werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

##  <a name="sendrequestex"></a>  CHttpFile::SendRequestEx

Rufen Sie diese Memberfunktion zum Senden einer Anforderung an einen HTTP-Server.

```
BOOL SendRequestEx(
    DWORD dwTotalLen,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);

BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,
    LPINTERNET_BUFFERS lpBuffOut,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*dwTotalLen*<br/>
Die Anzahl der Bytes, die in der Anforderung gesendet werden.

*dwFlags*<br/>
Flags, die den Vorgang beschreiben. Eine Liste der entsprechenden Flags, finden Sie unter [HttpSendRequestEx](/windows/desktop/api/wininet/nf-wininet-httpsendrequestexa) im Windows SDK.

*dwContext*<br/>
Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".

*lpBuffIn*<br/>
Zeiger auf ein initialisiertes [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-_internet_buffersa) , beschreibt den Eingabepuffer für den Vorgang verwendet.

*lpBuffOut*<br/>
Zeiger auf ein initialisiertes INTERNET_BUFFERS, die beschreibt, den Ausgabepuffer für den Vorgang verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Diese Funktion kann Ihre Anwendung zum Senden von Daten mithilfe der [schreiben](../../mfc/reference/cinternetfile-class.md#write) und [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) Methoden `CInternetFile`. Sie müssen die Länge der Daten, die vor dem Aufrufen von entweder außer Kraft setzen dieser Funktion senden kennen. Beim ersten überschreiben, können Sie die Länge der Daten angeben, die Sie senden möchten. Beim zweiten Überschreiben akzeptiert Zeigern auf INTERNET_BUFFERS-Strukturen, die verwendet werden kann, um den Puffer ausführlich zu beschreiben.

Nachdem der Inhalt in die Datei geschrieben wird, rufen [EndRequest](#endrequest) um den Vorgang zu beenden.

Der Standardwert für *DwContext* wird gesendet, von MFC über die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) -Objekt, das erstellt die `CHttpFile` Objekt. Beim Aufruf [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen einer `CHttpFile` Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zu Status für das Objekt mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

### <a name="example"></a>Beispiel

Dieses Codefragment sendet den Inhalt einer Zeichenfolge in eine DLL, die mit dem Namen MFCISAPI. Die DLL auf dem Server "localhost". Obwohl in diesem Beispiel nur einen Aufruf von verwendet `WriteString`, durch mehrere Aufrufe zum Senden von Daten in Blöcken akzeptabel ist.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)
