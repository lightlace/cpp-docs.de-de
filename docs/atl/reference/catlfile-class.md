---
title: Klasse "-Klasse"
ms.date: 11/04/2016
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
ms.openlocfilehash: 784086b1c2edef5eb0de3bba4a97d1e3cc6272e7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497821"
---
# <a name="catlfile-class"></a>Klasse "-Klasse"

Diese Klasse stellt einen schmalen Wrapper um die Windows-Datei Behandlungs-API bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CAtlFile : public CHandle
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Datendatei::](#catlfile)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlFile::Create](#create)|Rufen Sie diese Methode auf, um eine Datei zu erstellen oder zu öffnen.|
|[Datendatei:: Flush](#flush)|Rufen Sie diese Methode auf, um die Puffer für die Datei zu löschen und alle gepufferten Daten in die Datei zu schreiben.|
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|Mit dieser Methode können Sie die Ergebnisse eines überlappenden Vorgangs in der Datei abrufen.|
|[CAtlFile::GetPosition](#getposition)|Ruft diese Methode auf, um die aktuelle Dateizeiger Position aus der Datei abzurufen.|
|[CAtlFile::GetSize](#getsize)|Mit dieser Methode können Sie die Größe der Datei in Byte abrufen.|
|[CAtlFile::LockRange](#lockrange)|Wenn Sie diese Methode aufrufen, wird ein Bereich in der Datei gesperrt, um zu verhindern, dass andere Prozesse darauf zugreifen.|
|["": Lesen](#read)|Ruft diese Methode auf, um Daten aus einer Datei zu lesen, beginnend an der durch den Dateizeiger gekennzeichneten Position.|
|[CAtlFile::Seek](#seek)|Mit dieser Methode wird der Dateizeiger der Datei verschoben.|
|[CAtlFile::SetSize](#setsize)|Ruft diese Methode auf, um die Größe der Datei festzulegen.|
|[CAtlFile::UnlockRange](#unlockrange)|Mit dieser Methode wird ein Bereich der Datei entsperrt.|
|[CAtlFile::Write](#write)|Ruft diese Methode auf, um Daten in die Datei zu schreiben, beginnend an der durch den Dateizeiger gekennzeichneten Position.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAtlFile::m_pTM](#m_ptm)|Zeiger auf `CAtlTransactionManager` Objekt|

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Klasse, wenn die Datei Behandlungsanforderungen relativ einfach sind, aber mehr Abstraktion als die Windows-API erforderlich ist, ohne dass MFC-Abhängigkeiten eingeschlossen werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CHandle](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Anforderungen

**Header:** atlfile. h

##  <a name="catlfile"></a>Datendatei::

Der Konstruktor.

```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>Parameter

*datei*<br/>
Das Datei Objekt.

*hFile*<br/>
Das Datei handle.

*pTM*<br/>
Zeiger auf CAtlTransactionManager-Objekt

### <a name="remarks"></a>Hinweise

Der Kopierkonstruktor überträgt den Besitz des Datei Handles vom ursprünglichen `CAtlFile` -Objekt an das neu erstellte-Objekt.

##  <a name="create"></a>Erstellungs Datei:: Create

Rufen Sie diese Methode auf, um eine Datei zu erstellen oder zu öffnen.

```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```

### <a name="parameters"></a>Parameter

*szFilename*<br/>
Der Dateiname.

*dwDesiredAccess*<br/>
Der gewünschte Zugriff. Weitere Informationen finden Sie in der Windows SDK unter *dwDesiredAccess* in der [Datei](/windows/win32/api/fileapi/nf-fileapi-createfilew) "".

*dwShareMode*<br/>
Der Freigabe Modus. Weitere Informationen finden Sie unter `CreateFile` *dwsharemode* in.

*dwCreationDisposition*<br/>
Die Erstellungs Disposition. Weitere Informationen finden Sie unter *dwkreationdisposition* in `CreateFile`.

*dwFlagsAndAttributes*<br/>
Die Flags und Attribute. Weitere Informationen finden Sie unter *dwflagsandattribute* in `CreateFile`.

*lpsa*<br/>
Die Sicherheits Attribute. Weitere Informationen finden Sie unter *lpsecurityattribute* in `CreateFile`.

*hTemplateFile*<br/>
Die Vorlagen Datei. Weitere Informationen finden Sie unter *htemplatefile* in `CreateFile`.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft "up [File](/windows/win32/api/fileapi/nf-fileapi-createfilew) " auf, um die Datei zu erstellen oder zu öffnen.

##  <a name="flush"></a>Datendatei:: Flush

Rufen Sie diese Methode auf, um die Puffer für die Datei zu löschen und alle gepufferten Daten in die Datei zu schreiben.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [FlushFileBuffers](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers) auf, um gepufferte Daten in die Datei zu leeren.

##  <a name="getoverlappedresult"></a>"", "", "".

Mit dieser Methode können Sie die Ergebnisse eines überlappenden Vorgangs in der Datei abrufen.

```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Parameter

*pOverlapped*<br/>
Die überlappende Struktur. Weitere Informationen finden Sie unter *lpoverllapp* in [gepoverlappedresult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) in der Windows SDK.

*dwBytesTransferred*<br/>
Die übertragenen Bytes. Weitere Informationen finden Sie unter *lpnummeriofbytestransferred* in `GetOverlappedResult`.

*bWait*<br/>
Die Wait-Option. Siehe *bwait* in `GetOverlappedResult`.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [gedeverlappedresult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) auf, um die Ergebnisse eines überlappenden Vorgangs für die Datei zu erhalten.

##  <a name="getposition"></a>"-Datei": "Get Position"

Mit dieser Methode können Sie die aktuelle Dateizeiger Position abrufen.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Die Position in Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) auf, um die aktuelle Position des Dateizeigers zu erhalten.

##  <a name="getsize"></a>Datendatei:: GetSize

Mit dieser Methode können Sie die Größe der Datei in Byte abrufen.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parameter

*nLen*<br/>
Die Anzahl der Bytes in der Datei.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [GetFileSize](/windows/win32/api/fileapi/nf-fileapi-getfilesize) auf, um die Größe der Datei in Bytes zu erhalten.

##  <a name="lockrange"></a>Datendatei:: lockrange

Wenn Sie diese Methode aufrufen, wird ein Bereich in der Datei gesperrt, um zu verhindern, dass andere Prozesse darauf zugreifen.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Die Position in der Datei, an der die Sperre beginnen soll.

*nCount*<br/>
Die Länge des zu sperrenden Byte Bereichs.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [lockfile](/windows/win32/api/fileapi/nf-fileapi-lockfile) auf, um einen Bereich in der Datei zu sperren. Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als einen Bereich einer Dateisperren, aber es sind keine überlappenden Bereiche zulässig. Wenn Sie eine [Region mithilfe von](#unlockrange)"" mit "" "" "" mit "" "". `LockRange`angrenzende Bereiche werden nicht zusammengeführt. Wenn zwei gesperrte Bereiche nebeneinander liegen, müssen Sie diese separat entsperren.

##  <a name="m_ptm"></a>Datendatei:: m_pTM

Zeiger auf ein `CAtlTransactionManager` -Objekt.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Hinweise

##  <a name="read"></a>"": Lesen

Ruft diese Methode auf, um Daten aus einer Datei zu lesen, beginnend an der durch den Dateizeiger gekennzeichneten Position.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```

### <a name="parameters"></a>Parameter

*pBuffer*<br/>
Zeiger auf den Puffer, der die aus der Datei gelesenen Daten empfängt.

*nBufSize*<br/>
Die Puffergröße in Byte.

*nBytesRead*<br/>
Die Anzahl von gelesenen Bytes.

*pOverlapped*<br/>
Die überlappende Struktur. Weitere Informationen finden Sie unter *IpOverlapped* in [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile) im Windows SDK.

*pfnCompletionRoutine*<br/>
Die Vervollständigungs Routine. Weitere Informationen finden Sie unter *lpCompletionRoutine* in "read [fileex](/windows/win32/api/fileapi/nf-fileapi-readfileex) " in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Die ersten drei Formular Aufrufe " [Infofile](/windows/win32/api/fileapi/nf-fileapi-readfile)", die letzte " [infofileex](/windows/win32/api/fileapi/nf-fileapi-readfileex) " zum Lesen von Daten aus der Datei. Verwenden Sie "", um [den Dateizeiger](#seek) zu verschieben.

##  <a name="seek"></a>-Datei-Datei:: Seek

Mit dieser Methode wird der Dateizeiger der Datei verschoben.

```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parameter

*nOffset*<br/>
Der Offset vom Startpunkt, der von *dwfrom*angegeben wird.

*dwFrom*<br/>
Der Anfangspunkt (FILE_BEGIN, FILE_CURRENT oder FILE_END).

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) auf, um den Dateizeiger zu verschieben.

##  <a name="setsize"></a>Datendatei:: SetSize

Ruft diese Methode auf, um die Größe der Datei festzulegen.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parameter

*nNewLen*<br/>
Die neue Länge der Datei in Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) und [SetEndOfFile](/windows/win32/api/fileapi/nf-fileapi-setendoffile) auf, um die Größe der Datei festzulegen. Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.

##  <a name="unlockrange"></a>"": Unlockrange

Mit dieser Methode wird ein Bereich der Datei entsperrt.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Die Position in der Datei, an der die Entsperrung beginnen soll.

*nCount*<br/>
Die Länge des zu entsperrenden Byte Bereichs.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft [unlockfile](/windows/win32/api/fileapi/nf-fileapi-unlockfile) auf, um einen Bereich der Datei zu entsperren.

##  <a name="write"></a>"Datendatei:: Schreiben"

Ruft diese Methode auf, um Daten in die Datei zu schreiben, beginnend an der durch den Dateizeiger gekennzeichneten Position.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```

### <a name="parameters"></a>Parameter

*pBuffer*<br/>
Der Puffer, der die Daten enthält, die in die Datei geschrieben werden sollen.

*nBufSize*<br/>
Die Anzahl der Bytes, die aus dem Puffer übertragen werden sollen.

*pOverlapped*<br/>
Die überlappende Struktur. Weitere Informationen finden Sie unter *lpoverllapp* in " [Write File](/windows/win32/api/fileapi/nf-fileapi-writefile) " im Windows SDK.

*pfnCompletionRoutine*<br/>
Die Vervollständigungs Routine. Weitere Informationen finden Sie unter " *lpCompletionRoutine* " in " [Write fileex](/windows/win32/api/fileapi/nf-fileapi-writefileex) " in der Windows SDK.

*pnBytesWritten*<br/>
Die geschriebenen Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

In den ersten drei Formularen wird " [Write File](/windows/win32/api/fileapi/nf-fileapi-writefile)" aufgerufen, der letzte ruft "Write [fileex](/windows/win32/api/fileapi/nf-fileapi-writefileex) " auf, um Daten in die Datei zu schreiben. Verwenden Sie "", um [den Dateizeiger](#seek) zu verschieben.

## <a name="see-also"></a>Siehe auch

[Marquee-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CHandle-Klasse](../../atl/reference/chandle-class.md)
