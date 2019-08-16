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
ms.openlocfilehash: 56283b56a1c0832d34ce23c7db47c47d9480aec8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504566"
---
# <a name="cmonikerfile-class"></a>CMonikerFile-Klasse

Stellt einen Datenstrom ( [IStream](/windows/win32/api/objidl/nn-objidl-istream)) dar, der von einem [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)benannt wird.

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
|[CMonikerFile::Close](#close)|Trennt und gibt den Datenstrom frei und gibt den Moniker frei.|
|[CMonikerFile::Detach](#detach)|Trennt den `IMoniker` von diesem `CMonikerFile` -Objekt.|
|[CMonikerFile::GetMoniker](#getmoniker)|Gibt den aktuellen Moniker zurück.|
|[CMonikerFile::Open](#open)|Öffnet die angegebene Datei zum Abrufen eines Streams.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMonikerFile::CreateBindContext](#createbindcontext)|Ruft den Bindungs Kontext ab oder erstellt einen standardmäßigen initialisierten Bindungs Kontext.|

## <a name="remarks"></a>Hinweise

Ein Moniker enthält Informationen ähnlich wie ein Pfadname zu einer Datei. Wenn Sie einen Zeiger auf die-Schnittstelle eines Monikers- `IMoniker` Objekts haben, können Sie auf die identifizierte Datei zugreifen, ohne weitere spezifische Informationen dazu zu erhalten, wo sich die Datei tatsächlich befindet.

Wird von `COleStreamFile`abgeleitet `CMonikerFile` und übernimmt einen Moniker oder eine Zeichen folgen Darstellung, die er in einem Moniker erstellen kann, und bindet an den Datenstrom, für den der Moniker ein Name ist. Sie können dann in diesen Stream lesen und schreiben. Der eigentliche Zweck von `CMonikerFile` ist das Bereitstellen von einfachem Zugriff auf `IMoniker` `IStream`s, die von s benannt werden, damit Sie sich nicht selbst an einen Stream `CFile` binden müssen, aber über Funktionen für den Stream verfügen.

`CMonikerFile`kann nicht verwendet werden, um eine Bindung an nichts anderes als einen Datenstrom herzustellen. Wenn Sie eine Bindung an den Speicher oder ein Objekt herstellen möchten, müssen Sie `IMoniker` die-Schnittstelle direkt verwenden.

Weitere Informationen zu Streams und Monikern finden Sie unter [colestreamfile](../../mfc/reference/colestreamfile-class.md) in der *MFC-Referenz* und in [IStream](/windows/win32/api/objidl/nn-objidl-istream) und [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker) in der Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

`CMonikerFile`

## <a name="requirements"></a>Anforderungen

**Header:** Afxole. h

##  <a name="close"></a>CMonikerFile:: Close

Mit dieser Funktion können Sie den Stream trennen und freigeben und den Moniker freigeben.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Kann bei ungeöffneten oder bereits geschlossenen Streams aufgerufen werden.

##  <a name="cmonikerfile"></a>CMonikerFile:: CMonikerFile

Erstellt ein `CMonikerFile`-Objekt.

```
CMonikerFile();
```

##  <a name="createbindcontext"></a>CMonikerFile:: "kreatebindcontext"

Rufen Sie diese Funktion auf, um einen standardmäßigen initialisierten Bindungs Kontext zu erstellen.

```
IBindCtx* CreateBindContext(CFileException* pError);
```

### <a name="parameters"></a>Parameter

*pError*<br/>
Ein Zeiger auf eine Datei Ausnahme. Wenn ein Fehler auftritt, wird er auf die Ursache festgelegt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Bindungs Kontext [IBindCtx](/windows/win32/api/objidl/nn-objidl-ibindctx) , mit dem die Bindung erfolgen soll, wenn erfolgreich. andernfalls NULL. Wenn die-Instanz mit einer `IBindHost` -Schnittstelle geöffnet wurde, wird der Bindungs Kontext `IBindHost`aus abgerufen. Wenn keine `IBindHost` Schnittstelle vorhanden ist oder die Schnittstelle einen Bindungs Kontext nicht zurückgibt, wird ein Bindungs Kontext erstellt. Eine Beschreibung der [ibindhost](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms775076\(v=vs.85\)) -Schnittstelle finden Sie in der Windows SDK.

### <a name="remarks"></a>Hinweise

Ein Bindungs Kontext ist ein Objekt, das Informationen zu einem bestimmten Monikerbindungsvorgang speichert. Sie können diese Funktion überschreiben, um einen benutzerdefinierten Bindungs Kontext bereitzustellen.

##  <a name="detach"></a>CMonikerFile::D Etach

Diese Funktion wird aufgerufen, um den Stream zu schließen.

```
BOOL Detach(CFileException* pError = NULL);
```

### <a name="parameters"></a>Parameter

*pError*<br/>
Ein Zeiger auf eine Datei Ausnahme. Wenn ein Fehler auftritt, wird er auf die Ursache festgelegt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="getmoniker"></a>CMonikerFile:: getmoniker

Rufen Sie diese Funktion auf, um einen Zeiger auf den aktuellen Moniker abzurufen.

```
IMoniker* GetMoniker() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle monikerschnittstelle ( [IMoniker](/windows/win32/api/objidl/nn-objidl-imoniker)).

### <a name="remarks"></a>Hinweise

Da `CMonikerFile` keine Schnittstelle ist, erhöht der zurückgegebene Zeiger nicht den Verweis Zähler (durch [Adressaten](/windows/win32/api/unknwn/nf-unknwn-iunknown-addref)), und der Moniker wird freigegeben, wenn `CMonikerFile` das Objekt freigegeben wird. Wenn Sie den Moniker aufbewahren oder selbst freigeben möchten, müssen `AddRef` Sie ihn selbst freigeben.

##  <a name="open"></a>CMonikerFile:: Open

Diese Member-Funktion aufrufen, um ein Datei-oder monikerobjekt zu öffnen.

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
Eine URL oder ein Dateiname der Datei, die geöffnet werden soll.

*pError*<br/>
Ein Zeiger auf eine Datei Ausnahme. Wenn ein Fehler auftritt, wird er auf die Ursache festgelegt.

*pMoniker*<br/>
Ein Zeiger auf die monikerschnittstelle `IMoniker` , die zum Abrufen eines Streams verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der *lpszurl* -Parameter kann nicht in einem Macintosh verwendet werden. Nur die *pmoniker* -Form `Open` von kann auf einem Macintosh verwendet werden.

Sie können eine URL oder einen Dateinamen für den *lpszurl* -Parameter verwenden. Beispiel:

[!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]

\- oder –

[!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[COleStreamFile-Klasse](../../mfc/reference/colestreamfile-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)
