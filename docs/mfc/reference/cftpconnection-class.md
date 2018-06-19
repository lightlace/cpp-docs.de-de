---
title: CFtpConnection Klasse | Microsoft Docs
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
ms.openlocfilehash: f43df1cb610c785688db982be2ddc4a19cf140b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374535"
---
# <a name="cftpconnection-class"></a>CFtpConnection-Klasse
Verwaltet die FTP-Verbindung mit einem Internetserver und ermöglicht die direkte Bearbeitung von Verzeichnissen und Dateien auf diesem Server.  
  
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
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Ruft das aktuelle Verzeichnis für diese Verbindung als URL verwendet wird.|  
|[CFtpConnection::GetFile](#getfile)|Ruft eine Datei aus dem verbundenen Server ab.|  
|[CFtpConnection:: OpenFile](#openfile)|Öffnet eine Datei auf dem verbundenen Server.|  
|[CFtpConnection::PutFile](#putfile)|Fügt eine Datei auf dem Server.|  
|[CFtpConnection:: Remove](#remove)|Entfernt eine Datei vom Server an.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|Entfernt das angegebene Verzeichnis vom Server an.|  
|[CFtpConnection::Rename](#rename)|Benennt eine Datei auf dem Server.|  
|[CFtpConnection:: SetCurrentDirectory](#setcurrentdirectory)|Legt das aktuelle FTP-Verzeichnis fest.|  
  
## <a name="remarks"></a>Hinweise  
 FTP ist eines der drei Internetdienste erkannt, durch die MFC-WinInet-Klassen.  
  
 Die Kommunikation mit einem FTP-IIS-Server müssen Sie zunächst eine Instanz von erstellen [CInternetSession](../../mfc/reference/cinternetsession-class.md), und erstellen Sie eine `CFtpConnection` Objekt. Erstellen Sie nie eine `CFtpConnection` -Objekts direkt, sondern rufen [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), erstellt die `CFtpConnection` -Objekt und gibt einen Zeiger darauf zurück.  
  
 Erfahren Sie mehr darüber, wie `CFtpConnection` funktioniert mit anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zur Kommunikation mit den anderen beiden unterstützten Dienste, HTTP und Gopher, finden Sie in den Klassen [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## <a name="example"></a>Beispiel  
  Siehe das Beispiel in der [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) -Klassenübersicht.  
  
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
 `pSession`  
 Ein Zeiger auf den zugehörigen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.  
  
 `hConnected`  
 Das Windows-handle von der aktuellen Internet-Sitzung.  
  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des FTP-Server enthält.  
  
 `dwContext`  
 Der Kontextbezeichner für den Vorgang. `dwContext` identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Die Standardeinstellung ist auf 1 festgelegt. Allerdings können Sie eine bestimmten Kontext-ID für den Vorgang explizit zuweisen. Das Objekt und jede Arbeit, die es ausführt, werden dieser Kontext-ID zugeordnet werden.  
  
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
  
 `nPort`  
 Eine Zahl, die TCP/IP-Port für die Verwendung auf dem Server identifiziert.  
  
 `bPassive`  
 Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn auf festgelegt **"true"**, wird die Win32-API `dwFlag` auf **INTERNET_FLAG_PASSIVE**.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CFtpConnection` -Objekts direkt. Rufen Sie stattdessen [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), erstellt der **CFptConnection** Objekt.  
  
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
 `pszCommand`  
 Ein Zeiger auf eine Zeichenfolge, die den zu sendenden Befehl enthält.  
  
 *eResponse*  
 Bestimmt, ob eine Antwort vom FTP-Server erwartet wird. Kann einer der folgenden Werte sein:  
  
- **CmdRespNone** wird keine Antwort erwartet.  
  
- **CmdRespRead** eine Antwort wird erwartet.  
  
 `dwFlags`  
 Ein Wert mit den Flags, die diese Funktion steuern. Eine vollständige Liste finden Sie unter [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133).  
  
 `dwContext`  
 Ein Zeiger auf einen Wert mit einem anwendungsdefinierten Wert, der zur Identifizierung des Anwendungskontexts in Rückrufen verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) -Funktion wie auch in das Windows SDK beschrieben.  
  
 Wenn ein Fehler auftritt, löst MFC eine Ausnahme vom Typ [CInternetException](../../mfc/reference/cinternetexception-class.md).  
  
##  <a name="createdirectory"></a>  CFtpConnection::CreateDirectory  
 Rufen Sie diese Memberfunktion zum Erstellen eines Verzeichnisses auf dem verbundenen Server.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Verzeichnisses erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Windows-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `GetCurrentDirectory` zum Bestimmen des aktuellen Arbeitsverzeichnisses für diese Verbindung mit dem Server. Gehen Sie nicht, dass das Remotesystem in das Stammverzeichnis hergestellt hat.  
  
 Die `pstrDirName` Parameter kann es sich um eine teilweise oder vollständig qualifizierte Dateiname relativ zum aktuellen Verzeichnis. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `CreateDirectory` Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="getcurrentdirectory"></a>  CFtpConnection:: GetCurrentDirectory  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des aktuellen Verzeichnisses.  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strDirName`  
 Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses empfangen wird.  
  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses empfangen wird.  
  
 `lpdwLen`  
 Ein Zeiger auf ein DWORD, die folgende Informationen enthält:  
  
|||  
|-|-|  
|Auf Eintrag|Die Größe des Puffers verweist `pstrDirName`.|  
|Bei der Rückgabe|Die Anzahl der Zeichen gespeichert, damit eine `pstrDirName`. Wenn die Memberfunktion ein Fehler auftritt und ERROR_INSUFFICIENT_BUFFER wird, klicken Sie dann zurückgegeben `lpdwLen` enthält die Anzahl der Bytes, die die Anwendung zuweisen muss, um die Zeichenfolge zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Um den Namen des Verzeichnisses stattdessen als eine URL abzurufen, rufen [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).  
  
 Die Parameter `pstrDirName` oder `strDirName` kann entweder teilweise gekennzeichneten Dateinamen relativ zum aktuellen Verzeichnis oder vollständig qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `GetCurrentDirectory` Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="getcurrentdirectoryasurl"></a>  CFtpConnection::GetCurrentDirectoryAsURL  
 Rufen Sie diese Memberfunktion zum Abrufen des aktuellen Verzeichnisses namens als URL verwendet wird.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strDirName`  
 Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses empfangen wird.  
  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses empfangen wird.  
  
 `lpdwLen`  
 Ein Zeiger auf ein DWORD, die folgende Informationen enthält:  
  
|||  
|-|-|  
|Auf Eintrag|Die Größe des Puffers verweist `pstrDirName`.|  
|Bei der Rückgabe|Die Anzahl der Zeichen gespeichert, damit eine `pstrDirName`. Wenn die Memberfunktion ein Fehler auftritt und ERROR_INSUFFICIENT_BUFFER wird, klicken Sie dann zurückgegeben `lpdwLen` enthält die Anzahl der Bytes, die die Anwendung zuweisen muss, um die Zeichenfolge zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `GetCurrentDirectoryAsURL` verhält sich wie [GetCurrentDirectory](#getcurrentdirectory)  
  
 Der Parameter `strDirName` kann entweder teilweise gekennzeichneten Dateinamen relativ zum aktuellen Verzeichnis oder vollständig qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `GetCurrentDirectoryAsURL` Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="getfile"></a>  CFtpConnection::GetFile  
 Rufen Sie diese Memberfunktion zum Abrufen einer Datei von einem FTP-Server und auf dem lokalen Computer speichern.  
  
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
 `pstrRemoteFile`  
 Ein Zeiger auf einen Null-terminierte Zeichenfolge, die mit dem Namen einer Datei vom FTP-Server abgerufen.  
  
 `pstrLocalFile`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge, die mit dem Namen der Datei, die auf dem lokalen System erstellt.  
  
 *bFailIfExists*  
 Gibt an, ob der Dateiname bereits von einer vorhandenen Datei verwendet werden kann. Name der lokalen Datei bereits vorhanden ist und dieser Parameter ist **"true"**, `GetFile` ein Fehler auftritt. Andernfalls `GetFile` löscht die vorhandene Kopie der Datei.  
  
 `dwAttributes`  
 Gibt die Attribute der Datei an. Dies kann eine beliebige Kombination der folgenden Flags FILE_ATTRIBUTE_ * sein.  
  
-   FILE_ATTRIBUTE_ARCHIVE die Datei ist eine Archivdatei. Anwendungen verwenden Sie dieses Attribut zum Kennzeichnen von Dateien für die Sicherung oder entfernen.  
  
-   FILE_ATTRIBUTE_COMPRESSED die Datei oder das Verzeichnis komprimiert wird. Für eine Datei bedeutet Komprimierung an, dass alle Daten in der Datei komprimiert wird. Für ein Verzeichnis ist wird die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse.  
  
-   FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.  
  
-   FILE_ATTRIBUTE_NORMAL die Datei verfügt über keine anderen Attribute festgelegt. Dieses Attribut ist nur gültig, wenn isoliert verwendet. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL:  
  
-   FILE_ATTRIBUTE_HIDDEN die Datei wird ausgeblendet. Es ist nicht in einer normalen Verzeichnisliste enthalten sein.  
  
-   FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Anwendungen können sie lesen Sie die Datei aber kann nicht in ihn schreiben oder löschen.  
  
-   FILE_ATTRIBUTE_SYSTEM die Datei ist Teil oder ausschließlich vom Betriebssystem verwendet wird.  
  
-   FILE_ATTRIBUTE_TEMPORARY die Datei wird für die temporäre Speicherung verwendet. Anwendungen sollten in die Datei schreiben, der nur, wenn dies absolut notwendig ist. Die meisten Daten der Datei verbleibt im Arbeitsspeicher, ohne auf den Datenträger geleert werden, da die Datei bald gelöscht wird.  
  
 `dwFlags`  
 Gibt die Bedingungen, unter denen die Übertragung erfolgt. Dieser Parameter kann eine von der `dwFlags` Werte, die in beschriebenen [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) im Windows SDK.  
  
 `dwContext`  
 Der Kontextbezeichner für den Dateiabruf. Finden Sie unter **"Hinweise"** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `GetFile` ist eine allgemeine Routine, die vollständig von den Mehrbedarf in Verbindung mit dem Lesen einer Datei von einem FTP-Server und lokal speichern. Anwendungen, die nur Dateidaten abzurufen, oder, erfordern schließen Kontrolle über die Übertragung von Dateien, die zu verwendende `OpenFile` und [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) stattdessen.  
  
 Wenn `dwFlags` FILE_TRANSFER_TYPE_ASCII, Übersetzung von Dateidaten auch konvertiert-Steuerelement und Formatieren von Zeichen, die Windows-Entsprechungen. Die Standard-Übertragung ist binären Modus, in dem die Datei im gleichen Format heruntergeladen, auf dem Server gespeichert werden.  
  
 Beide `pstrRemoteFile` und `pstrLocalFile` kann entweder teilweise gekennzeichneten Dateinamen relativ zum aktuellen Verzeichnis oder vollständig qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `GetFile` Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CFtpConnection` Objekt erstellt wird, dessen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="openfile"></a>  CFtpConnection:: OpenFile  
 Rufen Sie diese Memberfunktion zum Öffnen einer Datei auf einem FTP-Server zum Lesen oder schreiben.  
  
```  
CInternetFile* OpenFile(
    LPCTSTR pstrFileName,  
    DWORD dwAccess = GENERIC_READ,  
    DWORD dwFlags = FTP_TRANSFER_TYPE_BINARY,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrFileName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen der Datei geöffnet werden.  
  
 *dwAccess*  
 Bestimmt, wie die Datei zugegriffen werden soll. Hierbei kann es sich um GENERIC_READ oder GENERIC_WRITE, aber nicht beides sein.  
  
 `dwFlags`  
 Gibt die Bedingungen, unter denen nachfolgenden Übertragungen auftreten. Dies kann eine der folgenden FTP_TRANSFER_ * Konstanten sein:  
  
-   FTP_TRANSFER_TYPE_ASCII Datei überträgt Übertragungsmethode FTP ASCII (Typ A) verwenden. Konvertiert-Steuerelement und Formatierungsinformationen für lokale Entsprechungen.  
  
-   FTP_TRANSFER_TYPE_BINARY Datei Übertragung von Daten mithilfe der Übertragungsmethode FTP's-Image (Typ I). Die Datei überträgt Daten genau wie vorhanden ist, ohne Änderungen. Dies ist die Standardmethode für die Übertragung.  
  
 `dwContext`  
 Der Kontextbezeichner für die Datei zu öffnen. Finden Sie unter **"Hinweise"** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CInternetFile](../../mfc/reference/cinternetfile-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `OpenFile` sollte in den folgenden Situationen verwendet werden:  
  
-   Eine Anwendung muss Daten, die jedoch, dass keine Daten in einer lokalen Datei gesendet und als Datei auf dem FTP-Server erstellt werden müssen. Einmal `OpenFile` öffnet eine Datei, die der Anwendung verwendeten [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write) auf die Daten einer FTP-Datei an den Server gesendet.  
  
-   Eine Anwendung muss eine Datei vom Server ab und platzieren Sie es in den Arbeitsspeicher Anwendung gesteuert, statt sie auf den Datenträger geschrieben. Die Anwendung verwendet [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) nach der Verwendung `OpenFile` zum Öffnen der Datei.  
  
-   Eine Anwendung erfordert eine gut Maß an Kontrolle über eine Übertragung von Dateien. Die Anwendung kann z. B. auf einer Fortschrittsanzeige verfolgen, Steuerelement den Status der Datei Übertragungsstatus beim Herunterladen einer Datei anzugeben.  
  
 Nach dem Aufruf `OpenFile` und bis zum Aufruf von **CInternetConnection::Close**, die Anwendung kann nur aufrufen [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write), **CInternetConnection::Close**, oder [CFtpFileFind:: FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Aufrufe von anderen FTP-Funktionen für die gleiche FTP-Sitzung werden fehlschlagen, und legen den Fehlercode auf FTP_ETRANSFER_IN_PROGRESS.  
  
 Die `pstrFileName` Parameter kann entweder ein teilweise qualifizierte Dateiname relativ zum aktuellen Verzeichnis oder einen vollqualifizierten sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `OpenFile` übersetzt Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen vor der Verwendung.  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CFtpConnection` Objekt erstellt wird, dessen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
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
 `pstrLocalFile`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Datei, die aus dem lokalen System gesendet.  
  
 `pstrRemoteFile`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Datei, die auf dem FTP-Server erstellt.  
  
 `dwFlags`  
 Gibt die Bedingungen, unter denen die Übertragung der Datei auftritt. Die FTP_TRANSFER_ *-Konstanten, die in beschriebenen möglich [OpenFile](#openfile).  
  
 `dwContext`  
 Der Kontextbezeichner für die Platzierung der das. Finden Sie unter **"Hinweise"** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `PutFile` ist eine allgemeine Routine, die alle Vorgänge, die Speichern einer Datei auf einem FTP-Server zugeordneten behandelt. Anwendungen, die nur Daten senden, oder erfordern genauere Kontrolle über die Übertragung von Dateien, die zu verwendende [OpenFile](#openfile) und [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write).  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CFtpConnection` Objekt erstellt wird, dessen [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="remove"></a>  CFtpConnection:: Remove  
 Rufen Sie diese Memberfunktion, um die angegebene Datei aus dem verbundenen Server zu löschen.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrFileName`  
 Ein Zeiger auf eine Zeichenfolge, enthält den Dateinamen zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die `pstrFileName` Parameter kann entweder ein teilweise qualifizierte Dateiname relativ zum aktuellen Verzeichnis oder einen vollqualifizierten sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. Die **entfernen** Funktion Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="removedirectory"></a>  CFtpConnection::RemoveDirectory  
 Rufen Sie diese Memberfunktion, um das angegebene Verzeichnis aus dem verbundenen Server zu entfernen.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Verzeichnis entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [GetCurrentDirectory](#getcurrentdirectory) zum aktuellen Arbeitsverzeichnis des Servers zu bestimmen. Gehen Sie nicht, dass das Remotesystem in das Stammverzeichnis hergestellt hat.  
  
 Die `pstrDirName` Parameter kann entweder ein teilweise oder vollständig qualifizierte Dateiname relativ zum aktuellen Verzeichnis sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `RemoveDirectory` Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="rename"></a>  CFtpConnection::Rename  
 Rufen Sie diese Memberfunktion, um die angegebene Datei auf dem verbundenen Server umzubenennen.  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrExisting`  
 Ein Zeiger auf eine Zeichenfolge mit den aktuellen Namen der Datei, die umbenannt werden soll.  
  
 `pstrNew`  
 Ein Zeiger auf eine Zeichenfolge, die den neuen Dateinamen enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die `pstrExisting` und `pstrNew` Parameter können entweder einen teilweise qualifizierte Dateiname relativ zum aktuellen Verzeichnis oder einen vollqualifizierten sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. **Benennen Sie** Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="setcurrentdirectory"></a>  CFtpConnection:: SetCurrentDirectory  
 Rufen Sie diese Memberfunktion auf, in einem anderen Verzeichnis auf dem FTP-Server zu ändern.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des Verzeichnisses.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden kann, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die `pstrDirName` Parameter kann entweder ein teilweise oder vollständig qualifizierte Dateiname relativ zum aktuellen Verzeichnis sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen für die beiden Namen verwendet werden kann. `SetCurrentDirectory` Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
 Verwendung [GetCurrentDirectory](#getcurrentdirectory) zum aktuellen Arbeitsverzeichnis eine FTP-Server zu ermitteln. Gehen Sie nicht, dass das Remotesystem in das Stammverzeichnis hergestellt hat.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)
