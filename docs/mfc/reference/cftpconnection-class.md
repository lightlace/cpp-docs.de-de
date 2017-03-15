---
title: CFtpConnection Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpConnection
dev_langs:
- C++
helpviewer_keywords:
- CFtpConnection class
- FTP (File Transfer Protocol), establishing connections
- Internet connections, FTP
- Internet services, FTP
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
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
ms.openlocfilehash: ebfe4078bf70d0afc2d36a222b61c11dbaf7c64d
ms.lasthandoff: 02/24/2017

---
# <a name="cftpconnection-class"></a>CFtpConnection-Klasse
Verwaltet die FTP-Verbindung mit einem Internetserver und ermöglicht die direkte Bearbeitung von Verzeichnissen und Dateien auf dem Server.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpConnection::CFtpConnection](#cftpconnection)|Erstellt ein `CFtpConnection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpConnection::Command](#command)|Sendet einen Befehl direkt an einen FTP-Server.|  
|[CFtpConnection::CreateDirectory](#createdirectory)|Erstellt ein Verzeichnis auf dem Server.|  
|[CFtpConnection:: GetCurrentDirectory](#getcurrentdirectory)|Ruft das aktuelle Verzeichnis für diese Verbindung.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl)|Ruft das aktuelle Verzeichnis für diese Verbindung als URL ab.|  
|[CFtpConnection::GetFile](#getfile)|Ruft eine Datei aus dem verbundenen server|  
|[CFtpConnection:: OpenFile](#openfile)|Öffnet eine Datei auf dem verbundenen Server.|  
|[CFtpConnection::PutFile](#putfile)|Speichert eine Datei auf dem Server.|  
|[CFtpConnection:: Remove](#remove)|Entfernt eine Datei vom Server.|  
|[CFtpConnection::RemoveDirectory](#removedirectory)|Entfernt das angegebene Verzeichnis auf dem Server.|  
|[CFtpConnection::Rename](#rename)|Benennt eine Datei auf dem Server.|  
|[CFtpConnection:: SetCurrentDirectory](#setcurrentdirectory)|Legt das aktuelle FTP-Verzeichnis fest.|  
  
## <a name="remarks"></a>Hinweise  
 FTP ist eines der drei Internetdienste erkannt werden, indem Sie die MFC-WinInet-Klassen.  
  
 Die Kommunikation mit einem FTP-IIS-Server müssen Sie zuerst eine Instanz erstellen [CInternetSession](../../mfc/reference/cinternetsession-class.md), und erstellen Sie ein `CFtpConnection` Objekt. Erstellen Sie nie eine `CFtpConnection` direkt, sondern rufen [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), erstellt das `CFtpConnection` -Objekt und gibt einen Zeiger darauf zurück.  
  
 Weitere Informationen zur Verwendung `CFtpConnection` arbeitet mit den anderen Internet MFC-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md). Weitere Informationen zur Kommunikation mit den anderen beiden unterstützten Dienste, HTTP und Gopher, finden Sie unter [CHttpConnection](../../mfc/reference/chttpconnection-class.md) und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## <a name="example"></a>Beispiel  
  Siehe das Beispiel in der [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) Übersicht über die Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CFtpConnection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="a-namecftpconnectiona--cftpconnectioncftpconnection"></a><a name="cftpconnection"></a>CFtpConnection::CFtpConnection  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CFtpConnection` Objekt.  
  
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
  
 `bPassive`  
 Gibt den passiven oder aktiven Modus für diese FTP-Sitzung an. Wenn auf festgelegt **TRUE**, wird die Win32-API- `dwFlag` auf **INTERNET_FLAG_PASSIVE**.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie nie eine `CFtpConnection` direkt. Rufen Sie stattdessen [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection), erstellt die **CFptConnection** Objekt.  
  
##  <a name="a-namecommanda--cftpconnectioncommand"></a><a name="command"></a>CFtpConnection::Command  
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
  
- **CmdRespRead** eine Antwort erwartet wird.  
  
 `dwFlags`  
 Ein Wert mit den Flags, die diese Funktion steuern. Eine vollständige Liste finden Sie unter [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133).  
  
 `dwContext`  
 Ein Zeiger auf einen Wert mit einem anwendungsdefinierten Wert, der zur Identifizierung des Anwendungskontexts in Rückrufen verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionalität der [FTPCommand](http://msdn.microsoft.com/library/windows/desktop/aa384133) Funktion, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn ein Fehler auftritt, löst MFC eine Ausnahme vom Typ [CInternetException](../../mfc/reference/cinternetexception-class.md).  
  
##  <a name="a-namecreatedirectorya--cftpconnectioncreatedirectory"></a><a name="createdirectory"></a>CFtpConnection::CreateDirectory  
 Rufen Sie diese Memberfunktion zum Erstellen eines Verzeichnisses auf dem verbundenen Server.  
  
```  
BOOL CreateDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Verzeichnisses, das erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Windows-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `GetCurrentDirectory` das aktuelle Arbeitsverzeichnis für die Verbindung mit dem Server zu bestimmen. Gehen Sie nicht davon aus, dass Sie das Remotesystem zum Root-Verzeichnis verbunden ist.  
  
 Die `pstrDirName` Parameter kann entweder eine teilweise oder vollständig qualifizierte Dateiname relativ zum aktuellen Verzeichnis. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `CreateDirectory`Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="a-namegetcurrentdirectorya--cftpconnectiongetcurrentdirectory"></a><a name="getcurrentdirectory"></a>CFtpConnection:: GetCurrentDirectory  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des aktuellen Verzeichnisses.  
  
```  
BOOL GetCurrentDirectory(CString& strDirName) const;  
  
BOOL GetCurrentDirectory(
    LPTSTR pstrDirName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strDirName`  
 Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten.  
  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten.  
  
 `lpdwLen`  
 Ein Zeiger auf ein DWORD, die folgende Informationen enthält:  
  
|||  
|-|-|  
|Auf Eintrag|Die Größe des Puffers auf die `pstrDirName`.|  
|Bei der Rückgabe|Die Anzahl der Zeichen, die gespeicherte `pstrDirName`. Wenn die Member-Funktion fehlschlägt und ERROR_INSUFFICIENT_BUFFER zurückgegeben wird, `lpdwLen` enthält die Anzahl der Bytes, die die Anwendung zugeordnet werden muss, um die Zeichenfolge zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Um den Namen des Verzeichnisses stattdessen als eine URL abzurufen, rufen [GetCurrentDirectoryAsURL](#getcurrentdirectoryasurl).  
  
 Die Parameter `pstrDirName` oder `strDirName` kann entweder teilweise qualifizierten Dateinamen relativ zum aktuellen Verzeichnis oder voll qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `GetCurrentDirectory`Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="a-namegetcurrentdirectoryasurla--cftpconnectiongetcurrentdirectoryasurl"></a><a name="getcurrentdirectoryasurl"></a>CFtpConnection::GetCurrentDirectoryAsURL  
 Rufen Sie diese Memberfunktion zum Abrufen des aktuellen Verzeichnisses namens als URL.  
  
```  
BOOL GetCurrentDirectoryAsURL(CString& strDirName) const;  
  
BOOL GetCurrentDirectoryAsURL(
    LPTSTR pstrName,  
    LPDWORD lpdwLen) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `strDirName`  
 Ein Verweis auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten.  
  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Verzeichnisses erhalten.  
  
 `lpdwLen`  
 Ein Zeiger auf ein DWORD, die folgende Informationen enthält:  
  
|||  
|-|-|  
|Auf Eintrag|Die Größe des Puffers auf die `pstrDirName`.|  
|Bei der Rückgabe|Die Anzahl der Zeichen, die gespeicherte `pstrDirName`. Wenn die Member-Funktion fehlschlägt und ERROR_INSUFFICIENT_BUFFER zurückgegeben wird, `lpdwLen` enthält die Anzahl der Bytes, die die Anwendung zugeordnet werden muss, um die Zeichenfolge zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `GetCurrentDirectoryAsURL`verhält sich wie [GetCurrentDirectory](#getcurrentdirectory)  
  
 Der Parameter `strDirName` kann entweder teilweise qualifizierten Dateinamen relativ zum aktuellen Verzeichnis oder voll qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `GetCurrentDirectoryAsURL`Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="a-namegetfilea--cftpconnectiongetfile"></a><a name="getfile"></a>CFtpConnection::GetFile  
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
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen der Datei, die vom FTP-Server abgerufen werden.  
  
 `pstrLocalFile`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namen der Datei auf dem lokalen System zu erstellen.  
  
 *bFailIfExists*  
 Gibt an, ob der Dateiname bereits von einer vorhandenen Datei verwendet werden kann. Wenn der lokale Dateiname bereits vorhanden ist, und dieser Parameter **TRUE**, `GetFile` ein Fehler auftritt. Andernfalls `GetFile` löscht die vorhandene Kopie der Datei.  
  
 `dwAttributes`  
 Gibt die Attribute der Datei. Dies kann eine beliebige Kombination der folgenden Flags FILE_ATTRIBUTE_ * sein.  
  
-   FILE_ATTRIBUTE_ARCHIVE die Datei ist eine Archivdatei. Clientanwendungen verwenden dieses Attribut zum Markieren von Dateien für die Sicherung oder Entfernung.  
  
-   FILE_ATTRIBUTE_COMPRESSED die Datei oder das Verzeichnis komprimiert wird. Für eine Datei also Komprimierung werden alle Daten in der Datei komprimiert. Für ein Verzeichnis ist wird die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse.  
  
-   FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.  
  
-   FILE_ATTRIBUTE_NORMAL die Datei verfügt über keine weiteren Attribute festgelegt. Dieses Attribut ist nur gültig, wenn allein verwendet. Alle anderen Dateiattribute überschreiben FILE_ATTRIBUTE_NORMAL:  
  
-   FILE_ATTRIBUTE_HIDDEN die Datei ist ausgeblendet. Es ist nicht in einer normalen Verzeichnisliste enthalten sein.  
  
-   FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Applikationen kann nicht lesen die Datei, aber in ihn schreiben oder löschen.  
  
-   FILE_ATTRIBUTE_SYSTEM die Datei gehört, oder wird ausschließlich durch das Betriebssystem verwendet.  
  
-   FILE_ATTRIBUTE_TEMPORARY die Datei wird für die temporäre Speicherung verwendet. Clientanwendungen sollten in die Datei geschrieben, wenn Sie nur, wenn es unbedingt erforderlich. Die meisten Daten der Datei verbleibt im Arbeitsspeicher, ohne auf den Datenträger geleert wird, da die Datei schnell gelöscht werden.  
  
 `dwFlags`  
 Gibt die Bedingung, unter denen die Übertragung auftritt. Dieser Parameter kann eine von der `dwFlags` Werte beschrieben, [FtpGetFile](http://msdn.microsoft.com/library/windows/desktop/aa384157) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwContext`  
 Der Kontextbezeichner für den Dateiabruf. Finden Sie unter **Hinweise** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `GetFile`ist eine allgemeine Routine, die alle von der Overhead beim Lesen einer Datei von einem FTP-Server, und speichern sie lokal verarbeitet. Clientanwendungen, die nur Daten abrufen, oder erfordern, dass schließen Kontrolle über die Übertragung von Dateien, zu verwendende `OpenFile` und [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) stattdessen.  
  
 Wenn `dwFlags` FILE_TRANSFER_TYPE_ASCII, Übersetzung von Dateidaten auch konvertiert Steuerelement und Formatieren von Zeichen, die Windows-Entsprechungen. Die Standard-Übertragung ist binären Modus, in dem die Datei in demselben Format heruntergeladen, auf dem Server gespeichert wird.  
  
 Beide `pstrRemoteFile` und `pstrLocalFile` kann entweder teilweise qualifizierten Dateinamen relativ zum aktuellen Verzeichnis oder voll qualifiziert. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `GetFile`Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CFtpConnection` Objekt erstellt, indem die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="a-nameopenfilea--cftpconnectionopenfile"></a><a name="openfile"></a>CFtpConnection:: OpenFile  
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
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Datei geöffnet werden.  
  
 *dwAccess*  
 Bestimmt, wie die Datei zugegriffen werden soll. Entweder GENERIC_READ oder GENERIC_WRITE, jedoch nicht beides kann sein.  
  
 `dwFlags`  
 Gibt die Bedingungen, unter denen nachfolgenden Übertragungen auftreten. Dies kann eine der folgenden FTP_TRANSFER_ *-Konstanten sein:  
  
-   FTP_TRANSFER_TYPE_ASCII die Datei überträgt mithilfe von FTP-ASCII (Typ A)-Übertragungsmethode. Steuerelement konvertiert und Formatierungsinformationen für lokalen Entsprechungen.  
  
-   FTP_TRANSFER_TYPE_BINARY die Datei Übertragung von Daten mithilfe der Methode zur Datenübertragung bei Bild (Typ I). Die Datei überträgt Daten genauso wie mit keine Änderungen vorhanden ist. Dies ist die Standardmethode für die Übertragung.  
  
 `dwContext`  
 Die Kontext-ID zum Öffnen der Datei. Finden Sie unter **Hinweise** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CInternetFile](../../mfc/reference/cinternetfile-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 `OpenFile`sollte in den folgenden Situationen verwendet werden:  
  
-   Eine Anwendung kann Daten, die gesendet und als Datei auf dem FTP-Server erstellt werden soll, aber, dass keine Daten in einer lokalen Datei. Einmal `OpenFile` öffnet eine Datei, verwendet die Anwendung [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write) die FTP-Daten an den Server zu senden.  
  
-   Eine Anwendung muss eine Datei vom Server ab und platzieren Sie es in den anwendungsgesteuerte Speicher statt auf den Datenträger geschrieben. Die Anwendung verwendet [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read) nach der Verwendung `OpenFile` zum Öffnen der Datei.  
  
-   Eine Anwendung benötigt hochgradige Kontrolle über eine Übertragung von Dateien. Die Anwendung kann z. B. zum Anzeigen einer Statusanzeige zeigt an, dass den Fortschritt der Übertragung den Status der Datei beim Herunterladen einer Datei.  
  
 Nach dem Aufruf von `OpenFile` und bis zum Aufruf von **CInternetConnection::Close**, die Anwendung kann nur aufrufen [CInternetFile:: Read](../../mfc/reference/cinternetfile-class.md#read), [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write), **CInternetConnection::Close**, oder [CFtpFileFind:: FindFile](../../mfc/reference/cftpfilefind-class.md#findfile). Aufrufe von anderen FTP-Funktionen für die gleiche FTP-Sitzung werden fehlschlagen und den Fehlercode auf FTP_ETRANSFER_IN_PROGRESS festgelegt.  
  
 Die `pstrFileName` Parameter kann entweder einen teilweise qualifizierten Dateinamen relativ zum aktuellen Verzeichnis oder vollständig qualifiziert sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `OpenFile`übersetzt Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen vor der Verwendung.  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CFtpConnection` Objekt erstellt, indem die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="a-nameputfilea--cftpconnectionputfile"></a><a name="putfile"></a>CFtpConnection::PutFile  
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
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der Datei auf dem FTP-Server erstellen.  
  
 `dwFlags`  
 Gibt die Bedingung, unter denen die Übertragung der Datei auftritt. Kann eine der in beschriebenen FTP_TRANSFER_ *-Konstanten [OpenFile](#openfile).  
  
 `dwContext`  
 Der Kontextbezeichner für die Platzierung der das. Finden Sie unter **Hinweise** Weitere Informationen zu `dwContext`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 `PutFile`ist eine allgemeine Routine, die alle Vorgänge zugeordnet, das Speichern einer Datei auf einem FTP-Server behandelt. Clientanwendungen, die nur Daten senden, oder erfordern, dass eine bessere Kontrolle über die Übertragung von Dateien, verwenden sollten [OpenFile](#openfile) und [CInternetFile:: Write](../../mfc/reference/cinternetfile-class.md#write).  
  
 Überschreiben Sie den `dwContext`-Standard, um den Kontextbezeichner auf einen ausgewählten Wert festzulegen. Der Kontextbezeichner wird diesem bestimmten Vorgang des zugeordneten der `CFtpConnection` Objekt erstellt, indem die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt. Der Wert wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Vorgangs bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="a-nameremovea--cftpconnectionremove"></a><a name="remove"></a>CFtpConnection:: Remove  
 Rufen Sie diese Memberfunktion zum Löschen der angegebenen Datei aus dem verbundenen Server.  
  
```  
BOOL Remove(LPCTSTR pstrFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrFileName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die `pstrFileName` Parameter kann entweder einen teilweise qualifizierten Dateinamen relativ zum aktuellen Verzeichnis oder vollständig qualifiziert sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. Die **entfernen** Funktion Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="a-nameremovedirectorya--cftpconnectionremovedirectory"></a><a name="removedirectory"></a>CFtpConnection::RemoveDirectory  
 Rufen Sie diese Memberfunktion, um das angegebene Verzeichnis aus dem verbundenen Server zu entfernen.  
  
```  
BOOL RemoveDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Verzeichnis entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [GetCurrentDirectory](#getcurrentdirectory) zum aktuellen Arbeitsverzeichnis des Servers zu bestimmen. Gehen Sie nicht davon aus, dass Sie das Remotesystem zum Root-Verzeichnis verbunden ist.  
  
 Die `pstrDirName` Parameter kann entweder eine teilweise oder vollständig qualifizierte Dateiname relativ zum aktuellen Verzeichnis. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `RemoveDirectory`Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="a-namerenamea--cftpconnectionrename"></a><a name="rename"></a>CFtpConnection::Rename  
 Rufen Sie diese Memberfunktion zum Umbenennen der angegebenen Datei auf dem verbundenen Server.  
  
```  
BOOL Rename(
    LPCTSTR pstrExisting,  
    LPCTSTR pstrNew);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrExisting`  
 Ein Zeiger auf eine Zeichenfolge mit den aktuellen Namen der Datei, die umbenannt werden soll.  
  
 `pstrNew`  
 Ein Zeiger auf eine Zeichenfolge mit dem neuen Dateinamen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die `pstrExisting` und `pstrNew` Parameter können entweder einen teilweise qualifizierten Dateinamen relativ zum aktuellen Verzeichnis oder vollständig qualifiziert sein. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. **Benennen Sie** Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
##  <a name="a-namesetcurrentdirectorya--cftpconnectionsetcurrentdirectory"></a><a name="setcurrentdirectory"></a>CFtpConnection:: SetCurrentDirectory  
 Rufen Sie diese Memberfunktion, in einem anderen Verzeichnis auf dem FTP-Server zu ändern.  
  
```  
BOOL SetCurrentDirectory(LPCTSTR pstrDirName);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrDirName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des Verzeichnisses.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Wenn der Aufruf fehlschlägt, die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) aufgerufen werden, um die Ursache des Fehlers zu ermitteln.  
  
### <a name="remarks"></a>Hinweise  
 Die `pstrDirName` Parameter kann entweder eine teilweise oder vollständig qualifizierte Dateiname relativ zum aktuellen Verzeichnis. Ein umgekehrter Schrägstrich (\\) oder einen Schrägstrich (/) als Verzeichnistrennzeichen entweder ein verwendet werden kann. `SetCurrentDirectory`Verzeichnistrennzeichen Namen auf die entsprechenden Zeichen übersetzt, bevor sie verwendet werden.  
  
 Verwendung [GetCurrentDirectory](#getcurrentdirectory) zum aktuellen Arbeitsverzeichnis in einem FTP-Server zu ermitteln. Gehen Sie nicht davon aus, dass Sie das Remotesystem zum Root-Verzeichnis verbunden ist.  
  
## <a name="see-also"></a>Siehe auch  
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CInternetConnection-Klasse](../../mfc/reference/cinternetconnection-class.md)   
 [CInternetSession-Klasse](../../mfc/reference/cinternetsession-class.md)

