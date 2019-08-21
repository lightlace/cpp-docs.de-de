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
ms.openlocfilehash: ff050a89a10c68c639c141891dd51b1b2d58e105
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916000"
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
|[CHttpFile:: CHttpFile](#chttpfile)|Erstellt ein `CHttpFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Fügt der an einen HTTP-Server gesendeten Anforderung Header hinzu.|
|[CHttpFile::EndRequest](#endrequest)|Beendet eine Anforderung, die an einen HTTP-Server mit der [sendrequestex](#sendrequestex) -Member-Funktion gesendet wird.|
|[CHttpFile::GetFileURL](#getfileurl)|Ruft die URL für die angegebene Datei ab.|
|[CHttpFile::GetObject](#getobject)|Ruft das Zielobjekt des Verbs in einer Anforderung an einen HTTP-Server ab.|
|[CHttpFile::GetVerb](#getverb)|Ruft das Verb ab, das in einer Anforderung an einen HTTP-Server verwendet wurde.|
|[CHttpFile::QueryInfo](#queryinfo)|Gibt die Antwort-oder Anforderungs Header vom HTTP-Server zurück.|
|[CHttpFile::QueryInfoStatusCode](#queryinfostatuscode)|Ruft den Statuscode ab, der einer HTTP-Anforderung zugeordnet ist, und legt `dwStatusCode` ihn im angegebenen-Parameter ab.|
|[CHttpFile::SendRequest](#sendrequest)|Sendet eine Anforderung an einen HTTP-Server.|
|[CHttpFile::SendRequestEx](#sendrequestex)|Sendet eine Anforderung an einen HTTP-Server mithilfe der [Write](../../mfc/reference/cinternetfile-class.md#write) -Methode oder der Write `CInternetFile` [String](../../mfc/reference/cinternetfile-class.md#writestring) -Methode von.|

## <a name="remarks"></a>Hinweise

Wenn in Ihrer Internet Sitzung Daten von einem HTTP-Server gelesen werden, müssen Sie eine `CHttpFile`Instanz von erstellen.

Weitere Informationen `CHttpFile` zum Arbeiten mit den anderen MFC-Internet Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="addrequestheaders"></a>CHttpFile:: adressquestheaders

Diese Member-Funktion wird aufgerufen, um dem HTTP-Anforderungs handle mindestens einen HTTP-Anforderungs Header hinzuzufügen.

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
Ein Zeiger auf eine Zeichenfolge, die die Header oder Header enthält, die an die Anforderung angefügt werden sollen. Jeder Header muss von einem CR/LF-paar beendet werden.

*dwFlags*<br/>
Ändert die Semantik der neuen Header. Kann einen der folgenden Werte annehmen:

- HTTP_ADDREQ_FLAG_COALESCE führt Header desselben Namens zusammen, wobei das-Flag verwendet wird, um den ersten Header hinzuzufügen, der dem nachfolgenden Header gefunden wurde. "Accept: Text\*/" gefolgt von "Accept: Audio/\*" führt z. b. zur Entstehung der einzelnen Kopfzeile "Accept: Text/\*, Audio/\*". Es liegt an der aufrufenden Anwendung, ein zusammenhängendes Schema in Bezug auf Daten zu gewährleisten, die von Anforderungen empfangen werden, die mit zusammengefügten oder getrennten Headern gesendet werden

- HTTP_ADDREQ_FLAG_REPLACE führt einen Remove-und Add-Abschnitt aus, um den aktuellen Header zu ersetzen. Der Header Name wird verwendet, um den aktuellen Header zu entfernen, und der vollständige Wert wird verwendet, um den neuen Header hinzuzufügen. Wenn der Header Wert leer ist und der Header gefunden wird, wird er entfernt. Wenn nicht leer, wird der Header Wert ersetzt.

- HTTP_ADDREQ_FLAG_ADD_IF_NEW fügt den Header nur hinzu, wenn er nicht bereits vorhanden ist. Wenn eine solche vorhanden ist, wird ein Fehler zurückgegeben.

- HTTP_ADDREQ_FLAG_ADD wird mit "Replace" verwendet. Fügt den Header hinzu, wenn er nicht vorhanden ist.

*dwHeadersLen*<br/>
Die Länge von *pstrinheaders*in Zeichen. Wenn dies-1L ist, wird davon ausgegangen, dass *pstrauheaders* mit 0 (null) beendet wird und die Länge berechnet wird.

*str*<br/>
Ein Verweis auf ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das die hinzu zufügenden Anforderungs Header oder-Header enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

`AddRequestHeaders`Fügt dem HTTP-Anforderungs handle weitere Header mit freiem Format an. Es ist für die Verwendung durch anspruchsvolle Clients vorgesehen, die eine ausführliche Kontrolle über die genaue Kontrolle über die genaue Anforderung an den HTTP-Server benötigen.

> [!NOTE]
>  Die Anwendung kann mehrere Header in *pstrauheaders* oder *Str* für einen `AddRequestHeaders` -Befehl über HTTP_ADDREQ_FLAG_ADD oder HTTP_ADDREQ_FLAG_ADD_IF_NEW übergeben. Wenn die Anwendung versucht, einen Header mit HTTP_ADDREQ_FLAG_REMOVE oder HTTP_ADDREQ_FLAG_REPLACE zu entfernen oder zu ersetzen, kann nur ein Header in *lpszheaders*angegeben werden.

##  <a name="chttpfile"></a>CHttpFile:: CHttpFile

Diese Member-Funktion wird aufgerufen, um `CHttpFile` ein-Objekt zu erstellen.

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
Ein Handle für eine Internet Datei.

*hSession*<br/>
Ein Handle für eine Internet Sitzung.

*pstrObject*<br/>
Ein Zeiger auf eine Zeichenfolge, `CHttpFile` die das-Objekt enthält.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.

*pstrVerb*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Methode enthält, die beim Senden der Anforderung verwendet werden soll. Kann Post, Head oder Get sein.

*dwContext*<br/>
Der Kontext Bezeichner für `CHttpFile` das-Objekt. Weitere Informationen zu diesem Parameter finden Sie unter " **Hinweise** ".

*pConnection*<br/>
Ein Zeiger auf ein [CHttpConnection](../../mfc/reference/chttpconnection-class.md) -Objekt.

### <a name="remarks"></a>Hinweise

Sie erstellen niemals direkt `CHttpFile` ein-Objekt, sondern stattdessen [cinternetzession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection:: openrequest](../../mfc/reference/chttpconnection-class.md#openrequest) .

Der Standardwert für `dwContext` wird von MFC an das `CHttpFile` -Objekt aus dem [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt gesendet, `CHttpFile` das das Objekt erstellt hat. Wenn Sie oder `CInternetSession::OpenURL` `CHttpConnection` zum Erstellen eines `CHttpFile` -Objekts aufzurufen, können Sie die Standardeinstellung überschreiben, um den Kontext Bezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontext Bezeichner wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für das Objekt bereitzustellen, mit dem es identifiziert wird. Weitere Informationen finden [Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

##  <a name="endrequest"></a>CHttpFile:: EndRequest

Mit dieser Member-Funktion können Sie eine Anforderung beenden, die mit der [sendrequestex](#sendrequestex) -Member-Funktion an einen HTTP-Server gesendet wird.

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Flags, die den Vorgang beschreiben. Eine Liste der entsprechenden Flags finden Sie unter [httpdrequest](/windows/desktop/api/wininet/nf-wininet-httpendrequesta) in der Windows SDK.

*lpBuffIn*<br/>
Zeiger auf eine initialisierte [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-internet_buffersa) , die den für den Vorgang verwendeten Eingabepuffer beschreibt.

*dwContext*<br/>
Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

### <a name="remarks"></a>Hinweise

Der Standardwert für *dwcontext* wird von MFC an das `CHttpFile` -Objekt aus dem [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt gesendet, `CHttpFile` das das Objekt erstellt hat. Wenn Sie [cinternettionession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen eines `CHttpFile` -Objekts aufzurufen, können Sie die Standardeinstellung überschreiben, um den Kontext Bezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontext Bezeichner wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für das Objekt bereitzustellen, mit dem es identifiziert wird. Weitere Informationen [finden Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

##  <a name="getfileurl"></a>CHttpFile:: getfileurl

Mit dieser Member-Funktion können Sie den Namen der http-Datei als URL abrufen.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das eine URL enthält, die auf die dieser Datei zugeordnete Ressource verweist.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Member-Funktion nur nach einem erfolgreichen [SendRequest](#sendrequest) -Aufrufvorgang oder einem `CHttpFile` erfolgreich von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)erstellten-Objekt.

##  <a name="getobject"></a>CHttpFile:: GetObject

Mit dieser Member-Funktion können Sie den Namen des Objekts abrufen, das `CHttpFile`diesem zugeordnet ist.

```
CString GetObject() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Namen des Objekts enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Member-Funktion nur nach einem erfolgreichen [SendRequest](#sendrequest) -Aufrufvorgang oder einem `CHttpFile` erfolgreich von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)erstellten-Objekt.

##  <a name="getverb"></a>CHttpFile:: getverb

Mit dieser Member-Funktion können Sie das HTTP-Verb (oder die-Methode `CHttpFile`) abrufen, das diesem zugeordnet ist.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Namen des HTTP-Verbs (oder der-Methode) enthält.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Member-Funktion nur nach einem erfolgreichen [SendRequest](#sendrequest) -Aufrufvorgang oder einem `CHttpFile` erfolgreich von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)erstellten-Objekt.

##  <a name="queryinfo"></a>CHttpFile:: QueryInfo

Mit dieser Member-Funktion können Sie Antwort-oder Anforderungs Header aus einer HTTP-Anforderung zurückgeben.

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
Eine Kombination aus dem abzufragende Attribut und den folgenden Flags, die den Typ der angeforderten Informationen angeben:

- HTTP_QUERY_CUSTOM sucht nach dem Header Namen und gibt diesen Wert in *lpvbuffer* bei der Ausgabe zurück. HTTP_QUERY_CUSTOM löst eine-Übersetzung aus, wenn der Header nicht gefunden wird.

- HTTP_QUERY_FLAG_REQUEST_HEADERS in der Regel fragt die Anwendung die Antwortheader ab, aber eine Anwendung kann auch Anforderungs Header mithilfe dieses Flags Abfragen.

- HTTP_QUERY_FLAG_SYSTEMTIME für Header, deren Wert eine Datums-/Uhrzeit-Zeichenfolge ist (z. b. "Last-modified-time"), gibt dieses Flag den Header Wert als standardmäßige Win32- [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) -Struktur zurück, die nicht erfordert, dass die Anwendung die Daten analysiert. Wenn Sie dieses Flag verwenden, können Sie die `SYSTEMTIME` Überschreibung der Funktion verwenden.

- HTTP_QUERY_FLAG_NUMBER für Header, deren Wert eine Zahl ist, z. b. der Statuscode, gibt dieses Flag die Daten als 32-Bit-Zahl zurück.

Eine Liste der möglichen Werte finden Sie im Abschnitt " **Hinweise** ".

*lpvBuffer*<br/>
Ein Zeiger auf den Puffer, der die Informationen empfängt.

*lpdwBufferLength*<br/>
Bei einem Eintrag zeigt dies auf einen Wert, der die Länge des Daten Puffers enthält, als Anzahl von Zeichen oder Bytes. Ausführlichere Informationen zu diesem Parameter finden Sie im Abschnitt " **Hinweise** ".

*lpdwIndex*<br/>
Ein Zeiger auf einen NULL basierten Header Index. Kann NULL sein. Verwenden Sie dieses Flag, um mehrere Header mit demselben Namen aufzuzählen. Bei Eingabe gibt *lpdwindex* den Index des angegebenen Headers an, der zurückgegeben werden soll. Bei der Ausgabe gibt *lpdwindex* den Index des nächsten Headers an. Wenn der nächste Index nicht gefunden werden kann, wird ERROR_HTTP_HEADER_NOT_FOUND zurückgegeben.

*str*<br/>
Ein Verweis auf das [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das die zurückgegebenen Informationen empfängt.

*dwIndex*<br/>
Ein Indexwert. Siehe *lpdwindex*.

*pSysTime*<br/>
Ein Zeiger auf eine Win32- [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) -Struktur.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Member-Funktion nur nach einem erfolgreichen [SendRequest](#sendrequest) -Aufrufvorgang oder einem `CHttpFile` erfolgreich von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)erstellten-Objekt.

Sie können die folgenden Datentypen aus `QueryInfo`abrufen:

- Zeichen folgen (Standard)

- `SYSTEMTIME`(für "Data:" läuft ab: "usw., Header)

- DWORD (für STATUS_CODE, CONTENT_LENGTH usw.)

Wenn eine Zeichenfolge in den Puffer geschrieben wird und die Member-Funktion erfolgreich `lpdwBufferLength` ist, enthält die Länge der Zeichenfolge in Zeichen minus 1 für das abschließende Null Zeichen.

*Folgende dwinfolevel* -Werte sind möglich:

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

##  <a name="queryinfostatuscode"></a>CHttpFile:: queryinfostatus Code

Mit dieser Member-Funktion können Sie den mit einer HTTP-Anforderung verknüpften Statuscode abrufen und ihn im angegebenen *dwstatuscode* -Parameter platzieren.

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Parameter

*dwStatusCode*<br/>
Ein Verweis auf einen Statuscode. Status Codes geben an, dass das angeforderte Ereignis erfolgreich war oder fehlgeschlagen ist. Unter **Hinweise** finden Sie eine Auswahl von Statuscode Beschreibungen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, kann die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Member-Funktion nur nach einem erfolgreichen [SendRequest](#sendrequest) -Aufrufvorgang oder einem `CHttpFile` erfolgreich von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl)erstellten-Objekt.

HTTP-Statuscodes werden in Gruppen angezeigt, die den Erfolg oder das Fehlschlagen der Anforderung angeben. In den folgenden Tabellen werden die Statuscode Gruppen und die gängigsten HTTP-Statuscodes erläutert.

|Gruppieren|Bedeutung|
|-----------|-------------|
|200-299|Erfolgreich|
|300-399|Information|
|400-499|Anforderungs Fehler|
|500-599|Server Fehler|

Allgemeine HTTP-Status Codes:

|Status Code|Bedeutung|
|-----------------|-------------|
|200|URL gefunden, Übertragung folgt|
|400|Unverständliche Anforderung|
|404|Angeforderte URL nicht gefunden.|
|405|Der Server unterstützt die angeforderte Methode nicht.|
|500|Unbekannter Server Fehler.|
|503|Server Kapazität erreicht|

##  <a name="sendrequest"></a>CHttpFile:: SendRequest

Mit dieser Member-Funktion können Sie eine Anforderung an einen HTTP-Server senden.

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
Ein Zeiger auf eine Zeichenfolge, die den Namen der zu sendenden Header enthält.

*dwHeadersLen*<br/>
Die Länge der durch *pstrinheaders*identifizierten Header.

*lpOptional*<br/>
Alle optionalen Daten, die unmittelbar nach den Anforderungs Headern gesendet werden sollen. Dies wird im Allgemeinen für Post-und Put-Vorgänge verwendet. Dieser Wert kann NULL sein, wenn keine optionalen Daten zum Senden vorhanden sind.

*dwOptionalLen*<br/>
Die Länge der *lpoptional*.

*strHeaders*<br/>
Eine Zeichenfolge, die den Namen der Header für die gesendete Anforderung enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

##  <a name="sendrequestex"></a>CHttpFile:: sendrequestex

Mit dieser Member-Funktion können Sie eine Anforderung an einen HTTP-Server senden.

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
Anzahl der Bytes, die in der Anforderung gesendet werden sollen.

*dwFlags*<br/>
Flags, die den Vorgang beschreiben. Eine Liste geeigneter Flags finden Sie unter [HttpSendRequestEx](/windows/desktop/api/wininet/nf-wininet-httpsendrequestexa) im Windows SDK.

*dwContext*<br/>
Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".

*lpBuffIn*<br/>
Zeiger auf eine initialisierte [INTERNET_BUFFERS](/windows/desktop/api/wininet/ns-wininet-internet_buffersa) , die den für den Vorgang verwendeten Eingabepuffer beschreibt.

*lpBuffOut*<br/>
Zeiger auf eine initialisierte INTERNET_BUFFERS, die den für den Vorgang verwendeten Ausgabepuffer beschreibt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich. Wenn der-Befehl fehlschlägt, ermitteln Sie die Ursache des Fehlers, indem Sie das ausgelöste [cinternettexception](../../mfc/reference/cinternetexception-class.md) -Objekt überprüfen.

### <a name="remarks"></a>Hinweise

Diese Funktion ermöglicht es Ihrer Anwendung, Daten mithilfe der [Write](../../mfc/reference/cinternetfile-class.md#write)- und [WriteString](../../mfc/reference/cinternetfile-class.md#writestring)-Methoden von `CInternetFile` zu senden. Sie müssen die Länge der zu sendenden Daten kennen, bevor Sie eine außer Kraft setzung dieser Funktion aufrufen. Mit der ersten außer Kraft Setzung können Sie die Länge der Daten angeben, die Sie senden möchten. Die zweite außer Kraft Setzung akzeptiert Zeiger auf INTERNET_BUFFERS-Strukturen, die verwendet werden können, um den Puffer ausführlich zu beschreiben.

Nachdem der Inhalt in die Datei geschrieben wurde, wird [EndRequest](#endrequest) aufgerufen, um den Vorgang zu beenden.

Der Standardwert für *dwcontext* wird von MFC an das `CHttpFile` -Objekt aus dem [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt gesendet, `CHttpFile` das das Objekt erstellt hat. Wenn Sie [cinternettionession:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen eines `CHttpFile` -Objekts aufzurufen, können Sie die Standardeinstellung überschreiben, um den Kontext Bezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontext Bezeichner wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für das Objekt bereitzustellen, mit dem es identifiziert wird. Weitere Informationen finden [Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

### <a name="example"></a>Beispiel

Dieses Code Fragment sendet den Inhalt einer Zeichenfolge an eine DLL mit dem Namen mfcisapi. DLL auf dem localhost-Server. Obwohl in diesem Beispiel nur ein Aufruf von `WriteString`verwendet wird, ist die Verwendung mehrerer Aufrufe zum Senden von Daten in-Blöcken akzeptabel.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>Siehe auch

[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)
