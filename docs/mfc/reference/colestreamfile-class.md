---
title: Colestreamfile-Klasse
ms.date: 11/04/2016
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
ms.openlocfilehash: 96e8fee71f02ea750fd8b33f41fd2fd517e9081e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503690"
---
# <a name="colestreamfile-class"></a>Colestreamfile-Klasse

Stellt einen Datenstream (`IStream`) in einer Verbunddatei als Teil einer strukturierten Speicherung (OLE Structured Storage) dar.

## <a name="syntax"></a>Syntax

```
class COleStreamFile : public CFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleStreamFile::COleStreamFile](#colestreamfile)|Erstellt ein `COleStreamFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleStreamFile::Attach](#attach)|Verknüpft einen Stream mit dem-Objekt.|
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Erstellt einen Stream aus dem globalen Speicher und ordnet ihn dem-Objekt zu.|
|[COleStreamFile::CreateStream](#createstream)|Erstellt einen Stream und ordnet ihn dem-Objekt zu.|
|[COleStreamFile::Detach](#detach)|Trennt den Datenstrom aus dem-Objekt.|
|[COleStreamFile::GetStream](#getstream)|Gibt den aktuellen Stream zurück.|
|[COleStreamFile::OpenStream](#openstream)|Öffnet einen Stream sicher und ordnet ihn dem-Objekt zu.|

## <a name="remarks"></a>Hinweise

Ein `IStorage` Objekt muss vorhanden sein, bevor der Stream geöffnet oder erstellt werden kann, es sei denn, es handelt sich um einen Speicherstream.

`COleStreamFile`Objekte werden genau wie [CFile](../../mfc/reference/cfile-class.md) -Objekte bearbeitet.

Weitere Informationen zum Bearbeiten von Streams und Speicher in finden Sie im Artikel [Container: Verbund Dateien](../../mfc/containers-compound-files.md)..

Weitere Informationen finden Sie unter [IStream](/windows/win32/api/objidl/nn-objidl-istream) und [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>Anforderungen

**Header:** Afxole. h

##  <a name="attach"></a>Colestreamfile:: Attach

Ordnet den bereitgestellten OLE-Stream `COleStreamFile` dem-Objekt zu.

```
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>Parameter

*lpStream*<br/>
Verweist auf den OLE-Stream`IStream`(), der dem-Objekt zugeordnet werden soll. Lässt keine NULL-Werte zu.

### <a name="remarks"></a>Hinweise

Das Objekt darf nicht bereits einem OLE-Stream zugeordnet sein.

Weitere Informationen finden Sie unter [IStream](/windows/win32/api/objidl/nn-objidl-istream) in der Windows SDK.

##  <a name="colestreamfile"></a>Colestreamfile:: colestreamfile

Erstellt ein `COleStreamFile`-Objekt.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>Parameter

*lpStream*<br/>
Zeiger auf den OLE-Stream, der dem-Objekt zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Wenn *lpstream* den Wert NULL hat, ist das Objekt keinem OLE-Stream zugeordnet; andernfalls wird das Objekt dem bereitgestellten OLE-Stream zugeordnet.

Weitere Informationen finden Sie unter [IStream](/windows/win32/api/objidl/nn-objidl-istream) in der Windows SDK.

##  <a name="creatememorystream"></a>Colestreamfile:: kreatememorystream

Erstellt sicher einen neuen Stream aus dem globalen, freigegebenen Speicher, bei dem ein Fehler eine normale, erwartete Bedingung ist.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*pError*<br/>
Verweist auf ein [CFileException](../../mfc/reference/cfileexception-class.md) -Objekt oder NULL, das den Abschluss Status des Erstellungs Vorgangs angibt. Geben Sie diesen Parameter an, wenn Sie mögliche Ausnahmen überwachen möchten, die beim Erstellen des Streams generiert wurden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Stream erfolgreich erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Arbeitsspeicher wird vom OLE-Subsystem zugeordnet.

Weitere Informationen finden Sie unter " [kreatestreamonhglobal](/windows/win32/api/combaseapi/nf-combaseapi-createstreamonhglobal) " in der Windows SDK.

##  <a name="createstream"></a>Colestreamfile:: foratestream

Erstellt sicher einen neuen Stream im bereitgestellten Speicher Objekt, bei dem ein Fehler eine normale, erwartete Bedingung ist.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpStorage*<br/>
Verweist auf das OLE-Speicher Objekt, das den zu erstellenden Stream enthält. Lässt keine NULL-Werte zu.

*lpszStreamName*<br/>
Der Name des zu erstellenden Streams. Lässt keine NULL-Werte zu.

*nOpenFlags*<br/>
Der Zugriffsmodus, der beim Öffnen des Streams verwendet werden soll. Exklusive, Lese-/Schreib-und Erstellungs Modi werden standardmäßig verwendet. Eine umfassende Liste der verfügbaren Modi finden Sie unter [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
Verweist auf ein [CFileException](../../mfc/reference/cfileexception-class.md) -Objekt oder auf NULL. Geben Sie diesen Parameter an, wenn Sie mögliche Ausnahmen überwachen möchten, die beim Erstellen des Streams generiert wurden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Stream erfolgreich erstellt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Datei Ausnahme wird ausgelöst, wenn das Öffnen fehlschlägt und *perror* nicht NULL ist.

Weitere Informationen finden Sie unter [IStorage:: foratestream](/windows/win32/api/objidl/nf-objidl-istorage-createstream) in der Windows SDK.

##  <a name="detach"></a>Colestreamfile::D Etach

Trennt den Datenstrom des Objekts, ohne den Stream zu schließen.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Stream (`IStream`), der dem-Objekt zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Der Stream muss auf andere Weise geschlossen werden, bevor das Programm beendet wird.

Weitere Informationen finden Sie unter [IStream](/windows/win32/api/objidl/nn-objidl-istream) in der Windows SDK.

##  <a name="getstream"></a>Colestreamfile:: GetStream

Mit dieser Funktion wird ein Zeiger auf den aktuellen Stream zurückgegeben.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle Stream-Schnittstelle ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)).

##  <a name="openstream"></a>Colestreamfile:: OpenStream

Öffnet einen vorhandenen Stream.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpStorage*<br/>
Verweist auf das OLE-Speicher Objekt, das den zu öffnenden Stream enthält. Lässt keine NULL-Werte zu.

*lpszStreamName*<br/>
Der Name des zu öffnenden Streams. Lässt keine NULL-Werte zu.

*nOpenFlags*<br/>
Der Zugriffsmodus, der beim Öffnen des Streams verwendet werden soll. Exklusive und Lese-/Schreibmodi werden standardmäßig verwendet. Eine komplette Liste der verfügbaren Modi finden Sie unter [CFile:: CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
Verweist auf ein [CFileException](../../mfc/reference/cfileexception-class.md) -Objekt oder auf NULL. Geben Sie diesen Parameter an, wenn Sie mögliche Ausnahmen überwachen möchten, die durch das Öffnen des Streams generiert werden.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn der Stream erfolgreich geöffnet wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Datei Ausnahme wird ausgelöst, wenn das Öffnen fehlschlägt und *perror* nicht NULL ist.

Weitere Informationen finden Sie unter [IStorage:: OpenStream](/windows/win32/api/objidl/nf-objidl-istorage-openstream) in der Windows SDK.

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
