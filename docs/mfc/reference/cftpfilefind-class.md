---
title: CFtpFileFind Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFtpFileFind
dev_langs:
- C++
helpviewer_keywords:
- CFtpFileFind class
- file searches [C++]
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
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
ms.openlocfilehash: 6e84282cc2f22e813ea44318d497c7e32e3280d8
ms.lasthandoff: 02/24/2017

---
# <a name="cftpfilefind-class"></a>CFtpFileFind-Klasse
Unterstützt die Internetsuche nach Dateien auf FTP-Servern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFtpFileFind : public CFileFind  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Erstellt ein `CFtpFileFind`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFtpFileFind:: FindFile](#findfile)|Sucht nach einer Datei auf einem FTP-Server.|  
|[CFtpFileFind:: FindNextFile](#findnextfile)|Weiterhin eine Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CFtpFileFind::GetFileURL](#getfileurl)|Ruft die URL, einschließlich des Pfades, der die gefundene Datei ab.|  
  
## <a name="remarks"></a>Hinweise  
 `CFtpFileFind`enthält Funktionen, die eine Suche zu starten, suchen Sie nach einer Datei und die URL oder andere beschreibende Informationen über die Datei zurück.  
  
 Andere MFC-Klassen für Internet- und lokalen durchsucht werden [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). Zusammen mit `CFtpFileFind`, diese Klassen bieten einen nahtlosen Mechanismus für bestimmte Dateien, unabhängig von der Server-Protokoll oder der Dateityp (einem lokalen Computer oder einem Remoteserver) finden. Beachten Sie, dass keine MFC-Klasse für die Suche von HTTP-Servern, da HTTP die direkte Bearbeitung erforderlich, für die Suche nicht unterstützt.  
  
 Weitere Informationen zur Verwendung von `CFtpFileFind` und die anderen WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code veranschaulicht, wie alle Dateien im aktuellen Verzeichnis des FTP-Servers aufgelistet werden.  
  
 [!code-cpp[NVC_MFCWinInet&#8;](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CFtpFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="a-namecftpfilefinda--cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>CFtpFileFind::CFtpFileFind  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CFtpFileFind` Objekt.  
  
```  
explicit CFtpFileFind(
    CFtpConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `pConnection`  
 Ein Zeiger auf ein `CFtpConnection` Objekt. Sie erhalten eine FTP-Verbindung durch Aufrufen von [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).  
  
 `dwContext`  
 Der Kontextbezeichner für den `CFtpFileFind` Objekt. Finden Sie unter **Hinweise** für Weitere Informationen zu diesem Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für `dwContext` von MFC gesendet wird die `CFtpFileFind` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellten Objekt der `CFtpFileFind` Objekt. Sie können die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen, überschreiben. Die Kontext-ID wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Objekts bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel in der Übersicht über die Klasse weiter oben in diesem Thema.  
  
##  <a name="a-namefindfilea--cftpfilefindfindfile"></a><a name="findfile"></a>CFtpFileFind:: FindFile  
 Rufen Sie diese Memberfunktion, um eine FTP-Datei zu suchen.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der zu suchenden Datei. Wenn **NULL**, der Aufruf führt eine Suche mit Platzhalterzeichen (*).  
  
 `dwFlags`  
 Die Flags, die beschreiben, wie diese Sitzung zu behandeln. Diese Flags können mit dem bitweisen OR-Operator (|) kombiniert werden und lauten wie folgt:  
  
-   INTERNET_FLAG_RELOAD rufen Sie Daten aus der Übertragung, selbst wenn er lokal zwischengespeichert wird. Dies ist die Standardeinstellung.  
  
-   INTERNET_FLAG_DONT_CACHE sollten Sie die Daten nicht zwischengespeichert, entweder lokal oder im Gateways.  
  
-   INTERNET_FLAG_RAW_DATA überschreiben die Standardeinstellung die unformatierten Daten zurück ( [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Strukturen für FTP).  
  
-   Sichert die INTERNET_FLAG_SECURE Transaktionen bei der Übertragung mit Secure Sockets Layer oder Prozent Dieses Flag gilt nur für HTTP-Anforderungen.  
  
-   INTERNET_FLAG_EXISTING_CONNECT Wenn möglich, alle bestehenden Verbindungen mit dem Server für die neue wiederverwenden **FindFile** Anforderungen anstatt für jede Anforderung eine neue Sitzung erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von **FindFile** zum Abrufen der ersten FTP-Datei rufen Sie [FindNextFile](#findnextfile) nachfolgenden Dateien über FTP abrufen.  
  
### <a name="example"></a>Beispiel  
  Finden Sie im früheren Beispiel in diesem Thema.  
  
##  <a name="a-namefindnextfilea--cftpfilefindfindnextfile"></a><a name="findnextfile"></a>CFtpFileFind:: FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortsetzen des Vorgangs einer Dateisuche begann mit einem Aufruf der [FindFile](#findfile) Member-Funktion.  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn mehrere Dateien vorhanden sind;&0; (null), wenn die Datei im Verzeichnis der letzte ist oder ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn die Datei die letzte Datei im Verzeichnis ist, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` Funktion gibt ERROR_NO_MORE_FILES zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion muss mindestens einmal, bevor eine Attribut-Funktion aufrufen (siehe [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).  
  
 `FindNextFile`Dient als Wrapper für die Win32-Funktion [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel weiter oben in diesem Thema.  
  
##  <a name="a-namegetfileurla--cftpfilefindgetfileurl"></a><a name="getfileurl"></a>CFtpFileFind::GetFileURL  
 Rufen Sie diese Memberfunktion zum Abrufen der URL der angegebenen Datei.  
  
```  
CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Datei und der Pfad der Universal Resource Locator (URL).  
  
### <a name="remarks"></a>Hinweise  
 `GetFileURL`ist vergleichbar mit der Memberfunktion [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), außer dass sie die URL im Format zurückgibt `ftp://moose/dir/file.txt`.  
  
## <a name="see-also"></a>Siehe auch  
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)

