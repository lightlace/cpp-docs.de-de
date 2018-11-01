---
title: CMonikerFile-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
ms.openlocfilehash: dc7c2615ff4de7370bee74c64c8bcddbd1f1fcd5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541903"
---
# <a name="cmonikerfile-class"></a>CMonikerFile-Klasse

Stellt einen Datenstrom ( [IStream](/windows/desktop/api/objidl/nn-objidl-istream)) mit dem Namen durch ein [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker).

## <a name="syntax"></a>Syntax

```
class CMonikerFile : public COleStreamFile
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Erstellt ein `CMonikerFile`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMonikerFile::Close](#close)|Trennt und den Stream frei und gibt den Moniker.|
|[CMonikerFile::Detach](#detach)|Trennt die `IMoniker` aus diesem `CMonikerFile` Objekt.|
|[CMonikerFile::GetMoniker](#getmoniker)|Gibt den aktuellen Moniker zurück.|
|[CMonikerFile::Open](#open)|Öffnet die angegebene Datei aus, um kein Stream abgerufen werden.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|Ruft den Bindungskontext ab oder erstellt einen Bindungskontext standardmäßig initialisiert.|

## <a name="remarks"></a>Hinweise

Ein Moniker enthält Informationen wie einen Pfadnamen in eine Datei. Wenn Sie einen Zeiger auf ein monikerobjekt haben `IMoniker` -Schnittstelle, Sie erhalten Zugriff auf die identifizierte Datei ohne andere spezifische Informationen über die auf dem sich die Datei tatsächlich befindet.

Abgeleitet von `COleStreamFile`, `CMonikerFile` nimmt einen Moniker oder eine Zeichenfolgendarstellung in einen Moniker vorzunehmen, und bindet Sie in den Stream für die der Moniker ein Name ist. Sie können dann lesen und Schreiben in den Stream. Der eigentliche Zweck von `CMonikerFile` besteht darin, bieten einfachen Zugriff auf `IStream`s mit dem Namen von `IMoniker`s, damit Sie nicht selbst die Bindung an einen Stream aus, die Sie verfügen noch nicht `CFile` Funktionalität in den Stream.

`CMonikerFile` kann nicht zum Binden an etwas anderes als ein Datenstrom verwendet werden. Wenn Sie an Speicher oder ein Objekt zu binden möchten, müssen Sie verwenden die `IMoniker` -Schnittstelle direkt.

Weitere Informationen zu Streams und den Moniker, finden Sie unter [COleStreamFile](../../mfc/reference/colestreamfile-class.md) in die *MFC-Referenz* und [IStream](/windows/desktop/api/objidl/nn-objidl-istream) und [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>Anforderungen

**Header:** afxole.h

##  <a name="close"></a>  CMonikerFile::Close

Mit dieser Funktion wird zum Trennen und den Stream freizugeben und den Moniker freizugeben.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Kann für nicht geöffneten oder bereits geschlossenen Streams aufgerufen werden.

##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile

Erstellt ein `CMonikerFile`-Objekt.

```
CMonikerFile();
```

##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext

Rufen Sie diese Funktion zum Erstellen einer Bindungskontext standardmäßig initialisiert.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>Parameter

*pError*<br/>
Ein Zeiger auf eine Ausnahme für die Datei. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Bindungskontext [IBindCtx](/windows/desktop/api/objidl/nn-objidl-ibindctx) mit gebunden werden soll, wenn erfolgreich; andernfalls NULL. Wenn Sie mit die Instanz geöffnet wurde ein `IBindHost` -Schnittstelle, aus dem Bindungskontext abgerufen wird die `IBindHost`. Es ist keine `IBindHost` Schnittstelle oder ein Fehler auftritt, um einen Bindungskontext zurückzugeben, einen Bindungskontext wird erstellt. Eine Beschreibung der [IBindHost](https://msdn.microsoft.com/library/ie/ms775076) Schnittstelle, finden Sie im Windows SDK.

### <a name="remarks"></a>Hinweise

Ein Bindungskontext ist ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang gespeichert werden. Sie können dieser Funktion können Sie einen benutzerdefinierte Bindungskontext bereitzustellen, überschreiben.

##  <a name="detach"></a>  CMonikerFile::Detach

Rufen Sie diese Funktion, um den Stream zu schließen.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*pError*<br/>
Ein Zeiger auf eine Ausnahme für die Datei. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker

Rufen Sie diese Funktion, um einen Zeiger auf den aktuellen Moniker abzurufen.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den aktuellen Moniker-Schnittstelle ( [IMoniker](/windows/desktop/api/objidl/nn-objidl-imoniker)).

### <a name="remarks"></a>Hinweise

Da `CMonikerFile` ist keine Schnittstelle, der zurückgegebene Zeiger nicht inkrementiert den Verweiszähler (über ["AddRef"](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)), und der Moniker wird freigegeben. wenn die `CMonikerFile` Objekt freigegeben wird. Wenn Sie nicht auf den Moniker oder selbst freigeben möchten, müssen Sie `AddRef` es.

##  <a name="open"></a>  CMonikerFile::Open

Rufen Sie diese Memberfunktion zum Öffnen einer Datei oder Moniker-Objekts.

```
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);

virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*lpszURL*<br/>
Eine URL oder der Dateiname der Datei geöffnet werden.

*pError*<br/>
Ein Zeiger auf eine Ausnahme für die Datei. Im Falle eines Fehlers wird es auf die Ursache festgelegt werden.

*pMoniker*<br/>
Ein Zeiger auf den Moniker-Schnittstelle `IMoniker` verwendet werden soll, kein Stream abgerufen werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die *LpszURL* Parameter kann nicht auf einem Macintosh-Computer verwendet werden. Nur die *pMoniker* Form `Open` kann auf einem Macintosh-Computer verwendet werden.

Sie können eine URL oder einen Dateinamen für die *LpszURL* Parameter. Zum Beispiel:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- oder –

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[COleStreamFile-Klasse](../../mfc/reference/colestreamfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)
