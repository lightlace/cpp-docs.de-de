---
title: CFileFind-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 2ec8c50a317a09e97a212e8cd7b9be1b58272af9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506569"
---
# <a name="cfilefind-class"></a>CFileFind-Klasse

Führt lokale Datei suchen aus und ist die Basisklasse für [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) und [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), die Internet Datei suchen ausführen.

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
|[CFileFind::Close](#close)|Schließt die Such Anforderung.|
|[CFileFind::FindFile](#findfile)|Durchsucht ein Verzeichnis nach einem angegebenen Dateinamen.|
|[CFileFind::FindNextFile](#findnextfile)|Setzt eine Dateisuche von einem vorherigen Befehl von " [FindFile](#findfile)" fort.|
|[CFileFind::GetCreationTime](#getcreationtime)|Ruft den Zeitpunkt ab, zu dem die Datei erstellt wurde.|
|[CFileFind::GetFileName](#getfilename)|Ruft den Namen der gefundenen Datei einschließlich der Erweiterung ab.|
|[CFileFind::GetFilePath](#getfilepath)|Ruft den gesamten Pfad der gefundenen Datei ab.|
|[CFileFind::GetFileTitle](#getfiletitle)|Ruft den Titel der gefundenen Datei ab. Der Titel enthält nicht die Erweiterung.|
|[CFileFind::GetFileURL](#getfileurl)|Ruft die URL der gefundenen Datei einschließlich des Dateipfads ab.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft den Zeitpunkt ab, zu dem zuletzt auf die Datei zugegriffen wurde.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Ruft den Zeitpunkt ab, zu dem die Datei zuletzt geändert und gespeichert wurde.|
|[CFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei in Bytes ab.|
|[CFileFind::GetRoot](#getroot)|Ruft das Stammverzeichnis der gefundenen Datei ab.|
|[CFileFind::IsArchived](#isarchived)|Bestimmt, ob die gefundene Datei archiviert wird.|
|[CFileFind::IsCompressed](#iscompressed)|Bestimmt, ob die gefundene Datei komprimiert ist.|
|[CFileFind::IsDirectory](#isdirectory)|Bestimmt, ob es sich bei der gefundenen Datei um ein Verzeichnis handelt.|
|[CFileFind::IsDots](#isdots)|Bestimmt, ob der Name der gefundenen Datei den Namen "." oder ".." hat und angibt, dass tatsächlich ein Verzeichnis ist.|
|[CFileFind::IsHidden](#ishidden)|Bestimmt, ob die gefundene Datei ausgeblendet ist.|
|[CFileFind::IsNormal](#isnormal)|Bestimmt, ob die gefundene Datei Normal ist (d. h. keine anderen Attribute hat).|
|[CFileFind::IsReadOnly](#isreadonly)|Bestimmt, ob die gefundene Datei schreibgeschützt ist.|
|[CFileFind::IsSystem](#issystem)|Bestimmt, ob es sich bei der gefundenen Datei um eine Systemdatei handelt.|
|[CFileFind::IsTemporary](#istemporary)|Bestimmt, ob die gefundene Datei temporär ist.|
|[CFileFind::MatchesMask](#matchesmask)|Gibt die gewünschten Dateiattribute der Datei an, die gefunden werden soll.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CFileFind::CloseContext](#closecontext)|Schließt die durch das aktuelle Such handle angegebene Datei.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|Zeiger auf ein `CAtlTransactionManager` -Objekt.|

## <a name="remarks"></a>Hinweise

`CFileFind`umfasst Member-Funktionen, die eine Suche starten, eine Datei suchen und den Titel, den Namen oder den Pfad der Datei zurückgeben. Bei Internet Suchvorgängen gibt die Member-Funktion [getfileurl](#getfileurl) die URL der Datei zurück.

`CFileFind`ist die Basisklasse für zwei weitere MFC-Klassen, die für das Durchsuchen `CGopherFileFind` bestimmter Server Typen entwickelt wurden: funktioniert speziell `CFtpFileFind` mit Gopher-Servern und funktioniert speziell mit FTP-Servern. Diese drei Klassen bieten eine nahtlose Methode, mit der der Client Dateien unabhängig vom Server Protokoll, dem Dateityp oder dem Speicherort auf einem lokalen Computer oder einem Remote Server findet.

Der folgende Code listet alle Dateien im aktuellen Verzeichnis auf, wobei die Namen der einzelnen Dateien gedruckt werden:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Um das Beispiel einfach zu halten, wird in diesem C++ Code die `cout` -Klasse der Standard Bibliothek verwendet. Die `cout` Zeile könnte z. b. durch einen `CListBox::AddString`-Befehl ersetzt werden, z. b. in einem Programm mit grafischer Benutzeroberfläche.

Weitere Informationen zur Verwendung `CFileFind` von und der anderen WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="cfilefind"></a>CFileFind:: CFileFind

Diese Member-Funktion wird aufgerufen, `CFileFind` wenn ein-Objekt erstellt wird.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parameter

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetFileName](#getfilename).

##  <a name="close"></a>CFileFind:: Close

Mit dieser Member-Funktion können Sie die Suche beenden, den Kontext zurücksetzen und alle Ressourcen freigeben.

```
void Close();
```

### <a name="remarks"></a>Hinweise

Nachdem Sie `Close`aufgerufen haben, müssen Sie keine neue `CFileFind` -Instanz erstellen, bevor Sie [FindFile](#findfile) aufrufen, um eine neue Suche zu starten.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetFileName](#getfilename).

##  <a name="closecontext"></a>CFileFind:: closecontext

Schließt die durch das aktuelle Such handle angegebene Datei.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Hinweise

Schließt die durch den aktuellen Wert des Such Handles angegebene Datei. Überschreiben Sie diese Funktion, um das Standardverhalten zu ändern.

Sie müssen die Funktionen [FindFile](#findfile) oder [FindNextFile](#findnextfile) mindestens einmal aufrufen, um ein gültiges Suchhandle abzurufen. Die `FindFile` Funktionen `FindNextFile` und verwenden das Suchhandle, um Dateien mit Namen zu suchen, die mit einem bestimmten Namen identisch sind.

##  <a name="findfile"></a>CFileFind:: FindFile

Mit dieser Member-Funktion Öffnen Sie eine Dateisuche.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Parameter

*pstrName*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen der zu suchenden Datei enthält. Wenn Sie NULL für *pstrinname*übergeben, `FindFile` führt eine Platzhalter Suche (\**.) durch.

*dwUnused*<br/>
Reserviert, um `FindFile` polymorph mit abgeleiteten Klassen zu erstellen. Muss 0 (null) sein.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, nennen Sie die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Hinweise

Rufen Sie `FindFile` nach dem Aufrufen von zum Starten der Dateisuche [FindNextFile](#findnextfile) auf, um nachfolgende Dateien abzurufen. Sie müssen mindestens `FindNextFile` einmal aufrufen, bevor Sie eine der folgenden Attribut Element Funktionen aufrufen:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [Isarchiviert](#isarchived)

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

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: IsDirectory](#isdirectory).

##  <a name="findnextfile"></a>CFileFind:: FindNextFile

Diese Member-Funktion wird aufgerufen, um eine Dateisuche von einem vorherigen Befehl von [FindFile](#findfile)fortzusetzen.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn weitere Dateien vorhanden sind. 0 (null), wenn die gefundene Datei das letzte im Verzeichnis ist, oder, wenn ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, nennen Sie die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Wenn es sich bei der gefundenen Datei um die letzte Datei im Verzeichnis handelt oder wenn keine übereinstimmenden Dateien gefunden `GetLastError` werden können, gibt die Funktion ERROR_NO_MORE_FILES zurück.

### <a name="remarks"></a>Hinweise

Sie müssen mindestens `FindNextFile` einmal aufrufen, bevor Sie eine der folgenden Attribut Element Funktionen aufrufen:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [GetLength](#getlength)

- [GetRoot](#getroot)

- [Isarchiviert](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [IsHidden](#ishidden)

- [IsNormal](#isnormal)

- [IsReadOnly](#isreadonly)

- [IsSystem](#issystem)

- [IsTemporary](#istemporary)

- [MatchesMask](#matchesmask)

`FindNextFile`umschließt die Win32-Funktion " [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)".

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: IsDirectory](#isdirectory).

##  <a name="getcreationtime"></a>CFileFind:: getkreationtime

Mit dieser Member-Funktion können Sie die Zeit abrufen, zu der die angegebene Datei erstellt wurde.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parameter

*pTimeStamp*<br/>
Ein Zeiger auf eine [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Struktur, die die Uhrzeit enthält, zu der die Datei erstellt wurde.

*refTime*<br/>
Ein Verweis auf ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich; 0, wenn nicht erfolgreich. `GetCreationTime`gibt 0 (null) nur dann zurück, wenn [FindNextFile](#findnextfile) für dieses `CFileFind` Objekt noch nie aufgerufen wurde.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetCreationTime`aufrufen.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den von dieser Funktion zurückgegebenen Zeitstempel zu implementieren. Diese Funktion gibt möglicherweise denselben Wert zurück, der von anderen Zeitstempel Funktionen zurückgegeben wird, wenn das zugrunde liegende Dateisystem oder der Server das Beibehalten des Zeit Attributs nicht unterstützt. Weitere Informationen zu Zeitformaten finden Sie in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur. Bei einigen Betriebssystemen befindet sich die zurückgegebene Zeit in der lokalen Zeitzone des Computers, in dem sich die Datei befindet. Weitere Informationen finden Sie in der Win32 [filetimetolocalfiletime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="getfilename"></a>CFileFind:: GetFilename

Mit dieser Member-Funktion können Sie den Namen der gefundenen Datei abrufen.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name der zuletzt gefundenen Datei.

### <a name="remarks"></a>Hinweise

[FindNextFile](#findnextfile) muss mindestens einmal aufgerufen werden, bevor GetFileName aufgerufen wird.

`GetFileName`ist eine von drei `CFileFind` Member-Funktionen, die eine Form des Datei namens zurückgeben. In der folgenden Liste werden die drei und deren Unterschiede beschrieben:

- `GetFileName`Gibt den Dateinamen einschließlich der Erweiterung zurück. Wenn Sie z. `GetFileName` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Dateiname *MyFile. txt*zurückgegeben.

- [GetFilePath](#getfilepath) gibt den gesamten Pfad für die Datei zurück. Wenn Sie z. `GetFilePath` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Dateipfad *c:\myhtml\myfile.txt*zurückgegeben.

- [GetFileTitle](#getfiletitle) gibt den Dateinamen mit Ausnahme der Dateierweiterung zurück. Wenn Sie z. `GetFileTitle` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Datei Titel *MyFile*zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

##  <a name="getfilepath"></a>CFileFind:: GetFilePath

Mit dieser Member-Funktion können Sie den vollständigen Pfad der angegebenen Datei abrufen.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Rückgabewert

Der Pfad der angegebenen Datei.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetFilePath`aufrufen.

`GetFilePath`ist eine von drei `CFileFind` Member-Funktionen, die eine Form des Datei namens zurückgeben. In der folgenden Liste werden die drei und deren Unterschiede beschrieben:

- [GetFileName](#getfilename) gibt den Dateinamen zurück, einschließlich der Erweiterung. Wenn Sie z. `GetFileName` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Dateiname *MyFile. txt*zurückgegeben.

- `GetFilePath`Gibt den gesamten Pfad für die Datei zurück. Wenn beispielsweise aufgerufen `GetFilePath` wird, um eine Benutzer Meldung über die `c:\myhtml\myfile.txt` Datei zu generieren, `c:\myhtml\myfile.txt`wird der Dateipfad zurückgegeben.

- [GetFileTitle](#getfiletitle) gibt den Dateinamen mit Ausnahme der Dateierweiterung zurück. Wenn Sie z. `GetFileTitle` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Datei Titel *MyFile*zurückgegeben.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetFileName](#getfilename).

##  <a name="getfiletitle"></a>CFileFind:: GetFileTitle

Mit dieser Member-Funktion können Sie den Titel der gefundenen Datei abrufen.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Rückgabewert

Der Titel der Datei.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetFileTitle`aufrufen.

`GetFileTitle`ist eine von drei `CFileFind` Member-Funktionen, die eine Form des Datei namens zurückgeben. In der folgenden Liste werden die drei und deren Unterschiede beschrieben:

- [GetFileName](#getfilename) gibt den Dateinamen zurück, einschließlich der Erweiterung. Wenn Sie z. `GetFileName` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Dateiname *MyFile. txt*zurückgegeben.

- [GetFilePath](#getfilepath) gibt den gesamten Pfad für die Datei zurück. Wenn Sie z. `GetFilePath` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Dateipfad *c:\myhtml\myfile.txt*zurückgegeben.

- `GetFileTitle`Gibt den Dateinamen mit Ausnahme der Dateierweiterung zurück. Wenn Sie z. `GetFileTitle` b. aufrufen, um eine Benutzer Meldung über die Datei *c:\myhtml\myfile.txt* zu generieren, wird der Datei Titel *MyFile*zurückgegeben.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetFileName](#getfilename).

##  <a name="getfileurl"></a>CFileFind:: getfileurl

Rufen Sie diese Member-Funktion auf, um die angegebene URL abzurufen.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Rückgabewert

Die komplette URL.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetFileURL`aufrufen.

`GetFileURL`ähnelt der Member-Funktion [GetFilePath](#getfilepath), mit dem Unterschied, dass Sie die URL im `file://path`Formular zurückgibt. Wenn Sie z. `GetFileURL` b. aufrufen, um die gesamte URL für *MyFile. txt* abzurufen, wird die URL `file://c:\myhtml\myfile.txt`zurückgegeben.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetFileName](#getfilename).

##  <a name="getlastaccesstime"></a>CFileFind:: GetLastAccessTime

Mit dieser Member-Funktion wird die Uhrzeit abgerufen, zu der die angegebene Datei zuletzt aufgerufen wurde.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parameter

*refTime*<br/>
Ein Verweis auf ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt.

*pTimeStamp*<br/>
Ein Zeiger auf eine [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Struktur, die die Uhrzeit des letzten Zugriffs auf die Datei enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich; 0, wenn nicht erfolgreich. `GetLastAccessTime`gibt 0 (null) nur dann zurück, wenn [FindNextFile](#findnextfile) für dieses `CFileFind` Objekt noch nie aufgerufen wurde.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetLastAccessTime`aufrufen.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den von dieser Funktion zurückgegebenen Zeitstempel zu implementieren. Diese Funktion gibt möglicherweise denselben Wert zurück, der von anderen Zeitstempel Funktionen zurückgegeben wird, wenn das zugrunde liegende Dateisystem oder der Server das Beibehalten des Zeit Attributs nicht unterstützt. Weitere Informationen zu Zeitformaten finden Sie in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur. Bei einigen Betriebssystemen befindet sich die zurückgegebene Zeit in der lokalen Zeitzone des Computers, in dem sich die Datei befindet. Weitere Informationen finden Sie in der Win32 [filetimetolocalfiletime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="getlastwritetime"></a>CFileFind:: getlastschreitetime

Mit dieser Member-Funktion können Sie den Zeitpunkt der letzten Änderung der Datei abrufen.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parameter

*pTimeStamp*<br/>
Ein Zeiger auf eine [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) -Struktur, die den Zeitpunkt enthält, zu dem zuletzt in die Datei geschrieben wurde.

*refTime*<br/>
Ein Verweis auf ein [ctime](../../atl-mfc-shared/reference/ctime-class.md) -Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn erfolgreich; 0, wenn nicht erfolgreich. `GetLastWriteTime`gibt 0 (null) nur dann zurück, wenn [FindNextFile](#findnextfile) für dieses `CFileFind` Objekt noch nie aufgerufen wurde.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetLastWriteTime`aufrufen.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den von dieser Funktion zurückgegebenen Zeitstempel zu implementieren. Diese Funktion gibt möglicherweise denselben Wert zurück, der von anderen Zeitstempel Funktionen zurückgegeben wird, wenn das zugrunde liegende Dateisystem oder der Server das Beibehalten des Zeit Attributs nicht unterstützt. Weitere Informationen zu Zeitformaten finden Sie in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur. Bei einigen Betriebssystemen befindet sich die zurückgegebene Zeit in der lokalen Zeitzone des Computers, in dem sich die Datei befindet. Weitere Informationen finden Sie in der Win32 [filetimetolocalfiletime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="getlength"></a>CFileFind:: GetLength

Mit dieser Member-Funktion können Sie die Länge der gefundenen Datei in Bytes abrufen.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der gefundenen Datei in Bytes.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetLength`aufrufen.

`GetLength`verwendet die Win32-Struktur [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) , um den Wert der Dateigröße in Bytes zu erhalten und zurückzugeben.

> [!NOTE]
>  Ab MFC 7,0 `GetLength` unterstützt ganzzahlige Typen mit 64 Bit. Bereits vorhandener Code, der mit dieser neueren Version der Bibliothek erstellt wurde, führt möglicherweise zu abkürzen von Warnungen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

##  <a name="getroot"></a>CFileFind:: GetRoot

Mit dieser Member-Funktion können Sie den Stamm der gefundenen Datei abrufen.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Rückgabewert

Der Stamm der aktiven Suche.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetRoot`aufrufen.

Diese Member-Funktion gibt den laufwerkspezifizierer und Pfadnamen zurück, die zum Starten einer Suche verwendet werden. Wenn Sie z. b. [FindFile](#findfile) `*.dat` mit `GetRoot` aufrufen, wird eine leere Zeichenfolge zurückgegeben. Übergeben `c:\windows\system\*.dll`eines Pfades (z. b.) an Ergebnisse `GetRoot` , die `FindFile` zurück `c:\windows\system\`geben.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetFileName](#getfilename).

##  <a name="isarchived"></a>CFileFind:: isarchiviert

Mit dieser Member-Funktion können Sie ermitteln, ob die gefundene Datei archiviert ist.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Anwendungen markieren eine zu sichernde oder zu entfernende Archivdatei mit FILE_ATTRIBUTE_ARCHIVE, einem in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur identifizierten Datei Attribut.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsArchived`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="iscompressed"></a>CFileFind:: IsCompressed

Mit dieser Member-Funktion können Sie ermitteln, ob die gefundene Datei komprimiert ist.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Eine komprimierte Datei ist mit FILE_ATTRIBUTE_COMPRESSED gekennzeichnet, einem in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur identifizierten Datei Attribut. Bei einer Datei gibt dieses Attribut an, dass alle Daten in der Datei komprimiert sind. Bei einem Verzeichnis gibt dieses Attribut an, dass die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse ist.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsCompressed`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="isdirectory"></a>CFileFind:: IsDirectory

Mit dieser Member-Funktion können Sie ermitteln, ob die gefundene Datei ein Verzeichnis ist.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Eine Datei, die ein Verzeichnis ist, ist mit FILE_ATTRIBUTE_DIRECTORY einem Datei Attribut gekennzeichnet, das in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur angegeben ist.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsDirectory`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

Dieses kleine Programm rekurtiert jedes Verzeichnis auf C:\. Laufwerk und druckt den Namen des Verzeichnisses.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

##  <a name="isdots"></a>CFileFind:: isdots

Mit dieser Member-Funktion können Sie beim Durchlaufen von Dateien auf die aktuellen Verzeichnis-und übergeordneten Verzeichnis Marker testen.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die gefundene Datei den Namen "." oder ".." hat, was darauf hinweist, dass es sich bei der gefundenen Datei tatsächlich um ein Verzeichnis handelt. Andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsDots`aufrufen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: IsDirectory](#isdirectory).

##  <a name="ishidden"></a>CFileFind:: IsHidden

Mit dieser Member-Funktion können Sie ermitteln, ob die gefundene Datei ausgeblendet ist.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Ausgeblendete Dateien, die mit FILE_ATTRIBUTE_HIDDEN markiert sind, ein Datei Attribut, das in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur angegeben ist. Eine versteckte Datei ist nicht in einer normalen Verzeichnis Auflistung enthalten.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsHidden`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="isnormal"></a>CFileFind:: isnormal

Mit dieser Member-Funktion können Sie ermitteln, ob es sich bei der gefundenen Datei um eine normale Datei handelt.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Mit FILE_ATTRIBUTE_NORMAL markierte Dateien, ein Datei Attribut, das in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur angegeben ist. Für eine normale Datei sind keine anderen Attribute festgelegt. Alle anderen Dateiattribute Überschreiben dieses Attribut.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsNormal`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="isreadonly"></a>CFileFind:: isschreib Only

Mit dieser Member-Funktion können Sie ermitteln, ob die gefundene Datei schreibgeschützt ist.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Eine schreibgeschützte Datei wird mit FILE_ATTRIBUTE_READONLY gekennzeichnet, einem in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur identifizierten Datei Attribut. Anwendungen können eine solche Datei lesen, aber nicht in diese schreiben oder Sie löschen.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsReadOnly`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="issystem"></a>CFileFind:: IsSystem

Mit dieser Member-Funktion können Sie ermitteln, ob es sich bei der gefundenen Datei um eine Systemdatei handelt.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Eine Systemdatei ist mit FILE_ATTRIBUTE_SYSTEM gekennzeichnet, einem in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur identifizierten Datei Attribut. Eine Systemdatei ist Teil des Betriebssystems oder wird ausschließlich von diesem verwendet.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsSystem`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="istemporary"></a>CFileFind:: IsTemporary

Mit dieser Member-Funktion können Sie ermitteln, ob es sich bei der gefundenen Datei um eine temporäre Datei handelt.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Eine temporäre Datei ist mit FILE_ATTRIBUTE_TEMPORARY gekennzeichnet, einem in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur identifizierten Datei Attribut. Eine temporäre Datei wird für den temporären Speicher verwendet. Anwendungen sollten nur dann in die Datei schreiben, wenn dies unbedingt erforderlich ist. Die meisten Daten der Datei verbleiben im Arbeitsspeicher, ohne auf die Medien geleert zu werden, da die Datei in Kürze gelöscht wird.

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsTemporary`aufrufen.

Eine komplette Liste der Dateiattribute finden Sie in der [memesmask](#matchesmask) -Member-Funktion.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFileFind:: GetLength](#getlength).

##  <a name="m_ptm"></a>CFileFind:: m_pTM

Zeiger auf ein `CAtlTransactionManager` -Objekt.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Hinweise

##  <a name="matchesmask"></a>CFileFind:: matchesmask

Mit dieser Member-Funktion können Sie die Dateiattribute der gefundenen Datei testen.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Parameter

*dwMask*<br/>
Gibt ein oder mehrere Dateiattribute an, die in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur für die gefundene Datei identifiziert werden. Um nach mehreren Attributen zu suchen, verwenden Sie den bitweisen or&#124;()-Operator. Eine beliebige Kombination der folgenden Attribute ist akzeptabel:

- FILE_ATTRIBUTE_ARCHIVE bei der Datei handelt es sich um eine Archivdatei. Anwendungen verwenden dieses Attribut, um Dateien für die Sicherung oder Entfernung zu markieren.

- FILE_ATTRIBUTE_COMPRESSED die Datei oder das Verzeichnis ist komprimiert. Bei einer Datei bedeutet dies, dass alle Daten in der Datei komprimiert sind. Bei einem Verzeichnis bedeutet dies, dass die Komprimierung der Standardwert für neu erstellte Dateien und Unterverzeichnisse ist.

- FILE_ATTRIBUTE_DIRECTORY die Datei ist ein Verzeichnis.

- FILE_ATTRIBUTE_NORMAL für die Datei sind keine anderen Attribute festgelegt. Dieses Attribut ist nur gültig, wenn es allein verwendet wird. Alle anderen Dateiattribute Überschreiben dieses Attribut.

- FILE_ATTRIBUTE_HIDDEN die Datei ist ausgeblendet. Er darf nicht in eine gewöhnliche Verzeichnis Auflistung eingeschlossen werden.

- FILE_ATTRIBUTE_READONLY die Datei ist schreibgeschützt. Anwendungen können die Datei lesen, aber nicht schreiben oder löschen.

- FILE_ATTRIBUTE_SYSTEM die Datei ist Teil von oder wird ausschließlich vom Betriebs System verwendet.

- FILE_ATTRIBUTE_TEMPORARY die Datei wird für den temporären Speicher verwendet. Anwendungen sollten nur dann in die Datei schreiben, wenn dies unbedingt erforderlich ist. Die meisten Daten der Datei verbleiben im Arbeitsspeicher, ohne auf die Medien geleert zu werden, da die Datei in Kürze gelöscht wird.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, nennen Sie die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `MatchesMask`aufrufen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)<br/>
[CGopherFileFind-Klasse](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
