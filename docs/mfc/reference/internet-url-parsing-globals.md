---
title: Analysieren von Internet-URLs und -Hilfsprogramme
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 310e4ffb3fc207d874e97ba1fac65f6f8cb41a31
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611026"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Analysieren von Internet-URLs und -Hilfsprogramme

Wenn ein Client eine Abfrage an der IIS-Server sendet, können eine der URLs Globals für das Analysieren Sie zum Extrahieren von Informationen über den Client. Die Hilfsfunktionen bieten andere Internetfunktionen.

## <a name="internet-url-parsing-globals"></a>Globale Variablen zur Analyse von Internet-URLs

|||
|-|-|
|[AfxParseURL](#afxparseurl)|Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten zurück.|
|[AfxParseURLEx](#afxparseurlex)|Analysiert eine URL-Zeichenfolge und gibt den Typ der Dienst und seiner Komponenten, sowie den Benutzernamen und ein Kennwort zurück.|

## <a name="other-internet-helpers"></a>Andere Internet-Hilfsprogramme

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Löst eine Ausnahme, die im Zusammenhang mit der Internetverbindung.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Bestimmt den Typ eines Internet-Handles.|

##  <a name="afxparseurl"></a>  AfxParseURL

Dieses globale werden in [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>Parameter

*pstrURL*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit der URL analysiert werden.

*dwServiceType*<br/>
Gibt den Typ des Internet-Diensts an. Folgende Werte sind möglich:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
Das erste Segment der URL nach der Diensttyp.

*strObject*<br/>
Ein Objekt, das auf die URL verweist (kann leer sein).

*nPort*<br/>
Durch den Server oder Objekt Teile der URL bestimmt, soweit vorhanden.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die URL erfolgreich analysiert wurde; andernfalls 0, wenn er leer ist oder enthält keinen bekannten Typ eines Internet-Diensts.

### <a name="remarks"></a>Hinweise

Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten zurück.

Z. B. `AfxParseURL` URLs im Format analysiert *Service://server/dir/dir/object.ext:port* und gibt seine Komponenten wie folgt gespeichert:

*strServer* == "server"

*strObject* == "/dir/dir/object/object.ext"

*nPort* == #port

*dwServiceType* == #service

> [!NOTE]
>  Um diese Funktion aufzurufen, muss Ihr Projekt CFILEFIND enthalten. H.

### <a name="requirements"></a>Anforderungen

  **Header** afxinet.h

##  <a name="afxparseurlex"></a>  AfxParseURLEx

Diese globale Funktion ist die erweiterte Version des [AfxParseURL](#afxparseurl) wird im [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort,
    CString& strUsername,
    CString& strPassword,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Parameter

*pstrURL*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit der URL analysiert werden.

*dwServiceType*<br/>
Gibt den Typ des Internet-Diensts an. Folgende Werte sind möglich:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
Das erste Segment der URL nach der Diensttyp.

*strObject*<br/>
Ein Objekt, das auf die URL verweist (kann leer sein).

*nPort*<br/>
Durch den Server oder Objekt Teile der URL bestimmt, soweit vorhanden.

*strUsername*<br/>
Ein Verweis auf eine `CString` -Objekt, das den Namen des Benutzers enthält.

*strPassword*<br/>
Ein Verweis auf eine `CString` -Objekt, das das Kennwort des Benutzers enthält.

*dwFlags*<br/>
Die Flags, steuern die URL zu analysieren. Eine Kombination der folgenden Werte sind möglich:

|Wert|Bedeutung|
|-----------|-------------|
|ICU_DECODE|Konvertieren Sie % XX Escape-Sequenzen, in Zeichen.|
|ICU_NO_ENCODE|Escape-Sequenz unsichere Zeichen nicht konvertieren.|
|ICU_NO_META|Entfernen Sie nicht Meta-Sequenzen (z. B. "\." und "\...") aus der URL.|
|ICU_ENCODE_SPACES_ONLY|Codieren Sie nur aus Leerzeichen bestehen.|
|ICU_BROWSER_MODE|Nicht codieren oder Decodieren von Zeichen nach "#" oder ", und Entfernen nicht nachgestellte Leerzeichen nach". Wenn dieser Wert nicht angegeben ist, wird die gesamte URL codiert und nachgestellte Leerzeichen entfernt.|

Bei Verwendung von MFC-Standard, der keine Flags ist, die Funktion konvertiert alle unsicheren Zeichen sowie Metadaten Sequenzen (z. B. \\., \.., und \\...) Sequenzen mit Escapezeichen versehen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die URL erfolgreich analysiert wurde; andernfalls 0, wenn er leer ist oder enthält keinen bekannten Typ eines Internet-Diensts.

### <a name="remarks"></a>Hinweise

Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten, sowie Name und das Kennwort des Benutzers bereitstellen. Die Flags geben an, wie unsicheren Zeichen behandelt werden.

> [!NOTE]
>  Um diese Funktion aufzurufen, muss Ihr Projekt CFILEFIND enthalten. H.

### <a name="requirements"></a>Anforderungen

  **Header** afxinet.h

## <a name="afxgetinternethandletype"></a>  AfxGetInternetHandleType

Verwenden Sie diese globale Funktion, um den Typ eines Internet-Handles zu bestimmen.

### <a name="syntax"></a>Syntax

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>Parameter

*hQuery*<br/>
Ein Handle für eine Internet-Abfrage.

### <a name="return-value"></a>Rückgabewert

Alle von der Internet-Diensttypen, die durch WININET definiert. H. Finden Sie im Abschnitt "Hinweise" eine Liste dieser Internet-Dienste. Wenn das Handle NULL ist oder nicht erkannt, gibt die Funktion AFX_INET_SERVICE_UNK an.

### <a name="remarks"></a>Hinweise

Die folgende Liste enthält mögliche Internet-Typen, die vom `AfxGetInternetHandleType`.

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
>  Um diese Funktion aufrufen, muss Ihr Projekt CFILEFIND enthalten. H.

### <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

## <a name="afxthrowinternetexception"></a>  AfxThrowInternetException

Eine Internet-Ausnahme ausgelöst.

### <a name="syntax"></a>Syntax

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>Parameter

*dwContext*<br/>
Der Kontextbezeichner für den Vorgang, der den Fehler verursacht hat. Der Standardwert von *DwContext* wurde ursprünglich im angegebenen [CInternetSession](cinternetsession-class.md) und übergeben [CInternetConnection](cinternetconnection-class.md)- und [CInternetFile](cinternetfile-class.md)-abgeleiteten Klassen. Für bestimmte Vorgänge, die für eine Verbindung oder eine Datei ausgeführt werden, überschreiben Sie in der Regel die Standardeinstellung mit einem *DwContext* selbst. Dieser Wert wird dann an zurückgegeben [CInternetSession:: OnStatusCallback](cinternetsession-class.md#onstatuscallback) bestimmte den Status des Vorgangs zu identifizieren.

*dwError*<br/>
Der Fehler, der die Ausnahme verursacht hat.

### <a name="remarks"></a>Hinweise

Sie sind verantwortlich für das Ermitteln der Ursache, die basierend auf dem Betriebssystem-Fehlercode.

> [!NOTE]
>  Um diese Funktion aufzurufen, muss Ihr Projekt CFILEFIND enthalten. H.

### <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](mfc-macros-and-globals.md)<br/>
[CInternetException-Klasse](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
