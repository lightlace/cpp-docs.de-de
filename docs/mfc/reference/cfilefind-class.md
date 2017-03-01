---
title: Klasse CFileFind | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileFind
dev_langs:
- C++
helpviewer_keywords:
- files [C++], finding
- Internet files [C++], finding
- CFileFind class
- URLs [C++], searching for
- local files
- local files, searching for
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
caps.latest.revision: 22
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
ms.openlocfilehash: d7e6500dfc0ff24f35dd021a54080eb7ba7f1655
ms.lasthandoff: 02/24/2017

---
# <a name="cfilefind-class"></a>CFileFind-Klasse
Führt lokale Dateisuchen und ist die Basisklasse für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), die internetdateisuchen ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Erstellt ein `CFileFind`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Schließt die Suchabfrage an.|  
|[CFileFind::FindFile](#findfile)|Sucht in einem Verzeichnis nach einem angegebenen Dateinamen.|  
|[CFileFind::FindNextFile](#findnextfile)|Weiterhin eine Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Ruft den Zeitpunkt der Erstellung die Datei.|  
|[CFileFind::GetFileName](#getfilename)|Ruft den Namen und die Erweiterung der gefundenen Datei|  
|[CFileFind::GetFilePath](#getfilepath)|Ruft den gesamten Pfad der gefundenen Datei.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Ruft den Titel der gefundenen Datei ab. Der Titel umfasst nicht die Erweiterung.|  
|[CFileFind::GetFileURL](#getfileurl)|Ruft die URL, einschließlich der Dateipfad der Datei gefunden.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft die Zeit ab, der die Datei zuletzt zugegriffen wurde.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Ruft den Zeitpunkt, den die Datei zuletzt geändert und gespeichert wurde.|  
|[CFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei in Bytes ab.|  
|[CFileFind::GetRoot](#getroot)|Ruft das Stammverzeichnis der gefundenen Datei ab.|  
|[CFileFind::IsArchived](#isarchived)|Bestimmt, ob die gefundene Datei archiviert wird.|  
|[CFileFind::IsCompressed](#iscompressed)|Bestimmt, ob die gefundene Datei komprimiert wird.|  
|[CFileFind::IsDirectory](#isdirectory)|Bestimmt, ob die gefundene Datei ein Verzeichnis ist.|  
|[CFileFind::IsDots](#isdots)|Bestimmt, ob der Name der gefundenen Datei der ist "."oder"..", bedeutet, dass ein Verzeichnis wird.|  
|[CFileFind::IsHidden](#ishidden)|Bestimmt, ob die gefundene Datei ausgeblendet ist.|  
|[CFileFind::IsNormal](#isnormal)|Bestimmt, ob die gefundene Datei normal ist (das heißt, keine anderen Attribute aufweist).|  
|[CFileFind::IsReadOnly](#isreadonly)|Bestimmt, ob die gefundene Datei schreibgeschützt ist.|  
|[CFileFind::IsSystem](#issystem)|Bestimmt, ob die gefundene Datei eine Systemdatei ist.|  
|[CFileFind::IsTemporary](#istemporary)|Bestimmt, ob die gefundene Datei temporär ist.|  
|[CFileFind::MatchesMask](#matchesmask)|Gibt die gewünschte Dateiattribute der Datei gefunden werden.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Schließt die Datei, die durch das aktuelle Handle für die Suche angegeben.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|Zeiger auf ein `CAtlTransactionManager` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CFileFind`enthält Funktionen, die eine Suche zu starten, suchen Sie nach einer Datei und den Titel, Name oder Pfad der Datei zurück. Für Suchvorgänge im Internet, die Memberfunktion [GetFileURL](#getfileurl) gibt die URL der Datei zurück.  
  
 `CFileFind`Dient die Basisklasse für zwei andere MFC-Klassen zum Suchen von bestimmten Servertypen: `CGopherFileFind` arbeitet spezifisch mit Gopher-Server und `CFtpFileFind` arbeitet spezifisch mit FTP-Servern. Zusammen bieten diese drei Klassen einen nahtlosen Mechanismus für den Client Dateien unabhängig von der Server-Protokoll, der Dateityp oder Speicherort, auf einem lokalen Computer oder einem Remoteserver zu ermitteln.  
  
 Im folgende Code werden alle Dateien im aktuellen Verzeichnis befindet, drucken den Namen der einzelnen Dateien aufzulisten:  
  
 [!code-cpp[NVC_MFCFiles&#31;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Um das Beispiel einfach zu halten, verwendet dieser Code die C++-Standardbibliothek `cout` Klasse. Die `cout` Zeile konnte ersetzt werden, mit einem Aufruf von `CListBox::AddString`, z. B. in einem Programm mit graphical User Interface.  
  
 Weitere Informationen zur Verwendung von `CFileFind` und die anderen WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="a-namecfilefinda--cfilefindcfilefind"></a><a name="cfilefind"></a>CFileFind::CFileFind  
 Diese Member-Funktion wird aufgerufen, wenn ein `CFileFind` -Objekt wird erstellt.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Parameter  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-nameclosea--cfilefindclose"></a><a name="close"></a>CFileFind::Close  
 Rufen Sie diese Memberfunktion, um die Suche zu beenden, den Kontext zurücksetzen und alle Ressourcen freizugeben.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von **schließen**, Sie haben nicht zum Erstellen eines neuen `CFileFind` -Instanz vor dem Aufruf von [FindFile](#findfile) um eine neue Suche zu beginnen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-nameclosecontexta--cfilefindclosecontext"></a><a name="closecontext"></a>CFileFind::CloseContext  
 Schließt die Datei, die durch das aktuelle Handle für die Suche angegeben.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließt die Datei, die durch den aktuellen Wert des Handles Suche angegeben. Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.  
  
 Müssen Sie aufrufen, die [FindFile](#findfile) oder [FindNextFile](#findnextfile) Funktionen, die mindestens einmal um eine gültige Handle abzurufen. Die **FindFile** und `FindNextFile` Funktionen, die das Handle für die Suche verwenden, um Dateien mit Namen suchen, die mit einen angegebenen Namen übereinstimmen.  
  
##  <a name="a-namefindfilea--cfilefindfindfile"></a><a name="findfile"></a>CFileFind::FindFile  
 Rufen Sie diese Memberfunktion, um eine Datei suchen zu öffnen.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen der zu suchenden Datei. Wenn Sie übergeben **NULL** für `pstrName`, **FindFile** ist einen Platzhalter (*.\*) suchen.  
  
 *dwUnused*  
 Reservierte zu **FindFile** polymorphen mit abgeleiteten Klassen. 0 muss sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von **FindFile** aufrufen, um die Dateisuche zu beginnen, [FindNextFile](#findnextfile) nachfolgende Dateien abgerufen. Sie müssen Aufrufen `FindNextFile` einmal, bevor Sie das folgende Attribut eines Memberfunktionen aufrufen:  
  
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
  
- [Zustand](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="a-namefindnextfilea--cfilefindfindnextfile"></a><a name="findnextfile"></a>CFileFind::FindNextFile  
 Rufen Sie diese Memberfunktion zum Fortsetzen des Vorgangs einer Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn mehrere Dateien vorhanden sind;&0; (null), wenn die Datei im Verzeichnis der letzte ist oder ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn die Datei die letzte Datei im Verzeichnis ist, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` Funktion gibt ERROR_NO_MORE_FILES zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen `FindNextFile` einmal, bevor Sie das folgende Attribut eines Memberfunktionen aufrufen:  
  
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
  
- [Zustand](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile`Dient als Wrapper für die Win32-Funktion [FindNextFile](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="a-namegetcreationtimea--cfilefindgetcreationtime"></a><a name="getcreationtime"></a>CFileFind::GetCreationTime  
 Rufen Sie diese Memberfunktion um den Zeitpunkt zu ermitteln, an den die angegebene Datei erstellt wurde.  
  
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
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetCreationTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, auf diesem `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetCreationTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen über Zeitformate. Unter einigen Betriebssystemen ist die zurückgegebene Zeit in der Zone lokal auf dem Computer wurden, dass sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namegetfilenamea--cfilefindgetfilename"></a><a name="getfilename"></a>CFileFind::GetFileName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens der Datei gefunden.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Datei vor kurzem gefunden.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal, bevor Sie GetFileName aufrufen.  
  
 `GetFileName`ist eine der drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie variieren:  
  
- `GetFileName`Gibt den Dateinamen einschließlich der Erweiterung. Zum Beispiel der Aufruf `GetFileName` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateinamen `myfile.txt`.  
  
- [GetFilePath](#getfilepath) gibt den vollständigen Pfad für die Datei. Zum Beispiel der Aufruf `GetFilePath` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateipfad `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) gibt den Dateinamen die Erweiterung ausschließen. Zum Beispiel der Aufruf `GetFileTitle` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Titel des `myfile`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#32;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="a-namegetfilepatha--cfilefindgetfilepath"></a><a name="getfilepath"></a>CFileFind::GetFilePath  
 Rufen Sie diese Memberfunktion zum Abrufen des vollständigen Pfads der angegebenen Datei.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Pfad der angegebenen Datei.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetFilePath`.  
  
 `GetFilePath`ist eine der drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie variieren:  
  
- [GetFileName](#getfilename) gibt den Dateinamen einschließlich der Erweiterung. Zum Beispiel der Aufruf `GetFileName` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateinamen `myfile.txt`.  
  
- `GetFilePath`Gibt den vollständigen Pfad für die Datei. Zum Beispiel der Aufruf `GetFilePath` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateipfad `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) gibt den Dateinamen die Erweiterung ausschließen. Zum Beispiel der Aufruf `GetFileTitle` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Titel des `myfile`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-namegetfiletitlea--cfilefindgetfiletitle"></a><a name="getfiletitle"></a>CFileFind::GetFileTitle  
 Rufen Sie diese Memberfunktion, um den Titel der gefundenen Datei abruft.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Titel der Datei.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetFileTitle`.  
  
 `GetFileTitle`ist eine der drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie variieren:  
  
- [GetFileName](#getfilename) gibt den Dateinamen einschließlich der Erweiterung. Zum Beispiel der Aufruf `GetFileName` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateinamen `myfile.txt`.  
  
- [GetFilePath](#getfilepath) gibt den vollständigen Pfad für die Datei. Zum Beispiel der Aufruf `GetFilePath` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateipfad `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle`Gibt den Dateinamen die Erweiterung ausschließen. Zum Beispiel der Aufruf `GetFileTitle` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Titel des `myfile`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-namegetfileurla--cfilefindgetfileurl"></a><a name="getfileurl"></a>CFileFind::GetFileURL  
 Rufen Sie diese Memberfunktion zum Abrufen der angegebenen URL.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die vollständige URL.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetFileURL`.  
  
 `GetFileURL`ist vergleichbar mit der Memberfunktion [GetFilePath](#getfilepath), außer dass sie die URL im Format zurückgibt `file://path`. Zum Beispiel der Aufruf `GetFileURL` die vollständige URL für die abzurufenden `myfile.txt` gibt die URL `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-namegetlastaccesstimea--cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime  
 Rufen Sie diese Memberfunktion um den Zeitpunkt zu ermitteln, den die angegebene Datei zuletzt zugegriffen wurde.  
  
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
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastAccessTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, auf diesem `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetLastAccessTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen über Zeitformate. Unter einigen Betriebssystemen ist die zurückgegebene Zeit in der Zone lokal auf dem Computer wurden, dass sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namegetlastwritetimea--cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CFileFind::GetLastWriteTime  
 Rufen Sie diese Memberfunktion zum Zeitpunkt der letzten zu erhalten, die die Datei geändert wurde.  
  
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
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastWriteTime`Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, auf diesem `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetLastWriteTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen über Zeitformate. Unter einigen Betriebssystemen ist die zurückgegebene Zeit in der Zone lokal auf dem Computer wurden, dass sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namegetlengtha--cfilefindgetlength"></a><a name="getlength"></a>CFileFind::GetLength  
 Rufen Sie diese Memberfunktion zum Abrufen der Länge der gefundenen Datei in Byte.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der gefundenen Datei in Byte.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetLength`.  
  
 `GetLength`verwendet die Win32-Struktur [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) abrufen und den Wert der Größe der Datei in Bytes zurückgegeben.  
  
> [!NOTE]
>  Ab MFC 7.0 `GetLength` unterstützt 64-Bit-Ganzzahl-Typen. Zuvor möglicherweise vorhandener Code integriert diese neuere Version der Bibliothek Abschneiden Warnungen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&33;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="a-namegetroota--cfilefindgetroot"></a><a name="getroot"></a>CFileFind::GetRoot  
 Rufen Sie diese Memberfunktion zum Abrufen der Stamm der gefundenen Datei.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stamm der aktiven Suche.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `GetRoot`.  
  
 Diese Memberfunktion gibt das Laufwerkangabe und der Name des Pfads verwendet, um eine Suche zu starten. Zum Beispiel der Aufruf [FindFile](#findfile) mit `*.dat` führt `GetRoot` eine leere Zeichenfolge zurückgibt. Übergeben einen Pfad ein, z. B. `c:\windows\system\*.dll`, **FindFile** Ergebnisse `GetRoot` zurückgeben `c:\windows\system\`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="a-nameisarchiveda--cfilefindisarchived"></a><a name="isarchived"></a>CFileFind::IsArchived  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei archiviert wird.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Applikationen kennzeichnen eine Archivdatei, die gesichert oder entfernt werden, mit FILE_ATTRIBUTE_ARCHIVE, ein Dateiattribut in identifiziert werden die [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsArchived`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameiscompresseda--cfilefindiscompressed"></a><a name="iscompressed"></a>CFileFind::IsCompressed  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei komprimiert wird.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine komprimierte Datei mit FILE_ATTRIBUTE_COMPRESSED markiert ist, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Für eine Datei gibt dieses Attribut an, dass alle Daten in der Datei komprimiert wird. Für ein Verzeichnis ist gibt dieses Attribut die Komprimierung als Standard für neu erstellte Dateien und Unterverzeichnisse.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsCompressed`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameisdirectorya--cfilefindisdirectory"></a><a name="isdirectory"></a>CFileFind::IsDirectory  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei ein Verzeichnis ist.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei, ein Verzeichnis mit FILE_ATTRIBUTE_DIRECTORY in ein Dateiattribut identifizierten gekennzeichnet ist die [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsDirectory`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
 Dieses kleine Programm durchläuft jedes Verzeichnis auf Laufwerk C:\, und gibt den Namen des Verzeichnisses.  
  
 [!code-cpp[NVC_MFCFiles&#34;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="a-nameisdotsa--cfilefindisdots"></a><a name="isdots"></a>CFileFind::IsDots  
 Rufen Sie diese Memberfunktion während des Durchlaufens der Dateien für die aktuellen Verzeichnis und übergeordneten Verzeichnis Marker zu testen.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null weist die gefundene Datei den Namen "."oder"..", was bedeutet, dass die gefundene Datei ein Verzeichnis ist. Andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsDots`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="a-nameishiddena--cfilefindishidden"></a><a name="ishidden"></a>CFileFind::IsHidden  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei ausgeblendet ist.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Ausgeblendete Dateien, die mit FILE_ATTRIBUTE_HIDDEN gekennzeichnet sind, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine versteckte Datei ist nicht in einer normalen Verzeichnisliste enthalten.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsHidden`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameisnormala--cfilefindisnormal"></a><a name="isnormal"></a>CFileFind::IsNormal  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die gefundene Datei eine normale Datei.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Dateien mit FILE_ATTRIBUTE_NORMAL, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine normale Datei hat keine weiteren Attribute festgelegt. Alle anderen Dateiattribute Überschreiben dieses Attribut.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsNormal`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameisreadonlya--cfilefindisreadonly"></a><a name="isreadonly"></a>CFileFind::IsReadOnly  
 Rufen Sie diese Memberfunktion auf, ob die gefundene Datei schreibgeschützt ist.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine schreibgeschützte Datei mit FILE_ATTRIBUTE_READONLY markiert ist, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Clientanwendungen können eine solche Datei gelesen, aber nicht in ihn schreiben oder löschen Sie ihn.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsReadOnly`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameissystema--cfilefindissystem"></a><a name="issystem"></a>CFileFind::IsSystem  
 Rufen Sie diese Memberfunktion auf, ob die gefundene Datei eine Systemdatei ist.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine Systemdatei mit FILE_ATTRIBUTE_SYSTEM gekennzeichnet ist, wird ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine Systemdatei ist Teil oder wird ausschließlich durch das Betriebssystem verwendet.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsSystem`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-nameistemporarya--cfilefindistemporary"></a><a name="istemporary"></a>CFileFind::IsTemporary  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die gefundene Datei eine temporäre Datei.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine temporäre Datei mit FILE_ATTRIBUTE_TEMPORARY markiert ist, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine temporäre Datei wird für die temporäre Speicherung verwendet. Clientanwendungen sollten in die Datei geschrieben, wenn Sie nur, wenn es unbedingt erforderlich. Die meisten Daten der Datei verbleibt im Arbeitsspeicher, ohne auf den Datenträger geleert wird, da die Datei schnell gelöscht werden.  
  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `IsTemporary`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste der Attribute.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="a-namemptma--cfilefindmptm"></a><a name="m_ptm"></a>CFileFind::m_pTM  
 Zeiger auf ein `CAtlTransactionManager` Objekt.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namematchesmaska--cfilefindmatchesmask"></a><a name="matchesmask"></a>CFileFind::MatchesMask  
 Rufen Sie diese Memberfunktion, um die Dateiattribute auf die gefundene Datei zu testen.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwMask`  
 Gibt einen oder mehrere Dateiattribute, gemäß der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) -Struktur, für die gefundene Datei. Um für mehrere Attribute zu suchen, verwenden Sie den bitweisen OR-Operator (|). Eine beliebige Kombination der folgenden Attribute ist zulässig:  
  
-   FILE_ATTRIBUTE_ARCHIVE die Datei ist eine Archivdatei. Clientanwendungen verwenden dieses Attribut zum Markieren von Dateien für die Sicherung oder Entfernung.  
  
-   FILE_ATTRIBUTE_COMPRESSED die Datei oder das Verzeichnis komprimiert wird. Für eine Datei bedeutet dies, dass alle Daten in der Datei komprimiert wird. Bei einem Verzeichnis bedeutet dies, dass Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse.  
  
-   FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.  
  
-   FILE_ATTRIBUTE_NORMAL die Datei verfügt über keine weiteren Attribute festgelegt. Dieses Attribut ist nur gültig, wenn allein verwendet. Alle anderen Dateiattribute Überschreiben dieses Attribut.  
  
-   FILE_ATTRIBUTE_HIDDEN die Datei ist ausgeblendet. Es ist nicht in einer normalen Verzeichnisliste enthalten sein.  
  
-   FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Applikationen kann nicht lesen die Datei, aber in ihn schreiben oder löschen.  
  
-   FILE_ATTRIBUTE_SYSTEM die Datei gehört, oder wird ausschließlich durch das Betriebssystem verwendet.  
  
-   FILE_ATTRIBUTE_TEMPORARY die Datei wird für die temporäre Speicherung verwendet. Clientanwendungen sollten in die Datei geschrieben, wenn Sie nur, wenn es unbedingt erforderlich. Die meisten Daten der Datei verbleibt im Arbeitsspeicher, ohne auf den Datenträger geleert wird, da die Datei schnell gelöscht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf von `MatchesMask`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles&#35;](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)

