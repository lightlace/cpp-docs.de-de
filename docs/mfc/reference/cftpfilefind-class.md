---
title: CFtpFileFind Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4fe3b188d5b03c9e727349b9e30982cf52006c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CFtpFileFind:: FindNextFile](#findnextfile)|Weiterhin eine Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CFtpFileFind::GetFileURL](#getfileurl)|Ruft die URL, einschließlich Pfad, der gefundenen Datei ab.|  
  
## <a name="remarks"></a>Hinweise  
 `CFtpFileFind`enthält die Memberfunktionen, die eine Suche zu starten, suchen Sie nach einer Datei und gibt die URL oder sonstige beschreibende Informationen über die Datei.  
  
 Andere MFC-Steuerelementklassen entwickelt für Internet und der lokalen Datei, die durchsucht werden [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). Zusammen mit `CFtpFileFind`, diese Klassen bieten einen nahtlosen Mechanismus für den Client mithilfe der Softwareoption bestimmte Dateien unabhängig von dem Server-Protokoll oder der Dateityp (einem lokalen Computer oder einem Remoteserver). Beachten Sie, dass keine MFC-Klasse für die Suche auf HTTP-Servern, da HTTP die direkte Bearbeitung erforderlich für die Suche nicht unterstützt.  
  
 Weitere Informationen zur Verwendung von `CFtpFileFind` und die anderen WinInet-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht, wie alle Dateien im aktuellen Verzeichnis des FTP-Servers aufgelistet werden.  
  
 [!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CFtpFileFind` Objekt.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `pConnection`  
 Ein Zeiger auf eine `CFtpConnection` Objekt. Erhalten Sie eine FTP-Verbindung durch Aufrufen von [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).  
  
 `dwContext`  
 Der Kontextbezeichner für den `CFtpFileFind` Objekt. Finden Sie unter **"Hinweise"** für Weitere Informationen zu diesem Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für `dwContext` wird gesendet, von MFC ermöglicht, die `CFtpFileFind` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellte Objekt die `CFtpFileFind` Objekt. Sie können die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen überschreiben. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Objekts bereitzustellen, mit denen es identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel in der Übersicht zur Klasse weiter oben in diesem Thema.  
  
##  <a name="findfile"></a>CFtpFileFind:: FindFile  
 Rufen Sie diese Memberfunktion, um eine FTP-Datei zu suchen.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des zu suchenden Datei. Wenn **NULL**, Ausführen des Aufrufs eine Suche mit Platzhalterzeichen (*).  
  
 `dwFlags`  
 Die Flags, die beschreiben, wie diese Sitzung zu behandeln. Diese Flags können kombiniert werden, mit dem bitweisen OR-Operator (&#124;) und lauten wie folgt:  
  
-   INTERNET_FLAG_RELOAD rufen Sie Daten aus der Übertragung, auch wenn diese lokal zwischengespeichert wird. Dies ist das Standardflag.  
  
-   INTERNET_FLAG_DONT_CACHE sollten Sie die Daten nicht zwischengespeichert, entweder lokal oder in Gateways.  
  
-   INTERNET_FLAG_RAW_DATA überschreiben die Standardeinstellung die unformatierten Daten zurück ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Strukturen für FTP).  
  
-   Sichert die INTERNET_FLAG_SECURE Transaktionen, bei der Übertragung mit Secure Sockets Layer "oder" Prozent Dieses Flag gilt nur für HTTP-Anforderungen zur Verfügung.  
  
-   Wiederverwenden, INTERNET_FLAG_EXISTING_CONNECT Wenn möglich, alle bestehenden Verbindungen mit dem Server für das neue **FindFile** Anforderungen und nicht für jede Anforderung eine neue Sitzung erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf **FindFile** zum Abrufen der ersten FTP-Datei können Sie aufrufen [FindNextFile](#findnextfile) nachfolgenden Dateien über FTP abrufen.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter dem oben aufgeführten Beispiel in diesem Thema.  
  
##  <a name="findnextfile"></a>CFtpFileFind:: FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortfahren einer Dateisuche begonnen, die durch einen Aufruf der [FindFile](#findfile) Memberfunktion.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn mehrere Dateien vorhanden sind; 0 (null) ist die gefundene Datei das letzte Lesezeichen im Verzeichnis, oder wenn ein Fehler aufgetreten. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn der Dateiname der gefundenen Datei ist die letzte Datei im Verzeichnis, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` -Funktion gibt ERROR_NO_MORE_FILES zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion muss mindestens einmal, bevor Sie eine Attribut-Funktion aufrufen (siehe [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile`Dient als Wrapper für die Win32-Funktion [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel weiter oben in diesem Thema.  
  
##  <a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 Rufen Sie diese Memberfunktion, um die URL der angegebenen Datei zu erhalten.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datei und der Pfad der Universal Resource Locator (URL).  
  
### <a name="remarks"></a>Hinweise  
 `GetFileURL`die Memberfunktion gleicht [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), außer dass sie die URL im Format zurückgibt `ftp://moose/dir/file.txt`.  
  
## <a name="see-also"></a>Siehe auch  
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
