---
title: CSharedFile-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: 74a34ec169868d3e28f78f33da38dbda21ef23b3
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502614"
---
# <a name="csharedfile-class"></a>CSharedFile-Klasse

Die von [CMemFile](../../mfc/reference/cmemfile-class.md)abgeleitete Klasse, die freigegebene Speicherdateien unterstützt.

## <a name="syntax"></a>Syntax

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSharedFile::CSharedFile](#csharedfile)|Erstellt ein `CSharedFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSharedFile::Detach](#detach)|Schließt die Shared Memory-Datei und gibt das Handle des zugehörigen Speicherblocks zurück.|
|[CSharedFile::SetHandle](#sethandle)|Fügt die Shared Memory-Datei an einen Speicherblock an.|

## <a name="remarks"></a>Hinweise

Speicherdateien Verhalten sich wie Datenträger Dateien. Der Unterschied besteht darin, dass eine Speicherdatei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert wird. Eine Speicherdatei eignet sich für eine schnelle temporäre Speicherung oder zum Übertragen von Rohdaten Bytes oder serialisierten Objekten zwischen unabhängigen Prozessen.

Freigegebene Speicherdateien unterscheiden sich von anderen Speicherdateien darin, dass der Arbeitsspeicher für Sie mit der [globalbelegc](/windows/win32/api/winbase/nf-winbase-globalalloc) -Windows-Funktion zugewiesen wird. Die `CSharedFile` -Klasse speichert Daten in einem Global zugeordneten Speicherblock ( `GlobalAlloc`erstellt mit), und dieser Speicherblock kann mithilfe von DDE, der Zwischenablage oder anderen OLE/com-Daten Übertragungs Vorgängen freigegeben werden `IDataObject`, z. b. mithilfe von.

`GlobalAlloc`Gibt ein HGLOBAL-Handle anstelle eines Zeigers auf den Arbeitsspeicher zurück, z. b. den von [malloc](../../c-runtime-library/reference/malloc.md)zurückgegebenen Zeiger. Das HGLOBAL-Handle wird in bestimmten Anwendungen benötigt. Wenn Sie z. b. Daten in die Zwischenablage einfügen möchten, benötigen Sie ein HGLOBAL-Handle.

`CSharedFile`verwendet keine im Speicher abgebildete Dateien, und die Daten können nicht direkt zwischen Prozessen freigegeben werden.

`CSharedFile`-Objekte können automatisch Ihren eigenen Arbeitsspeicher zuordnen. Sie können auch einen eigenen Speicherblock an das `CSharedFile` -Objekt anfügen, indem Sie [CSharedFile:: SetHandle](#sethandle)aufrufen. In beiden Fällen wird der Arbeitsspeicher für die Vergrößerung der Speicherdatei automatisch `nGrowBytes`in Schritten, wenn `nGrowBytes` nicht 0 (null) ist.

Weitere Informationen finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Datei Behandlung](../../c-runtime-library/file-handling.md) in der *Lauf Zeit Bibliotheks Referenz*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxadv. h

##  <a name="csharedfile"></a>CSharedFile:: CSharedFile

Erstellt ein `CSharedFile` -Objekt und ordnet ihm Speicher zu.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Parameter

*nAllocFlags*<br/>
Flags, die angeben, wie der Arbeitsspeicher zugeordnet werden soll. Eine Liste der gültigen Flagwerte finden Sie unter [globalzuordc](/windows/win32/api/winbase/nf-winbase-globalalloc) .

*nGrowBytes*<br/>
Das Inkrement der Arbeitsspeicher Belegung in Bytes.

##  <a name="detach"></a>CSharedFile::D Etach

Mit dieser Funktion schließen Sie die Speicherdatei und trennen Sie vom Speicherblock.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Rückgabewert

Das Handle des Speicherblocks, der den Inhalt der Speicherdatei enthält.

### <a name="remarks"></a>Hinweise

Sie können Sie erneut öffnen, indem Sie " [lthandle](#sethandle)" mithilfe des Handles aufrufen, das von **Detach**zurückgegeben wurde.

##  <a name="sethandle"></a>CSharedFile:: lthandle

Mit dieser Funktion können Sie einen Block des globalen Speichers an das `CSharedFile` -Objekt anfügen.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Parameter

*hGlobalMemory*<br/>
Handle für den globalen Speicher, der an das `CSharedFile`angefügt werden soll.

*bAllowGrow*<br/>
Gibt an, ob der Speicherblock vergrößert werden darf.

### <a name="remarks"></a>Hinweise

Wenn " *ballowgrow* " ungleich 0 (null) ist, wird die Größe des Speicherblocks bei Bedarf erhöht, z. b. Wenn Sie versuchen, mehr Bytes als die Größe des Speicherblocks in die Datei zu schreiben.

## <a name="see-also"></a>Siehe auch

[CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)
