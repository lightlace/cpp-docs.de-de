---
title: COleStreamFile-Klasse
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
ms.openlocfilehash: 25d3da4ac9092fe53e84e446e93ff7aa030e6709
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577540"
---
# <a name="colestreamfile-class"></a>COleStreamFile-Klasse

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
|[COleStreamFile::Attach](#attach)|Ordnet einen Stream mit dem Objekt.|
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Erstellt einen Datenstrom aus dem globalen Arbeitsspeicher, und ordnet es dem Objekt.|
|[COleStreamFile::CreateStream](#createstream)|Erstellt einen Datenstrom und ordnet es dem Objekt.|
|[COleStreamFile::Detach](#detach)|Hebt die Zuordnung des Streams, aus dem Objekt.|
|[COleStreamFile::GetStream](#getstream)|Gibt den aktuellen Stream zurück.|
|[COleStreamFile::OpenStream](#openstream)|Sicher öffnet einen Datenstrom und ordnet es dem Objekt.|

## <a name="remarks"></a>Hinweise

Ein `IStorage` Objekt muss vorhanden sein, bevor der Stream geöffnet oder erstellt, wenn es sich um einen Speicherstream ist werden kann.

`COleStreamFile` Objekte bearbeitet werden, genau wie [CFile](../../mfc/reference/cfile-class.md) Objekte.

Weitere Informationen zum Bearbeiten von Datenströmen und speichern können, finden Sie im Artikel [Container: Verbunddateien](../../mfc/containers-compound-files.md)...

Weitere Informationen finden Sie unter [IStream](/windows/desktop/api/objidl/nn-objidl-istream) und [IStorage](/windows/desktop/api/objidl/nn-objidl-istorage) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="attach"></a>  COleStreamFile::Attach

Ordnet den angegebenen OLE-Stream mit der `COleStreamFile` Objekt.

```
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>Parameter

*lpStream*<br/>
Verweist auf die OLE-Datenstrom (`IStream`) mit dem Objekt zugeordnet werden soll. Darf nicht NULL sein.

### <a name="remarks"></a>Hinweise

Das Objekt darf nicht bereits ein OLE-Datenstrom zugeordnet sein.

Weitere Informationen finden Sie unter [IStream](/windows/desktop/api/objidl/nn-objidl-istream) im Windows SDK.

##  <a name="colestreamfile"></a>  COleStreamFile::COleStreamFile

Erstellt ein `COleStreamFile`-Objekt.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>Parameter

*lpStream*<br/>
Zeiger auf die OLE-Stream mit dem Objekt zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Wenn *LpStream* NULL ist, das Objekt ist nicht verknüpft mit einem OLE-Stream, andernfalls das Objekt den angegebenen OLE-Stream zugeordnet ist.

Weitere Informationen finden Sie unter [IStream](/windows/desktop/api/objidl/nn-objidl-istream) im Windows SDK.

##  <a name="creatememorystream"></a>  COleStreamFile::CreateMemoryStream

Sichere erstellt einen neuen Datenstrom aus dem globalen, freigegebenen Arbeitsspeicher, in denen ein Fehler für eine normale, erwartete Bedingung ist.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*pError*<br/>
Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder NULL, der den Abschlussstatus des Vorgangs erstellen angibt. Geben Sie diesen Parameter, wenn zum Überwachen von möglicher Ausnahmen, die generiert werden, indem versucht wird, den Stream erstellt werden sollen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Stream erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Der Speicher wird vom OLE-Subsystem zugeordnet.

Weitere Informationen finden Sie unter [CreateStreamOnHGlobal](/windows/desktop/api/combaseapi/nf-combaseapi-createstreamonhglobal) im Windows SDK.

##  <a name="createstream"></a>  COleStreamFile::CreateStream

Sichere erstellt einen neuen Stream im bereitgestellten Speicher-Objekt, in denen ein Fehler für eine normale, erwartete Bedingung ist, ein.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpStorage*<br/>
Verweist auf das OLE-Speicher-Objekt, das den zu erstellenden Datenstroms enthält. Darf nicht NULL sein.

*lpszStreamName*<br/>
Der Name des Datenstroms erstellt werden. Darf nicht NULL sein.

*nOpenFlags*<br/>
Der Zugriffsmodus verwenden, wenn Sie den Stream zu öffnen. Exklusive, Lese-/Schreibzugriff, und erstellen Sie die Modi als Standard verwendet wird. Eine vollständige Liste der verfügbaren Modi, finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder NULL. Geben Sie diesen Parameter, wenn zum Überwachen von möglicher Ausnahmen, die generiert werden, indem versucht wird, den Stream erstellt werden sollen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Stream erfolgreich erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Datei Ausnahme wird ausgelöst, wenn die Open schlägt fehl, und *pError* nicht NULL ist.

Weitere Informationen finden Sie unter [IStorage::CreateStream](/windows/desktop/api/objidl/nf-objidl-istorage-createstream) im Windows SDK.

##  <a name="detach"></a>  COleStreamFile::Detach

Hebt die Zuordnung des Streams, aus dem Objekt ohne das Schließen des Streams.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Datenstrom (`IStream`), die dem Objekt zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Der Datenstrom muss auf eine andere Art geschlossen werden, bevor das Programm beendet wird.

Weitere Informationen finden Sie unter [IStream](/windows/desktop/api/objidl/nn-objidl-istream) im Windows SDK.

##  <a name="getstream"></a>  COleStreamFile::GetStream

Rufen Sie diese Funktion, um einen Zeiger auf den aktuellen Stream zurückzugeben.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den aktuellen Stream-Schnittstelle ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream)).

##  <a name="openstream"></a>  COleStreamFile::OpenStream

Öffnet einen vorhandenen Datenstrom.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpStorage*<br/>
Verweist auf das OLE-Speicher-Objekt mit den Stream geöffnet werden. Darf nicht NULL sein.

*lpszStreamName*<br/>
Der Name des Datenstroms geöffnet werden. Darf nicht NULL sein.

*nOpenFlags*<br/>
Der Zugriffsmodus verwenden, wenn Sie den Stream zu öffnen. Exklusive und Lese-/Schreibzugriff-Modus als Standard verwendet wird. Eine vollständige Liste der verfügbaren Modi finden Sie unter [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pError*<br/>
Verweist auf eine [CFileException](../../mfc/reference/cfileexception-class.md) Objekt oder NULL. Geben Sie diesen Parameter, wenn zum Überwachen von möglicher Ausnahmen generiert, indem Sie versuchen, den Stream geöffnet werden sollen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Stream erfolgreich geöffnet wird; andernfalls 0.

### <a name="remarks"></a>Hinweise

Eine Datei Ausnahme wird ausgelöst, wenn die Open schlägt fehl, und *pError* nicht NULL ist.

Weitere Informationen finden Sie unter [IStorage::OpenStream](/windows/desktop/api/objidl/nf-objidl-istorage-openstream) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

