---
title: CGopherFileFind-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: 55c40fc04934f00ccb541a01cce611d9532bee1a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506174"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind-Klasse

Unterstützt die Internetsuche nach Dateien auf Gopherservern.

> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind` undihreMembersindveraltet,daSienichtaufderWindowsXP-Plattformfunktionieren,aberSiefunktionierenweiterhinauf`CGopherLocator` früheren Plattformen.

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
|[CGopherFileFind::FindFile](#findfile)|Sucht eine Datei auf einem Gopher-Server.|
|[CGopherFileFind::FindNextFile](#findnextfile)|Setzt eine Dateisuche von einem vorherigen Befehl von " [FindFile](#findfile)" fort.|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Ruft den Zeitpunkt ab, zu dem die angegebene Datei erstellt wurde.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei ab.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Ruft den Zeitpunkt ab, zu dem zuletzt in die angegebene Datei geschrieben wurde.|
|[CGopherFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei in Bytes ab.|
|[CGopherFileFind::GetLocator](#getlocator)|Ein `CGopherLocator` -Objekt zu erhalten.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Ruft den Namen eines Gopher-Bildschirms ab.|
|[CGopherFileFind::IsDots](#isdots)|Testet beim Durchlaufen von Dateien auf die aktuellen Verzeichnis-und übergeordneten Verzeichnis Marker.|

## <a name="remarks"></a>Hinweise

`CGopherFileFind`umfasst Member-Funktionen, die eine Suche starten, eine Datei suchen und die URL einer Datei zurückgeben.

Andere MFC-Klassen, die für das Internet und die lokale Datei durchsucht wurden, umfassen [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). In Kombi `CGopherFileFind`Nieren diese Klassen eine nahtlose Methode, mit der der Benutzer nach bestimmten Dateien suchen kann, unabhängig vom Server Protokoll, Dateityp oder Speicherort (entweder auf einem lokalen Computer oder auf einem Remote Server). Beachten Sie, dass es keine MFC-Klasse für die Suche von HTTP-Servern gibt, da HTTP die von Such Vorgängen benötigte direkte Dateibearbeitung nicht unterstützt.

> [!NOTE]
> `CGopherFileFind`die folgenden Member-Funktionen der Basisklasse [CFileFind](../../mfc/reference/cfilefind-class.md)werden von nicht unterstützt:

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Außerdem ist bei Verwendung mit `CGopherFileFind`der `CFileFind` Member-Funktions- [isdots](../../mfc/reference/cfilefind-class.md#isdots) immer false.

Weitere Informationen zur Verwendung `CGopherFileFind` von und der anderen WinInet-Klassen finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cgopherfilefind"></a>CGopherFileFind:: CGopherFileFind

Diese Member-Funktion wird aufgerufen, um `CGopherFileFind` ein-Objekt zu erstellen.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pConnection*<br/>
Ein Zeiger auf ein [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) -Objekt.

*dwContext*<br/>
Der Kontext Bezeichner für den Vorgang. Weitere Informationen zu *dwcontext*finden Sie unter " **Hinweise** ".

### <a name="remarks"></a>Hinweise

Der Standardwert für *dwcontext* wird von MFC an das `CGopherFileFind` -Objekt aus dem [cinternetzession](../../mfc/reference/cinternetsession-class.md) -Objekt gesendet, `CGopherFileFind` das das Objekt erstellt hat. Wenn Sie ein `CGopherFileFind` -Objekt erstellen, können Sie die Standardeinstellung überschreiben, um den Kontext Bezeichner auf einen Wert Ihrer Wahl festzulegen. Der Kontext Bezeichner wird an [cinternetzession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zurückgegeben, um den Status für das Objekt bereitzustellen, mit dem es identifiziert wird. Weitere Informationen finden [Sie im Artikel Internet First Steps: WinInet](../../mfc/wininet-basics.md) für weitere Informationen zum Kontext Bezeichner.

##  <a name="findfile"></a>CGopherFileFind:: FindFile

Diese Member-Funktion wird aufgerufen, um eine Gopher-Datei zu suchen.

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

*refLocator*<br/>
Ein Verweis auf ein [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) -Objekt.

*pstrString*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält.

*dwFlags*<br/>
Die Flags, die beschreiben, wie diese Sitzung behandelt werden soll. Gültige Flags:

- INTERNET_FLAG_RELOAD Sie sollten die Daten vom Remote Server auch dann erhalten, wenn Sie lokal zwischengespeichert werden.

- INTERNET_FLAG_DONT_CACHE speichern Sie die Daten weder lokal noch in Gateways.

- INTERNET_FLAG_SECURE fordern Sie mit Secure Sockets Layer oder PCT sichere Transaktionen an. Dieses Flag gilt nur für HTTP-Anforderungen.

- INTERNET_FLAG_USE_EXISTING verwenden Sie nach Möglichkeit die vorhandenen Verbindungen mit dem Server für neue `FindFile` Anforderungen, anstatt eine neue Sitzung für jede Anforderung zu erstellen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, nennen Sie die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Hinweise

Nachdem Sie `FindFile` aufgerufen haben, um das erste Gopher-Objekt abzurufen, können Sie [FindNextFile](#findnextfile) aufrufen, um nachfolgende Gopher-Dateien abzurufen.

##  <a name="findnextfile"></a>CGopherFileFind:: FindNextFile

Diese Member-Funktion wird aufgerufen, um eine Dateisuche fortzusetzen, die mit einem [CGopherFileFind:: FindFile](#findfile)-Befehl begonnen wurde.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn weitere Dateien vorhanden sind. 0 (null), wenn die gefundene Datei das letzte im Verzeichnis ist, oder, wenn ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, nennen Sie die Win32-Funktion [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Wenn es sich bei der gefundenen Datei um die letzte Datei im Verzeichnis handelt oder wenn keine übereinstimmenden Dateien gefunden `GetLastError` werden können, gibt die Funktion ERROR_NO_MORE_FILES zurück.

##  <a name="getcreationtime"></a>CGopherFileFind:: getkreationtime

Ruft den Erstellungs Zeitpunkt für die aktuelle Datei ab.

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

Ungleich NULL, wenn erfolgreich; 0, wenn nicht erfolgreich. `GetCreationTime`gibt 0 (null) nur dann zurück, wenn [FindNextFile](#findnextfile) für dieses `CGopherFileFind` Objekt noch nie aufgerufen wurde.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetCreationTime`aufrufen.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den von dieser Funktion zurückgegebenen Zeitstempel zu implementieren. Diese Funktion gibt möglicherweise denselben Wert zurück, der von anderen Zeitstempel Funktionen zurückgegeben wird, wenn das zugrunde liegende Dateisystem oder der Server das Beibehalten des Zeit Attributs nicht unterstützt. Weitere Informationen zu Zeitformaten finden Sie in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur. Bei einigen Betriebssystemen befindet sich die zurückgegebene Zeit in der lokalen Zeitzone des Computers, in dem sich die Datei befindet. Weitere Informationen finden Sie in der Win32 [filetimetolocalfiletime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API.

##  <a name="getlastaccesstime"></a>CGopherFileFind:: GetLastAccessTime

Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei ab.

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

Ungleich NULL, wenn erfolgreich; 0, wenn nicht erfolgreich. `GetLastAccessTime`gibt 0 (null) nur dann zurück, wenn [FindNextFile](#findnextfile) für dieses `CGopherFileFind` Objekt noch nie aufgerufen wurde.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetLastAccessTime`aufrufen.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den von dieser Funktion zurückgegebenen Zeitstempel zu implementieren. Diese Funktion gibt möglicherweise denselben Wert zurück, der von anderen Zeitstempel Funktionen zurückgegeben wird, wenn das zugrunde liegende Dateisystem oder der Server das Beibehalten des Zeit Attributs nicht unterstützt. Weitere Informationen zu Zeitformaten finden Sie in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur. Bei einigen Betriebssystemen befindet sich die zurückgegebene Zeit in der lokalen Zeitzone des Computers, in dem sich die Datei befindet. Weitere Informationen finden Sie in der Win32 [filetimetolocalfiletime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API.

##  <a name="getlastwritetime"></a>CGopherFileFind:: getlastschreitetime

Ruft den Zeitpunkt ab, zu dem die Datei zuletzt geändert wurde.

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

Ungleich NULL, wenn erfolgreich; 0, wenn nicht erfolgreich. `GetLastWriteTime`gibt 0 (null) nur dann zurück, wenn [FindNextFile](#findnextfile) für dieses `CGopherFileFind` Objekt noch nie aufgerufen wurde.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `GetLastWriteTime`aufrufen.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den von dieser Funktion zurückgegebenen Zeitstempel zu implementieren. Diese Funktion gibt möglicherweise denselben Wert zurück, der von anderen Zeitstempel Funktionen zurückgegeben wird, wenn das zugrunde liegende Dateisystem oder der Server das Beibehalten des Zeit Attributs nicht unterstützt. Weitere Informationen zu Zeitformaten finden Sie in der [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) -Struktur. Bei einigen Betriebssystemen befindet sich die zurückgegebene Zeit in der lokalen Zeitzone des Computers, in dem sich die Datei befindet. Weitere Informationen finden Sie in der Win32 [filetimetolocalfiletime](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API.

##  <a name="getlength"></a>CGopherFileFind:: GetLength

Mit dieser Member-Funktion können Sie die Länge der gefundenen Datei in Byte abrufen.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge (in Byte) der gefundenen Datei.

### <a name="remarks"></a>Hinweise

`GetLength`verwendet die Win32-Struktur [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) , um den Wert der Dateigröße in Bytes zu erhalten.

> [!NOTE]
>  Ab MFC 7,0 `GetLength` unterstützt ganzzahlige Typen mit 64 Bit. Zuvor vorhandener Code, der mit dieser neueren Version der Bibliothek erstellt wurde, führt möglicherweise zu abkürzen von Warnungen.

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für [CFile:: GetLength](../../mfc/reference/cfile-class.md#getlength) (die Basisklassen Implementierung).

##  <a name="getlocator"></a>CGopherFileFind:: GetLocator

Mit dieser Member-Funktion können Sie das [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) -Objekt abrufen, das von [FindFile](#findfile) zum Suchen der Gopher-Datei verwendet wird.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CGopherLocator`-Objekt.

##  <a name="getscreenname"></a>CGopherFileFind:: getscreenname

Mit dieser Member-Funktion können Sie den Namen des Gopher-Bildschirms abrufen.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des Gopher-Bildschirms.

##  <a name="isdots"></a>CGopherFileFind:: isdots

Testet beim Durchlaufen von Dateien auf die aktuellen Verzeichnis-und übergeordneten Verzeichnis Marker.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die gefundene Datei den Namen "." oder ".." hat, was darauf hinweist, dass es sich bei der gefundenen Datei tatsächlich um ein Verzeichnis handelt. Andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie müssen [FindNextFile](#findnextfile) mindestens einmal aufrufen, bevor Sie `IsDots`aufrufen.

## <a name="see-also"></a>Siehe auch

[CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)<br/>
[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
