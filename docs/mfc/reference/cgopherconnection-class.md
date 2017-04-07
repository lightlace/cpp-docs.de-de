---
title: CGopherConnection Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- servers, connecting to
- Internet server, gopher
- connecting to servers, gopher servers
- protocols, gopher
- services, gopher
- CGopherConnection class
- gopher protocol
- gopher server
- connecting to servers
- Internet connections, gopher
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
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
ms.openlocfilehash: 6267dd226e87e5bf64faa7225e49d9a99af93e3e
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherconnection-class"></a>CGopherConnection-Klasse
Verwaltet die Verbindung mit einem Gopherinternetserver.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da nicht unter Windows XP funktionieren, aber sie werden weiterhin auf frühere Plattformen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Erstellt ein `CGopherConnection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherConnection:: CreateLocator](#createlocator)|Erstellt eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt, um Dateien auf einem Gopherserver zu suchen.|  
|[CGopherConnection::GetAttribute](#getattribute)|Ruft Informationen über das Gopher-Objekt ab.|  
|[CGopherConnection:: OpenFile](#openfile)|Öffnet eine Gopherdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Gopher-Dienst ist eine der drei Internetdienste erkannt werden, indem Sie die MFC-WinInet-Klassen.  
  
 Die Klasse `CGopherConnection` enthält einen Konstruktor und drei zusätzliche Memberfunktionen, die den Gopher-Dienst zu verwalten: [OpenFile](#openfile), [CreateLocator](#createlocator), und [GetAttribute](#getattribute).  
  
 Die Kommunikation mit einem gopherinternetserver müssen Sie zuerst eine Instanz von erstellen [CInternetSession](../../mfc/reference/cinternetsession-class.md), und rufen Sie dann [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), erstellt das `CGopherConnection` -Objekt und gibt einen Zeiger darauf zurück. Erstellen Sie nie eine `CGopherConnection` direkt.  
  
 Weitere Informationen zur Verwendung `CGopherConnection` arbeitet mit den anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zum Verwenden von der anderen beiden Internet Services unterstützt, FTP und HTTP finden Sie unter die Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CGopherConnection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherconnection"></a>CGopherConnection::CGopherConnection  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CGopherConnection` Objekt.  
  
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
 `pSession`  
 Ein Zeiger auf die zugehörige [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.  
  
 `hConnected`  
 Das Windows-Handle der aktuellen Sitzung Internet.  
  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den FTP-Servernamen enthält.  
  
 `dwContext`  
 Die Kontext-ID für den Vorgang. `dwContext`identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Der Standardwert ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und die Arbeit ist, werden dieser Kontext-ID zugeordnet werden.  
  
 `pstrUserName`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers an, Anmeldung angibt. Wenn **NULL**, der Standardwert ist anonymous.  
  
 `pstrPassword`  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Kennwort für die Anmeldung verwenden. Wenn beide `pstrPassword` und `pstrUserName` sind **NULL**, das anonyme Standardkennwort lautet die e-Mail-Namen des Benutzers. Wenn `pstrPassword` ist **NULL** (oder eine leere Zeichenfolge), aber `pstrUserName` nicht **NULL**, ein leeres Kennwort verwendet wird. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der `pstrUserName` und `pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|FTP-Server gesendeten Benutzernamen|Kennwort zum FTP-Server gesendet wird.|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL** oder ""|**NULL** oder ""|"Anonym"|Die e-Mail-Namen des Benutzers|  
|Nicht- **NULL** Zeichenfolge|**NULL** oder ""|`pstrUserName`|" "|  
|**NULL** nicht **NULL** Zeichenfolge|**FEHLER**|**FEHLER**||  
|Nicht- **NULL** Zeichenfolge|Nicht- **NULL** Zeichenfolge|`pstrUserName`|`pstrPassword`|  
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port an, auf dem Server identifiziert.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CGopherConnection` direkt. Rufen Sie stattdessen [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), erstellt ein `CGopherConnection` -Objekt und gibt einen Zeiger darauf zurück.  
  
##  <a name="createlocator"></a>CGopherConnection:: CreateLocator  
 Rufen Sie diese Memberfunktion zum Erstellen oder eine Datei auf einem Gopherserver zu identifizieren.  
  
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
 `pstrDisplayString`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Gopher-Dokuments oder des Verzeichnisses abgerufen werden sollen. Wenn die `pstrDisplayString` Parameter ist **NULL**, wird das Standardverzeichnis für den Gopher-Server zurückgegeben.  
  
 `pstrSelectorString`  
 Ein Zeiger auf die Auswahlzeichenfolge Gopher-Server gesendet werden, um ein Element abgerufen werden. `pstrSelectorString`kann **NULL**.  
  
 *dwGopherType*  
 Dies gibt an, ob `pstrSelectorString` bezieht sich auf ein Verzeichnis oder ein Dokument, und ob die Anforderung Gopher oder Gopher ist. Finden Sie die Attribute für die Struktur [GOPHER_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa384215) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pstrLocator`  
 Ein Zeiger auf eine Zeichenfolge, die die zu öffnende Datei. Diese Zeichenfolge wird in der Regel durch einen Aufruf von zurückgegeben [CGopherFileFind:: GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).  
  
 *pstrServerName*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Gopher-Servers enthält.  
  
 `nPort`  
 Die Anzahl den Internet-Port für diese Verbindung identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die statische Version der Memberfunktion müssen Sie einen Server angeben, während die nicht statische Version den Servernamen aus dem Verbindungsobjekt verwendet.  
  
 Zum Abrufen von Informationen aus einem Gopher-Server muss eine Anwendung zunächst einen Gopher-Locator abrufen. Die Anwendung muss den Locator als nicht transparente Token behandeln (, die Anwendung kann den Locator verwenden jedoch nicht direkt bearbeiten oder vergleichen). In der Regel verwendet die Anwendung den Locator für Aufrufe an die [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) Member-Funktion, um eine bestimmte Information abzurufen.  
  
##  <a name="getattribute"></a>CGopherConnection::GetAttribute  
 Rufen Sie diese Memberfunktion, um spezifische Informationen über ein Element vom Gopher-Server abzurufen.  
  
```  
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,  
    CString& strResult,);
```  
  
### <a name="parameters"></a>Parameter  
 `refLocator`  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 *strRequestedAttributes*  
 Eine durch Leerzeichen getrennte Zeichenfolge die Namen der erforderlichen Attribute angeben.  
  
 `strResult`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) , empfängt den URL-Typ.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
##  <a name="openfile"></a>CGopherConnection:: OpenFile  
 Rufen Sie diese Memberfunktion zum Öffnen einer Datei auf einem Gopherserver.  
  
```  
CGopherFile* OpenFile(
    CGopherLocator& refLocator,  
    DWORD dwFlags = 0,  
    LPCTSTR pstrView = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `refLocator`  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 `dwFlags`  
 Eine beliebige Kombination von INTERNET_FLAG_ *-flags. Finden Sie unter [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) Weitere Informationen zu INTERNET_FLAG_\* Flags.  
  
 `pstrView`  
 Ein Zeiger auf eine Zeichenfolge für die Datei anzeigen. Wenn mehrere Ansichten der Datei auf dem Server vorhanden sind, gibt dieser Parameter die Dateiansicht zu öffnen. Wenn `pstrView` ist **NULL**, die Standardansicht für die Datei verwendet wird.  
  
 `dwContext`  
 Die Kontext-ID für die zu öffnende Datei. Finden Sie unter **Hinweise** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CGopherFile](../../mfc/reference/cgopherfile-class.md) Objekt geöffnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CGopherConnection` Objekt erstellt, indem die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpConnection-Klasse](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection-Klasse](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CGopherLocator-Klasse](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)

