---
title: Klasse von "Klasse"
ms.date: 11/04/2016
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: d6a7a61d1886a264f8575e8d7325d6639d21338d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497712"
---
# <a name="catltemporaryfile-class"></a>Klasse von "Klasse"

Diese Klasse stellt Methoden zum Erstellen und Verwenden einer temporären Datei bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen, die im Windows-Runtime ausgeführt werden, nicht verwendet werden.

## <a name="syntax"></a>Syntax

```
class CAtlTemporaryFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile)|Der Konstruktor.|
|[CAtlTemporaryFile::~CAtlTemporaryFile](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAtlTemporaryFile::Close](#close)|Mit dieser Methode können Sie eine temporäre Datei schließen und ihre Inhalte entweder löschen oder unter dem angegebenen Dateinamen speichern.|
|[CAtlTemporaryFile::Create](#create)|Rufen Sie diese Methode auf, um eine temporäre Datei zu erstellen.|
|["":](#flush)|Mit dieser Methode können Sie erzwingen, dass alle im Datei Puffer verbleibenden Daten in die temporäre Datei geschrieben werden.|
|[CAtlTemporaryFile::GetPosition](#getposition)|Mit dieser Methode können Sie die aktuelle Dateizeiger Position abrufen.|
|[CAtlTemporaryFile::GetSize](#getsize)|Mit dieser Methode können Sie die Größe der temporären Datei in Byte abrufen.|
|[CAtlTemporaryFile::HandsOff](#handsoff)|Mit dieser Methode wird die Zuordnung der Datei `CAtlTemporaryFile` zum-Objekt aufgehoben.|
|[CAtlTemporaryFile::HandsOn](#handson)|Diese Methode wird aufgerufen, um eine vorhandene temporäre Datei zu öffnen und den Zeiger am Ende der Datei zu positionieren.|
|[CAtlTemporaryFile::LockRange](#lockrange)|Wenn Sie diese Methode aufrufen, wird ein Bereich in der Datei gesperrt, um zu verhindern, dass andere Prozesse darauf zugreifen.|
|["": Lesen](#read)|Mit dieser Methode können Sie Daten aus der temporären Datei beginnend an der durch den Dateizeiger gekennzeichneten Position lesen.|
|[CAtlTemporaryFile::Seek](#seek)|Mit dieser Methode können Sie den Dateizeiger der temporären Datei verschieben.|
|[CAtlTemporaryFile::SetSize](#setsize)|Mit dieser Methode können Sie die Größe der temporären Datei festlegen.|
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Mit dieser Methode wird der Name der temporären Datei zurückgegeben.|
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Mit dieser Methode wird ein Bereich der temporären Datei entsperrt.|
|[CAtlTemporaryFile::Write](#write)|Ruft diese Methode auf, um Daten in die temporäre Datei zu schreiben, beginnend an der durch den Dateizeiger gekennzeichneten Position.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[""-Operator handle](#operator_handle)|Gibt ein Handle für die temporäre Datei zurück.|

## <a name="remarks"></a>Hinweise

`CAtlTemporaryFile`macht es einfach, eine temporäre Datei zu erstellen und zu verwenden. Die Datei wird automatisch benannt, geöffnet, geschlossen und gelöscht. Wenn der Inhalt der Datei nach dem Schließen der Datei erforderlich ist, können Sie in einer neuen Datei mit einem angegebenen Namen gespeichert werden.

## <a name="requirements"></a>Anforderungen

**Header:** atlfile. h

## <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

##  <a name="catltemporaryfile"></a>"" "" "".

Der Konstruktor.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Hinweise

Eine Datei wird erst [geöffnet, wenn](#create)ein Aufrufen von "" für "" "" "" ".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

##  <a name="dtor"></a>"" "" "".

Der Destruktor.

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor Ruft die [Datei](#close)"".

##  <a name="close"></a>"":

Mit dieser Methode können Sie eine temporäre Datei schließen und ihre Inhalte entweder löschen oder unter dem angegebenen Dateinamen speichern.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Parameter

*szNewName*<br/>
Der Name der neuen Datei, in der der Inhalt der temporären Datei gespeichert werden soll. Wenn dieses Argument NULL ist, wird der Inhalt der temporären Datei gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

##  <a name="create"></a>"": Create

Rufen Sie diese Methode auf, um eine temporäre Datei zu erstellen.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Parameter

*pszDir*<br/>
Der Pfad für die temporäre Datei. Wenn dieser Wert NULL ist, wird [GetTempPath](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) aufgerufen, um einen Pfad zuzuweisen.

*dwDesiredAccess*<br/>
Der gewünschte Zugriff. Weitere Informationen finden Sie in der Windows SDK unter *dwDesiredAccess* in der [Datei](/windows/win32/api/fileapi/nf-fileapi-createfilew) "".

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

##  <a name="flush"></a>"":

Mit dieser Methode können Sie erzwingen, dass alle im Datei Puffer verbleibenden Daten in die temporäre Datei geschrieben werden.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ähnlich wie [bei der](#handsoff)Datei "" von "" mit "", mit dem Unterschied, dass die Datei nicht geschlossen ist.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

##  <a name="getposition"></a>' ' ' ' ' ' ' ' ' ' ' ' ' '

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

Um die Position des Dateizeigers zu ändern, verwenden Sie " [chanltemporaryfile:: Seek](#seek)".

##  <a name="getsize"></a>"" "" ".

Mit dieser Methode können Sie die Größe der temporären Datei in Byte abrufen.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parameter

*nLen*<br/>
Die Anzahl der Bytes in der Datei.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

##  <a name="handsoff"></a>"" "".

Mit dieser Methode wird die Zuordnung der Datei `CAtlTemporaryFile` zum-Objekt aufgehoben.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`HandsOff`und [die Datei "](#handson) " mit "" ("" "), um die Zuordnung der Datei zum Objekt aufzuheben und bei Bedarf erneut anzufügen. `HandsOff`erzwingt, dass alle im Datei Puffer verbleibenden Daten in die temporäre Datei geschrieben werden, und schließt dann die Datei. Wenn Sie die Datei dauerhaft schließen und löschen möchten, oder wenn Sie den Inhalt der Datei mit einem bestimmten Namen schließen und beibehalten möchten [, verwenden Sie die Datei "](#close)".

##  <a name="handson"></a>"" "" "" ".

Diese Methode wird aufgerufen, um eine vorhandene temporäre Datei zu öffnen und den Zeiger am Ende der Datei zu positionieren.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

"" Mit "" "", "" und `HandsOn` "" wird verwendet, um die Zuordnung der Datei zum Objekt [aufzuheben und bei](#handsoff) Bedarf erneut anzufügen.

##  <a name="lockrange"></a>"' ' ' ' ' ' ' ' ': ' '

Wenn Sie diese Methode aufrufen, wird ein Bereich in der temporären Datei gesperrt, um zu verhindern, dass andere Prozesse darauf zugreifen.

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

Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als einen Bereich einer Dateisperren, aber es sind keine überlappenden Bereiche zulässig. Wenn Sie einen Bereich erfolgreich entsperren möchten [, verwenden Sie](#unlockrange)"" "" "" "" "" "". `LockRange`angrenzende Bereiche werden nicht zusammengeführt. Wenn zwei gesperrte Bereiche nebeneinander liegen, müssen Sie diese separat entsperren.

##  <a name="operator_handle"></a>""-Operator handle

Gibt ein Handle für die temporäre Datei zurück.

```
operator HANDLE() throw();
```

##  <a name="read"></a>"": Lesen

Mit dieser Methode können Sie Daten aus der temporären Datei beginnend an der durch den Dateizeiger gekennzeichneten Position lesen.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Parameter

*pBuffer*<br/>
Zeiger auf den Puffer, der die aus der Datei gelesenen Daten empfängt.

*nBufSize*<br/>
Die Puffergröße in Byte.

*nBytesRead*<br/>
Die Anzahl von gelesenen Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft ["](../../atl/reference/catlfile-class.md#read)" "". Um die Position des Dateizeigers zu ändern, nennen Sie " [chanltemporaryfile:: Seek](#seek)".

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

##  <a name="seek"></a>"":

Mit dieser Methode können Sie den Dateizeiger der temporären Datei verschieben.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parameter

*nOffset*<br/>
Der Offset in Bytes vom Startpunkt, der von *dwfrom* angegeben wird.

*dwFrom*<br/>
Der Anfangspunkt (FILE_BEGIN, FILE_CURRENT oder FILE_END).

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft ["](../../atl/reference/catlfile-class.md#seek)" "". Rufen Sie zum Abrufen der aktuellen Position des Dateizeigers [die Datei "](#getposition)" mit "".

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

##  <a name="setsize"></a>"" "".

Mit dieser Methode können Sie die Größe der temporären Datei festlegen.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parameter

*nNewLen*<br/>
Die neue Länge der Datei in Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft ["](../../atl/reference/catlfile-class.md#setsize)" "". Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.

##  <a name="tempfilename"></a>"" "" ".

Mit dieser Methode wird der Name der temporären Datei zurückgegeben.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den LPCTSTR zurück, der auf den Dateinamen zeigt.

### <a name="remarks"></a>Hinweise

Der Dateiname [wird in der Datei "](#catltemporaryfile) " mit der Funktion " [gettempfile](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)Windows SDK" generiert. Die Dateierweiterung ist für die temporäre Datei immer "TFR".

##  <a name="unlockrange"></a>' ' ' ' ' ' ' ' ' ' ' ' ' ' '

Mit dieser Methode wird ein Bereich der temporären Datei entsperrt.

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

Ruft ["](../../atl/reference/catlfile-class.md#unlockrange)" "".

##  <a name="write"></a>"":

Ruft diese Methode auf, um Daten in die temporäre Datei zu schreiben, beginnend an der durch den Dateizeiger gekennzeichneten Position.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Parameter

*pBuffer*<br/>
Der Puffer, der die Daten enthält, die in die Datei geschrieben werden sollen.

*nBufSize*<br/>
Die Anzahl der Bytes, die aus dem Puffer übertragen werden sollen.

*pnBytesWritten*<br/>
Die Anzahl der geschriebenen Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ruft ["](../../atl/reference/catlfile-class.md#write)" "".

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für die [Datei](#catltemporaryfile)"".

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CAtlFile-Klasse](../../atl/reference/catlfile-class.md)
