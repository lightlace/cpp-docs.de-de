---
title: CFileFind-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82639ff7d4c4f6c6e33778b47509a2744cb12f13
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337394"
---
# <a name="cfilefind-class"></a>CFileFind-Klasse
Führt lokale Dateisuchen und ist die Basisklasse für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), die internetdateisuchen ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Erstellt ein `CFileFind`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Schließt die suchanforderung an.|  
|[CFileFind::FindFile](#findfile)|Durchsucht ein Verzeichnis für einen angegebenen Dateinamen.|  
|[CFileFind::FindNextFile](#findnextfile)|Weiterhin eine Dateisuche in einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Ruft die Uhrzeit, die Erstellung die Datei, ab.|  
|[CFileFind::GetFileName](#getfilename)|Ruft den Namen, einschließlich der Erweiterung der gefundenen Datei ab|  
|[CFileFind::GetFilePath](#getfilepath)|Ruft ab, der gesamte Pfad der Datei gefunden.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Ruft den Titel der gefundenen Datei ab. Der Titel ist die Erweiterung nicht enthalten.|  
|[CFileFind::GetFileURL](#getfileurl)|Ruft die URL, einschließlich den Dateipfad, der die gefundene Datei ab.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft die Zeit ab, der die Datei zuletzt verwendet wurden.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Ruft den Zeitpunkt an, den die Datei zuletzt geändert und gespeichert wurde.|  
|[CFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei in Bytes ab.|  
|[CFileFind::GetRoot](#getroot)|Ruft das Stammverzeichnis der gefundenen Datei ab.|  
|[CFileFind::IsArchived](#isarchived)|Bestimmt, ob die gefundene Datei archiviert wird.|  
|[CFileFind::IsCompressed](#iscompressed)|Bestimmt, ob die gefundene Datei komprimiert wird.|  
|[CFileFind::IsDirectory](#isdirectory)|Bestimmt, ob die gefundene Datei um ein Verzeichnis handelt.|  
|[CFileFind::IsDots](#isdots)|Bestimmt, ob der Name der gefundenen Datei den Namen hat "."oder"..", der angibt, die ein Verzeichnis ist.|  
|[CFileFind::IsHidden](#ishidden)|Bestimmt, ob die gefundene Datei ausgeblendet ist.|  
|[CFileFind::IsNormal](#isnormal)|Bestimmt, ob die gefundene Datei normal (also keine anderen Attribute aufweist).|  
|[CFileFind::IsReadOnly](#isreadonly)|Bestimmt, ob die gefundene Datei schreibgeschützt ist.|  
|[CFileFind::IsSystem](#issystem)|Bestimmt, ob die gefundene Datei eine Systemdatei ist.|  
|[CFileFind::IsTemporary](#istemporary)|Bestimmt, ob die gefundene Datei temporär ist.|  
|[CFileFind::MatchesMask](#matchesmask)|Gibt die gewünschte Dateiattribute der Datei gefunden werden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Schließt die Datei, die durch das aktuelle Suchhandle angegeben.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|Zeiger auf eine `CAtlTransactionManager` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CFileFind` enthält die Member-Funktionen, die eine Suche zu starten, suchen Sie nach einer Datei und geben Sie den Titel, Namen und Pfad der Datei zurück. Für Suchvorgänge im Internet, die Member-Funktion [GetFileURL](#getfileurl) der Datei-URL zurückgegeben.  
  
 `CFileFind` ist die Basisklasse für zwei andere MFC-Klassen sollen bestimmte Servertypen zu suchen: `CGopherFileFind` kann insbesondere mit Gopher-Server, und `CFtpFileFind` speziell mit FTP-Server funktioniert. Zusammen bieten diese drei Klassen einen nahtlose Mechanismus für den Client zum Suchen von Dateien unabhängig von dem Serverprotokoll, Typ oder Speicherort, auf einem lokalen Computer oder einem Remoteserver.  
  
 Der folgende Code Listet alle Dateien im aktuellen Verzeichnis, wobei der Name der jeweiligen Datei:  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Um das Beispiel einfach zu halten, dieser Code verwendet die C++-Standardbibliothek `cout` Klasse. Die `cout` Zeile ersetzt werden kann, mit einem Aufruf von `CListBox::AddString`, z. B. in einem Programm mit einer grafischen Benutzeroberfläche.  
  
 Weitere Informationen zur Verwendung von `CFileFind` und die andere WinInet-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 Diese Memberfunktion wird aufgerufen, wenn eine `CFileFind` -Objekt erstellt wird.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Parameter  
 *pTM*  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>  CFileFind::Close  
 Rufen Sie diese Memberfunktion zum Beenden der Suche, den Kontext zurückgesetzt und gibt alle Ressourcen frei.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `Close`, Sie haben nicht zum Erstellen eines neuen `CFileFind` Instanz vor dem Aufruf [FindFile](#findfile) um eine neue Suche zu starten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 Schließt die Datei, die durch das aktuelle Suchhandle angegeben.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließt die Datei, die durch den aktuellen Wert des Handles Suche angegeben. Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.  
  
 Rufen Sie die [FindFile](#findfile) oder [FindNextFile](#findnextfile) Funktionen, die sich mindestens einmal um eine gültige Suchhandle abzurufen. Die `FindFile` und `FindNextFile` Funktionen, die das Suchhandle verwenden, um Dateien mit Namen suchen, die mit einen angegebenen Namen übereinstimmen.  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 Rufen Sie diese Memberfunktion zum Öffnen einer Datei suchen.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *pstrName*  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen des zu suchenden Datei. Wenn Sie NULL, für die übergeben *PstrName*, `FindFile` ist einen Platzhalter (*.\*) suchen.  
  
 *dwUnused*  
 Reserviert, um die stellen `FindFile` von abgeleiteten Klassen polymorph. 0 muss sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `FindFile` rufen Sie zunächst die Dateisuche [FindNextFile](#findnextfile) nachfolgende Dateien abgerufen. Rufen Sie `FindNextFile` einmal, bevor Sie eine der folgenden Attributs Memberfunktionen aufrufen:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="findnextfile"></a>  CFileFind::FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortsetzen der Dateisuche eine aus einem vorherigen Aufruf von [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn weitere Dateien vorhanden sind; NULL, wenn die Datei im Verzeichnis das letzte ist oder ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn die Datei die letzte Datei im Verzeichnis ist, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` Funktionsergebnis ERROR_NO_MORE_FILES.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `FindNextFile` einmal, bevor Sie eine der folgenden Attributs Memberfunktionen aufrufen:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile` Dient als Wrapper für die Win32-Funktion [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime  
 Rufen Sie diese Memberfunktion um den Zeitpunkt zu ermitteln, die, den die angegebene Datei erstellt wurde.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pTimeStamp*  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) -Struktur, enthält die Zeit, die die Datei erstellt wurde.  
  
 *refTime*  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; 0, wenn der Vorgang fehlschlägt. `GetCreationTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, dazu `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetCreationTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen zu implementieren. Diese Funktion kann den gleichen Wert von anderen Time Stamp-Funktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das zeitattribut beibehalten zurückgeben. Finden Sie unter den [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur für Informationen zu Zeitformaten. Unter einigen Betriebssystemen ist die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, wenn sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="getfilename"></a>  CFileFind::GetFileName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der Datei gefunden.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Datei vor kurzem gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von "GetFileName".  
  
 `GetFileName` ist eine von drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie sie variieren:  
  
- `GetFileName` Gibt den Dateinamen, einschließlich der Erweiterung zurück. Zum Beispiel der Aufruf `GetFileName` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateinamen *myfile.txt*.  
  
- [GetFilePath](#getfilepath) gibt den vollständigen Pfad für die Datei. Zum Beispiel der Aufruf `GetFilePath` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateipfad zurück *c:\myhtml\myfile.txt*.  
  
- [GetFileTitle](#getfiletitle) gibt den Dateinamen, ohne die Dateierweiterung der Datei zurück. Zum Beispiel der Aufruf `GetFileTitle` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateititel *Myfile*.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 Rufen Sie diese Memberfunktion um den vollständigen Pfad der angegebenen Datei zu erhalten.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Pfad der angegebenen Datei.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetFilePath`.  
  
 `GetFilePath` ist eine von drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie sie variieren:  
  
- [GetFileName](#getfilename) gibt den Dateinamen, einschließlich der Erweiterung zurück. Zum Beispiel der Aufruf `GetFileName` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateinamen *myfile.txt*.  
  
- `GetFilePath` Gibt den vollständigen Pfad der Datei zurück. Zum Beispiel der Aufruf `GetFilePath` zum Generieren einer benutzermeldung zu der Datei `c:\myhtml\myfile.txt` gibt den Dateipfad zurück `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) gibt den Dateinamen, ohne die Dateierweiterung der Datei zurück. Zum Beispiel der Aufruf `GetFileTitle` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateititel *Myfile*.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle  
 Rufen Sie diese Memberfunktion um den Titel der gefundenen Datei zu erhalten.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetFileTitle`.  
  
 `GetFileTitle` ist eine von drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie sie variieren:  
  
- [GetFileName](#getfilename) gibt den Dateinamen, einschließlich der Erweiterung zurück. Zum Beispiel der Aufruf `GetFileName` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateinamen *myfile.txt*.  
  
- [GetFilePath](#getfilepath) gibt den vollständigen Pfad für die Datei. Zum Beispiel der Aufruf `GetFilePath` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateipfad zurück *c:\myhtml\myfile.txt*.  
  
- `GetFileTitle` Gibt den Dateinamen ohne die Dateierweiterung der Datei zurück. Zum Beispiel der Aufruf `GetFileTitle` zum Generieren einer benutzermeldung zu der Datei *c:\myhtml\myfile.txt* gibt den Dateititel *Myfile*.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfileurl"></a>  CFileFind::GetFileURL  
 Rufen Sie diese Memberfunktion zum Abrufen der angegebenen URL.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vollständige URL.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetFileURL`.  
  
 `GetFileURL` die Memberfunktion ähnelt [GetFilePath](#getfilepath), außer dass sie die URL im Format zurückgibt `file://path`. Zum Beispiel der Aufruf `GetFileURL` die vollständige URL für die abzurufenden *myfile.txt* gibt die URL zurück `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 Rufen Sie diese Memberfunktion um den Zeitpunkt zu ermitteln, den die angegebene Datei zuletzt verwendet wurden.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *refTime*  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
 *pTimeStamp*  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur, die beim Zugriff auf die Datei wurde zuletzt enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; 0, wenn der Vorgang fehlschlägt. `GetLastAccessTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, dazu `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastAccessTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen zu implementieren. Diese Funktion kann den gleichen Wert von anderen Time Stamp-Funktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das zeitattribut beibehalten zurückgeben. Finden Sie unter den [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur für Informationen zu Zeitformaten. Unter einigen Betriebssystemen ist die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, wenn sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 Rufen Sie diese Memberfunktion zum Zeitpunkt der letzten zu erhalten, die die Datei geändert wurde.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pTimeStamp*  
 Ein Zeiger auf eine [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) -Struktur, enthält die Datei zum letzten geschrieben wurde.  
  
 *refTime*  
 Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; 0, wenn der Vorgang fehlschlägt. `GetLastWriteTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, dazu `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastWriteTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen zu implementieren. Diese Funktion kann den gleichen Wert von anderen Time Stamp-Funktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das zeitattribut beibehalten zurückgeben. Finden Sie unter den [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur für Informationen zu Zeitformaten. Unter einigen Betriebssystemen ist die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, wenn sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 Rufen Sie diese Memberfunktion zum Abrufen der Länge der gefundenen Datei, in Bytes.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der gefundenen Datei, in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLength`.  
  
 `GetLength` verwendet die Win32-Struktur [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) abrufen, und geben Sie den Wert der Größe der Datei, in Bytes zurück.  
  
> [!NOTE]
>  Ab MFC 7.0 `GetLength` 64-Bit-Integer-Typen unterstützt. Zuvor kann vorhandener Code, der durch diese neuere Version der Bibliothek erstellt Abschneiden Warnungen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 Rufen Sie diese Memberfunktion um den Stamm der gefundenen Datei zu erhalten.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stamm der aktiven Suche.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetRoot`.  
  
 Diese Memberfunktion gibt die Laufwerksangabe und der Name des Pfads verwendet, um eine Suche zu starten. Zum Beispiel der Aufruf [FindFile](#findfile) mit `*.dat` führt `GetRoot` eine leere Zeichenfolge zurückgibt. Übergeben einen Pfad ein, z. B. `c:\windows\system\*.dll`zu `FindFile` Ergebnisse `GetRoot` zurückgeben `c:\windows\system\`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="isarchived"></a>  CFileFind::IsArchived  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei archiviert wird.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Anwendungen kennzeichnen eine Archivdatei, die gesichert oder entfernt werden, mit FILE_ATTRIBUTE_ARCHIVE, ein Dateiattribut-identifiziert wird die [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsArchived`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="iscompressed"></a>  CFileFind::IsCompressed  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei komprimiert wird.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine komprimierte Datei mit FILE_ATTRIBUTE_COMPRESSED markiert ist, die ein Dateiattribut identifiziert werden, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Bei einer Datei gibt dieses Attribut an, dass alle Daten in der Datei komprimiert wird. Für ein Verzeichnis gibt dieses Attribut an, dass die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse ist.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsCompressed`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei um ein Verzeichnis handelt.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei, die ein Verzeichnis ist mit FILE_ATTRIBUTE_DIRECTORY ein Dateiattribut-identifiziert markiert die [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsDirectory`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
 Dieses kleine Programm jedes Verzeichnis auf dem Laufwerk C:\ zurückgeführt werden kann, und gibt den Namen des Verzeichnisses.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 Rufen Sie diese Memberfunktion für die aktuelle Verzeichnis und das übergeordnete Verzeichnis Marker zu testen, während des Durchlaufens der Dateien an.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die gefundene Datei den Namen hat "."oder"..", was bedeutet, dass die gefundene Datei um ein Verzeichnis ist. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsDots`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="ishidden"></a>  CFileFind::IsHidden  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei ausgeblendet ist.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ausgeblendete Dateien, die mit FILE_ATTRIBUTE_HIDDEN gekennzeichnet sind, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine versteckte Datei ist nicht in einer normalen Verzeichnisliste enthalten.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsHidden`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="isnormal"></a>  CFileFind::IsNormal  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei eine normale Datei ist.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dateien mit FILE_ATTRIBUTE_NORMAL markiert ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine normale Datei verfügt über keine anderen Attribute festgelegt. Alle anderen Dateiattribute Überschreiben dieses Attribut.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsNormal`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei schreibgeschützt ist.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine schreibgeschützte Datei mit FILE_ATTRIBUTE_READONLY markiert ist, die ein Dateiattribut identifiziert werden, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Anwendungen können eine solche Datei lesen, aber nicht in ihn schreiben oder löschen.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsReadOnly`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="issystem"></a>  CFileFind::IsSystem  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei eine Systemdatei ist.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine Systemdatei mit FILE_ATTRIBUTE_SYSTEM markiert ist, wird ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine Systemdatei ist Teil, oder Sie wird ausschließlich durch das Betriebssystem verwendet.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsSystem`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei eine temporäre Datei ist.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine temporäre Datei mit FILE_ATTRIBUTE_TEMPORARY markiert ist, die ein Dateiattribut identifiziert werden, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine temporäre Datei wird für die temporäre Speicherung verwendet. Anwendungen sollten in die Datei schreiben, der nur, wenn es unbedingt erforderlich ist. Die meisten der die Daten der Datei verbleibt im Arbeitsspeicher, ohne auf die Medien geleert werden, da die Datei wird bald gelöscht werden.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsTemporary`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute der Datei.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 Rufen Sie diese Memberfunktion, um die Attribute der Datei auf die gefundene Datei zu testen.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *dwMask*  
 Gibt an, eine oder mehrere Dateiattribute in identifiziert die [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) -Struktur, für die gefundene Datei. Um für mehrere Attribute zu suchen, verwenden Sie bitweise OR (&#124;) Operator. Es ist eine beliebige Kombination der folgenden Attribute zulässig:  
  
-   FILE_ATTRIBUTE_ARCHIVE die Datei ist eine Archivdatei. Anwendungen verwenden Sie dieses Attribut zum Markieren von Dateien für die Sicherung oder zum Entfernen.  
  
-   FILE_ATTRIBUTE_COMPRESSED Datei oder des Verzeichnisses werden komprimiert. Bei einer Datei bedeutet dies, dass alle Daten in der Datei komprimiert wird. Bei einem Verzeichnis bedeutet dies, dass Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse.  
  
-   FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.  
  
-   FILE_ATTRIBUTE_NORMAL die Datei verfügt über keine anderen Attribute festgelegt. Dieses Attribut ist nur gültig, wenn allein verwendet wird. Alle anderen Dateiattribute Überschreiben dieses Attribut.  
  
-   FILE_ATTRIBUTE_HIDDEN die Datei ist ausgeblendet. Es ist nicht in einer normalen Verzeichnisliste enthalten sein.  
  
-   FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Anwendungen kann nicht lesen die Datei, aber in ihn schreiben oder löschen.  
  
-   FILE_ATTRIBUTE_SYSTEM, die Datei gehört, oder wird ausschließlich durch das Betriebssystem verwendet.  
  
-   FILE_ATTRIBUTE_TEMPORARY die Datei wird für die temporäre Speicherung verwendet. Anwendungen sollten in die Datei schreiben, der nur, wenn es unbedingt erforderlich ist. Die meisten der die Daten der Datei verbleibt im Arbeitsspeicher, ohne auf die Medien geleert werden, da die Datei wird bald gelöscht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `MatchesMask`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
