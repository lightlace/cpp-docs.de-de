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
ms.openlocfilehash: 0a9bbf3072a665c04501025d421839fa90a37225
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344422"
---
# <a name="csharedfile-class"></a>CSharedFile-Klasse

Die [CMemFile](../../mfc/reference/cmemfile-class.md)-abgeleiteten Klasse, die unterstützt die freigegebene arbeitsspeicherdateien.

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
|[CSharedFile::Detach](#detach)|Schließt die shared Memory-Datei, und gibt das Handle des Speicherblocks zurück.|
|[CSharedFile::SetHandle](#sethandle)|Fügt die shared Memory-Datei auf einen Speicherblock.|

## <a name="remarks"></a>Hinweise

Speicherdateien Verhalten sich wie Dateien auf Datenträgern. Der Unterschied besteht darin, eine Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert ist. Eine Arbeitsspeicherdatei eignet sich zur schnellen temporären Speicherung oder für die Übertragung von unformatierten Bytes oder von serialisierten Objekten zwischen voneinander unabhängige Prozesse.

Freigegebene arbeitsspeicherdateien unterscheiden sich von anderen arbeitsspeicherdateien Arbeitsspeicher dafür zugeordnet wird, die [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) Windows-Funktion. Die `CSharedFile` Klasse speichert Daten in einer global belegten Speicherblocks (erstellt mit `GlobalAlloc`), und diesem Speicherblock freigegeben werden kann mit DDE, die Zwischenablage oder andere OLE/COM uniform Data Transfer Vorgänge, z. B. mit `IDataObject`.

`GlobalAlloc` Gibt HGLOBAL verarbeiten, anstatt ein Zeiger auf Speicher, z. B. der zurückgegebene Zeiger [Malloc](../../c-runtime-library/reference/malloc.md). Das Handle HGLOBAL ist in bestimmten Anwendungen erforderlich. Beispielsweise benötigen Sie zum Einfügen von Daten in die Zwischenablage ein HGLOBAL-Handle.

`CSharedFile` nicht verwendeter Speicher abgebildete Dateien, und die Daten direkt zwischen Prozessen gemeinsam genutzt werden kann.

`CSharedFile` Objekte können automatisch mit ihren eigenen Arbeitsspeicher zuordnen. Oder Sie können Ihre eigenen Speicherblock, der Anfügen der `CSharedFile` Objekt durch Aufrufen von [CSharedFile::SetHandle](#sethandle). In beiden Fällen wird im Arbeitsspeicher für die Arbeitsspeicherdatei automatisch wachsende reserviert `nGrowBytes`-Größe erhöht, wenn `nGrowBytes` ist nicht 0 (null).

Weitere Informationen finden Sie im Artikel [Dateien in MFC](../../mfc/files-in-mfc.md) und [Dateibehandlung](../../c-runtime-library/file-handling.md) in die *Run-Time Library Reference*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxadv.h

##  <a name="csharedfile"></a>  CSharedFile::CSharedFile

Erstellt eine `CSharedFile` -Objekt und belegt Speicher für sie.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Parameter

*nAllocFlags*<br/>
Flags, der angibt, wie Speicher zugeordnet werden. Finden Sie unter [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) eine Liste der gültigen Flagwerte.

*nGrowBytes*<br/>
Das Inkrement, Memory Allocation in Byte.

##  <a name="detach"></a>  CSharedFile::Detach

Rufen Sie diese Funktion, um die Arbeitsspeicherdatei schließen und trennen Sie das Objekt aus den Speicherblock.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Rückgabewert

Das Handle der Speicherblock, der den Inhalt der Datei für den Speicher enthält.

### <a name="remarks"></a>Hinweise

Sie können erneut öffnen, es durch Aufrufen von [SetHandle auf](#sethandle), mit dem Handle zurückgegebenes **trennen**.

##  <a name="sethandle"></a>  CSharedFile::SetHandle

Mit dieser Funktion können Sie einen Block von globalen Arbeitsspeicher zum Anfügen der `CSharedFile` Objekt.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Parameter

*hGlobalMemory*<br/>
Handle für den globalen Speicher zugeordnet werden soll die `CSharedFile`.

*bAllowGrow*<br/>
Gibt an, ob der Speicherblock wachsen darf.

### <a name="remarks"></a>Hinweise

Wenn *bAllowGrow* ist ungleich NULL ist, die Größe des Speicherblocks wird erhöht, nach Bedarf, z. B. Wenn Sie versuchen, mehr Bytes in der Datei als die Größe des Speicherblocks zu schreiben.

## <a name="see-also"></a>Siehe auch

[CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CMemFile-Klasse](../../mfc/reference/cmemfile-class.md)
