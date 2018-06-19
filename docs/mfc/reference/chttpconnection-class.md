---
title: CHttpConnection-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs:
- C++
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 808c88e3a98df12d35afa9ce207f57456520b169
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367645"
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
|[CHttpConnection:: OpenRequest](#openrequest)|Öffnet eine HTTP-Anforderung.|  
  
## <a name="remarks"></a>Hinweise  
 HTTP ist eines der drei Internet-Server-Protokolle, die von den MFC-WinInet-Klassen implementiert.  
  
 Die Klasse `CHttpConnection` enthält einen Konstruktor und eine Memberfunktion, [OpenRequest](#openrequest), verwaltet die Verbindungen mit einem Server mit einem HTTP-Protokoll.  
  
 Für die Kommunikation mit einem HTTP-Server müssen zuerst erstellen Sie eine Instanz des [CInternetSession](../../mfc/reference/cinternetsession-class.md), und erstellen Sie eine [CHttpConnection](#_mfc_chttpconnection) Objekt. Erstellen Sie nie eine `CHttpConnection` -Objekts direkt, sondern rufen [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), erstellt die `CHttpConnection` -Objekt und gibt einen Zeiger darauf zurück.  
  
 Erfahren Sie mehr darüber, wie `CHttpConnection` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zum Herstellen einer Verbindung mit Servern, die mit den anderen beiden Internetprotokolle, Gopher und FTP-unterstützt, finden Sie unter den Klassen [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
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
 `pSession`  
 Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.  
  
 `hConnected`  
 Ein Handle für eine Internetverbindung.  
  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CInternetConnection` Objekt. Finden Sie unter **"Hinweise"** Weitere Informationen zu `dwContext`.  
  
 `nPort`  
 Die Zahl, die den Internet-Port für diese Verbindung identifiziert.  
  
 `pstrUserName`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers anmelden angibt. Wenn **NULL**, der Standardwert ist anonymous.  
  
 `pstrPassword`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Kennwort zur Anmeldung verwenden. Wenn beide `pstrPassword` und `pstrUserName` sind **NULL**, das anonymen Standard-Kennwort ist die e-Mail-Namen des Benutzers. Wenn `pstrPassword` ist **NULL** (oder eine leere Zeichenfolge), aber `pstrUserName` nicht **NULL**, ein leeres Kennwort verwendet. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der `pstrUserName` und `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP-Server gesendeten Benutzernamen|Kennwort mit FTP-Server gesendet wird.|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** oder ""|**NULL** oder ""|"Anonym"|Die e-Mail-Namen des Benutzers|  
|Nicht- **NULL** Zeichenfolge|**NULL** oder ""|`pstrUserName`|" "|  
|**NULL** nicht- **NULL** Zeichenfolge|**FEHLER**|**FEHLER**||  
|Nicht- **NULL** Zeichenfolge|Nicht- **NULL** Zeichenfolge|`pstrUserName`|`pstrPassword`|  
  
 `dwFlags`  
 Eine beliebige Kombination der **INTERNET_ FLAG_\***  Flags. Finden Sie in der Tabelle in der **"Hinweise"** Abschnitt [CHttpConnection:: OpenRequest](#openrequest) eine Beschreibung der `dwFlags` Werte.  
  
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
 `pstrVerb`  
 Ein Zeiger auf eine Zeichenfolge, die das Verb enthält, das in der Anforderung verwendet werden soll. Wenn `NULL`, wird "GET" verwendet.  
  
 `pstrObjectName`  
 Ein Zeiger auf eine Zeichenfolge, die das Zielobjekt des angegebenen Verbs enthält. Dies ist in der Regel ein Dateiname, ein ausführbares Modul oder ein Suchspezifizierer.  
  
 `pstrReferer`  
 Ein Zeiger auf eine Zeichenfolge, die die Adresse (URL) des Dokuments aus dem gibt die URL in der Anforderung ( `pstrObjectName`) abgerufen wurde. Wenn `NULL`, wird kein HTTP-Header angegeben.  
  
 `dwContext`  
 Der Kontextbezeichner für den `OpenRequest`-Vorgang. Weitere Informationen zu `dwContext` finden Sie im Abschnitt "Hinweise".  
  
 `ppstrAcceptTypes`  
 Ein Zeiger auf ein mit NULL endendes Array von `LPCTSTR`-Zeigern auf Zeichenfolgen, die durch den Client akzeptierte Inhaltstypen angeben. Wenn `ppstrAcceptTypes` den Wert `NULL` hat, wird von den Server interpretiert, dass der Client nur Dokumente des Typs "text/*" akzeptiert (also nur Textdokumente, keine Bilder oder andere Binärdateien). Der Inhaltstyp entspricht der CGI-Variable CONTENT_TYPE, die den Typ der Daten für Abfragen kennzeichnet, denen Informationen wie HTTP POST und PUT angefügt sind.  
  
 `pstrVersion`  
 Ein Zeiger auf eine Zeichenfolge, mit der die HTTP-Version definiert wird. Wenn `NULL`, wird "HTTP/1.0" verwendet.  
  
 `dwFlags`  
 Beliebige Kombinationen der Flags INTERNET_ FLAG_*. Eine Beschreibung möglicher `dwFlags`-Werte finden Sie im Abschnitt "Hinweise".  
  
 `nVerb`  
 Eine mit dem HTTP-Anforderungstyp verknüpfte Zahl. Einer der folgenden Werte ist möglich:  
  
|HTTP-Anforderungstyp|`nVerb`-Wert|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CHttpFile](../../mfc/reference/chttpfile-class.md) Objekt angefordert.  
  
### <a name="remarks"></a>Hinweise  
 `dwFlags` kann eines der folgenden Elemente sein:  
  
|Internet-Flag|Beschreibung|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|Erzwingt einen Download der angeforderten Datei, des angeforderten Objekts oder der angeforderten Verzeichnisliste vom ursprünglichen Server, nicht aus dem Cache.|  
|`INTERNET_FLAG_DONT_CACHE`|Fügt die zurückgegebene Entität nicht dem Cache hinzu.|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|Fügt die zurückgegebene Entität dem Cache als permanente Entität hinzu. Dies bedeutet, dass die Standardcachebereinigung, Konsistenzüberprüfung oder Garbage Collection dieses Element nicht aus dem Cache entfernen kann.|  
|`INTERNET_FLAG_SECURE`|Verwendung eine sichere Transaktionssemantik. Dies wird für die Verwendung von SSL/PCT übersetzt und ist nur in HTTP-Anforderungen sinnvoll.|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|Nur mit HTTP verwendet wird, gibt an, dass umleitungen nicht automatisch in erfolgen soll [CHttpFile:: SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CHttpConnection` Objekt erstellt wird, dessen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
 Mit dieser Funktion können Ausnahmen ausgelöst werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
