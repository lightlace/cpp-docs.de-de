---
title: CHttpConnection-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: 7d11420ca48bfcecbd2534123a36364314b9651c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611002"
---
# <a name="chttpconnection-class"></a>CHttpConnection-Klasse

Verwaltet die Verbindung mit einem HTTP-Server.

## <a name="syntax"></a>Syntax

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHttpConnection::CHttpConnection](#chttpconnection)|Erstellt ein `CHttpConnection`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHttpConnection:: OpenRequest](#openrequest)|Öffnet eine HTTP-Anforderung an.|

## <a name="remarks"></a>Hinweise

HTTP ist eines der drei Internet-Server-Protokolle, die von den MFC-WinInet-Klassen implementiert.

Die Klasse `CHttpConnection` enthält einen Konstruktor und ein Member-Funktion [OpenRequest](#openrequest), verwaltet die Verbindungen mit einem Server mit einer HTTP-Protokoll.

Mit einem HTTP-Server kommunizieren kann, müssen Sie zunächst eine Instanz von erstellen [CInternetSession](../../mfc/reference/cinternetsession-class.md), und erstellen Sie eine [CHttpConnection](#_mfc_chttpconnection) Objekt. Erstellen Sie nie eine `CHttpConnection` direkt, sondern rufen [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), erstellt die `CHttpConnection` Objekt und gibt einen Zeiger darauf zurück.

Weitere Informationen finden Sie `CHttpConnection` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zum Herstellen einer Verbindung mit Servern, die über die anderen beiden Internetprotokolle, Gopher und FTP unterstützt, finden Sie unter den Klassen [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="chttpconnection"></a>  CHttpConnection::CHttpConnection

Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CHttpConnection` Objekt.

```
CHttpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pSession*<br/>
Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.

*hConnected*<br/>
Ein Handle für eine Internetverbindung besteht.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.

*dwContext*<br/>
Der Kontextbezeichner für den `CInternetConnection` Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.

*%nPort*<br/>
Die Zahl, die den Internet-Port für diese Verbindung identifiziert.

*pstrUserName*<br/>
Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers für die Anmeldung angibt. Wenn der Wert NULL ist, ist die Standardeinstellung anonym.

*pstrPassword*<br/>
Ein Zeiger auf eine auf Null endende Zeichenfolge, die das Kennwort für die Anmeldung angibt. Wenn beide *PstrPassword* und *PstrUserName* NULL sind, die das anonymen Standard-Kennwort wird den e-Mail-Adresse des Benutzers. Wenn *PstrPassword* ist NULL (oder eine leere Zeichenfolge), aber *PstrUserName* ist nicht NULL ist, wird ein leeres Kennwort verwendet. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der *PstrUserName* und *PstrPassword*:

|*pstrUserName*|*pstrPassword*|FTP-Server gesendeten Benutzernamen|Kennwort für FTP-Server gesendet wird.|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL oder ""|NULL oder ""|"Anonym"|Die e-Mail-Adresse des Benutzers|
|Nicht-NULL-Zeichenfolge|NULL oder ""|*pstrUserName*|" "|
|NULL-nicht-NULL-Zeichenfolge|FEHLER|FEHLER||
|Nicht-NULL-Zeichenfolge|Nicht-NULL-Zeichenfolge|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
Eine beliebige Kombination der `INTERNET_FLAG_*` Flags. Finden Sie in der Tabelle in der **"Hinweise"** Abschnitt [CHttpConnection:: OpenRequest](#openrequest) eine Beschreibung der *DwFlags* Werte.

### <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CHttpConnection` direkt. Stattdessen erstellen Sie ein Objekt durch Aufrufen von [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).

##  <a name="openrequest"></a>  CHttpConnection:: OpenRequest

Rufen Sie diese Memberfunktion auf, um eine HTTP-Verbindung zu öffnen.

```
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

CHttpFile* OpenRequest(
    int nVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```

### <a name="parameters"></a>Parameter

*pstrVerb*<br/>
Ein Zeiger auf eine Zeichenfolge, die das Verb enthält, das in der Anforderung verwendet werden soll. Wenn der Wert NULL, werden "GET" verwendet.

*pstrObjectName*<br/>
Ein Zeiger auf eine Zeichenfolge, die das Zielobjekt des angegebenen Verbs enthält. Dies ist in der Regel ein Dateiname, ein ausführbares Modul oder ein Suchspezifizierer.

*pstrReferer*<br/>
Ein Zeiger auf eine Zeichenfolge, die die Adresse (URL) des Dokuments aus dem gibt an, die URL in der Anforderung ( *PstrObjectName*) abgerufen wurde. Wenn der Wert NULL ist, wird kein HTTP-Header angegeben.

*dwContext*<br/>
Der Kontextbezeichner für den `OpenRequest`-Vorgang. Finden Sie im Abschnitt "Hinweise" Weitere Informationen zu *DwContext*.

*ppstrAcceptTypes*<br/>
Ein Zeiger auf eine mit Null endendes Array von LPCTSTR-Zeigern auf Zeichenfolgen, der angibt, Inhaltstypen, die vom Client akzeptiert. Wenn *PpstrAcceptTypes* NULL ist, den Server interpretiert, dass der Client nur Dokumente des Typs akzeptiert "Text / *" (d. h. nur Textdokumente und keine Bilder oder andere Binärdateien). Der Inhaltstyp entspricht der CGI-Variable CONTENT_TYPE, die den Typ der Daten für Abfragen kennzeichnet, denen Informationen wie HTTP POST und PUT angefügt sind.

*pstrVersion*<br/>
Ein Zeiger auf eine Zeichenfolge, mit der die HTTP-Version definiert wird. Wenn der Wert NULL ist, wird "HTTP/1.0" verwendet.

*dwFlags*<br/>
Beliebige Kombinationen der Flags INTERNET_ FLAG_*. Finden Sie im Abschnitt "Hinweise" eine Beschreibung der möglichen *DwFlags* Werte.

*nVerb*<br/>
Eine mit dem HTTP-Anforderungstyp verknüpfte Zahl. Einer der folgenden Werte ist möglich:

|HTTP-Anforderungstyp|*nVerb* Wert|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [CHttpFile](../../mfc/reference/chttpfile-class.md) angeforderte Objekt.

### <a name="remarks"></a>Hinweise

*DwFlags* kann einen der folgenden sein:

|Internet-Flag|Beschreibung|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|Erzwingt einen Download der angeforderten Datei, des angeforderten Objekts oder der angeforderten Verzeichnisliste vom ursprünglichen Server, nicht aus dem Cache.|
|INTERNET_FLAG_DONT_CACHE|Fügt die zurückgegebene Entität nicht dem Cache hinzu.|
|INTERNET_FLAG_MAKE_PERSISTENT|Fügt die zurückgegebene Entität dem Cache als permanente Entität hinzu. Dies bedeutet, dass die Standardcachebereinigung, Konsistenzüberprüfung oder Garbage Collection dieses Element nicht aus dem Cache entfernen kann.|
|INTERNET_FLAG_SECURE|Verwendung eine sichere Transaktionssemantik. Dies wird für die Verwendung von SSL/PCT übersetzt und ist nur in HTTP-Anforderungen sinnvoll.|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Nur mit HTTP verwendet wird, gibt an, dass umleitungen nicht automatisch verarbeitet werden sollen [CHttpFile:: SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|

Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordnet der `CHttpConnection` von erstelltes Objekt seine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Vorgangs bereitzustellen mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

Mit dieser Funktion können Ausnahmen ausgelöst werden.

## <a name="see-also"></a>Siehe auch

[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
