---
title: CD2DTextFormat-Klasse
ms.date: 11/04/2016
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: 9d796ac39ba29e6d286926f4975f8f6d2054e7ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297891"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat-Klasse

Ein Wrapper für IDWriteTextFormat.

## <a name="syntax"></a>Syntax

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Erstellt ein CD2DTextFormat-Objekt.|
|[CD2DTextFormat::~CD2DTextFormat](#cd2dtextformat__~cd2dtextformat)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Textformatobjekt zerstört wird.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextFormat::Create](#create)|Erstellt eine CD2DTextFormat an. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2DTextFormat::Destroy](#destroy)|Zerstört ein CD2DTextFormat-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|
|[CD2DTextFormat::Get](#get)|Gibt die IDWriteTextFormat-Schnittstelle|
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Ruft eine Kopie der den Namen der Schriftfamilie ab.|
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Ruft eine Kopie des Namen des Gebietsschemas ab.|
|[CD2DTextFormat::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2DTextFormat::ReCreate](#recreate)|Wird Sie einer CD2DTextFormat neu erstellt. (Überschreibt [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CD2DTextFormat::operator IDWriteTextFormat*](#operator_idwritetextformat_star)|Gibt die IDWriteTextFormat-Schnittstelle|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|Ein Zeiger auf ein IDWriteTextFormat.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxrendertarget.h

##  <a name="_dtorcd2dtextformat"></a>  CD2DTextFormat:: ~ CD2DTextFormat

Der Destruktor. Wird aufgerufen, wenn ein D2D-Textformatobjekt zerstört wird.

```
virtual ~CD2DTextFormat();
```

##  <a name="cd2dtextformat"></a>  CD2DTextFormat::CD2DTextFormat

Erstellt ein CD2DTextFormat-Objekt.

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*pParentTarget*<br/>
Ein Zeiger auf das Renderziel.

*strFontFamilyName*<br/>
Eine CString-Objekt mit dem Namen der Schriftfamilie zurück.

*fontSize*<br/>
Die logische Größe der Schriftart in Einheiten der DIP-Adresse ("geräteunabhängige Pixel"). Eine DIP entspricht 1/96 Zoll.

*fontWeight*<br/>
Ein Wert, der die Schriftbreite für das Textobjekt angibt.

*fontStyle*<br/>
Ein Wert, der den Schriftschnitt für das Textobjekt angibt.

*fontStretch*<br/>
Ein Wert, der die schriftartstreckung für das Textobjekt angibt.

*strFontLocale*<br/>
Eine CString-Objekt, das den Gebietsschemanamen enthält.

*pFontCollection*<br/>
Ein Zeiger auf ein Schriftartobjekt-Auflistung. Wenn der Wert NULL ist, gibt die systemschriftsammlung an.

*bAutoDestroy*<br/>
Gibt an, dass vom Besitzer (pParentTarget) das Objekt zerstört wird.

##  <a name="create"></a>  CD2DTextFormat::Create

Erstellt eine CD2DTextFormat an.

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

##  <a name="destroy"></a>  CD2DTextFormat::Destroy

Zerstört ein CD2DTextFormat-Objekt.

```
virtual void Destroy();
```

##  <a name="get"></a>  CD2DTextFormat::Get

Gibt die IDWriteTextFormat-Schnittstelle

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein IDWriteTextFormat-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="getfontfamilyname"></a>  CD2DTextFormat::GetFontFamilyName

Ruft eine Kopie der den Namen der Schriftfamilie ab.

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>Rückgabewert

CString-Objekt, das den aktuellen Namen der Schriftfamilie enthält.

##  <a name="getlocalename"></a>  CD2DTextFormat::GetLocaleName

Ruft eine Kopie des Namen des Gebietsschemas ab.

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>Rückgabewert

CString-Objekt, das den aktuellen Gebietsschemanamen enthält.

##  <a name="isvalid"></a>  CD2DTextFormat::IsValid

Die Gültigkeit der Überprüfungen-Ressource

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Ressource gültig ist. andernfalls "false".

##  <a name="m_ptextformat"></a>  CD2DTextFormat::m_pTextFormat

Ein Zeiger auf ein IDWriteTextFormat.

```
IDWriteTextFormat* m_pTextFormat;
```

##  <a name="operator_idwritetextformat_star"></a>  CD2DTextFormat::Operator IDWriteTextFormat *

Gibt die IDWriteTextFormat-Schnittstelle

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf ein IDWriteTextFormat-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.

##  <a name="recreate"></a>  CD2DTextFormat::ReCreate

Wird Sie einer CD2DTextFormat neu erstellt.

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>Rückgabewert

Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.

## <a name="see-also"></a>Siehe auch

[Klassen](../../mfc/reference/mfc-classes.md)
