---
title: CMemFile-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
dev_langs:
- C++
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90203a2e4fc29b28e6c75193ed1db35e25044951
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076957"
---
# <a name="cmemfile-class"></a>CMemFile-Klasse

Die [CFile](../../mfc/reference/cfile-class.md)-abgeleitete Klasse, die arbeitsspeicherdateien unterstützt.

## <a name="syntax"></a>Syntax

```
class CMemFile : public CFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMemFile::CMemFile](#cmemfile)|Erstellt ein Speicherobjekt für die Datei an.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMemFile::Attach](#attach)|Fügt einen Speicherblock zu `CMemFile`.|
|[CMemFile::Detach](#detach)|Trennt den Speicherblock aus `CMemFile` und gibt einen Zeiger auf den Speicherblock, getrennt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMemFile::Alloc](#alloc)|Überschreiben Sie, um das Zuordnungsverhalten des Arbeitsspeichers zu ändern.|
|[CMemFile::Free](#free)|Außer Kraft setzen Sie, um Arbeitsspeicher Aufhebung der Zuordnung Verhalten zu ändern.|
|[CMemFile::GrowFile](#growfile)|Überschreiben Sie, um das Verhalten zu ändern, wenn eine Datei vergrößert.|
|[CMemFile::Memcpy](#memcpy)|Überschreiben Sie, um Arbeitsspeicher Kopierverhalten beim Lesen und Schreiben von Dateien ändern.|
|[CMemFile::Realloc](#realloc)|Außer Kraft setzen Sie, um Arbeitsspeicher neuzuordnung Verhalten zu ändern.|

## <a name="remarks"></a>Hinweise

Diese arbeitsspeicherdateien Verhalten sich wie Dateien auf Datenträgern, mit dem Unterschied, dass die Datei im Arbeitsspeicher und nicht auf dem Datenträger gespeichert wird. Eine Arbeitsspeicherdatei eignet sich zur schnellen temporären Speicherung oder für die Übertragung von unformatierten Bytes oder von serialisierten Objekten zwischen voneinander unabhängige Prozesse.

`CMemFile` Objekte können automatisch ihre eigenen Speicher belegen oder anfügen, die Ihre eigenen Speicherblock, der die `CMemFile` Objekt durch Aufrufen von [Anfügen](#attach). In beiden Fällen wird im Arbeitsspeicher für die Arbeitsspeicherdatei automatisch wachsende reserviert `nGrowBytes`-Größe erhöht, wenn `nGrowBytes` ist nicht 0 (null).

Der Speicherblock wird automatisch entfernt, nach der Destruktion von der `CMemFile` Objekt, wenn der Arbeitsspeicher von ursprünglich zugeordnet wurde die `CMemFile` Objekt; andernfalls sind Sie verantwortlich für die Zuordnung des Speicherplatzes, die Sie an das Objekt aufzuheben.

Sie können auf den Speicherblock zugreifen, über den Zeiger angegeben, wenn Sie von getrennt den `CMemFile` Objekt durch Aufrufen von [trennen](#detach).

Die häufigste Verwendung von `CMemFile` ist die Erstellung einer `CMemFile` Objekt, und verwenden Sie es durch Aufrufen von [CFile](../../mfc/reference/cfile-class.md) Memberfunktionen. Beachten Sie, dass die Erstellung einer `CMemFile` wird es automatisch geöffnet: nicht aufgerufen [CFile::Open](../../mfc/reference/cfile-class.md#open), die nur für Dateien auf Datenträgern verwendet wird. Da `CMemFile` verwendet nicht die Datei auf einem Datenträger, der den Datenmember `CFile::m_hFile` wird nicht verwendet.

Die `CFile` Memberfunktionen [doppelte](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), und [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) sind nicht für implementiert `CMemFile`. Wenn Sie für diese Funktionen aufrufen einer `CMemFile` Objekt ist, erhalten Sie eine [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

`CMemFile` verwendet die Funktionen der Laufzeitbibliothek [Malloc](../../c-runtime-library/reference/malloc.md), [Realloc](../../c-runtime-library/reference/realloc.md), und [kostenlose](../../c-runtime-library/reference/free.md) zum Zuordnen zum erneuten Zuweisen und Freigeben von Arbeitsspeicher und die systeminterne Funktion [Memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) Block Kopie Arbeitsspeicher beim Lesen und schreiben. Wenn Sie, um dieses Verhalten oder das Verhalten zu ändern möchten beim `CMemFile` nimmt eine Datei, leiten Sie eine eigene Klasse von `CMemFile` und überschreiben Sie die entsprechenden Funktionen.

Weitere Informationen zu `CMemFile`, finden Sie in den Artikeln [Dateien in MFC](../../mfc/files-in-mfc.md) und [Memory Management (MFC)](../../mfc/memory-management.md) und finden Sie unter [Dateibehandlung](../../c-runtime-library/file-handling.md) in die *Run-Time Referenz zur Bibliothek*.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>Anforderungen

**Header:** afx.h

##  <a name="alloc"></a>  CMemFile::Alloc

Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Anzahl der Bytes im Arbeitsspeicher zugeordnet werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Speicherblock, der belegt wurde, oder NULL, wenn die speicherbelegung fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um benutzerdefinierte speicherbelegung zu implementieren. Wenn Sie diese Funktion außer Kraft setzen, sollten Sie wahrscheinlich überschreiben [Free](#free) und [Realloc](#realloc) ebenfalls.

Die Standardimplementierung verwendet die Funktion der Laufzeitbibliothek [Malloc](../../c-runtime-library/reference/malloc.md) um Speicher zu belegen.

##  <a name="attach"></a>  CMemFile::Attach

Mit dieser Funktion können Sie einen Speicherblock zu Anfügen `CMemFile`.

```
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Parameter

*lpBuffer*<br/>
Zeiger auf den Puffer anzufügenden `CMemFile`.

*nBufferSize*<br/>
Eine ganze Zahl, die die Größe des Puffers in Bytes angibt.

*nGrowBytes*<br/>
Das Inkrement, Memory Allocation in Byte.

### <a name="remarks"></a>Hinweise

Dies bewirkt, dass `CMemFile` den Speicherblock, der als Datei für den Speicher zu verwenden.

Wenn *nGrowBytes* ist 0 (null) `CMemFile` wird festgelegt, die Dateilänge mit *nBufferSize*. Dies bedeutet, dass die Daten in den Speicherblock, bevor er angefügt war `CMemFile` verwendet werden, wie die Datei. Speicher-Dateien, die auf diese Weise erstellten können nicht vergrößert werden.

Da die Datei vergrößert werden kann, werden nicht dazu führen, dass `CMemFile` versucht, die Datei vergrößert werden. Beispielsweise rufen Sie nicht die `CMemFile` überschreibungen der [CFile:Write](../../mfc/reference/cfile-class.md#write) , nach Erreichen des Dateiendes schreiben, oder rufen Sie nicht [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) mit einer Länge von mehr als *nBufferSize*.

Wenn *nGrowBytes* ist größer als 0 (null) `CMemFile` ignoriert den Inhalt des Speicherblocks, der Sie hinzugefügt haben. Sie müssen den Inhalt der Datei für den Speicher von der Verwendung von Grund auf neu schreiben die `CMemFile` -Überschreibung `CFile::Write`. Wenn Sie versuchen, nach dem Ende der Datei zu schreiben, oder vergrößern Sie die Datei durch Aufrufen der `CMemFile` Überschreiben von `CFile::SetLength`, `CMemFile` wächst die speicherbelegung in Schritten von *nGrowBytes*. Wächst die speicherbelegung schlägt fehl, wenn der Speicherblock an Sie übergeben `Attach` wurde nicht zugeordnet, mit einer Methode, die kompatibel mit [Alloc](#alloc). Mit der Standardimplementierung von kompatibel `Alloc`, müssen Sie den Arbeitsspeicher mit der Funktion der Laufzeitbibliothek zuordnen [Malloc](../../c-runtime-library/reference/malloc.md) oder ["calloc"](../../c-runtime-library/reference/calloc.md).

##  <a name="cmemfile"></a>  CMemFile::CMemFile

Die erste Überladung wird eine leerer Speicher-Datei geöffnet.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Parameter

*nGrowBytes*<br/>
Das Inkrement, Memory Allocation in Byte.

*LpBuffe*R Zeiger auf einen Puffer, der Informationen der Größe empfängt *nBufferSize*.

*nBufferSize*<br/>
Eine ganze Zahl, die die Größe des Dateipuffers in Bytes angibt.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die Datei, durch den Konstruktor geöffnet wird und Sie nicht aufrufen sollten [CFile::Open](../../mfc/reference/cfile-class.md#open).

Die zweite Überladung entspricht das Verhalten, als ob Sie sofort aufgerufen und den ersten Konstruktor verwendet [Anfügen](#attach) mit denselben Parametern. Ausführliche Informationen finden Sie unter `Attach`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

##  <a name="detach"></a>  CMemFile::Detach

Mit dieser Funktion wird zum Abrufen eines Zeigers auf den Speicherblock, der von verwendeten `CMemFile`.

```
BYTE* Detach();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger zum Speicherblock, der den Inhalt der Datei für den Speicher enthält.

### <a name="remarks"></a>Hinweise

Das Aufrufen dieser Funktion auch schließt die `CMemFile`. Sie können den Speicherblock Anfügen `CMemFile` durch Aufrufen von [Anfügen](#attach). Wenn Sie die Datei anfügen und verwenden Sie die Daten darin möchten, sollten Sie aufrufen [CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) zum Abrufen der Länge der Datei vor dem Aufruf `Detach`. Beachten Sie, dass, wenn Sie einen Speicherblock zu Anfügen `CMemFile` , damit Sie ihre Daten verwenden können ( `nGrowBytes` == 0), und klicken Sie dann Sie nicht die Arbeitsspeicherdatei vergrößert werden können.

##  <a name="free"></a>  CMemFile::Free

Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>Parameter

*lpMem*<br/>
Zeiger auf den Speicher aufgehoben werden.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um benutzerdefinierte Speicherfreigabe zu implementieren. Wenn Sie diese Funktion außer Kraft setzen, sollten Sie wahrscheinlich überschreiben [Alloc](#alloc) und [Realloc](#realloc) ebenfalls.

##  <a name="growfile"></a>  CMemFile::GrowFile

Diese Funktion wird aufgerufen, von einigen der `CMemFile` Memberfunktionen.

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>Parameter

*dwNewLen*<br/>
Neue Größe der Datei für den Speicher.

### <a name="remarks"></a>Hinweise

Sie können es überschreiben, wenn Sie ändern möchten wie `CMemFile` wächst die Datei. Die Standardimplementierung ruft [Realloc](#realloc) einen vorhandenen Block wächst (oder [Alloc](#alloc) um einen Speicherblock zu erstellen), belegen von Speicher in Vielfachen von der `nGrowBytes` im Konstruktor angegebene Wert oder [Anfügen](#attach) aufrufen.

##  <a name="memcpy"></a>  CMemFile::Memcpy

Diese Funktion wird aufgerufen, indem die `CMemFile` überschreibungen der [CFile:: Read](../../mfc/reference/cfile-class.md#read) und [CFile::Write](../../mfc/reference/cfile-class.md#write) zum Übertragen von Daten in und aus dem Speicher-Datei.

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Parameter

*lpMemTarget*<br/>
Zeiger auf den Speicherblock, in dem der Arbeitsspeicher kopiert werden.

*lpMemSource*<br/>
Zeiger zum Speicherblock Quelle.

*nBytes*<br/>
Anzahl der zu kopierenden Bytes.

### <a name="return-value"></a>Rückgabewert

Eine Kopie des *LpMemTarget*.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie ändern möchten, die `CMemFile` diese Speicher kopiert wird.

##  <a name="realloc"></a>  CMemFile::Realloc

Diese Funktion wird aufgerufen, indem `CMemFile` Memberfunktionen.

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Parameter

*lpMem*<br/>
Ein Zeiger zum Speicherblock, verschoben werden.

*nBytes*<br/>
Neue Größe für den Speicherblock.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger zum Speicherblock, der zugewiesen (und möglicherweise verschoben), oder NULL, wenn die neuzuordnung ist fehlgeschlagen.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um benutzerdefinierte neuzuordnung zu implementieren. Wenn Sie diese Funktion außer Kraft setzen, sollten Sie wahrscheinlich überschreiben [Alloc](#alloc) und [Free](#free) ebenfalls.

## <a name="see-also"></a>Siehe auch

[CFile-Klasse](../../mfc/reference/cfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

