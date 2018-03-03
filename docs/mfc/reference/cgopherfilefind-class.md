---
title: CGopherFileFind Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6133fc593cb2fc53dfb7b6498711ae32713a4731
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind-Klasse
Unterstützt die Internetsuche nach Dateien auf Gopherservern.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da sie nicht auf Windows XP-Plattform funktionieren, jedoch wird auf älteren Plattformen funktionieren weiterhin.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Erstellt ein `CGopherFileFind`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherFileFind:: FindFile](#findfile)|Sucht nach einer Datei auf einem Gopherserver.|  
|[CGopherFileFind:: FindNextFile](#findnextfile)|Weiterhin eine Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Ruft den Zeitpunkt der Erstellung die angegebene Datei ab.|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei.|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Ruft die Uhrzeit der letzten auf die angegebene Datei Schreibzugriffs ab.|  
|[CGopherFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei, in Bytes ab.|  
|[CGopherFileFind:: GetLocator](#getlocator)|Abrufen einer `CGopherLocator` Objekt.|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Ruft den Namen eines Bildschirms Gopher ab.|  
|[CGopherFileFind::IsDots](#isdots)|Testet, ob die aktuelle Marker eines Verzeichnisses und übergeordnetes Verzeichnis beim Durchlaufen von Dateien.|  
  
## <a name="remarks"></a>Hinweise  
 `CGopherFileFind`enthält die Memberfunktionen, die eine Suche zu starten, suchen Sie nach einer Datei und Rückgabe-URL für eine Datei.  
  
 Andere MFC-Steuerelementklassen entwickelt für Internet und der lokalen Datei, die durchsucht werden [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). Zusammen mit `CGopherFileFind`, diese Klassen bieten einen nahtlosen Mechanismus für den Benutzer zu bestimmten Dateien unabhängig von den Serverprotokoll, Dateityp oder Speicherort (einem lokalen Computer oder einem Remoteserver.) Beachten Sie, dass keine MFC-Klasse für die Suche auf HTTP-Servern, da HTTP die direkte Bearbeitung erforderlich, suchen nicht unterstützt.  
  
> [!NOTE]
> `CGopherFileFind`unterstützt nicht die folgenden Memberfunktionen ihrer Basisklasse [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 Darüber hinaus bei Verwendung mit `CGopherFileFind`, `CFileFind` Memberfunktion [IsDots](../../mfc/reference/cfilefind-class.md#isdots) ist immer **"false"**.  
  
 Weitere Informationen zur Verwendung von `CGopherFileFind` und die anderen WinInet-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>CGopherFileFind::CGopherFileFind  
 Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherFileFind` Objekt.  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `pConnection`  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.  
  
 `dwContext`  
 Der Kontextbezeichner für den Vorgang. Finden Sie unter **"Hinweise"** Weitere Informationen zu `dwContext`.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für `dwContext` wird gesendet, von MFC ermöglicht, die `CGopherFileFind` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellte Objekt die `CGopherFileFind` Objekt. Bei der Erstellung einer `CGopherFileFind` -Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Objekts bereitzustellen, mit denen es identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="findfile"></a>CGopherFileFind:: FindFile  
 Rufen Sie diese Memberfunktion, um einen Gopherdatei zu suchen.  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>Parameter  
 `refLocator`  
 Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.  
  
 *pstrString*  
 Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält.  
  
 `dwFlags`  
 Die Flags, die beschreiben, wie diese Sitzung zu behandeln. Die gültigen Flags sind:  
  
-   INTERNET_FLAG_RELOAD rufen Sie Daten vom Remoteserver, auch wenn diese lokal zwischengespeichert wird.  
  
-   INTERNET_FLAG_DONT_CACHE sollten Sie die Daten nicht zwischengespeichert, entweder lokal oder in Gateways.  
  
-   Sichere Transaktionen bei der Übertragung mit Secure Sockets Layer "oder" Prozent INTERNET_FLAG_SECURE anfordern Dieses Flag gilt nur für HTTP-Anforderungen zur Verfügung.  
  
-   Wiederverwenden, INTERNET_FLAG_USE_EXISTING Wenn möglich, alle bestehenden Verbindungen mit dem Server für das neue **FindFile** Anforderungen, anstatt eine neue Sitzung für jede Anforderung erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf **FindFile** um das erste Gopher-Objekt abzurufen, rufen Sie [FindNextFile](#findnextfile) nachfolgende Gopher-Dateien abzurufen.  
  
##  <a name="findnextfile"></a>CGopherFileFind:: FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortfahren einer Dateisuche begonnen, die mit einem Aufruf von [CGopherFileFind:: FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn mehrere Dateien vorhanden sind; 0 (null) ist die gefundene Datei das letzte Lesezeichen im Verzeichnis, oder wenn ein Fehler aufgetreten. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn der Dateiname der gefundenen Datei ist die letzte Datei im Verzeichnis, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` -Funktion gibt ERROR_NO_MORE_FILES zurück.  
  
##  <a name="getcreationtime"></a>CGopherFileFind::GetCreationTime  
 Ruft den Zeitpunkt der Erstellung für die aktuelle Datei ab.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pTimeStamp`  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, enthält die Uhrzeit der dateierstellung.  
  
 `refTime`  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetCreationTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) nie aufgerufen wurde für dieses `CGopherFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetCreationTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder dem Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen Zeitformate. Bei einigen Betriebssystemen ist die zurückgegebene Zeit in der Zeit, die Zone lokal auf dem Computer wurden, dass die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
##  <a name="getlastaccesstime"></a>CGopherFileFind::GetLastAccessTime  
 Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `refTime`  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
 `pTimeStamp`  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, enthält die Zeit, die auf die Datei zuletzt zugegriffen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastAccessTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) nie aufgerufen wurde für dieses `CGopherFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastAccessTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder dem Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen Zeitformate. Bei einigen Betriebssystemen ist die zurückgegebene Zeit in der Zeit, die Zone lokal auf dem Computer wurden, dass die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
##  <a name="getlastwritetime"></a>CGopherFileFind::GetLastWriteTime  
 Ruft ab der letzten Ausführung der Datei geändert wurde.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pTimeStamp`  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, die die Zeit, die die Datei letzten in Schreibvorgangs enthält.  
  
 `refTime`  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastWriteTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) nie aufgerufen wurde für dieses `CGopherFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastWriteTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder dem Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen Zeitformate. Bei einigen Betriebssystemen ist die zurückgegebene Zeit in der Zeit, die Zone lokal auf dem Computer wurden, dass die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
##  <a name="getlength"></a>CGopherFileFind::GetLength  
 Rufen Sie diese Memberfunktion, um die Länge in Bytes, die gefundene Datei abrufen.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der gefundenen Datei in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 `GetLength`verwendet die Win32-Struktur [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) auf den Wert der Dateigröße in Bytes abrufen.  
  
> [!NOTE]
>  Ab MFC 7.0 `GetLength` unterstützt 64-Bit-Ganzzahl-Typen. Abschneiden Warnungen möglicherweise zuvor vorhandenen Code mit dieser neueren Version der Bibliothek erstellt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (Implementierung der Basisklasse).  
  
##  <a name="getlocator"></a>CGopherFileFind:: GetLocator  
 Rufen Sie diese Memberfunktion zum Abrufen der [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt, mit [FindFile](#findfile) verwendet, um die Gopherdatei zu suchen.  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CGopherLocator`-Objekt.  
  
##  <a name="getscreenname"></a>CGopherFileFind::GetScreenName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Bildschirms Gopher.  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des Bildschirms Gopher.  
  
##  <a name="isdots"></a>CGopherFileFind::IsDots  
 Testet, ob die aktuelle Marker eines Verzeichnisses und übergeordnetes Verzeichnis beim Durchlaufen von Dateien.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, verfügt die gefundene Datei den Namen "."oder"..", was bedeutet, dass die gefundene Datei um ein Verzeichnis ist. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsDots`.  
  
## <a name="see-also"></a>Siehe auch  
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
