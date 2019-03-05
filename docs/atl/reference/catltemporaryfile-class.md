---
title: CAtlTemporaryFile-Klasse
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
ms.openlocfilehash: c1da5037deb0143c6d05009baccc8c1553616028
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288189"
---
# <a name="catltemporaryfile-class"></a>CAtlTemporaryFile-Klasse

Diese Klasse stellt Methoden bereit, für die Erstellung und Verwendung einer temporären Datei.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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
|[CAtlTemporaryFile::Close](#close)|Rufen Sie diese Methode, um eine temporäre Datei zu schließen und seinen Inhalt löschen oder speichern Sie sie unter dem angegebenen Dateinamen.|
|[CAtlTemporaryFile::Create](#create)|Rufen Sie diese Methode zum Erstellen einer temporären Datei.|
|[CAtlTemporaryFile::Flush](#flush)|Rufen Sie diese Methode, um zu erzwingen, dass alle Daten verbleiben in der Dateipuffer, in die temporäre Datei geschrieben werden.|
|[CAtlTemporaryFile::GetPosition](#getposition)|Rufen Sie diese Methode, um die aktuelle Zeigerposition für die Datei zu erhalten.|
|[CAtlTemporaryFile::GetSize](#getsize)|Rufen Sie diese Methode zum Abrufen der Größe in Byte der temporären Datei.|
|[CAtlTemporaryFile::HandsOff](#handsoff)|Rufen Sie diese Methode, um die Zuordnung aufheben, die Datei aus dem `CAtlTemporaryFile` Objekt.|
|[CAtlTemporaryFile::HandsOn](#handson)|Rufen Sie diese Methode, um eine vorhandene temporäre Datei zu öffnen, und positionieren Sie den Zeiger am Ende der Datei.|
|[CAtlTemporaryFile::LockRange](#lockrange)|Rufen Sie diese Methode, um einen Bereich in der Datei, um zu verhindern, dass andere Prozesse darauf zugreifen zu sperren.|
|[CAtlTemporaryFile::Read](#read)|Rufen Sie diese Methode zum Lesen von Daten aus der temporären Datei, die an der durch den Dateizeiger angegebenen Position ab.|
|[CAtlTemporaryFile::Seek](#seek)|Rufen Sie diese Methode, um den Dateizeiger, der die temporäre Datei zu verschieben.|
|[CAtlTemporaryFile::SetSize](#setsize)|Rufen Sie diese Methode, um die Größe der temporären Datei festzulegen.|
|[CAtlTemporaryFile::TempFileName](#tempfilename)|Rufen Sie diese Methode, um den Namen der temporären Datei zurückzugeben.|
|[CAtlTemporaryFile::UnlockRange](#unlockrange)|Rufen Sie diese Methode, um eine Region der temporären Datei zu entsperren.|
|[CAtlTemporaryFile::Write](#write)|Rufen Sie diese Methode zum Schreiben von Daten in die temporäre Datei, die an der durch den Dateizeiger angegebenen Position ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlTemporaryFile::operator HANDLE](#operator_handle)|Gibt ein Handle für die temporäre Datei zurück.|

## <a name="remarks"></a>Hinweise

`CAtlTemporaryFile` erleichtert Ihnen zum Erstellen und verwenden eine temporäre Datei. Die Datei wird automatisch mit dem Namen, geöffnet, geschlossen und gelöscht. Wenn Sie den Inhalt der Datei erforderlich sind, nachdem die Datei geschlossen wird, können sie in eine neue Datei mit dem angegebenen Namen gespeichert werden.

## <a name="requirements"></a>Anforderungen

**Header:** atlfile.h

## <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="catltemporaryfile"></a>  CAtlTemporaryFile::CAtlTemporaryFile

Der Konstruktor.

```
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Hinweise

Eine Datei ist nicht tatsächlich geöffnet, bis eine aufgerufen wird [CAtlTemporaryFile::Create](#create).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

##  <a name="dtor"></a>  CAtlTemporaryFile:: ~ CAtlTemporaryFile

Der Destruktor.

```
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor ruft [CAtlTemporaryFile::Close](#close).

##  <a name="close"></a>  CAtlTemporaryFile::Close

Rufen Sie diese Methode, um eine temporäre Datei zu schließen und seinen Inhalt löschen oder speichern Sie sie unter dem angegebenen Dateinamen.

```
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Parameter

*szNewName*<br/>
Der Name für die neue Datei auf den Inhalt in die temporäre Datei speichern. Wenn dieses Argument NULL ist, werden die Inhalte der temporären Datei gelöscht.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="create"></a>  CAtlTemporaryFile::Create

Rufen Sie diese Methode zum Erstellen einer temporären Datei.

```
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Parameter

*pszDir*<br/>
Der Pfad für die temporäre Datei. Wenn diese NULL ist [GetTempPath](/windows/desktop/api/fileapi/nf-fileapi-gettemppatha) wird aufgerufen, um dem angegebenen Pfad zuweisen.

*dwDesiredAccess*<br/>
Der gewünschte Zugriff. Finden Sie unter *DwDesiredAccess* in [CreateFile](/windows/desktop/api/fileapi/nf-fileapi-createfilea) im Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="flush"></a>  CAtlTemporaryFile::Flush

Rufen Sie diese Methode, um zu erzwingen, dass alle Daten verbleiben in der Dateipuffer, in die temporäre Datei geschrieben werden.

```
HRESULT Flush() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Ähnlich wie [CAtlTemporaryFile::HandsOff](#handsoff), außer dass die Datei nicht geschlossen wird.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="getposition"></a>  CAtlTemporaryFile::GetPosition

Rufen Sie diese Methode, um die aktuelle Zeigerposition für die Datei zu erhalten.

```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Die Position in Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Verwenden Sie zum Ändern der Position des Dateizeigers [CAtlTemporaryFile::Seek](#seek).

##  <a name="getsize"></a>  CAtlTemporaryFile::GetSize

Rufen Sie diese Methode zum Abrufen der Größe in Byte der temporären Datei.

```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Parameter

*nLen*<br/>
Die Anzahl der Bytes in der Datei.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="handsoff"></a>  CAtlTemporaryFile::HandsOff

Rufen Sie diese Methode, um die Zuordnung aufheben, die Datei aus dem `CAtlTemporaryFile` Objekt.

```
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

`HandsOff` und [CAtlTemporaryFile::HandsOn](#handson) werden verwendet, um die Zuordnung aufheben, die Datei aus dem Objekt, und bei Bedarf erneut an. `HandsOff` wird erzwingen, dass alle Daten verbleiben in der Dateipuffer, in die temporäre Datei geschrieben werden soll, und schließen Sie die Datei. Wenn schließen und die Datei dauerhaft gelöscht werden sollen, oder Sie verwenden möchten, schließen und den Inhalt der Datei mit einem angegebenen Namen, [CAtlTemporaryFile::Close](#close).

##  <a name="handson"></a>  CAtlTemporaryFile::HandsOn

Rufen Sie diese Methode, um eine vorhandene temporäre Datei zu öffnen, und positionieren Sie den Zeiger am Ende der Datei.

```
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

[CAtlTemporaryFile::HandsOff](#handsoff) und `HandsOn` werden verwendet, um die Zuordnung aufheben, die Datei aus dem Objekt, und bei Bedarf erneut an.

##  <a name="lockrange"></a>  CAtlTemporaryFile::LockRange

Rufen Sie diese Methode, um einen Bereich in der temporären Datei, um zu verhindern, dass andere Prozesse darauf zugreifen zu sperren.

```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Die Position in der Datei, in dem die Sperre begonnen werden soll.

*nCount*<br/>
Die Länge des Bytebereichs gesperrt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Das Sperren von Bytes in einer Datei verhindert den Zugriff auf diese Bytes durch andere Prozesse. Sie können mehr als einer Region in einer Datei sperren, aber keine sich überschneidenden Bereiche sind zulässig. Verwenden, um einen Bereich erfolgreich zu entsperren, [CAtlTemporaryFile::UnlockRange](#unlockrange), sicherstellen des Bytebereichs entspricht genau der Region, die zuvor gesperrt war. `LockRange` benachbarte Bereiche zusammen nicht; Wenn zwei gesperrte Bereiche aneinandergrenzen, müssen Sie jeweils separat entsperren.

##  <a name="operator_handle"></a>  CAtlTemporaryFile::operator HANDLE

Gibt ein Handle für die temporäre Datei zurück.

```
operator HANDLE() throw();
```

##  <a name="read"></a>  CAtlTemporaryFile::Read

Rufen Sie diese Methode zum Lesen von Daten aus der temporären Datei, die an der durch den Dateizeiger angegebenen Position ab.

```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Parameter

*pBuffer*<br/>
Zeiger auf den Puffer, der die Daten erhält, die aus der Datei gelesen werden.

*nBufSize*<br/>
Die Puffergröße in Byte.

*nBytesRead*<br/>
Die Anzahl von gelesenen Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlFile::Read](../../atl/reference/catlfile-class.md#read). Rufen Sie zum Ändern der Position des Dateizeigers [CAtlTemporaryFile::Seek](#seek).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="seek"></a>  CAtlTemporaryFile::Seek

Rufen Sie diese Methode, um den Dateizeiger, der die temporäre Datei zu verschieben.

```
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Parameter

*nOffset*<br/>
Der Offset in Bytes, aus der vom Ausgangspunkt *DwFrom.*

*dwFrom*<br/>
Der Anfangspunkt (FILE_BEGIN, FILE_CURRENT oder FILE_END).

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlFile::Seek](../../atl/reference/catlfile-class.md#seek). Rufen Sie zum Abrufen der aktuellen Position der Datei Zeiger [CAtlTemporaryFile::GetPosition](#getposition).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

##  <a name="setsize"></a>  CAtlTemporaryFile::SetSize

Rufen Sie diese Methode, um die Größe der temporären Datei festzulegen.

```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Parameter

*nNewLen*<br/>
Die neue Länge der Datei in Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlFile::SetSize](../../atl/reference/catlfile-class.md#setsize). Bei der Rückgabe wird der Dateizeiger am Ende der Datei positioniert.

##  <a name="tempfilename"></a>  CAtlTemporaryFile::TempFileName

Rufen Sie diese Methode, um den Namen der temporären Datei zurückzugeben.

```
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die LPCTSTR verweist auf den Dateinamen zurück.

### <a name="remarks"></a>Hinweise

Der Dateiname wird in generiert [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile) durch einen Aufruf der [GetTempFile](/windows/desktop/api/fileapi/nf-fileapi-gettempfilenamea)Windows SDK-Funktion. Die Erweiterung wird immer "TFR" für die temporäre Datei sein.

##  <a name="unlockrange"></a>  CAtlTemporaryFile::UnlockRange

Rufen Sie diese Methode, um eine Region der temporären Datei zu entsperren.

```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Die Position in der Datei, in dem das Entsperren begonnen werden soll.

*nCount*<br/>
Die Länge des Bytebereichs entsperrt werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlFile::UnlockRange](../../atl/reference/catlfile-class.md#unlockrange).

##  <a name="write"></a>  CAtlTemporaryFile::Write

Rufen Sie diese Methode zum Schreiben von Daten in die temporäre Datei, die an der durch den Dateizeiger angegebenen Position ab.

```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Parameter

*pBuffer*<br/>
Der Puffer mit Daten, die in die Datei geschrieben werden.

*nBufSize*<br/>
Die Anzahl der Bytes, aus dem Puffer übertragen werden sollen.

*pnBytesWritten*<br/>
Die Anzahl der geschriebenen Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Aufrufe [CAtlFile::Write](../../atl/reference/catlfile-class.md#write).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CAtlTemporaryFile::CAtlTemporaryFile](#catltemporaryfile).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CAtlFile-Klasse](../../atl/reference/catlfile-class.md)
