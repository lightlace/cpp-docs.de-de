---
title: CHttpFile Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- HTTP files
- HTTP requests, requesting and reading files
- CHttpFile class
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
caps.latest.revision: 23
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
ms.openlocfilehash: 0077c04f53514901dccaa3d162cd132578270225
ms.lasthandoff: 02/24/2017

---
# <a name="chttpfile-class"></a>CHttpFile-Klasse
Stellt die Funktionalität bereit, um Dateien auf einem HTTP-Server anfordern und zu lesen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHttpFile : public CInternetFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHttpFile::CHttpFile](#chttpfile)|Erstellt ein `CHttpFile`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHttpFile:: AddRequestHeaders](#addrequestheaders)|Die an einen HTTP-Server gesendete Anforderung hinzugefügt Header.|  
|[CHttpFile::EndRequest](#endrequest)|Beendet eine Anforderung an einen HTTP-Server mit der [SendRequestEx](#sendrequestex) Member-Funktion.|  
|[CHttpFile::GetFileURL](#getfileurl)|Ruft die URL für die angegebene Datei.|  
|[CHttpFile::GetObject](#getobject)|Ruft das Zielobjekt des Verbs in einer Anforderung mit einem HTTP-Server.|  
|[CHttpFile::GetVerb](#getverb)|Ruft das Verb, das in einer Anforderung mit einem HTTP-Server verwendet wurde.|  
|[CHttpFile::](#queryinfo)|Gibt die Antwort oder Anforderung-Header der HTTP-Server zurück.|  
|[QueryInfoStatusCode](#queryinfostatuscode)|Den Statuscode einer HTTP-Anforderung zugeordnet und speichert sie in der angegebenen `dwStatusCode` Parameter.|  
|[CHttpFile:: SendRequest](#sendrequest)|Sendet eine Anforderung an einen HTTP-Server.|  
|[CHttpFile::SendRequestEx](#sendrequestex)|Sendet eine Anforderung an eine HTTP-Server mit der [schreiben](../../mfc/reference/cinternetfile-class.md#write) oder [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) Methoden der `CInternetFile`.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Ihre Internet-Sitzung von einem HTTP-Server Daten liest, muss, erstellen Sie eine Instanz des `CHttpFile`.  
  
 Weitere Informationen zur Verwendung `CHttpFile` arbeitet mit den anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CHttpFile`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="addrequestheaders"></a>CHttpFile:: AddRequestHeaders  
 Rufen Sie diese Memberfunktion zum Hinzufügen oder weitere HTTP-Anforderungsheader der HTTP-Anforderung verarbeiten.  
  
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
 Ein Zeiger auf eine Zeichenfolge mit der Kopf- oder der Header der Anforderung angefügt. Jeder Header muss durch ein paar CR/LF beendet werden.  
  
 `dwFlags`  
 Ändert sich die Semantik der neuen Header. Einer der folgenden Werte ist möglich:  
  
- `HTTP_ADDREQ_FLAG_COALESCE`Verbindet Header mit dem gleichen Namen, die mithilfe des Flags, die den ersten Header finden Sie in der nachfolgenden Header hinzufügen. Z. B. "Accept: Text / *" gefolgt von "Accept: audio /\*" führt die Bildung von den einzelnen Header "Accept: Text /\*, audio /\*". Es ist Aufgabe der aufrufenden Anwendung um ein zusammenhängendes Schema in Bezug auf die von gesendeten Anforderungen mit zusammengeführte oder separate Header empfangenen Daten sicherzustellen.  
  
- `HTTP_ADDREQ_FLAG_REPLACE`Führt eine entfernen und Ersetzen Sie den aktuellen Header hinzuzufügen. Der Headername Entfernen des aktuellen Headers verwendet werden, und der vollständige Wert der neuen Header hinzuzufügen, verwendet werden. Wenn der Header-Wert leer ist, und der Header gefunden wird, wird es entfernt. Wenn nicht leer ist, wird der Header-Wert ersetzt.  
  
- `HTTP_ADDREQ_FLAG_ADD_IF_NEW`Fügt den Header nur hinzu, wenn sie nicht bereits vorhanden ist. Sofern vorhanden, wird ein Fehler zurückgegeben.  
  
- `HTTP_ADDREQ_FLAG_ADD`Wird verwendet, und ersetzen. Fügt den Header hinzu, wenn er nicht vorhanden ist.  
  
 `dwHeadersLen`  
 Die Länge in Zeichen des `pstrHeaders`. Wenn dies-1 L, dann ist `pstrHeaders` wird davon ausgegangen, dass null-terminiert sein, und die Länge wird berechnet.  
  
 `str`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt mit der Anforderungsheader oder dem Header hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `AddRequestHeaders`Das Handle der HTTP-Anforderung hinzufügt zusätzliche, freiem Header. Es ist für die Verwendung durch ausgereiften Clients vorgesehen, die detaillierte Kontrolle über die genaue Anforderung an den HTTP-Server gesendet.  
  
> [!NOTE]
>  Die Anwendung kann in mehrere Header übergeben `pstrHeaders` oder `str` für eine `AddRequestHeaders` -Aufruf mit `HTTP_ADDREQ_FLAG_ADD` oder `HTTP_ADDREQ_FLAG_ADD_IF_NEW`. Wenn die Anwendung versucht, entfernen oder Ersetzen Sie einen Header mit **HTTP_ADDREQ_FLAG_REMOVE** oder `HTTP_ADDREQ_FLAG_REPLACE`, nur einen Header kann angegeben werden, `lpszHeaders`.  
  
##  <a name="chttpfile"></a>CHttpFile::CHttpFile  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CHttpFile` Objekt.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.  
  
 `pstrVerb`  
 Ein Zeiger auf eine Zeichenfolge, die die Methode, die beim Senden der Anforderung verwendet werden. Can be **POST**, **HEAD**, or `GET`.  
  
 dwContext  
 Der Kontextbezeichner für den `CHttpFile` Objekt. Finden Sie unter **Hinweise** für Weitere Informationen zu diesem Parameter.  
  
 `pConnection`  
 Ein Zeiger auf eine [CHttpConnection](../../mfc/reference/chttpconnection-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CHttpFile` direkt, sondern rufen [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) stattdessen.  
  
 Der Standardwert für `dwContext` von MFC gesendet wird die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellten Objekt der `CHttpFile` Objekt. Beim Aufruf von `CInternetSession::OpenURL` oder `CHttpConnection` zum Erstellen einer `CHttpFile` -Objekt können Sie die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen überschreiben. Die Kontext-ID wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Objekts bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="endrequest"></a>CHttpFile::EndRequest  
 Rufen Sie diese Memberfunktion, um eine Anforderung an einen HTTP-Server Beenden der [SendRequestEx](#sendrequestex) Member-Funktion.  
  
```  
BOOL EndRequest(
    DWORD dwFlags = 0,  
    LPINTERNET_BUFFERS lpBuffIn = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Flags, die den Vorgang beschreiben. Eine Übersicht über den geeigneten Flags finden Sie unter [HttpEndRequest](http://msdn.microsoft.com/library/windows/desktop/aa384230) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpBuffIn`  
 Zeiger auf ein initialisiertes [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , beschreibt die Puffer für den Vorgang verwendet.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für `dwContext` von MFC gesendet wird die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellten Objekt der `CHttpFile` Objekt. Beim Aufruf von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen einer `CHttpFile` -Objekt können Sie die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen überschreiben. Die Kontext-ID wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Objekts bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="getfileurl"></a>CHttpFile::GetFileURL  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der Datei HTTP-URL.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das eine URL verweisen auf die Ressource hat diese Datei enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf einer `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getobject"></a>CHttpFile::GetObject  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des zugeordneten Objekts `CHttpFile`.  
  
```  
CString GetObject() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das den Namen des Objekts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf einer `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="getverb"></a>CHttpFile::GetVerb  
 Rufen Sie diese Memberfunktion zum Abrufen der HTTP-Verb (oder Methode) zugeordneten `CHttpFile`.  
  
```  
CString GetVerb() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt mit dem Namen der HTTP-Verb (oder Methode).  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf einer `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
##  <a name="queryinfo"></a>CHttpFile::  
 Rufen Sie diese Memberfunktion zum Zurückgeben der Antwort oder Anforderungsheader aus einer HTTP-Anforderung.  
  
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
 Eine Kombination des Attributs, Abfrage und die folgenden Flags, die den Typ der angeforderten Informationen anzugeben:  
  
- **HTTP_QUERY_CUSTOM** sucht nach den Headernamen an und gibt diesen Wert im `lpvBuffer` bei der Ausgabe. **HTTP_QUERY_CUSTOM** löst eine Assertion aus, wenn der Header nicht gefunden wurde.  
  
- **HTTP_QUERY_FLAG_REQUEST_HEADERS** in der Regel die Anwendung fragt die Antwortheader, aber eine Anwendung kann auch Anforderungsheader mithilfe dieses Flag Abfragen.  
  
- **HTTP_QUERY_FLAG_SYSTEMTIME** für Header, dessen Wert ein Datum/Uhrzeit-Zeichenfolge, z. B. "Last-Modified-Zeit," wird, dieses Flag gibt den Headerwert als standardmäßige Win32- [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die keine Anwendung zum Analysieren der Daten erforderlich ist. Wenn Sie dieses Flag verwenden, möchten Sie möglicherweise verwenden die `SYSTEMTIME` der Funktion überschreiben.  
  
- **HTTP_QUERY_FLAG_NUMBER** für Header, dessen Wert eine Zahl, z. B. den Statuscode ist, gibt dieses Flag die Daten als 32-Bit-Zahl.  
  
 Finden Sie unter der **Hinweise** Abschnitt für eine Liste der möglichen Werte.  
  
 `lpvBuffer`  
 Ein Zeiger auf den Puffer, der die Informationen empfängt.  
  
 `lpdwBufferLength`  
 Eintrag zeigt dies auf einen Wert, der die Länge des Datenpuffers in Anzahl von Bytes oder Zeichen. Finden Sie unter der **Hinweise** Abschnitt Ausführlichere Informationen zu diesem Parameter.  
  
 `lpdwIndex`  
 Ein Zeiger auf eine nullbasierte Headerindex. Kann **NULL**. Verwenden Sie dieses Flag gibt es mehrere Header mit dem gleichen Namen aufgelistet werden. Bei der Eingabe `lpdwIndex` gibt den Index des angegebenen Headers zurückgegeben. Bei der Ausgabe `lpdwIndex` gibt den Index des nächsten-Header. Wenn Sie der Index nicht gefunden werden kann, **ERROR_HTTP_HEADER_NOT_FOUND** wird zurückgegeben.  
  
 `str`  
 Ein Verweis auf die [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt empfangen die zurückgegebene Informationen.  
  
 `dwIndex`  
 Ein Indexwert. Siehe `lpdwIndex`.  
  
 *pSysTime*  
 Ein Zeiger auf eine Win32- [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf einer `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 Sie können die folgenden Arten von Daten aus abrufen `QueryInfo`:  
  
-   Zeichenfolgen (Standard)  
  
- `SYSTEMTIME`(für "Data:" "Expires:" usw., Header)  
  
- `DWORD`(für **STATUS_CODE**, **CONTENT_LENGTH**usw..)  
  
 Wenn eine Zeichenfolge in den Puffer geschrieben wird, und die Member-Funktion erfolgreich ist, `lpdwBufferLength` enthält die Länge der Zeichenfolge in Zeichen minus 1 für die abschließende **NULL** Zeichen.  
  
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
  
##  <a name="queryinfostatuscode"></a>QueryInfoStatusCode  
 Rufen Sie diese Memberfunktion zum Abrufen des Statuscode einer HTTP-Anforderung zugeordnet, und platzieren Sie es in der angegebenen `dwStatusCode` Parameter.  
  
```  
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwStatusCode`  
 Ein Verweis auf einen Statuscode. Statuscodes geben an, den Erfolg oder Misserfolg des angeforderten Ereignisses. Finden Sie unter **Hinweise** für eine Auswahl von Status Code beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Memberfunktion erst nach einem erfolgreichen Aufruf von [SendRequest](#sendrequest) oder auf einer `CHttpFile` Objekt erfolgreich erstellt, indem [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
 HTTP-Statuscodes werden in Gruppen, die den Erfolg oder Misserfolg der Anforderung angibt. In den folgenden Tabellen beschreiben die Codegruppen Status und die am häufigsten verwendeten HTTP-Statuscodes.  
  
|Gruppieren|Bedeutung|  
|-----------|-------------|  
|200-299|Erfolgreich|  
|300-399|Information|  
|400-499|Fehler beim Anfordern|  
|500-599|Server-Fehler|  
  
 Häufige HTTP-Statuscodes:  
  
|Statuscode|Bedeutung|  
|-----------------|-------------|  
|300|URL gefunden, Übertragung folgt|  
|400|Unzulässige Anforderung|  
|404|Angeforderte URL nicht gefunden|  
|405|Server unterstützt angeforderte Methode nicht.|  
|500|Unbekannter Serverfehler|  
|503|Server-Kapazität erreicht|  
  
##  <a name="sendrequest"></a>CHttpFile:: SendRequest  
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
 `pstrHeaders`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Header senden.  
  
 `dwHeadersLen`  
 Die Länge der Header identifizierten `pstrHeaders`.  
  
 `lpOptional`  
 Optionale Daten unmittelbar nach dem Header der Anforderung zu senden. Dies wird im Allgemeinen zum **POST** und **PUT** Vorgänge. Dies kann **NULL** Wenn keine optionalen Daten senden.  
  
 *dwOptionalLen*  
 Die Länge von `lpOptional`.  
  
 `strHeaders`  
 Eine Zeichenfolge mit dem Namen der Header für die Anforderung gesendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
##  <a name="sendrequestex"></a>CHttpFile::SendRequestEx  
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
 *dwTotalLen*  
 Anzahl der Bytes, die in der Anforderung gesendet werden.  
  
 `dwFlags`  
 Flags, die den Vorgang beschreiben. Eine Liste der entsprechenden Flags, finden Sie unter [HttpSendRequestEx](http://msdn.microsoft.com/library/windows/desktop/aa384318) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 `dwContext`  
 Der Kontextbezeichner für den `CHttpFile`-Vorgang. Weitere Informationen zu diesem Parameter finden Sie unter "Hinweise".  
  
 `lpBuffIn`  
 Zeiger auf ein initialisiertes [INTERNET_BUFFERS](http://msdn.microsoft.com/library/windows/desktop/aa385132) , beschreibt die Puffer für den Vorgang verwendet.  
  
 *lpBuffOut*  
 Zeiger auf ein initialisiertes **INTERNET_BUFFERS** , beschreibt den Ausgabepuffer für den Vorgang verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, falls erfolgreich. Wenn der Aufruf fehlschlägt, ermitteln Sie die Ursache des Fehlers durch Untersuchen der ausgelösten [CInternetException](../../mfc/reference/cinternetexception-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie Ihre Anwendung zum Senden von Daten mithilfe der [schreiben](../../mfc/reference/cinternetfile-class.md#write) und [WriteString](../../mfc/reference/cinternetfile-class.md#writestring) Methoden der `CInternetFile`. Sie müssen die Länge der Daten, die vor dem Aufrufen dieser Funktion überschreiben senden kennen. Die erste außer Kraft setzen können Sie die Länge der Daten angeben, die Sie senden möchten. Die zweite Außerkraftsetzung akzeptiert Zeiger auf **INTERNET_BUFFERS** -Strukturen, die mit dem Puffer ausführlich beschrieben werden können.  
  
 Nachdem Inhalt in die Datei geschrieben wird, rufen Sie [EndRequest](#endrequest) um den Vorgang zu beenden.  
  
 Der Standardwert für `dwContext` von MFC gesendet wird die `CHttpFile` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellten Objekt der `CHttpFile` Objekt. Beim Aufruf von [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) oder [CHttpConnection](../../mfc/reference/chttpconnection-class.md) zum Erstellen einer `CHttpFile` -Objekt können Sie die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen überschreiben. Die Kontext-ID wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Objekts bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment sendet den Inhalt einer Zeichenfolge in eine DLL mit dem Namen MFCISAPI. Die DLL auf dem Server "localhost". In diesem Beispiel wird nur ein Aufruf verwendet `WriteString`, verwenden mehrere Aufrufe zum Senden von Daten in Blöcken akzeptabel ist.  
  
 [!code-cpp[NVC_MFCWinInet&#9;](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)

