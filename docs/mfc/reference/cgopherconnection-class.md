---
title: CGopherConnection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f4bc06415d804aa48b7d12ac28b1181e818a2c2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082566"
---
# <a name="cgopherconnection-class"></a>CGopherConnection-Klasse

Verwaltet die Verbindung mit einem Gopherinternetserver.

> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und deren Member sind veraltet, da, nicht auf der Windows XP-Plattform funktionieren, während sie weiterhin auf frühere Plattformen funktionieren.

## <a name="syntax"></a>Syntax

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Erstellt ein `CGopherConnection`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CGopherConnection::CreateLocator](#createlocator)|Erstellt eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt, um Dateien auf einem Gopherserver zu suchen.|
|[CGopherConnection::GetAttribute](#getattribute)|Ruft Attributinformationen über das Gopher-Objekt ab.|
|[CGopherConnection::OpenFile](#openfile)|Öffnet eine Gopherdatei.|

## <a name="remarks"></a>Hinweise

Der Gopher-Dienst ist einer der drei Internetdienste, die von den MFC-WinInet-Klassen erkannt.

Die Klasse `CGopherConnection` enthält einen Konstruktor und drei weitere Memberfunktionen, die den Gopher-Dienst zu verwalten: [OpenFile](#openfile), [CreateLocator](#createlocator), und [GetAttribute](#getattribute).

Mit einem gopherinternetserver kommunizieren kann, müssen Sie zunächst eine Instanz von erstellen [CInternetSession](../../mfc/reference/cinternetsession-class.md), und rufen dann [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), erstellt die `CGopherConnection` -Objekt und gibt einen Zeiger darauf zurück. Erstellen Sie nie eine `CGopherConnection` direkt.

Weitere Informationen finden Sie `CGopherConnection` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zur Verwendung von der anderen beiden Internetdienste unterstützt, FTP und HTTP finden Sie unter den Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cgopherconnection"></a>  CGopherConnection::CGopherConnection

Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherConnection` Objekt.

```
CGopherConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CGopherConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parameter

*pSession*<br/>
Ein Zeiger auf den zugehörigen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.

*hConnected*<br/>
Das Windows-Handle von der aktuellen Internet-Sitzung.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des FTP-Server.

*dwContext*<br/>
Der Kontextbezeichner für den Vorgang. *DwContext* identifiziert des Vorgangs der vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Der Standardwert ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und Arbeit ist, werden diese Kontext-ID zugeordnet werden.

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

*%nPort*<br/>
Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.

### <a name="remarks"></a>Hinweise

Erstellen Sie nie eine `CGopherConnection` direkt. Rufen Sie stattdessen [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), erstellt eine `CGopherConnection` Objekt und gibt einen Zeiger darauf zurück.

##  <a name="createlocator"></a>  CGopherConnection:: CreateLocator

Rufen Sie diese Memberfunktion zum Erstellen eines Gopher-Locators zum Suchen oder eine Datei auf einem Gopherserver zu identifizieren.

```
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType);

static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Parameter

*pstrDisplayString*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Gopher-Dokuments oder des Verzeichnisses abgerufen werden sollen. Wenn die *PstrDisplayString* Parameter NULL ist, wird das Standardverzeichnis für das Gopher-Server zurückgegeben.

*pstrSelectorString*<br/>
Ein Zeiger auf die Auswahlzeichenfolge, die an den Gopherserver gesendet werden, um ein Element abgerufen werden. *PstrSelectorString* kann NULL sein.

*dwGopherType*<br/>
Gibt an, ob *PstrSelectorString* bezieht sich auf ein Verzeichnis oder ein Dokument, und gibt an, ob die Anforderung Gopher oder Gopher erfolgt. Die Attribute für die Struktur [GOPHER_FIND_DATA](/windows/desktop/api/wininet/ns-wininet-gopher_find_dataa) im Windows SDK.

*pstrLocator*<br/>
Ein Zeiger auf eine Zeichenfolge, die die zu öffnende Datei identifiziert. Diese Zeichenfolge wird in der Regel von einem Aufruf zurückgegeben [CGopherFileFind:: GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).

*pstrServerName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Gopher-Servers enthält.

*%nPort*<br/>
Die Anzahl den Internet-Port für diese Verbindung identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Die statische Version von der Memberfunktion müssen Sie einen Server an, während die nicht statische Version den Servernamen aus dem Verbindungsobjekt verwendet.

Zum Abrufen von Informationen von einem Gopherserver muss eine Anwendung zunächst einen Gopher-Locator abrufen. Die Anwendung muss dann den Locator als nicht transparente Token behandeln (, also die Anwendung kann den Locator verwenden, aber nicht direkt bearbeiten oder vergleichen Sie ihn). Die Anwendung in der Regel für Aufrufe des Locators verwendet den [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) Memberfunktion versucht, eine bestimmte Information abzurufen.

##  <a name="getattribute"></a>  CGopherConnection::GetAttribute

Rufen Sie diese Memberfunktion, um spezifische Informationen über ein Element aus der Gopher-Server abzurufen.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Parameter

*refLocator*<br/>
Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.

*strRequestedAttributes*<br/>
Ein Leerzeichen getrennte Zeichenfolge, der Sie den Namen der erforderlichen Attribute angeben.

*"strResult"*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) , empfängt den Locatortyp.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.

##  <a name="openfile"></a>  CGopherConnection:: OpenFile

Rufen Sie diese Memberfunktion zum Öffnen einer Datei auf einem Gopherserver.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*refLocator*<br/>
Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.

*dwFlags*<br/>
Eine beliebige Kombination von INTERNET_FLAG_ *-flags. Finden Sie unter [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) für Weitere Informationen zu INTERNET_FLAG_\* Flags.

*pstrView*<br/>
Ein Zeiger auf eine Datei-View-Zeichenfolge. Wenn mehrere Ansichten der Datei auf dem Server vorhanden ist, gibt dieser Parameter die Dateiansicht zu öffnen. Wenn *PstrView* NULL ist, wird die Standardansicht für die Datei verwendet.

*dwContext*<br/>
Die Kontext-ID für die Datei geöffnet wird. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [CGopherFile](../../mfc/reference/cgopherfile-class.md) Objekt, das geöffnet werden.

### <a name="remarks"></a>Hinweise

Überschreiben der *DwContext* standardmäßig den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordnet der `CGopherConnection` von erstelltes Objekt seine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Vorgangs bereitzustellen mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

## <a name="see-also"></a>Siehe auch

[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)<br/>
[CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)<br/>
[CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)<br/>
[CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)<br/>
[CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)
