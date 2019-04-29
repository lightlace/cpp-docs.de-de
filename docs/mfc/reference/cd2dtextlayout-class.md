---
title: CD2DTextLayout-Klasse
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: ca89d12c6aeed33be740aa9f999e7c11d6c32056
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396183"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout-Klasse

Ein Wrapper für IDWriteTextLayout.

## <a name="syntax"></a>Syntax

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Erstellt ein CD2DTextLayout-Objekt.|
|[CD2DTextLayout::~CD2DTextLayout](#_dtorcd2dtextlayout)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Text-Layout-Objekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextLayout::Create](#create)|Erstellt eine CD2DTextLayout an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextLayout::Destroy](#destroy)|Zerstört ein CD2DTextLayout-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextLayout::Get](#get)|Gibt die IDWriteTextLayout-Schnittstelle|
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Kopiert die Namen der Schriftfamilie des Texts an der angegebenen Position.|
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Ruft den Namen des Gebietsschemas des Texts an der angegebenen Position ab.|
|[CD2DTextLayout::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextLayout::ReCreate](#recreate)|Wird Sie einer CD2DTextLayout neu erstellt. (Überschreibt [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Legt Null-terminierte Schriftfamiliennamen für Text in einen angegebenen Textbereich|
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Legt den Namen des Gebietsschemas für Text in einen angegebenen Textbereich|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextLayout::operator IDWriteTextLayout*](#operator_idwritetextlayout_star)|Gibt die IDWriteTextLayout-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Ein Zeiger auf ein IDWriteTextLayout.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dtextlayout"></a>  CD2DTextLayout:: ~ CD2DTextLayout

Der Destruktor. Wird aufgerufen, wenn ein D2D-Text-Layout-Objekt zerstört wird.

```
virtual ~CD2DTextLayout();
```

##  <a name="cd2dtextlayout"></a>  CD2DTextLayout::CD2DTextLayout

Erstellt ein CD2DTextLayout-Objekt.

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*strText*<br/>
Eine CString-Objekt, das enthält die Zeichenfolge zum Erstellen eines neuen CD2DTextLayout-Objekts aus.

*textFormat*<br/>
Eine CString-Objekt, das auf die Zeichenfolge anzuwendende Format enthält.

*sizeMax*<br/>
Die Größe des im Layout.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DTextLayout::Create

Erstellt eine CD2DTextLayout an.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DTextLayout::Destroy

Zerstört ein CD2DTextLayout-Objekt.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextLayout::Get

Gibt die IDWriteTextLayout-Schnittstelle

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein IDWriteTextLayout-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getfontfamilyname"></a>  CD2DTextLayout::GetFontFamilyName

Kopiert die Namen der Schriftfamilie des Texts an der angegebenen Position.

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parameter

*currentPosition*<br/>
Die Position des zu untersuchenden Texts.

*textRange*<br/>
Der Bereich des Texts mit dem gleichen Formatierung wie der Text an der Position von CurrentPosition angegeben. Dies bedeutet, dass die Ausführung die exakte Formatierung als die angegebene Position, einschließlich, aber nicht beschränkt auf den Namen der Schriftfamilie.

### <a name="return-value"></a>Rückgabewert

CString-Objekt, das den aktuellen Namen der Schriftfamilie enthält.

##  <a name="getlocalename"></a>  CD2DTextLayout::GetLocaleName

Ruft den Namen des Gebietsschemas des Texts an der angegebenen Position ab.

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>Parameter

*currentPosition*<br/>
Die Position des zu untersuchenden Texts.

*textRange*<br/>
Der Bereich des Texts mit dem gleichen Formatierung wie der Text an der Position von CurrentPosition angegeben. Dies bedeutet, dass die Ausführung die exakte Formatierung als die angegebene Position, einschließlich, aber nicht beschränkt auf den Gebietsschemanamen.

### <a name="return-value"></a>Rückgabewert

CString-Objekt, das den aktuellen Gebietsschemanamen enthält.

##  <a name="isvalid"></a>  CD2DTextLayout::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_ptextlayout"></a>  CD2DTextLayout::m_pTextLayout

Ein Zeiger auf ein IDWriteTextLayout.

```
IDWriteTextLayout* m_pTextLayout;
```

##  <a name="operator_idwritetextlayout_star"></a>  CD2DTextLayout::Operator IDWriteTextLayout *

Gibt die IDWriteTextLayout-Schnittstelle

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein IDWriteTextLayout-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="recreate"></a>  CD2DTextLayout::ReCreate

Wird Sie einer CD2DTextLayout neu erstellt.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="setfontfamilyname"></a>  CD2DTextLayout::SetFontFamilyName

Legt Null-terminierte Schriftfamiliennamen für Text in einen angegebenen Textbereich

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parameter

*pwzFontFamilyName*<br/>
Den Namen der Schriftfamilie, der für die gesamte Textzeichenfolge innerhalb des Bereichs von TextRange angegebenen gilt

*textRange*<br/>
Text-Bereich, für die diese Änderung gilt

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird "false" zurückgegeben

##  <a name="setlocalename"></a>  CD2DTextLayout::SetLocaleName

Legt den Namen des Gebietsschemas für Text in einen angegebenen Textbereich

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>Parameter

*pwzLocaleName*<br/>
Eine Gebietsschema Null-terminierte Zeichenfolge

*textRange*<br/>
Text-Bereich, für die diese Änderung gilt

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird "true" zurückgegeben. Andernfalls wird "false" zurückgegeben

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
