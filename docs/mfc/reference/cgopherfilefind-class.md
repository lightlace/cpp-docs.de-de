---
title: CGopherFileFind Klasse | Microsoft-Dokumentation
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
- CGopherFileFind class
- file searches [C++]
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 93f30e83369ad1bff7222f26d0782eed11e73f66
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfilefind-class"></a>CGopherFileFind-Klasse
Unterstützt die Internetsuche nach Dateien auf Gopherservern.  
  
> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und ihre Member sind veraltet, da nicht unter Windows XP funktionieren, aber sie werden weiterhin auf frühere Plattformen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Erstellt ein `CGopherFileFind`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CGopherFileFind:: FindFile](#findfile)|Eine Datei auf einem Gopherserver findet.|  
|[CGopherFileFind:: FindNextFile](#findnextfile)|Weiterhin eine Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Ruft den Erstellungszeitpunkt die angegebene Datei ab.|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei.|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Ruft die Zeit, der die angegebene Datei zuletzt in geschrieben wurde.|  
|[CGopherFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei in Bytes ab.|  
|[CGopherFileFind:: GetLocator](#getlocator)|Abrufen einer `CGopherLocator` Objekt.|  
|[CGopherFileFind::GetScreenName](#getscreenname)|Ruft den Namen eines Bildschirms Gopher.|  
|[CGopherFileFind::IsDots](#isdots)|Tests für die aktuellen Verzeichnis und übergeordneten Verzeichnis-Marker, beim Durchlaufen von Dateien.|  
  
## <a name="remarks"></a>Hinweise  
 `CGopherFileFind`Memberfunktionen, die eine Suche zu starten, suchen Sie nach einer Datei und Rückgabe-URL einer Datei umfasst.  
  
 Andere MFC-Klassen für Internet- und lokalen durchsucht werden [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). Zusammen mit `CGopherFileFind`, diese Klassen bieten einen nahtlosen Mechanismus für die Benutzer bestimmte Dateien, unabhängig von der Server-Protokoll, Dateityp oder Speicherort (einem lokalen Computer oder einem remote-Server.) Beachten Sie, dass keine MFC-Klasse für die Suche von HTTP-Servern, da HTTP die direkte Bearbeitung erforderlich, die für Suchvorgänge nicht unterstützt.  
  
> [!NOTE]
> `CGopherFileFind`unterstützt nicht die folgenden Memberfunktionen der Basisklasse [CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 Darüber hinaus mit `CGopherFileFind`, `CFileFind` Memberfunktion [IsDots](../../mfc/reference/cfilefind-class.md#isdots) ist immer **FALSE**.  
  
 Weitere Informationen zur Verwendung von `CGopherFileFind` und die anderen WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cgopherfilefind"></a>CGopherFileFind::CGopherFileFind  
 Diese Member-Funktion wird aufgerufen, um das Erstellen einer `CGopherFileFind` Objekt.  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `pConnection`  
 Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.  
  
 `dwContext`  
 Die Kontext-ID für den Vorgang. Finden Sie unter **Hinweise** Weitere Informationen zu `dwContext`.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardwert für `dwContext` von MFC gesendet wird die `CGopherFileFind` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellten Objekt der `CGopherFileFind` Objekt. Bei der Erstellung einer `CGopherFileFind` -Objekt, Sie können die Standardeinstellung auf einen Wert Ihrer Wahl die Kontext-ID festgelegt. Die Kontext-ID wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Objekts bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
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
 Die Flags, die beschreiben, wie diese Sitzung zu behandeln. Gültige Flags sind:  
  
-   INTERNET_FLAG_RELOAD Daten vom remote-Server abrufen, auch wenn er lokal zwischengespeichert wird.  
  
-   INTERNET_FLAG_DONT_CACHE sollten Sie die Daten nicht zwischengespeichert, entweder lokal oder im Gateways.  
  
-   Sichere Transaktionen bei der Übertragung mit Secure Sockets Layer oder Prozent INTERNET_FLAG_SECURE anfordern Dieses Flag gilt nur für HTTP-Anforderungen.  
  
-   INTERNET_FLAG_USE_EXISTING Wenn möglich, alle bestehenden Verbindungen mit dem Server für die neue wiederverwenden **FindFile** Anforderungen, statt für jede Anforderung eine neue Sitzung erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von **FindFile** um das erste Gopher-Objekt abzurufen, rufen Sie [FindNextFile](#findnextfile) nachfolgende Gopher-Dateien abzurufen.  
  
##  <a name="findnextfile"></a>CGopherFileFind:: FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortsetzen des Vorgangs einer Dateisuche begann mit einem Aufruf von [CGopherFileFind:: FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn mehrere Dateien vorhanden sind;&0; (null), wenn die Datei im Verzeichnis der letzte ist oder ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn die Datei die letzte Datei im Verzeichnis ist, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` Funktion gibt ERROR_NO_MORE_FILES zurück.  
  
##  <a name="getcreationtime"></a>CGopherFileFind::GetCreationTime  
 Ruft die Erstellungszeit für die aktuelle Datei ab.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pTimeStamp`  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, enthält die Zeit, die die Datei erstellt wurde.  
  
 `refTime`  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetCreationTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, auf diesem `CGopherFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetCreationTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen über Zeitformate. Bei einigen Betriebssystemen ist die zurückgegebene Zeit in der Zone lokal auf dem Computer wurden, dass sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
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
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, die die Zeit der letzten Zugriff auf die Datei enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastAccessTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, auf diesem `CGopherFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetLastAccessTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen über Zeitformate. Bei einigen Betriebssystemen ist die zurückgegebene Zeit in der Zone lokal auf dem Computer wurden, dass sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
##  <a name="getlastwritetime"></a>CGopherFileFind::GetLastWriteTime  
 Ruft ab der letzten Ausführung der Datei geändert wurde.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pTimeStamp`  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, enthält die Datei zum letzten geschrieben wurde.  
  
 `refTime`  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastWriteTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, auf diesem `CGopherFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetLastWriteTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen über Zeitformate. Bei einigen Betriebssystemen ist die zurückgegebene Zeit in der Zone lokal auf dem Computer wurden, dass sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
##  <a name="getlength"></a>CGopherFileFind::GetLength  
 Rufen Sie diese Memberfunktion, um die Länge in Bytes, die gefundene Datei abrufen.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der gefundenen Datei in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 `GetLength`verwendet die Win32-Struktur [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) nutzen die Dateigröße in Bytes.  
  
> [!NOTE]
>  Ab MFC 7.0 `GetLength` unterstützt 64-Bit-Ganzzahl-Typen. Abschneiden Warnungen möglicherweise zuvor vorhandenen Code durch diese neuere Version der Bibliothek erstellt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (Implementierung der Basisklasse).  
  
##  <a name="getlocator"></a>CGopherFileFind:: GetLocator  
 Rufen Sie diese Memberfunktion zum Abrufen der [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt, [FindFile](#findfile) verwendet, um die Gopherdatei zu suchen.  
  
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
 Tests für die aktuellen Verzeichnis und übergeordneten Verzeichnis-Marker, beim Durchlaufen von Dateien.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null weist die gefundene Datei den Namen "."oder"..", was bedeutet, dass die gefundene Datei ein Verzeichnis ist. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsDots`.  
  
## <a name="see-also"></a>Siehe auch  
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)

