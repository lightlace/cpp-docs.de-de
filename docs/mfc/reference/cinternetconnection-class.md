---
title: CInternetConnection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 650935eec8d268aa5e1433ebd9a60b0bc63d0296
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409427"
---
# <a name="cinternetconnection-class"></a>CInternetConnection-Klasse

Verwaltet die Verbindung mit einem Internetserver.

## <a name="syntax"></a>Syntax

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Erstellt ein `CInternetConnection`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CInternetConnection::GetContext](#getcontext)|Ruft die Kontext-ID für dieses Verbindungsobjekt ab.|
|[CInternetConnection::GetServerName](#getservername)|Ruft den Namen des Servers mit der Verbindung verknüpft sind.|
|[CInternetConnection::GetSession](#getsession)|Ruft einen Zeiger auf die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt, mit der Verbindung verknüpft ist.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Ein Handle für eine internetsitzung.|

## <a name="remarks"></a>Hinweise

Es ist die Basisklasse für MFC-Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Jede dieser Klassen bietet zusätzliche Funktionen für die Kommunikation mit den jeweiligen FTP, HTTP oder Gopher-Server.

Um direkt mit einem Internetserver zu kommunizieren, benötigen Sie eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt und ein `CInternetConnection` Objekt.

Finden Sie im Artikel, um weitere Informationen dazu, wie von der WinInet-Klassen, [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection

Diese Memberfunktion wird aufgerufen, wenn eine `CInternetConnection` Objekt erstellt wird.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pSession*<br/>
Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.

*pstrServer*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.

*%nPort*<br/>
Die Zahl, die den Internet-Port für diese Verbindung identifiziert.

*dwContext*<br/>
Der Kontextbezeichner für den `CInternetConnection` Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.

### <a name="remarks"></a>Hinweise

Rufen Sie nie `CInternetConnection` müssen Sie selbst rufen Sie stattdessen die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Memberfunktion für die Art der Verbindung, die Sie einrichten möchten:

- [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

Der Standardwert für *DwContext* wird gesendet, von MFC über die `CInternetConnection`-abgeleitetes Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) -Objekt, das erstellt die **InternetConnection**- abgeleitetes Objekt. Der Standardwert ist auf 1 festgelegt. Sie können jedoch explizit zuweisen eine spezifischen Kontext-ID in der [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) Konstruktor für die Verbindung. Das Objekt und Arbeit ist, werden diese Kontext-ID zugeordnet werden. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zu Status für das Objekt mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

##  <a name="getcontext"></a>  CInternetConnection::GetContext

Rufen Sie diese Memberfunktion, um die Kontext-ID für diese Sitzung zu erhalten.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anwendung zugewiesene Kontext-ID

### <a name="remarks"></a>Hinweise

Die Kontext-ID wird in ursprünglich angegeben [CInternetSession](../../mfc/reference/cinternetsession-class.md) und überträgt auf `CInternetConnection`- und [CInternetFile](../../mfc/reference/cinternetfile-class.md)-Klassen abgeleitet, es sei denn, die im Aufruf an eine Funktion anders angegeben, das geöffnet wird die Verbindung. Die Kontext-ID jeder Vorgang in das angegebene Objekt zugeordnet ist und vom zurückgegebenen des Vorgangs Statusinformationen identifiziert [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).

Weitere Informationen dazu, wie `GetContext` funktioniert mit anderen WinInet-Klassen, gewähren Sie die Benutzerinformationen zum clientinstallationsstatus finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

##  <a name="getservername"></a>  CInternetConnection::GetServerName

Rufen Sie diese Memberfunktion zum Abrufen des Namens des Servers mit diesem Internet-Verbindung verknüpft sind.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des Servers, mit denen dieses Verbindungsobjekt arbeiten wird.

##  <a name="getsession"></a>  CInternetConnection::GetSession

Rufen Sie diese Memberfunktion, um einen Zeiger auf die `CInternetSession` -Objekt, das dieser Verbindung zugeordnet ist.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt mit diesem Internet Connection-Objekt verknüpft ist.

##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET

Verwenden Sie diesen Operator, um das Handle für die API-Ebene für die aktuelle Sitzung des Internet abzurufen.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)



