---
title: CFileFind Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e890e59896d1f69264ab479168385cf2a05d9fb7
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="cfilefind-class"></a>CFileFind-Klasse
Führt lokale Dateisuchen aus und ist die Basisklasse für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), dem internetdateisuchen.  
  
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
|[CFileFind::FindFile](#findfile)|Sucht in einem Verzeichnis für einen angegebenen Dateinamen.|  
|[CFileFind::FindNextFile](#findnextfile)|Weiterhin eine Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Ruft den Zeitpunkt der Erstellung die Datei ab.|  
|[CFileFind::GetFileName](#getfilename)|Ruft den Namen ab, einschließlich der Erweiterung der gefundenen Datei|  
|[CFileFind::GetFilePath](#getfilepath)|Ruft den gesamten Pfad der gefundenen Datei.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Ruft den Titel der gefundenen Datei ab. Der Titel umfasst nicht die Erweiterung.|  
|[CFileFind::GetFileURL](#getfileurl)|Ruft die URL, einschließlich der Dateipfad der gefundenen Datei ab.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft die Zeit ab, der die Datei zuletzt verwendet wurden.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Ruft die Zeit, die Datei zuletzt geändert und gespeichert wurde.|  
|[CFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei, in Bytes ab.|  
|[CFileFind::GetRoot](#getroot)|Ruft das Stammverzeichnis der gefundenen Datei ab.|  
|[CFileFind::IsArchived](#isarchived)|Bestimmt, ob die gefundene Datei archiviert wird.|  
|[CFileFind::IsCompressed](#iscompressed)|Bestimmt, ob die gefundene Datei komprimiert wird.|  
|[CFileFind::IsDirectory](#isdirectory)|Bestimmt, ob die gefundene Datei ein Verzeichnis ist.|  
|[CFileFind::IsDots](#isdots)|Bestimmt, ob der Name der gefundenen Datei den Namen hat "."oder"..", dass ein Verzeichnis ist.|  
|[CFileFind::IsHidden](#ishidden)|Bestimmt, ob die gefundene Datei ausgeblendet ist.|  
|[CFileFind::IsNormal](#isnormal)|Bestimmt, ob die gefundene Datei normal ist (das heißt, keine anderen Attribute aufweist).|  
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
 `CFileFind` enthält die Memberfunktionen, die eine Suche starten, suchen Sie nach einer Datei und der Titel, Name oder Pfad der Datei zurück. Für Suchvorgänge im Internet, die Memberfunktion [GetFileURL](#getfileurl) gibt die URL der Datei zurück.  
  
 `CFileFind` ist die Basisklasse für zwei andere MFC-Klassen entwickelt, bestimmte Servertypen gesucht werden soll: `CGopherFileFind` kann insbesondere mit Gopher-Server und `CFtpFileFind` kann insbesondere mit FTP-Servern. Zusammen ermöglichen diese drei Klassen einen nahtlosen Mechanismus für den Client zum Suchen von Dateien unabhängig von das Serverprotokoll, den Dateityp oder Speicherort, auf einem lokalen Computer oder einem Remoteserver.  
  
 Der folgende Code Listet alle Dateien im aktuellen Verzeichnis, wobei der Name der einzelnen Dateien:  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Um das Beispiel einfach zu halten, dieser Code verwendet die C++-Standardbibliothek `cout` Klasse. Die `cout` Zeile konnten ersetzt werden, mit einem Aufruf von `CListBox::AddString`, z. B. in einem Programm mit einer grafischen Benutzeroberfläche.  
  
 Weitere Informationen zur Verwendung von `CFileFind` und die anderen WinInet-Klassen finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 Diese Memberfunktion wird aufgerufen, wenn ein `CFileFind` -Objekt erstellt wird.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Parameter  
 `pTM`  
 Zeiger auf CAtlTransactionManager-Objekt  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>  CFileFind::Close  
 Rufen Sie diese Memberfunktion, um die Suche zu beenden, setzen Sie den Kontext zurück und gibt alle Ressourcen frei.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf **schließen**, Sie haben nicht zum Erstellen eines neuen `CFileFind` -Instanz vor dem Aufruf von [FindFile](#findfile) um eine neue Suche zu starten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 Schließt die Datei, die durch das aktuelle Suchhandle angegeben.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließt die Datei, die durch den aktuellen Wert des Handles Suche angegeben. Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.  
  
 Rufen Sie die [FindFile](#findfile) oder [FindNextFile](#findnextfile) Funktionen, die mindestens einmal um eine gültige Suchergebnisse Handle abgerufen werden soll. Die **FindFile** und `FindNextFile` Funktionen, die das Handle für die Suche verwenden, um Dateien mit dem Namen zu suchen, die mit einen angegebenen Namen übereinstimmen.  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 Rufen Sie diese Memberfunktion zum Öffnen einer Datei suchen.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `pstrName`  
 Ein Zeiger auf eine Zeichenfolge mit dem Namen des zu suchenden Datei. Wenn Sie übergeben **NULL** für `pstrName`, **FindFile** ist einen Platzhalter (*.\*) suchen.  
  
 *dwUnused*  
 Reservierte vornehmen **FindFile** polymorphen mit abgeleiteten Klassen. 0 muss sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf **FindFile** aufrufen, um die Dateisuche zu starten, [FindNextFile](#findnextfile) nachfolgende Dateien abgerufen. Rufen Sie `FindNextFile` mindestens einmal, bevor Sie eine der folgenden Attribut Memberfunktionen aufrufen:  
  
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
 Rufen Sie diese Memberfunktion zum Fortfahren einer Dateisuche aus einem vorherigen Aufruf von [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn mehrere Dateien vorhanden sind; 0 (null) ist die gefundene Datei das letzte Lesezeichen im Verzeichnis, oder wenn ein Fehler aufgetreten. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Wenn der Dateiname der gefundenen Datei ist die letzte Datei im Verzeichnis, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` -Funktion gibt ERROR_NO_MORE_FILES zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `FindNextFile` mindestens einmal, bevor Sie eine der folgenden Attribut Memberfunktionen aufrufen:  
  
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
 Rufen Sie diese Memberfunktion um den Zeitpunkt zu ermitteln, an den die angegebene Datei erstellt wurde.  
  
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
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetCreationTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) nie aufgerufen wurde für dieses `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetCreationTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder dem Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen Zeitformate. Ist auf einige Systeme Vorgang die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, dass die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
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
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal, bevor Sie GetFileName aufrufen.  
  
 `GetFileName` ist eine von drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie sie variieren:  
  
- `GetFileName` Gibt den Dateinamen, einschließlich der Erweiterung zurück. Beispielsweise Aufrufen `GetFileName` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateinamen `myfile.txt`.  
  
- [GetFilePath](#getfilepath) gibt den vollständigen Pfad für die Datei. Beispielsweise Aufrufen `GetFilePath` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Pfad der `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) gibt den Dateinamen an, mit Ausnahme der Dateierweiterung zurück. Beispielsweise Aufrufen `GetFileTitle` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateititel `myfile`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 Rufen Sie diese Memberfunktion zum Abrufen des vollständigen Pfads der angegebenen Datei.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Pfad der angegebenen Datei.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetFilePath`.  
  
 `GetFilePath` ist eine von drei `CFileFind` Memberfunktionen, die eine Form des Dateinamens zurückgeben. Die folgende Liste beschreibt die drei und wie sie variieren:  
  
- [GetFileName](#getfilename) gibt den Dateinamen, einschließlich der Erweiterung zurück. Beispielsweise Aufrufen `GetFileName` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateinamen `myfile.txt`.  
  
- `GetFilePath` Gibt den vollständigen Pfad für die Datei zurück. Beispielsweise Aufrufen `GetFilePath` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Pfad der `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) gibt den Dateinamen an, mit Ausnahme der Dateierweiterung zurück. Beispielsweise Aufrufen `GetFileTitle` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateititel `myfile`.  
  
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
  
- [GetFileName](#getfilename) gibt den Dateinamen, einschließlich der Erweiterung zurück. Beispielsweise Aufrufen `GetFileName` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateinamen `myfile.txt`.  
  
- [GetFilePath](#getfilepath) gibt den vollständigen Pfad für die Datei. Beispielsweise Aufrufen `GetFilePath` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Pfad der `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle` Gibt den Dateinamen die Erweiterung ausschließen. Beispielsweise Aufrufen `GetFileTitle` zum Generieren einer Benutzernachricht über die Datei `c:\myhtml\myfile.txt` gibt den Dateititel `myfile`.  
  
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
  
 `GetFileURL` die Memberfunktion gleicht [GetFilePath](#getfilepath), außer dass sie die URL im Format zurückgibt `file://path`. Beispielsweise Aufrufen `GetFileURL` die vollständige URL für die abzurufenden `myfile.txt` gibt die URL `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 Rufen Sie diese Memberfunktion um den Zeitpunkt zu ermitteln, den die angegebene Datei zuletzt zugegriffen wurde.  
  
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
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastAccessTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) nie aufgerufen wurde für dieses `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastAccessTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder dem Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen Zeitformate. Ist auf einige Systeme Vorgang die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, dass die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 Rufen Sie diese Memberfunktion zum Zeitpunkt der letzten zu erhalten, die die Datei geändert wurde.  
  
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
 Der Wert ist ungleich NULL bei Erfolg; 0, wenn nicht erfolgreich. `GetLastWriteTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) nie aufgerufen wurde für dieses `CFileFind` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastWriteTime`.  
  
> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen implementieren. Diese Funktion kann von anderen Stempel Zeitfunktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder dem Server nicht unterstützt wird das Attribut Zeit beibehalten denselben Wert zurückgeben. Finden Sie unter der [Win32_Find_Data](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur Informationen Zeitformate. Ist auf einige Systeme Vorgang die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, dass die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) -API für Weitere Informationen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 Rufen Sie diese Memberfunktion zum Abrufen der Länge der gefundenen Datei in Bytes.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der gefundenen Datei in Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLength`.  
  
 `GetLength` verwendet die Win32-Struktur [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) abgerufen und der Rückgabewert der Größe der Datei in Bytes.  
  
> [!NOTE]
>  Ab MFC 7.0 `GetLength` unterstützt 64-Bit-Ganzzahl-Typen. Zuvor kann vorhandener Code, der mit dieser neueren Version der Bibliothek erstellt Abschneiden Warnungen führen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 Rufen Sie diese Memberfunktion zum Abrufen der Stamm der gefundenen Datei.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stamm der aktiven Suche.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetRoot`.  
  
 Diese Memberfunktion gibt die Laufwerk-Bezeichner und der Name des Pfads verwendet, um eine Suche zu starten. Beispielsweise Aufrufen [FindFile](#findfile) mit `*.dat` führt `GetRoot` eine leere Zeichenfolge zurückgeben. Übergeben einen Pfad, z. B. `c:\windows\system\*.dll`in **FindFile** Ergebnisse `GetRoot` zurückgeben `c:\windows\system\`.  
  
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
 Anwendungen markieren eine Archivdatei, die gesichert werden, oder entfernt werden, mit FILE_ATTRIBUTE_ARCHIVE ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsArchived`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
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
 Eine komprimierte Datei mit FILE_ATTRIBUTE_COMPRESSED markiert ist, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Bei einer Datei gibt dieses Attribut an, dass alle Daten in der Datei komprimiert wird. Für ein Verzeichnis ist gibt dieses Attribut an, dass die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse ist.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsCompressed`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei ein Verzeichnis ist.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine Datei, ein Verzeichnis ist, RuntimeCompatibility mit FILE_ATTRIBUTE_DIRECTORY ein Dateiattribut, in identifiziert der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsDirectory`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
### <a name="example"></a>Beispiel  
 Dieses kleine Programm jedes Verzeichnis auf dem Laufwerk C:\ zurückgeführt werden kann, und gibt den Namen des Verzeichnisses.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 Rufen Sie diese Memberfunktion beim Durchlaufen von Dateien für die aktuellen Verzeichnisses und übergeordnetes Verzeichnis Marker zu testen.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, verfügt die gefundene Datei den Namen "."oder"..", was bedeutet, dass die gefundene Datei um ein Verzeichnis ist. Andernfalls 0.  
  
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
 Ausgeblendete Dateien, die mit FILE_ATTRIBUTE_HIDDEN gekennzeichnet sind, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine ausgeblendete Datei ist nicht in einer normalen Verzeichnisliste enthalten.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsHidden`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
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
 Dateien mit FILE_ATTRIBUTE_NORMAL gekennzeichnet, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine normale Datei hat keine anderen Attribute festgelegt. Alle anderen Dateiattribute Überschreiben dieses Attribut.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsNormal`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 Rufen Sie diese Memberfunktion zu bestimmen, ob die gefundene Datei schreibgeschützt ist.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine schreibgeschützte Datei mit FILE_ATTRIBUTE_READONLY markiert ist, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Anwendungen können eine solche Datei lesen, aber nicht in ihn schreiben oder löschen Sie ihn.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsReadOnly`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
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
 A system file is marked with FILE_ATTRIBUTE_SYSTEM, , a file attribute identified in the [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) structure. Eine Systemdatei ist Bestandteil des oder ausschließlich vom Betriebssystem verwendet wird.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsSystem`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 Rufen Sie diese Memberfunktion, um festzustellen, ob die gefundene Datei einer temporären Datei ist.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Eine temporäre Datei mit FILE_ATTRIBUTE_TEMPORARY markiert ist, ein Dateiattribut identifiziert, der [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur. Eine temporäre Datei wird für die temporäre Speicherung verwendet. Anwendungen sollten in die Datei schreiben, der nur, wenn dies absolut notwendig ist. Die meisten Daten der Datei verbleibt im Arbeitsspeicher, ohne auf den Datenträger geleert werden, da die Datei bald gelöscht wird.  
  
 Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsTemporary`.  
  
 Finden Sie unter der Memberfunktion [MatchesMask](#matchesmask) für eine vollständige Liste von Dateiattributen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 Zeiger auf eine `CAtlTransactionManager` Objekt.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 Rufen Sie diese Memberfunktion, um die Dateiattribute der gefundenen Datei zu testen.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwMask`  
 Gibt einen oder mehrere Dateiattribute identifiziert die [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) Struktur für die Datei gefunden. Um für mehrere Attribute zu suchen, verwenden Sie den bitweisen OR-Operator (&#124;) Operator. Eine beliebige Kombination der folgenden Attribute ist zulässig:  
  
-   FILE_ATTRIBUTE_ARCHIVE die Datei ist eine Archivdatei. Anwendungen verwenden Sie dieses Attribut zum Kennzeichnen von Dateien für die Sicherung oder entfernen.  
  
-   FILE_ATTRIBUTE_COMPRESSED die Datei oder das Verzeichnis komprimiert wird. Bei einer Datei bedeutet dies, dass alle Daten in der Datei komprimiert wird. Für ein Verzeichnis ist bedeutet dies, dass die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse ist.  
  
-   FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.  
  
-   FILE_ATTRIBUTE_NORMAL die Datei verfügt über keine anderen Attribute festgelegt. Dieses Attribut ist nur gültig, wenn isoliert verwendet. Alle anderen Dateiattribute Überschreiben dieses Attribut.  
  
-   FILE_ATTRIBUTE_HIDDEN   The file is hidden. Es ist nicht in einer normalen Verzeichnisliste enthalten sein.  
  
-   FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Anwendungen können sie lesen Sie die Datei aber kann nicht in ihn schreiben oder löschen.  
  
-   FILE_ATTRIBUTE_SYSTEM die Datei ist Teil oder ausschließlich vom Betriebssystem verwendet wird.  
  
-   FILE_ATTRIBUTE_TEMPORARY die Datei wird für die temporäre Speicherung verwendet. Anwendungen sollten in die Datei schreiben, der nur, wenn dies absolut notwendig ist. Die meisten Daten der Datei verbleibt im Arbeitsspeicher, ohne auf den Datenträger geleert werden, da die Datei bald gelöscht wird.  
  
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
