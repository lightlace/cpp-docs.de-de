---
title: CHttpFile Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a7fbdb3baff7531aa4e391e5d7e936c39e38fc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372618"
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
|[CHttpFile:: AddRequestHeaders](#addrequestheaders)|Die an einem HTTP-Server gesendete Anforderung hinzugefügt Header.|  
|[CHttpFile::EndRequest](#endrequest)|Beendet eine Anforderung gesendet, um eine HTTP-Server mit der [SendRequestEx](#sendrequestex) Memberfunktion.|  
|[CHttpFile::GetFileURL](#getfileurl)|Ruft die URL für die angegebene Datei ab.|  
|[CHttpFile::GetObject](#getobject)|Ruft das Zielobjekt des Verbs in einer Anforderung mit einem HTTP-Server.|  
|[CHttpFile::GetVerb](#getverb)|Ruft das Verb an, das in einer Anforderung an einen HTTP-Server verwendet wurde.|  
|[CHttpFile::](#queryinfo)|Gibt die Antwort oder die Anforderung Header aus der HTTP-Server zurück.|  
|[QueryInfoStatusCode](#queryinfostatuscode)|Ruft den Statuscode einer HTTP-Anforderung zugeordnet ist, und platziert sie in der angegebenen `dwStatusCode` Parameter.|  
|[CHttpFile:: SendRequest](#sendrequest)|Sendet eine Anforderung an einen HTTP-Server an.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|Sendet eine Anforderung an einen HTTP-Server mithilfe der [schreiben](../../mfc/reference/cinternetfile-class.md#write) oder [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) Methoden der `CInternetFile`.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Ihre Internet-Sitzung Daten aus einem HTTP-Server liest, muss, erstellen Sie eine Instanz des `CHttpFile`.  
  
 Erfahren Sie mehr darüber, wie `CHttpFile` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="addrequestheaders"></a>  CHttpFile:: AddRequestHeaders  
 Rufen Sie diese Memberfunktion zum Hinzufügen oder weitere HTTP-Anforderungsheader, die HTTP-Anforderung verarbeiten.  
  
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
 `pstrHeaders`  
 Ein Zeiger auf eine Zeichenfolge, enthält der Kopf- oder der Header, um die Anforderung angefügt werden soll. Jeder Header muss durch ein Koordinatenpaar CR/LF beendet werden.  
  
 `dwFlags`  
 Ändert die Semantik der neuen Header an. Einer der folgenden Werte ist möglich:  
  
- `HTTP_ADDREQ_FLAG_COALESCE` Werden die Header mit dem gleichen Namen, verwenden das Flag zum Hinzufügen von des ersten Headers gefunden, die dem nachfolgenden Header zusammengeführt. Z. B. "annehmen: Text / *" gefolgt von "annehmen: Audio-/\*" führt zur Bildung eines einzelnen Header "Accept: Text /\*, audio /\*". Es ist Aufgabe der aufrufenden Anwendung um sicherzustellen, dass ein zusammenhängender Schema in Bezug auf die Daten vom mit zusammengeführte oder separate Header gesendeten Anforderungen empfangen werden.  
  
- `HTTP_ADDREQ_FLAG_REPLACE` Führt eine entfernen und Ersetzen Sie den aktuellen Headerausgabestream hinzuzufügen. So entfernen Sie den aktuellen Headerausgabestream der Headernamen verwendet werden, und der vollständige Wert der neuen Header hinzuzufügen, verwendet werden. Wenn der Header-Wert leer ist, und der Header gefunden wird, wird es entfernt. Wenn dies nicht leer ist, wird der Header-Wert ersetzt.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW` Nur hinzufügt die Header, wenn er nicht bereits vorhanden ist. Wenn eine vorhanden ist, wird ein Fehler zurückgegeben.  
  
- `HTTP_ADDREQ_FLAG_ADD` Wird verwendet, und ersetzen. Fügt den Header an, wenn er nicht vorhanden ist.  
  
 `dwHeadersLen`  
 Die Länge in Zeichen, d. h. der `pstrHeaders`. Wenn dies-1 L, dann ist `pstrHeaders` wird davon ausgegangen, dass null-terminiert sein und die Länge berechnet wird.  
  
 `str`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, enthält der Anforderungsheader oder dem Header hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `AddRequestHeaders` fügt zusätzliche, freiem Format Header an das Handle des HTTP-Anforderung an. Es dient zur Verwendung von anspruchsvollen Clients, die detaillierte Kontrolle über die genaue Anforderung an den HTTP-Server gesendet.  
  
> [!NOTE]
>  Leitet die Anwendung kann mehrere Header in `pstrHeaders` oder `str` für eine `AddRequestHeaders` -Aufruf mit `HTTP_ADDREQ_FLAG_ADD` oder `HTTP_ADDREQ_FLAG_ADD_IF_NEW`. Wenn die Anwendung versucht, entfernen oder Ersetzen Sie einen Header mit **HTTP_ADDREQ_FLAG_REMOVE** oder `HTTP_ADDREQ_FLAG_REPLACE`, nur einen Header kann angegeben werden, in `lpszHeaders`.  
  
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
 `hFile`  
 Ein Handle für eine Internetdatei.  
  
 `hSession`  
 Ein Handle für eine Internet-Sitzung.  
  
 *pstrObject*  
 Ein Zeiger auf eine Zeichenfolge mit der `CHttpFile` Objekt.  
  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Servers.  
  
 `pstrVerb`  
 Ein Zeiger auf eine Zeichenfolge, enthält die Methode, die beim Senden der Anforderung verwendet werden. Kann **POST**, **HEAD**, oder `GET`.  
  
 dwContext  
 Der Kontextbezeichner für den `CHttpFile` Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu diesem Parameter.  
  
 `pConnection`  
 Ein Zeiger auf eine [CHttpConnection](../../mfc/reference/chttpconnection-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CHttpFile` -Objekts direkt, sondern rufen [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) stattdessen.  
  
 Der Standardwert für `dwContext` wird gesendet, von MFC ermöglicht, die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellte Objekt die `CHttpFile` Objekt. Beim Aufruf `CInternetSession::OpenURL` oder `CHttpConnection` zum Erstellen einer `CHttpFile` -Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Objekts bereitzustellen, mit denen es identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="endrequest"></a>  CHttpFile::EndRequest  
 Rufen Sie diese Memberfunktion zum Beenden einer Anforderung an einen HTTP-Server mit der [SendRequestEx](#sendrequestex) Memberfunktion.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Flags, die den Vorgang beschreiben. Eine Liste der erforderlichen Flags, finden Sie unter [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) im Windows SDK.  
  
 `lpBuffIn`  
 Zeiger auf ein initialisiertes [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , beschreibt der Eingabepuffer für den Vorgang verwendet.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für `dwContext` wird gesendet, von MFC ermöglicht, die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellte Objekt die `CHttpFile` Objekt. Beim Aufruf [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen einer `CHttpFile` -Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Objekts bereitzustellen, mit denen es identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="getfileurl"></a>  CHttpFile::GetFileURL  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der HTTP-Datei als URL verwendet wird.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das eine URL verweisen auf die Ressource, die mit dieser Datei verknüpften enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getobject"></a>  CHttpFile::GetObject  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des zugeordneten Objekts `CHttpFile`.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das den Namen des Objekts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getverb"></a>  CHttpFile::GetVerb  
 Rufen Sie diese Memberfunktion zum Abrufen der HTTP-Verb (oder Methode) zugeordnete `CHttpFile`.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit dem Namen der HTTP-Verb (oder Methode).  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="queryinfo"></a>  CHttpFile::  
 Rufen Sie diese Memberfunktion zum Zurückgeben der Antwort oder Anforderungsheader über eine HTTP-Anforderung.  
  
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
 `dwInfoLevel`  
 Eine Kombination des Attributs Abfragen ausgeführt und die folgenden Flags, die den Typ der angeforderten Informationen anzugeben:  
  
- **HTTP_QUERY_CUSTOM** sucht nach den Headernamen an und gibt diesen Wert im `lpvBuffer` bei der Ausgabe. **HTTP_QUERY_CUSTOM** löst Sie eine Assertion aus, wenn der Header nicht gefunden wird.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** in der Regel wird die Anwendung fordert die Antwortheader, aber eine Anwendung kann auch Anforderungsheader mithilfe dieses Flag Abfragen.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** für diesen Header, dessen Wert ist eine Datum/Uhrzeit-Zeichenfolge, z. B. "Last-Modified-Zeit," dieses Flag gibt die Header-Wert als eine standardmäßige Win32- [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die keine erfordert die die Anwendung, die Daten zu analysieren. Wenn Sie dieses Flag verwenden, sollten Sie verwenden die `SYSTEMTIME` außer Kraft setzen, der Funktion.  
  
- **HTTP_QUERY_FLAG_NUMBER** für diesen Header, dessen Wert eine Zahl, z. B. den Statuscode ist, dieses Flag gibt die Daten als 32-Bit-Zahl zurück.  
  
 Finden Sie unter der **"Hinweise"** Abschnitt für eine Liste der möglichen Werte.  
  
 `lpvBuffer`  
 Ein Zeiger auf den Puffer, der die Informationen erhält.  
  
 `lpdwBufferLength`  
 Bei der Eintrag zeigt dies auf einen Wert, der die Länge des Datenpuffers in Anzahl von Zeichen oder Bytes. Finden Sie unter der **"Hinweise"** Abschnitt Ausführlichere Informationen zu diesem Parameter.  
  
 `lpdwIndex`  
 Ein Zeiger auf einen nullbasierten Headerindex. Kann **NULL**. Verwenden Sie dieses Flag, um mehrere Header mit dem gleichen Namen aufzulisten. Bei der Eingabe `lpdwIndex` gibt den Index des angegebenen Headers zurückgegeben. Bei der Ausgabe `lpdwIndex` gibt den Index des nächsten-Header. Wenn der nächste Index kann nicht gefunden werden, **ERROR_HTTP_HEADER_NOT_FOUND** wird zurückgegeben.  
  
 `str`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt empfängt die zurückgegebene Informationen.  
  
 `dwIndex`  
 Ein Indexwert. Siehe `lpdwIndex`.  
  
 *pSysTime*  
 Ein Zeiger auf eine Win32- [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Sie können die folgenden Typen von Daten aus abrufen `QueryInfo`:  
  
-   Zeichenfolgen (Standard)  
  
- `SYSTEMTIME` (für "Daten:" "Expires:" usw., Kopfzeilen)  
  
- `DWORD` (für **STATUS_CODE**, **CONTENT_LENGTH**usw..)  
  
 Wenn eine Zeichenfolge in den Puffer geschrieben wird, und die Member-Funktion erfolgreich ist, `lpdwBufferLength` enthält die Länge der Zeichenfolge in Zeichen minus 1 für das abschließende **NULL** Zeichen.  
  
 Die möglichen `dwInfoLevel` Werte sind:  
  
- **HTTP_QUERY_MIME_VERSION**  
  
- **HTTP_QUERY_CONTENT_TYPE**  
  
- **HTTP_QUERY_CONTENT_TRANSFER_ENCODING**  
  
- **HTTP_QUERY_CONTENT_ID**  
  
- **HTTP_QUERY_CONTENT_DESCRIPTION**  
  
- **HTTP_QUERY_CONTENT_LENGTH**  
  
- **HTTP_QUERY_ALLOWED_METHODS**  
  
- **HTTP_QUERY_PUBLIC_METHODS**  
  
- **HTTP_QUERY_DATE**  
  
- **HTTP_QUERY_EXPIRES**  
  
- **HTTP_QUERY_LAST_MODIFIED**  
  
- **HTTP_QUERY_MESSAGE_ID**  
  
- **HTTP_QUERY_URI**  
  
- **HTTP_QUERY_DERIVED_FROM**  
  
- **HTTP_QUERY_LANGUAGE**  
  
- **HTTP_QUERY_COST**  
  
- **HTTP_QUERY_WWW_LINK**  
  
- **HTTP_QUERY_PRAGMA**  
  
- **HTTP_QUERY_VERSION**  
  
- **HTTP_QUERY_STATUS_CODE**  
  
- **HTTP_QUERY_STATUS_TEXT**  
  
- **HTTP_QUERY_RAW_HEADERS**  
  
- **HTTP_QUERY_RAW_HEADERS_CRLF**  
  
##  <a name="queryinfostatuscode"></a>  QueryInfoStatusCode  
 Rufen Sie diese Memberfunktion zum Abrufen des Statuscode einer HTTP-Anforderung zugeordnet ist, und fügen Sie ihn in das angegebene `dwStatusCode` Parameter.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwStatusCode`  
 Ein Verweis auf einen Statuscode. Statuscodes geben an, den Erfolg oder Fehler des angeforderten Ereignisses. Finden Sie unter **"Hinweise"** für eine Auswahl von Status Code Beschreibungen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion nur nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf eine `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 HTTP-Statuscodes fallen in Gruppen, die den Erfolg oder Fehler der Anforderung angibt. In den folgenden Tabellen beschreiben die Codegruppen für Status und die am häufigsten verwendeten HTTP-Statuscodes.  
  
|Gruppieren|Bedeutung|  
|-----------|-------------|  
|200-299|Erfolgreich|  
|300-399|Information|  
|400-499|Fehler beim Anfordern|  
|500-599|Serverfehler|  
  
 Allgemeine Statuscodes http:  
  
|Statuscode|Bedeutung|  
|-----------------|-------------|  
|300|URL befindet, Übertragung folgt.|  
|400|Unzulässige Anforderung|  
|404|Angeforderte URL wurde nicht gefunden.|  
|405|Server unterstützt nicht die angeforderte Methode|  
|500|Unbekannter Serverfehler|  
|503|Server-Kapazität erreicht|  
  
##  <a name="sendrequest"></a>  CHttpFile:: SendRequest  
 Rufen Sie diese Memberfunktion, um eine Anforderung an einen HTTP-Server senden.  
  
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
 `pstrHeaders`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Header zu senden.  
  
 `dwHeadersLen`  
 Die Länge der identifizierten Header `pstrHeaders`.  
  
 `lpOptional`  
 Optionale Daten unmittelbar nach der Anforderungsheader zu senden. Dies wird im Allgemeinen zum **POST** und **PUT** Vorgänge. Dies kann **NULL** , wenn keine optionalen Daten senden.  
  
 *dwOptionalLen*  
 Die Länge von `lpOptional`.  
  
 `strHeaders`  
 Eine Zeichenfolge, die mit dem Namen der Header für die Anforderung gesendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
##  <a name="sendrequestex"></a>  CHttpFile::SendRequestEx  
 Rufen Sie diese Memberfunktion, um eine Anforderung an einen HTTP-Server senden.  
  
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
 *dwTotalLen*  
 Anzahl der Bytes, die in der Anforderung gesendet werden.  
  
 `dwFlags`  
 Flags, die den Vorgang beschreiben. Eine Liste der erforderlichen Flags, finden Sie unter [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) im Windows SDK.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".  
  
 `lpBuffIn`  
 Zeiger auf ein initialisiertes [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , beschreibt der Eingabepuffer für den Vorgang verwendet.  
  
 *lpBuffOut*  
 Zeiger auf ein initialisiertes **INTERNET_BUFFERS** , beschreibt den Ausgabepuffer für den Vorgang verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ermöglicht Ihrer Anwendung zum Senden von Daten mithilfe der [schreiben](../../mfc/reference/cinternetfile-class.md#write) und [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) Methoden der `CInternetFile`. Sie müssen die Länge der Daten, die vor dem Aufrufen dieser Funktion überschreiben senden kennen. Die erste Außerkraftsetzung können Sie die Länge der Daten angeben, die Sie senden möchten. Die zweite Außerkraftsetzung akzeptiert Zeiger auf **INTERNET_BUFFERS** Strukturen, die verwendet werden kann, um den Puffer ausführlich zu beschreiben.  
  
 Rufen Sie nach dem Inhalt der Datei geschrieben wird, [EndRequest](#endrequest) um den Vorgang zu beenden.  
  
 Der Standardwert für `dwContext` wird gesendet, von MFC ermöglicht, die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellte Objekt die `CHttpFile` Objekt. Beim Aufruf [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen einer `CHttpFile` -Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Objekts bereitzustellen, mit denen es identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment sendet den Inhalt einer Zeichenfolge in eine DLL mit dem Namen MFCISAPI. Die DLL auf dem Server "localhost". Zwar in diesem Beispiel wird nur ein Aufruf von nutzt `WriteString`, verwenden mehrere Aufrufe zum Senden von Daten in Blöcken akzeptabel ist.  
  
 [!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)
