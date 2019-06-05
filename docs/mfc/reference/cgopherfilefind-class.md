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
ms.openlocfilehash: bced5a95f65713915a1f06094bfe059db79aab2d
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503638"
---
# <a name="cgopherfilefind-class"></a>CGopherFileFind-Klasse

Unterstützt die Internetsuche nach Dateien auf Gopherservern.

> [!NOTE]
>  Die Klassen `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` und deren Member sind veraltet, da, nicht auf der Windows XP-Plattform funktionieren, während sie weiterhin auf frühere Plattformen funktionieren.

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
|[CGopherFileFind::FindFile](#findfile)|Sucht nach einer Datei auf einem Gopher-Server.|
|[CGopherFileFind::FindNextFile](#findnextfile)|Weiterhin eine Dateisuche in einem vorherigen Aufruf von [FindFile](#findfile).|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Ruft den Zeitpunkt, an den die angegebene Datei erstellt wurde.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Ruft den Zeitpunkt an, die, dem die angegebene Datei zuletzt in geschrieben wurde.|
|[CGopherFileFind::GetLength](#getlength)|Ruft die Länge der gefundenen Datei in Bytes ab.|
|[CGopherFileFind::GetLocator](#getlocator)|Abrufen einer `CGopherLocator` Objekt.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Ruft den Namen eines Bildschirms Gopher.|
|[CGopherFileFind::IsDots](#isdots)|Testet, ob die aktuelle Verzeichnis und das übergeordnete Verzeichnis-Marker, während des Durchlaufens der Dateien.|

## <a name="remarks"></a>Hinweise

`CGopherFileFind` enthält die Member-Funktionen, die eine Suche zu starten, suchen Sie nach einer Datei und Rückgabe-URL von einer Datei.

Andere MFC-Klassen für Internet und die lokale Datei durchsucht enthalten [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) und [CFileFind](../../mfc/reference/cfilefind-class.md). Zusammen mit `CGopherFileFind`, diese Klassen bieten einen nahtlose Mechanismus für den Benutzer zum Suchen von Dateien, die unabhängig von der Server-Protokoll, Dateityp oder Position (einem lokalen Computer oder einem Remoteserver.) Beachten Sie, dass es keine MFC-Klasse ist für die Suche auf HTTP-Servern, da HTTP nicht die direkten Bearbeitung erforderlich, die für Suchvorgänge unterstützt.

> [!NOTE]
> `CGopherFileFind` unterstützt nicht die folgenden Memberfunktionen der Basisklasse [CFileFind](../../mfc/reference/cfilefind-class.md):

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Darüber hinaus wird bei mit `CGopherFileFind`, `CFileFind` Memberfunktion [IsDots](../../mfc/reference/cfilefind-class.md#isdots) ist immer "false".

Weitere Informationen zur Verwendung von `CGopherFileFind` und die andere WinInet-Klassen finden Sie im Artikel [Internet zu programmieren, mit WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Anforderungen

**Header:** afxinet.h

##  <a name="cgopherfilefind"></a>  CGopherFileFind::CGopherFileFind

Diese Memberfunktion wird aufgerufen, um das Erstellen einer `CGopherFileFind` Objekt.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parameter

*pConnection*<br/>
Ein Zeiger auf eine [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) Objekt.

*dwContext*<br/>
Der Kontextbezeichner für den Vorgang. Finden Sie unter **"Hinweise"** für Weitere Informationen zu *DwContext*.

### <a name="remarks"></a>Hinweise

Der Standardwert für *DwContext* wird gesendet, von MFC über die `CGopherFileFind` -Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) -Objekt, das erstellt die `CGopherFileFind` Objekt. Beim Erstellen einer `CGopherFileFind` Objekt, Sie können angeben, überschreiben die Standardeinstellung, um den Kontextbezeichner auf einen Wert Ihrer Wahl festgelegt. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zu Status für das Objekt mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen zu den Kontextbezeichner.

##  <a name="findfile"></a>  CGopherFileFind:: FindFile

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

*refLocator*<br/>
Ein Verweis auf eine [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) Objekt.

*pstrString*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Dateinamen enthält.

*dwFlags*<br/>
Die Flags, die beschreibt, wie diese Sitzung behandelt. Die gültigen Flags sind:

- INTERNET_FLAG_RELOAD Abrufen der Daten aus den Remoteserver, auch wenn es lokal zwischengespeichert werden.

- INTERNET_FLAG_DONT_CACHE Zwischenspeichern nicht der Daten, entweder lokal oder in der Gateways.

- Sichere Transaktionen bei der Übertragung mit Secure Sockets Layer "oder" Prozent INTERNET_FLAG_SECURE anfordern Dieses Flag gilt nur für HTTP-Anforderungen.

- INTERNET_FLAG_USE_EXISTING Wenn möglich, alle bestehenden Verbindungen mit dem Server wiederverwenden, für den neuen `FindFile` Anforderungen, anstatt eine neue Sitzung für jede Anforderung erstellen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null). Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Hinweise

Nach dem Aufruf `FindFile` um das erste Gopher-Objekt abzurufen, rufen Sie [FindNextFile](#findnextfile) zum Abrufen von nachfolgenden Gopher-Dateien.

##  <a name="findnextfile"></a>  CGopherFileFind:: FindNextFile

Rufen Sie diese Memberfunktion zum Fortsetzen einer der Dateisuche begonnen, die mit einem Aufruf von [CGopherFileFind:: FindFile](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn weitere Dateien vorhanden sind; NULL, wenn die Datei im Verzeichnis das letzte ist oder ein Fehler aufgetreten ist. Um erweiterte Fehlerinformationen abzurufen, rufen Sie die Win32-Funktion [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror). Wenn die Datei die letzte Datei im Verzeichnis ist, oder wenn keine übereinstimmenden Dateien gefunden werden können, die `GetLastError` Funktionsergebnis ERROR_NO_MORE_FILES.

##  <a name="getcreationtime"></a>  CGopherFileFind::GetCreationTime

Ruft den Zeitpunkt der Erstellung für die aktuelle Datei ab.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parameter

*pTimeStamp*<br/>
Ein Zeiger auf eine [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) -Struktur, enthält die Zeit, die die Datei erstellt wurde.

*refTime*<br/>
Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; 0, wenn der Vorgang fehlschlägt. `GetCreationTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, dazu `CGopherFileFind` Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetCreationTime`.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen zu implementieren. Diese Funktion kann den gleichen Wert von anderen Time Stamp-Funktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das zeitattribut beibehalten zurückgeben. Finden Sie unter den [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) Struktur für Informationen zu Zeitformaten. Bei einigen Betriebssystemen ist die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, wenn sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API für Weitere Informationen.

##  <a name="getlastaccesstime"></a>  CGopherFileFind::GetLastAccessTime

Ruft den Zeitpunkt des letzten Zugriffs auf die angegebene Datei.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Parameter

*refTime*<br/>
Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.

*pTimeStamp*<br/>
Ein Zeiger auf eine [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) Struktur, die beim Zugriff auf die Datei wurde zuletzt enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; 0, wenn der Vorgang fehlschlägt. `GetLastAccessTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, dazu `CGopherFileFind` Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastAccessTime`.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen zu implementieren. Diese Funktion kann den gleichen Wert von anderen Time Stamp-Funktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das zeitattribut beibehalten zurückgeben. Finden Sie unter den [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) Struktur für Informationen zu Zeitformaten. Bei einigen Betriebssystemen ist die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, wenn sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API für Weitere Informationen.

##  <a name="getlastwritetime"></a>  CGopherFileFind::GetLastWriteTime

Ruft den letzten Zeitpunkt, die die Datei geändert wurde.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Parameter

*pTimeStamp*<br/>
Ein Zeiger auf eine [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) -Struktur, enthält die Datei zum letzten geschrieben wurde.

*refTime*<br/>
Ein Verweis auf eine [CTime](../../atl-mfc-shared/reference/ctime-class.md) Objekt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn erfolgreich; 0, wenn der Vorgang fehlschlägt. `GetLastWriteTime` Gibt 0 zurück, wenn nur [FindNextFile](#findnextfile) noch nie aufgerufen wurde, dazu `CGopherFileFind` Objekt.

### <a name="remarks"></a>Hinweise

Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `GetLastWriteTime`.

> [!NOTE]
>  Nicht alle Dateisysteme verwenden die gleiche Semantik, um den Zeitstempel, der von dieser Funktion zurückgegebenen zu implementieren. Diese Funktion kann den gleichen Wert von anderen Time Stamp-Funktionen zurückgegeben werden, wenn der zugrunde liegenden Dateisystem oder Server nicht unterstützt wird das zeitattribut beibehalten zurückgeben. Finden Sie unter den [Win32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) Struktur für Informationen zu Zeitformaten. Bei einigen Betriebssystemen ist die zurückgegebene Zeit, in der Zeit, die Zone lokal auf dem Computer wurden, wenn sich die Datei befindet. Finden Sie unter Win32 [FileTimeToLocalFileTime](/windows/desktop/api/fileapi/nf-fileapi-filetimetolocalfiletime) -API für Weitere Informationen.

##  <a name="getlength"></a>  CGopherFileFind::GetLength

Rufen Sie diese Memberfunktion, um die Länge in Bytes, die gefundene Datei abrufen.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der gefundenen Datei in Bytes.

### <a name="remarks"></a>Hinweise

`GetLength` verwendet die Win32-Struktur [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) , den Wert der Dateigröße in Bytes abzurufen.

> [!NOTE]
>  Ab MFC 7.0 `GetLength` 64-Bit-Integer-Typen unterstützt. Bereits vorhandene-Code, der durch diese neuere Version der Bibliothek kann Abschneiden Warnungen führen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (der Implementierung der Basisklasse).

##  <a name="getlocator"></a>  CGopherFileFind::GetLocator

Rufen Sie diese Memberfunktion zum Abrufen der [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) -Objekt, [FindFile](#findfile) verwendet, um die Gopherdatei zu suchen.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CGopherLocator`-Objekt.

##  <a name="getscreenname"></a>  CGopherFileFind::GetScreenName

Rufen Sie diese Memberfunktion um den Namen des Bildschirms Gopher abzurufen.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Rückgabewert

Der Name des Bildschirms Gopher.

##  <a name="isdots"></a>  CGopherFileFind::IsDots

Testet, ob die aktuelle Verzeichnis und das übergeordnete Verzeichnis-Marker, während des Durchlaufens der Dateien.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die gefundene Datei den Namen hat "."oder"..", was bedeutet, dass die gefundene Datei um ein Verzeichnis ist. Andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen Sie [FindNextFile](#findnextfile) mindestens einmal vor dem Aufruf `IsDots`.

## <a name="see-also"></a>Siehe auch

[CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CFtpFileFind-Klasse](../../mfc/reference/cftpfilefind-class.md)<br/>
[CFileFind-Klasse](../../mfc/reference/cfilefind-class.md)<br/>
[CInternetFile-Klasse](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile-Klasse](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile-Klasse](../../mfc/reference/chttpfile-class.md)
