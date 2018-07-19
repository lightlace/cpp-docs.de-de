---
title: CFtpConnection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFtpConnection
- AFXINET/CFtpConnection
- AFXINET/CFtpConnection::CFtpConnection
- AFXINET/CFtpConnection::Command
- AFXINET/CFtpConnection::CreateDirectory
- AFXINET/CFtpConnection::GetCurrentDirectory
- AFXINET/CFtpConnection::GetCurrentDirectoryAsURL
- AFXINET/CFtpConnection::GetFile
- AFXINET/CFtpConnection::OpenFile
- AFXINET/CFtpConnection::PutFile
- AFXINET/CFtpConnection::Remove
- AFXINET/CFtpConnection::RemoveDirectory
- AFXINET/CFtpConnection::Rename
- AFXINET/CFtpConnection::SetCurrentDirectory
dev_langs:
- C++
helpviewer_keywords:
- CFtpConnection [MFC], CFtpConnection
- CFtpConnection [MFC], Command
- CFtpConnection [MFC], CreateDirectory
- CFtpConnection [MFC], GetCurrentDirectory
- CFtpConnection [MFC], GetCurrentDirectoryAsURL
- CFtpConnection [MFC], GetFile
- CFtpConnection [MFC], OpenFile
- CFtpConnection [MFC], PutFile
- CFtpConnection [MFC], Remove
- CFtpConnection [MFC], RemoveDirectory
- CFtpConnection [MFC], Rename
- CFtpConnection [MFC], SetCurrentDirectory
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5e0c902b9de9ea4d742d96b88f86d47231597f7
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337332"
---
# <a name="cftpconnection-class"></a>CFtpConnection-Klasse
Verwaltet die FTP-Verbindung mit einem Internetserver und ermöglicht die direkte Bearbeitung von Verzeichnissen und Dateien auf dem Server.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|Erstellt ein `CFtpConnection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|Sendet einen Befehl direkt an einen FTP-Server.|  
|[CFtpConnection::CreateDirectory](#createdirectory)|Erstellt ein Verzeichnis auf dem Server.|  
|[CFtpConnection:: GetCurrentDirectory](#getcurrentdirectory)|Ruft das aktuelle Verzeichnis für diese Verbindung ab.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Ruft das aktuelle Verzeichnis für diese Verbindung als URL ab.|  
|[CFtpConnection::GetFile](#getfile)|Ruft eine Datei aus dem verbundenen Server ab.|  
|[CFtpConnection:: OpenFile](#openfile)|Öffnet eine Datei auf dem verbundenen Server.|  
|[CFtpConnection::PutFile](#putfile)|Fügt eine Datei auf dem Server.|  
|[CFtpConnection:: Remove](#remove)|Entfernt eine Datei vom Server an.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|Entfernt das angegebene Verzeichnis auf dem Server.|  
|[CFtpConnection::Rename](#rename)|Benennt eine Datei auf dem Server.|  
|[CFtpConnection:: SetCurrentDirectory](#setcurrentdirectory)|Legt das aktuelle FTP-Verzeichnis fest.|  
  
## <a name="remarks"></a>Hinweise  
 FTP ist eines der drei Internetdienste erkannt, die von den MFC-WinInet-Klassen.  
  
 Mit einem FTP-IIS-Server kommunizieren kann, müssen Sie zuerst eine Instanz von erstellen [CInternetSession](../../mfc/reference/cinternetsession-class.md), und erstellen Sie eine `CFtpConnection` Objekt. Erstellen Sie nie eine `CFtpConnection` direkt, sondern rufen [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), erstellt die `CFtpConnection` Objekt und gibt einen Zeiger darauf zurück.  
  
 Weitere Informationen finden Sie `CFtpConnection` funktioniert mit den anderen Internet von MFC-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen über die Kommunikation mit den anderen beiden unterstützten Dienste, HTTP und Gopher, finden Sie unter den Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## <a name="example"></a>Beispiel  
  Siehe das Beispiel in der [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) Übersicht über die Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cftpconnection"></a>  CFtpConnection::CFtpConnection  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CFtpConnection` Objekt.  
  
```  
CFtpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CFtpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 0,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    BOOL bPassive = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *pSession*  
 Ein Zeiger auf den zugehörigen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.  
  
 *hConnected*  
 Das Windows-Handle von der aktuellen Internet-Sitzung.  
  
 *pstrServer*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des FTP-Server.  
  
 *dwContext*  
 Der Kontextbezeichner für den Vorgang. *DwContext* identifiziert des Vorgangs der vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Der Standardwert ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und Arbeit ist, werden diese Kontext-ID zugeordnet werden.  
  
 *pstrUserName*  
 Zeiger auf eine auf Null endende Zeichenfolge, die den Namen des Benutzers für die Anmeldung angibt. Wenn der Wert NULL ist, ist die Standardeinstellung anonym.  
  
 *pstrPassword*  
 Ein Zeiger auf eine auf Null endende Zeichenfolge, die das Kennwort für die Anmeldung angibt. Wenn beide *PstrPassword* und *PstrUserName* NULL sind, die das anonymen Standard-Kennwort wird den e-Mail-Adresse des Benutzers. Wenn *PstrPassword* ist NULL (oder eine leere Zeichenfolge), aber *PstrUserName* ist nicht NULL ist, wird ein leeres Kennwort verwendet. Die folgende Tabelle beschreibt das Verhalten für die vier möglichen Einstellungen der *PstrUserName* und *PstrPassword*:  
  
|*pstrUserName*|*pstrPassword*|FTP-Server gesendeten Benutzernamen|Kennwort für FTP-Server gesendet wird.|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|NULL oder ""|NULL oder ""|"Anonym"|Die e-Mail-Adresse des Benutzers|  
|Nicht-NULL-Zeichenfolge|NULL oder ""|*pstrUserName*|" "|  
|NULL-nicht-NULL-Zeichenfolge|FEHLER|FEHLER||  
|Nicht-NULL-Zeichenfolge|Nicht-NULL-Zeichenfolge|*pstrUserName*|*pstrPassword*|  
  
 *%nPort*  
 Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.  
  
 *bPassive*  
 Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn Sie auf "true" festgelegt, die Win32-API wird *DwFlag* zu INTERNET_FLAG_PASSIVE.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CFtpConnection` direkt. Rufen Sie stattdessen [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), erstellt die `CFptConnection` Objekt.  
  
##  <a name="command"></a>  CFtpConnection::Command  
 Sendet einen Befehl direkt an einen FTP-Server.  
  
```  
CInternetFile* Command(
    LPCTSTR pszCommand,  
    CmdResponseType eResponse = CmdRespNone,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *pszCommand*  
 Ein Zeiger auf eine Zeichenfolge, die den zu sendenden Befehl enthält.  
  
 *eResponse*  
 Bestimmt, ob eine Antwort vom FTP-Server erwartet wird. Kann einer der folgenden Werte sein:  
  
- `CmdRespNone` Es wird keine Antwort erwartet.  
  
- `CmdRespRead` Es wird eine Antwort erwartet.  
  
 *dwFlags*  
 Ein Wert mit den Flags, die diese Funktion steuern. Eine vollständige Liste finden Sie unter [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133).  
  
 *dwContext*  
 Ein Zeiger auf einen Wert mit einem anwendungsdefinierten Wert, der zur Identifizierung des Anwendungskontexts in Rückrufen verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) Funktion, wie im Windows SDK beschrieben.  
  
 Wenn ein Fehler auftritt, löst MFC eine Ausnahme vom Typ [CInternetException](../../mfc/reference/cinternetexception-class.md).  
  
##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory  
 Rufen Sie diese Memberfunktion zum Erstellen eines Verzeichnisses auf dem verbundenen Server.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrDirName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Verzeichnisses, das erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Windows-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `GetCurrentDirectory` um das aktuelle Arbeitsverzeichnis für diese Verbindung an den Server zu ermitteln. Gehen Sie nicht, dass Sie das Remotesystem in das Stammverzeichnis verbunden ist.  
  
 Die `pstrDirName` Parameter kann es sich um eine teilweise oder ein vollqualifizierter Dateiname relativ zum aktuellen Verzeichnis. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `CreateDirectory` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="getcurrentdirectory"></a>  CFtpConnection:: GetCurrentDirectory  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des aktuellen Verzeichnisses.  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *strDirName*  
 Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten sollen.  
  
 *pstrDirName*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten sollen.  
  
 *lpdwLen*  
 Ein Zeiger auf ein DWORD, die folgende Informationen enthält:  
  
|||  
|-|-|  
|Auf Eintrag|Die Größe des Puffers verweist *PstrDirName*.|  
|Bei der Rückgabe|Die Anzahl der Zeichen gespeichert, um *PstrDirName*. Wenn die Member-Funktion ein Fehler auftritt und ERROR_INSUFFICIENT_BUFFER, klicken Sie dann zurückgegeben wird *LpdwLen* enthält die Anzahl der Bytes, die die Anwendung reserviert werden muss, um die Zeichenfolge zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Um den Namen des Verzeichnisses stattdessen als eine URL zu erhalten, rufen [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).  
  
 Die Parameter *PstrDirName* oder *StrDirName* kann entweder teilweise qualifizierten Dateinamen, relativ zum aktuellen Verzeichnis oder voll qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `GetCurrentDirectory` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="getcurrentdirectoryasurl"></a>  CFtpConnection::GetCurrentDirectoryAsURL  
 Rufen Sie diese Memberfunktion um den aktuellen Namen des Verzeichnisses als URL zu erhalten.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *strDirName*  
 Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten sollen.  
  
 *pstrDirName*  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten sollen.  
  
 *lpdwLen*  
 Ein Zeiger auf ein DWORD, die folgende Informationen enthält:  
  
|||  
|-|-|  
|Auf Eintrag|Die Größe des Puffers verweist *PstrDirName*.|  
|Bei der Rückgabe|Die Anzahl der Zeichen gespeichert, um *PstrDirName*. Wenn die Member-Funktion ein Fehler auftritt und ERROR_INSUFFICIENT_BUFFER, klicken Sie dann zurückgegeben wird *LpdwLen* enthält die Anzahl der Bytes, die die Anwendung reserviert werden muss, um die Zeichenfolge zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `GetCurrentDirectoryAsURL` verhält sich wie [GetCurrentDirectory](#getcurrentdirectory)  
  
 Der Parameter *StrDirName* kann entweder teilweise qualifizierten Dateinamen, relativ zum aktuellen Verzeichnis oder voll qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `GetCurrentDirectoryAsURL` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="getfile"></a>  CFtpConnection::GetFile  
 Rufen Sie diese Memberfunktion zum Abrufen einer Datei von einem FTP-Server und auf dem lokalen Computer zu speichern.  
  
```  
BOOL GetFile(
    LPCTSTR pstrRemoteFile,  
    LPCTSTR pstrLocalFile,  
    BOOL bFailIfExists = TRUE,  
    DWORD dwAttributes = FILE_ATTRIBUTE_NORMAL,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrRemoteFile*  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen einer Datei vom FTP-Server abgerufen.  
  
 *pstrLocalFile*  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge, die mit dem Namen der Datei, die auf dem lokalen System erstellt.  
  
 *bFailIfExists*  
 Gibt an, ob der Dateiname bereits von einer vorhandenen Datei verwendet werden kann. Wenn der Name der lokalen Datei bereits vorhanden ist, und dieser Parameter ist "true", `GetFile` ein Fehler auftritt. Andernfalls `GetFile` wird die vorhandene Kopie der Datei zu löschen.  
  
 *dwAttributes*  
 Gibt die Attribute der Datei an. Dies kann eine beliebige Kombination der folgenden FILE_ATTRIBUTE_ * Flags sein.  
  
-   FILE_ATTRIBUTE_ARCHIVE die Datei ist eine Archivdatei. Anwendungen verwenden Sie dieses Attribut zum Markieren von Dateien für die Sicherung oder zum Entfernen.  
  
-   FILE_ATTRIBUTE_COMPRESSED Datei oder des Verzeichnisses werden komprimiert. Bei einer Datei also Komprimierung aller Daten in der Datei komprimiert wird. Für ein Verzeichnis ist die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse.  
  
-   FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.  
  
-   FILE_ATTRIBUTE_NORMAL die Datei verfügt über keine anderen Attribute festgelegt. Dieses Attribut ist nur gültig, wenn allein verwendet wird. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL:  
  
-   FILE_ATTRIBUTE_HIDDEN die Datei ist ausgeblendet. Es ist nicht in einer normalen Verzeichnisliste enthalten sein.  
  
-   FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Anwendungen kann nicht lesen die Datei, aber in ihn schreiben oder löschen.  
  
-   FILE_ATTRIBUTE_SYSTEM, die Datei gehört, oder wird ausschließlich durch das Betriebssystem verwendet.  
  
-   FILE_ATTRIBUTE_TEMPORARY die Datei wird für die temporäre Speicherung verwendet. Anwendungen sollten in die Datei schreiben, der nur, wenn es unbedingt erforderlich ist. Die meisten der die Daten der Datei verbleibt im Arbeitsspeicher, ohne auf die Medien geleert werden, da die Datei wird bald gelöscht werden.  
  
 *dwFlags*  
 Gibt die Bedingungen, unter denen die Übertragung erfolgt. Dieser Parameter kann sein, eines der *DwFlags* Werte, die in beschriebenen [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) im Windows SDK.  
  
 *dwContext*  
 Der Kontextbezeichner für den Dateiabruf. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `GetFile` ist eine Routine auf oberster Ebene, die alle der Overhead beim Lesen einer Datei aus einem FTP-Server, und speichern es lokal verarbeitet. Anwendungen, die nur Daten abzurufen, oder schließen Kontrolle über die Dateiübertragung erfordern, sollten verwenden `OpenFile` und [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) stattdessen.  
  
 Wenn *DwFlags* FILE_TRANSFER_TYPE_ASCII, Übersetzung von Dateidaten auch konvertiert Steuerelement und Formatieren von Zeichen in Windows-Entsprechungen. Die Standard-Übertragung ist binären Modus, in dem die Datei im gleichen Format heruntergeladen, auf dem Server gespeichert werden.  
  
 Beide *PstrRemoteFile* und *PstrLocalFile* kann entweder teilweise qualifizierten Dateinamen, relativ zum aktuellen Verzeichnis oder voll qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `GetFile` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
 Überschreiben der *DwContext* standardmäßig den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordnet der `CFtpConnection` von erstelltes Objekt seine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Vorgangs bereitzustellen mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.  
  
##  <a name="openfile"></a>  CFtpConnection:: OpenFile  
 Rufen Sie diese Memberfunktion zum Öffnen einer Datei befindet sich auf einem FTP-Server zum Lesen oder schreiben.  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrFileName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Datei, die geöffnet werden.  
  
 *dwAccess*  
 Bestimmt, wie die Datei zugegriffen werden soll. Entweder GENERIC_READ oder GENERIC_WRITE, jedoch nicht beides kann sein.  
  
 *dwFlags*  
 Gibt die Bedingungen, unter denen nachfolgende Übertragungen auftreten. Dies kann eine der folgenden FTP_TRANSFER_ *-Konstanten sein:  
  
-   FTP_TRANSFER_TYPE_ASCII der Datei werden übertragen, mit der Übertragungsmethode für FTP-ASCII (Typ A). Konvertiert-Steuerelement und Formatierungsinformationen für die lokalen Entsprechungen.  
  
-   FTP_TRANSFER_TYPE_BINARY der Datei überträgt Daten, die mit der Übertragungsmethode bei Image (Typ I). Die Datei überträgt Daten genau wie vorhanden ist, ohne Änderungen. Dies ist die Standardmethode für die Übertragung.  
  
 *dwContext*  
 Der Kontextbezeichner für die Datei zu öffnen. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CInternetFile](../../mfc/reference/cinternetfile-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `OpenFile` sollte in den folgenden Situationen verwendet werden:  
  
-   Eine Anwendung kann Daten, die jedoch, dass keine Daten in einer lokalen Datei gesendet und als Datei auf dem FTP-Server erstellt werden müssen. Einmal `OpenFile` öffnet eine Datei, die Anwendung verwendet [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write) auf die Daten einer FTP-Datei an den Server gesendet.  
  
-   Eine Anwendung muss eine Datei vom Server abzurufen, und platzieren Sie sie in der Anwendung gesteuert Arbeitsspeicher, anstatt auf den Datenträger geschrieben. Die Anwendung verwendet [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) nach der Verwendung von `OpenFile` zum Öffnen der Datei.  
  
-   Eine Anwendung benötigt eine hochgradige Kontrolle über die Dateiübertragung. Die Anwendung kann z. B. einen Fortschritt angezeigt zeigt an, dass der Status, der den dateiübertragungsstatus beim Herunterladen einer Datei.  
  
 Nach dem Aufruf `OpenFile` und bis zum Aufruf `CInternetConnection::Close`, die Anwendung kann nur aufrufen [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write), `CInternetConnection::Close`, oder [ CFtpFileFind:: FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Aufrufe von anderen FTP-Funktionen für die gleiche FTP-Sitzung fehl und den Fehlercode auf FTP_ETRANSFER_IN_PROGRESS festgelegt.  
  
 Die *PstrFileName* Parameter kann entweder einen teilweise qualifizierten Dateinamen in das aktuelle Verzeichnis relativen oder vollqualifizierten sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `OpenFile` übersetzt die Name-Verzeichnistrennzeichen in die entsprechenden Zeichen vor der Verwendung.  
  
 Überschreiben der *DwContext* standardmäßig den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordnet der `CFtpConnection` von erstelltes Objekt seine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Vorgangs bereitzustellen mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.  
  
##  <a name="putfile"></a>  CFtpConnection::PutFile  
 Rufen Sie diese Memberfunktion zum Speichern einer Datei auf einem FTP-Server.  
  
```  
BOOL PutFile(
    LPCTSTR pstrLocalFile,  
    LPCTSTR pstrRemoteFile,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrLocalFile*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Datei, die aus dem lokalen System zu senden.  
  
 *pstrRemoteFile*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Datei, die auf dem FTP-Server zu erstellen.  
  
 *dwFlags*  
 Gibt die Bedingungen, unter denen die Übertragung der Datei erfolgt. Die FTP_TRANSFER_ *-Konstanten, die in beschriebenen möglich [OpenFile](#openfile).  
  
 *dwContext*  
 Der Kontextbezeichner für die Platzierung der das. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `PutFile` ist eine Routine auf oberster Ebene, die vollständig von der Operationen, die für das Speichern einer Datei auf einem FTP-Server übernommen wird. Anwendungen, die nur Daten senden, oder erfordern eine bessere Kontrolle über die Dateiübertragung, sollten verwenden [OpenFile](#openfile) und [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write).  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordnet der `CFtpConnection` von erstelltes Objekt seine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Vorgangs bereitzustellen mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.  
  
##  <a name="remove"></a>  CFtpConnection:: Remove  
 Rufen Sie diese Memberfunktion, um die angegebene Datei aus dem verbundenen Server zu löschen.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrFileName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Dateinamen entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die *PstrFileName* Parameter kann entweder einen teilweise qualifizierten Dateinamen in das aktuelle Verzeichnis relativen oder vollqualifizierten sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. Die `Remove` Funktion Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory  
 Rufen Sie diese Memberfunktion, um das angegebene Verzeichnis aus dem verbundenen Server zu entfernen.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrDirName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Verzeichnis entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [GetCurrentDirectory](#getcurrentdirectory) zum aktuellen Verzeichnis des Servers zu bestimmen. Gehen Sie nicht, dass Sie das Remotesystem in das Stammverzeichnis verbunden ist.  
  
 Die *PstrDirName* Parameter kann entweder ein Teil- oder vollqualifizierter Dateiname relativ zum aktuellen Verzeichnis sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `RemoveDirectory` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="rename"></a>  CFtpConnection::Rename  
 Rufen Sie diese Memberfunktion zum Umbenennen der angegebenen Datei auf dem verbundenen Server.  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrExisting*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem aktuellen Namen der Datei, die umbenannt werden.  
  
 *pstrNew*  
 Ein Zeiger auf eine Zeichenfolge mit dem neuen Dateinamen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die *PstrExisting* und *PstrNew* Parameter können entweder einen teilweise qualifizierten Dateinamen in das aktuelle Verzeichnis relativen oder vollqualifizierten sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `Rename` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="setcurrentdirectory"></a>  CFtpConnection:: SetCurrentDirectory  
 Rufen Sie diese Memberfunktion so ändern Sie in einem anderen Verzeichnis auf dem FTP-Server.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrDirName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Verzeichnisses.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die *PstrDirName* Parameter kann entweder ein Teil- oder vollqualifizierter Dateiname relativ zum aktuellen Verzeichnis sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als das Verzeichnistrennzeichen entweder Namen verwendet werden kann. `SetCurrentDirectory` Verzeichnistrennzeichen Namen in die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
 Verwendung [GetCurrentDirectory](#getcurrentdirectory) zum aktuellen Arbeitsverzeichnis in einem FTP-Server zu ermitteln. Gehen Sie nicht, dass Sie das Remotesystem in das Stammverzeichnis verbunden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)
