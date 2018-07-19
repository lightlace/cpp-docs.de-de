---
title: CFtpFileFind-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8cf828ab0373c3bd09d22af5f2ced702cc68aa
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336018"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind-Klasse
Unterstützt die Internetsuche nach Dateien auf FTP-Servern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Erstellt ein `CFtpFileFind`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpFileFind:: FindFile](#findfile)|Sucht nach einer Datei auf einem FTP-Server.|  
|[CFtpFileFind:: FindNextFile](#findnextfile)|Weiterhin eine Dateisuche in einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CFtpFileFind::GetFileURL](#getfileurl)|Ruft die URL, einschließlich Pfad, der die gefundene Datei ab.|  
  
## <a name="remarks"></a>Hinweise  
 `CFtpFileFind` enthält die Member-Funktionen, die eine Suche zu starten, suchen Sie nach einer Datei und die URL oder sonstige beschreibende Informationen zu der Datei zurück.  
  
 Andere MFC-Klassen für Internet und die lokale Datei durchsucht enthalten [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). Zusammen mit `CFtpFileFind`, diese Klassen bieten einen nahtlose Mechanismus für den Client Dateien, die unabhängig von dem Server-Protokoll oder der Dateityp (einem lokalen Computer oder einem Remoteserver) gefunden. Beachten Sie, dass es keine MFC-Klasse ist für die Suche auf HTTP-Servern, da HTTP nicht die direkten Bearbeitung erforderlich, die für Suchvorgänge unterstützt.  
  
 Weitere Informationen zur Verwendung von `CFtpFileFind` und die andere WinInet-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie alle Dateien im aktuellen Verzeichnis des FTP-Servers aufgelistet werden.  
  
 [!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cftpfilefind"></a>  CFtpFileFind::CFtpFileFind  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CFtpFileFind` Objekt.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 *pConnection*  
 Ein Zeiger auf eine `CFtpConnection` Objekt. Sie erhalten eine FTP-Verbindung durch den Aufruf [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).  
  
 *dwContext*  
 Der Kontextbezeichner für den `CFtpFileFind` Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu diesem Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für *DwContext* wird gesendet, von MFC über die `CFtpFileFind` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) -Objekt, das erstellt die `CFtpFileFind` Objekt. Sie können die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt überschreiben. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zu Status für das Objekt mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel in der Übersicht über die Klasse weiter oben in diesem Thema.  
  
##  <a name="findfile"></a>  CFtpFileFind:: FindFile  
 Rufen Sie diese Memberfunktion, um eine FTP-Datei zu suchen.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des zu suchenden Datei. Wenn der Wert NULL ist, führt der Aufruf eine Suche mit Platzhalterzeichen (*).  
  
 *dwFlags*  
 Die Flags, die beschreibt, wie diese Sitzung behandelt. Diese Flags können mit dem bitweisen OR-Operator kombiniert werden (&#124;) und lauten wie folgt:  
  
-   INTERNET_FLAG_RELOAD rufen Sie Daten aus der Übertragung, auch wenn es lokal zwischengespeichert werden. Dies ist der Standard-Flag.  
  
-   INTERNET_FLAG_DONT_CACHE Zwischenspeichern nicht der Daten, entweder lokal oder in der Gateways.  
  
-   INTERNET_FLAG_RAW_DATA überschreiben die Standardeinstellung, um die unformatierten Daten zurückzugeben ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Strukturen für FTP).  
  
-   Sichert die INTERNET_FLAG_SECURE Transaktionen, bei der Übertragung mit Secure Sockets Layer "oder" Prozent Dieses Flag gilt nur für HTTP-Anforderungen.  
  
-   INTERNET_FLAG_EXISTING_CONNECT Wenn möglich, alle bestehenden Verbindungen mit dem Server wiederverwenden, für den neuen `FindFile` -Anforderungen und nicht das Erstellen einer neuen Sitzung für jede Anforderung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `FindFile` um die erste FTP-Datei abzurufen, können Sie aufrufen [FindNextFile](#findnextfile) nachfolgenden Dateien über FTP abrufen.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter dem früheren Beispiel in diesem Thema.  
  
##  <a name="findnextfile"></a>  CFtpFileFind:: FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortsetzen einer der Dateisuche begonnen, die mit einem Aufruf von der [FindFile](#findfile) Member-Funktion.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn weitere Dateien vorhanden sind; NULL, wenn die Datei im Verzeichnis das letzte ist oder ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn die Datei die letzte Datei im Verzeichnis ist, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` Funktionsergebnis ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion muss sich mindestens einmal, bevor Sie eine Attribut-Funktion aufrufen (siehe [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile` Dient als Wrapper für die Win32-Funktion [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel weiter oben in diesem Thema.  
  
##  <a name="getfileurl"></a>  CFtpFileFind::GetFileURL  
 Rufen Sie diese Memberfunktion zum Abrufen der URL der angegebenen Datei.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datei und der Pfad der Universal Resource Locator (URL).  
  
### <a name="remarks"></a>Hinweise  
 `GetFileURL` die Memberfunktion ähnelt [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), außer dass sie die URL im Format zurückgibt `ftp://moose/dir/file.txt`.  
  
## <a name="see-also"></a>Siehe auch  
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
