---
title: CStockPropImpl-Klasse
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 246e2a26db6adde0fec06523c1b8db09c5f552f3
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221073"
---
# <a name="cstockpropimpl-class"></a>CStockPropImpl-Klasse

Diese Klasse stellt Methoden zur Unterstützung der vordefinierten Werte.

> [!IMPORTANT]
> Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <
    class T, 
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, 
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Klasse, die das Steuerelement zu implementieren und Ableiten von `CStockPropImpl`.

*InterfaceName*<br/>
Eine duale Schnittstelle, die die vordefinierten Eigenschaften verfügbar zu machen.

*piid*<br/>
Ein Zeiger auf die IID der `InterfaceName`.

*plibid*<br/>
Ein Zeiger auf die LIBID der Typbibliothek mit der Definition der `InterfaceName`.

*wMajor*<br/>
Die Hauptversion der Typbibliothek Der Standardwert ist 1.

*wMinor*<br/>
Die Nebenversion der Typbibliothek Der Standardwert ist 0.

*tihclass*<br/>
Die Klasse, die zum Verwalten von Informationen für den *T*. Der Standardwert ist `CComTypeInfoHolder`.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|||
|-|-|
|[get_Appearance](#get_appearance)|Rufen Sie diese Methode zum Abrufen der Paint-Stil, die vom Steuerelement verwendet, z. B., flach oder 3D.|
|[get_AutoSize](#get_autosize)|Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob das Steuerelement eine beliebige andere Größe aufweisen, kann nicht an.|
|[get_BackColor](#get_backcolor)|Rufen Sie diese Methode, um die Hintergrundfarbe des Steuerelements zu erhalten.|
|[get_BackStyle](#get_backstyle)|Rufen Sie diese Methode, um den Hintergrundformat des Steuerelements, entweder transparenten oder deckenden zu erhalten.|
|[get_BorderColor](#get_bordercolor)|Rufen Sie diese Methode, um die Farbe des Rahmens des Steuerelements zu erhalten.|
|[get_BorderStyle](#get_borderstyle)|Rufen Sie diese Methode, um die Rahmenart des Steuerelements zu erhalten.|
|[get_BorderVisible](#get_bordervisible)|Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob der Rahmen des Steuerelements sichtbar ist.|
|[get_BorderWidth](#get_borderwidth)|Rufen Sie diese Methode, um die Breite (in Pixel), der den Rahmen des Steuerelements abzurufen.|
|[get_Caption](#get_caption)|Rufen Sie diese Methode zum Abrufen des Texts in ein Objekt mit der Beschriftung angegeben.|
|[get_DrawMode](#get_drawmode)|Rufen Sie diese Methode zum Abrufen des Steuerelements Zeichnungsmodus des, z. B. XOR Stift oder Farben umkehren.|
|[get_DrawStyle](#get_drawstyle)|Rufen Sie diese Methode zum Abrufen des Steuerelements Zeichnungsart, z. B. solid, gestrichelt oder gepunktet.|
|[get_DrawWidth](#get_drawwidth)|Rufen Sie diese Methode, um die Zeichnung Breite (in Pixel) ein, die die Methoden des Steuerelements zeichnen abzurufen.|
|[get_Enabled](#get_enabled)|Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob das Steuerelement aktiviert ist.|
|[get_FillColor](#get_fillcolor)|Rufen Sie diese Methode, um die Füllfarbe des Steuerelements zu erhalten.|
|[get_FillStyle](#get_fillstyle)|Rufen Sie diese Methode zum Abrufen von Füllformat des Steuerelements, z. B. ein, solid, transparente oder schraffiert.|
|[get_Font](#get_font)|Rufen Sie diese Methode, um einen Zeiger auf die Schriftarteigenschaften des Steuerelements abzurufen.|
|[get_ForeColor](#get_forecolor)|Rufen Sie diese Methode, um die Vordergrundfarbe des Steuerelements zu erhalten.|
|[get_HWND](#get_hwnd)|Rufen Sie diese Methode, um das Fensterhandle, das dem Steuerelement zugeordnete zu erhalten.|
|[get_MouseIcon](#get_mouseicon)|Rufen Sie diese Methode zum Abrufen der Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, wenn der Mauszeiger über dem Steuerelement befindet.|
|[get_MousePointer](#get_mousepointer)|Rufen Sie diese Methode zum Abrufen des Typs des Mauszeiger-auf, die angezeigt wird, wenn der Mauszeiger über dem Steuerelement, z. B., Pfeil, übergreifende oder Sanduhr dargestellt.|
|[get_Picture](#get_picture)|Rufen Sie diese Methode zum Abrufen eines Zeigers auf die Bildeigenschaften, der eine Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden.|
|[get_ReadyState](#get_readystate)|Rufen Sie diese Methode rufen Sie den Zustand des Steuerelements bereit, z. B., laden oder geladen wird.|
|[get_TabStop](#get_tabstop)|Rufen Sie diese Methode, um das Flag ab, die angibt, ob das Steuerelement einen Tabstopp oder nicht darstellt.|
|[get_Text](#get_text)|Rufen Sie diese Methode zum Abrufen des Texts, der mit dem Steuerelement angezeigt wird.|
|[getvalid](#get_valid)|Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob das Steuerelement gültig oder nicht ist.|
|[get_Window](#get_window)|Rufen Sie diese Methode, um das Fensterhandle, das dem Steuerelement zugeordnete zu erhalten. Identisch mit [CStockPropImpl::get_HWND](#get_hwnd).|
|[put_Appearance](#put_appearance)|Rufen Sie diese Methode, um die Paint-Stil, die vom Steuerelement verwendet, z. B., flach oder 3D festgelegt.|
|[put_AutoSize](#put_autosize)|Rufen Sie diese Methode, um den Wert des Flags festlegen, die angibt, ob das Steuerelement eine beliebige andere Größe aufweisen, kann nicht an.|
|[put_BackColor](#put_backcolor)|Rufen Sie diese Methode, um die Hintergrundfarbe des Steuerelements festzulegen.|
|[put_BackStyle](#put_backstyle)|Rufen Sie diese Methode zum Festlegen von Hintergrund-Format des Steuerelements.|
|[put_BorderColor](#put_bordercolor)|Rufen Sie diese Methode, um die Farbe des Rahmens des Steuerelements festgelegt.|
|[put_BorderStyle](#put_borderstyle)|Rufen Sie diese Methode, um die Rahmenart des Steuerelements festgelegt.|
|[put_BorderVisible](#put_bordervisible)|Rufen Sie diese Methode, um den Wert des Flags festlegen, die angibt, ob der Rahmen des Steuerelements sichtbar ist.|
|[put_BorderWidth](#put_borderwidth)|Rufen Sie diese Methode, um die Breite des Rahmens des Steuerelements festgelegt.|
|[put_Caption](#put_caption)|Rufen Sie diese Methode zum Festlegen des Texts, der mit dem Steuerelement angezeigt werden.|
|[put_DrawMode](#put_drawmode)|Rufen Sie diese Methode zum Festlegen des Steuerelements Zeichnungsmodus des, z. B. XOR Stift oder Farben umkehren.|
|[put_DrawStyle](#put_drawstyle)|Rufen Sie diese Methode, um das Format des Steuerelements zeichnen, legen Sie z. B. solid, gestrichelt oder gepunktet.|
|[put_DrawWidth](#put_drawwidth)|Rufen Sie diese Methode, um die Breite (in Pixel) ein, die die Methoden des Steuerelements zeichnen festgelegt.|
|[put_Enabled](#put_enabled)|Rufen Sie diese Methode, um das Flag festgelegt, die angibt, ob das Steuerelement aktiviert ist.|
|[put_FillColor](#put_fillcolor)|Rufen Sie diese Methode, um die Füllfarbe des Steuerelements festgelegt.|
|[put_FillStyle](#put_fillstyle)|Rufen Sie diese Methode, um das Füllformat des Steuerelements, legen Sie z. B. solid, transparente oder schraffiert.|
|[put_Font](#put_font)|Rufen Sie diese Methode, um die Schriftarteigenschaften des Steuerelements festgelegt.|
|[put_ForeColor](#put_forecolor)|Rufen Sie diese Methode zum Festlegen der Vordergrundfarbe des Steuerelements.|
|[put_HWND](#put_hwnd)|Diese Methode gibt E_FAIL zurück.|
|[put_MouseIcon](#put_mouseicon)|Rufen Sie diese Methode zum Festlegen der Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, wenn der Mauszeiger über dem Steuerelement befindet.|
|[put_MousePointer](#put_mousepointer)|Rufen Sie diese Methode, um den Typ des Mauszeiger-auf, die angezeigt wird, wenn der Mauszeiger über dem Steuerelement, z. B., Pfeil, übergreifende oder Sanduhr dargestellt.|
|[put_Picture](#put_picture)|Rufen Sie diese Methode zum Festlegen der Bildeigenschaften, der eine Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden.|
|[put_ReadyState](#put_readystate)|Rufen Sie diese Methode, um den Zustand des Steuerelements bereit, legen Sie z. B. Laden oder geladen.|
|[put_TabStop](#put_tabstop)|Rufen Sie diese Methode, um den Wert des Flags festgelegt, der angibt, ob das Steuerelement einen Tabstopp oder nicht.|
|[put_Text](#put_text)|Rufen Sie diese Methode, um den Text festlegen, der mit dem Steuerelement angezeigt wird.|
|[putvalid](#put_valid)|Rufen Sie diese Methode, um das Flag festgelegt, die angibt, ob das Steuerelement gültig oder nicht ist.|
|[put_Window](#put_window)|Diese Methode ruft [CStockPropImpl::put_HWND](#put_hwnd), E_FAIL zurückgegeben.|
|[putref_Font](#putref_font)|Rufen Sie diese Methode, um die Schriftarteigenschaften des Steuerelements, mit einer Verweisanzahl festgelegt.|
|[putref_MouseIcon](#putref_mouseicon)|Rufen Sie diese Methode zum Festlegen der Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, wenn der Mauszeiger über dem Steuerelement, mit einer Verweisanzahl ein.|
|[putref_Picture](#putref_picture)|Rufen Sie diese Methode zum Festlegen der Bildeigenschaften, der eine Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, mit einer Verweisanzahl ein.|

## <a name="remarks"></a>Hinweise

`CStockPropImpl` bietet **put** und **erhalten** Methoden für jede Eigenschaft. Diese Methoden geben Sie den Code zum Festlegen oder Abrufen des Datenmembers, der jede Eigenschaft zugeordnet, und informieren und mit dem Container synchronisiert werden, wenn sich eine Eigenschaft ändert.

Visual Studio bietet Unterstützung für vordefinierte Eigenschaften, die über den zugehörigen Assistenten. Weitere Informationen zu Hinzufügen von vordefinierten Eigenschaften auf ein Steuerelement, finden Sie unter den [ATL-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).

Für die Abwärtskompatibilität `CStockPropImpl` außerdem `get_Window` und `put_Window` Methoden, die einfach aufrufen `get_HWND` und `put_HWND`bzw. Die standardmäßige Implementierung des `put_HWND` gibt E_FAIL zurück, da HWND eine schreibgeschützte Eigenschaft sein sollte.

Die folgenden Eigenschaften verfügen, auch ein **Putref** Implementierung:

- Schriftart

- MouseIcon

- Picture

Die gleichen drei vordefinierten Eigenschaften erfordern ihre entsprechenden Datenmember des Typs `CComPtr` oder beliebigen anderen Klasse, die richtige Schnittstelle Referenz bietet mithilfe des Zuweisungsoperators zählen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>Anforderungen

**Header:** atlctl.h

##  <a name="get_appearance"></a>  CStockPropImpl::get_Appearance

Rufen Sie diese Methode zum Abrufen der Paint-Stil, die vom Steuerelement verwendet, z. B., flach oder 3D.

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>Parameter

*pnAppearance*<br/>
Eine Variable, die Paint-Format des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_autosize"></a>  CStockPropImpl::get_AutoSize

Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob das Steuerelement eine beliebige andere Größe aufweisen, kann nicht an.

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>Parameter

*pbAutoSize*<br/>
Variablen, die den Kennzeichnungsstatus empfängt. TRUE gibt an, dass das Steuerelement eine beliebige andere Größe sein kann.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_backcolor"></a>  CStockPropImpl::get_BackColor

Rufen Sie diese Methode, um die Hintergrundfarbe des Steuerelements zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>Parameter

*pclrBackColor*<br/>
Variablen, die Hintergrundfarbe des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_backstyle"></a>  CStockPropImpl::get_BackStyle

Rufen Sie diese Methode, um den Hintergrundformat des Steuerelements, entweder transparenten oder deckenden zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>Parameter

*pnBackStyle*<br/>
Eine Variable, die Hintergrund-Format des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_bordercolor"></a>  CStockPropImpl::get_BorderColor

Rufen Sie diese Methode, um die Farbe des Rahmens des Steuerelements zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>Parameter

*pclrBorderColor*<br/>
Eine Variable, die Farbe des Rahmens des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_borderstyle"></a>  CStockPropImpl::get_BorderStyle

Rufen Sie diese Methode, um die Rahmenart des Steuerelements zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>Parameter

*pnBorderStyle*<br/>
Eine Variable, die Rahmenart des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_bordervisible"></a>  CStockPropImpl::get_BorderVisible

Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob der Rahmen des Steuerelements sichtbar ist.

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>Parameter

*pbBorderVisible*<br/>
Variablen, die den Kennzeichnungsstatus empfängt. TRUE gibt an, dass der Rahmen des Steuerelements sichtbar ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_borderwidth"></a>  CStockPropImpl::get_BorderWidth

Rufen Sie diese Methode, um die Breite des Rahmens des Steuerelements zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>Parameter

*pnBorderWidth*<br/>
Eine Variable, die Breite des Rahmens des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_caption"></a>  CStockPropImpl::get_Caption

Rufen Sie diese Methode zum Abrufen des Texts in ein Objekt mit der Beschriftung angegeben.

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>Parameter

*pbstrCaption*<br/>
Der Text, mit dem Steuerelement angezeigt werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_drawmode"></a>  CStockPropImpl::get_DrawMode

Rufen Sie diese Methode zum Abrufen des Steuerelements Zeichnungsmodus des, z. B. XOR Stift oder Farben umkehren.

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>Parameter

*pnDrawMode*<br/>
Eine Variable, die Zeichnungsmodus des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_drawstyle"></a>  CStockPropImpl::get_DrawStyle

Rufen Sie diese Methode zum Abrufen des Steuerelements Zeichnungsart, z. B. solid, gestrichelt oder gepunktet.

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>Parameter

*pnDrawStyle*<br/>
Eine Variable, die Zeichnungsart des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_drawwidth"></a>  CStockPropImpl::get_DrawWidth

Rufen Sie diese Methode, um die Zeichnung Breite (in Pixel) ein, die die Methoden des Steuerelements zeichnen abzurufen.

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>Parameter

*pnDrawWidth*<br/>
Variablen, empfängt den Wert des Steuerelements Breite, in Pixel.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_enabled"></a>  CStockPropImpl::get_Enabled

Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob das Steuerelement aktiviert ist.

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>Parameter

*pbEnabled*<br/>
Variablen, die den Kennzeichnungsstatus empfängt. TRUE gibt an, dass das Steuerelement aktiviert ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_fillcolor"></a>  CStockPropImpl::get_FillColor

Rufen Sie diese Methode, um die Füllfarbe des Steuerelements zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>Parameter

*pclrFillColor*<br/>
Eine Variable, die Füllfarbe des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_fillstyle"></a>  CStockPropImpl::get_FillStyle

Rufen Sie diese Methode zum Abrufen von Füllformat des Steuerelements, z. B. ein, solid, transparente oder schraffierten.

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>Parameter

*pnFillStyle*<br/>
Variablen, die Füllformat des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_font"></a>  CStockPropImpl::get_Font

Rufen Sie diese Methode, um einen Zeiger auf die Schriftarteigenschaften des Steuerelements abzurufen.

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>Parameter

*ppFont*<br/>
Variable, die einen Zeiger auf die Schriftarteigenschaften des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_forecolor"></a>  CStockPropImpl::get_ForeColor

Rufen Sie diese Methode, um die Vordergrundfarbe des Steuerelements zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>Parameter

*pclrForeColor*<br/>
Eine Variable, die die Vordergrundfarbe der Steuerelemente empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_hwnd"></a>  CStockPropImpl::get_HWND

Rufen Sie diese Methode, um das Fensterhandle, das dem Steuerelement zugeordnete zu erhalten.

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parameter

*phWnd*<br/>
Das Fensterhandle, das dem Steuerelement zugeordnet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_mouseicon"></a>  CStockPropImpl::get_MouseIcon

Rufen Sie diese Methode zum Abrufen der Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, wenn der Mauszeiger über dem Steuerelement befindet.

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parameter

*ppPicture*<br/>
Variable, die einen Zeiger auf die Bildeigenschaften der Grafik empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_mousepointer"></a>  CStockPropImpl::get_MousePointer

Rufen Sie diese Methode zum Abrufen des Typs des Mauszeiger-auf, die angezeigt wird, wenn der Mauszeiger über dem Steuerelement, z. B., Pfeil, übergreifende oder Sanduhr dargestellt.

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>Parameter

*pnMousePointer*<br/>
Eine Variable, die den Typ des Mauszeigers empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_picture"></a>  CStockPropImpl::get_Picture

Rufen Sie diese Methode zum Abrufen eines Zeigers auf die Bildeigenschaften, der eine Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden.

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>Parameter

*ppPicture*<br/>
Variable, die einen Zeiger auf das Bild in den Eigenschaften empfängt. Finden Sie unter [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_readystate"></a>  CStockPropImpl::get_ReadyState

Rufen Sie diese Methode rufen Sie den Zustand des Steuerelements bereit, z. B., laden oder geladen wird.

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>Parameter

*pnReadyState*<br/>
Eine Variable, die Status "bereit" des Steuerelements empfängt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_tabstop"></a>  CStockPropImpl::get_TabStop

Rufen Sie diese Methode, um den Status des Flags erhalten, der angibt, ob das Steuerelement einen Tabstopp oder nicht.

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>Parameter

*pbTabStop*<br/>
Variablen, die den Kennzeichnungsstatus empfängt. TRUE gibt an, dass das Steuerelement einen Tabstopp.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_text"></a>  CStockPropImpl::get_Text

Rufen Sie diese Methode zum Abrufen des Texts, der mit dem Steuerelement angezeigt wird.

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>Parameter

*pbstrText*<br/>
Der Text, der mit dem Steuerelement angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_valid"></a>  CStockPropImpl::getvalid

Rufen Sie diese Methode, um den Status des Flags erhalten, die angibt, ob das Steuerelement gültig oder nicht ist.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>Parameter

*pbValid*<br/>
Variablen, die den Kennzeichnungsstatus empfängt. TRUE gibt an, dass das Steuerelement gültig ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="get_window"></a>  CStockPropImpl::get_Window

Rufen Sie diese Methode, um das Fensterhandle, das dem Steuerelement zugeordnete zu erhalten. Identisch mit [CStockPropImpl::get_HWND](#get_hwnd).

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>Parameter

*phWnd*<br/>
Das Fensterhandle, das dem Steuerelement zugeordnet.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_appearance"></a>  CStockPropImpl::put_Appearance

Rufen Sie diese Methode, um die Paint-Stil, die vom Steuerelement verwendet, z. B., flach oder 3D festgelegt.

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>Parameter

*nAppearance*<br/>
Der neue Paint-Stil, der vom Steuerelement verwendet werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_autosize"></a>  CStockPropImpl::put_AutoSize

Rufen Sie diese Methode, um den Wert des Flags festlegen, die angibt, ob das Steuerelement eine beliebige andere Größe aufweisen, kann nicht an.

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>Parameter

*bAutoSize*<br/>
TRUE, wenn das Steuerelement eine beliebige andere Größe darf nicht sein.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_backcolor"></a>  CStockPropImpl::put_BackColor

Rufen Sie diese Methode, um die Hintergrundfarbe des Steuerelements festzulegen.

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>Parameter

*clrBackColor*<br/>
Die neue Hintergrundfarbe Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_backstyle"></a>  CStockPropImpl::put_BackStyle

Rufen Sie diese Methode zum Festlegen von Hintergrund-Format des Steuerelements.

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>Parameter

*nBackStyle*<br/>
Das neue Steuerelement Hintergrundformat.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_bordercolor"></a>  CStockPropImpl::put_BorderColor

Rufen Sie diese Methode, um die Farbe des Rahmens des Steuerelements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>Parameter

*clrBorderColor*<br/>
Farbe des neuen Rahmens. Der Datentyp OLE_COLOR wird intern als eine 32-Bit-Ganzzahl dargestellt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_borderstyle"></a>  CStockPropImpl::put_BorderStyle

Rufen Sie diese Methode, um die Rahmenart des Steuerelements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>Parameter

*nBorderStyle*<br/>
Die neue Rahmenart.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_bordervisible"></a>  CStockPropImpl::put_BorderVisible

Rufen Sie diese Methode, um den Wert des Flags festlegen, die angibt, ob der Rahmen des Steuerelements sichtbar ist.

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>Parameter

*bBorderVisible*<br/>
TRUE, wenn der Rahmen sichtbar ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_borderwidth"></a>  CStockPropImpl::put_BorderWidth

Rufen Sie diese Methode, um die Breite des Rahmens des Steuerelements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>Parameter

*nBorderWidth*<br/>
Die neue Breite des Rahmens des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_caption"></a>  CStockPropImpl::put_Caption

Rufen Sie diese Methode zum Festlegen des Texts, der mit dem Steuerelement angezeigt werden.

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>Parameter

*bstrCaption*<br/>
Der Text, mit dem Steuerelement angezeigt werden.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_drawmode"></a>  CStockPropImpl::put_DrawMode

Rufen Sie diese Methode zum Festlegen des Steuerelements Zeichnungsmodus des, z. B. XOR Stift oder Farben umkehren.

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>Parameter

*nDrawMode*<br/>
Die neue Zeichnungsmodus für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_drawstyle"></a>  CStockPropImpl::put_DrawStyle

Rufen Sie diese Methode, um das Format des Steuerelements zeichnen, legen Sie z. B. solid, gestrichelt oder gepunktet.

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>Parameter

*nDrawStyle*<br/>
Die neue Zeichnungsart für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_drawwidth"></a>  CStockPropImpl::put_DrawWidth

Rufen Sie diese Methode, um die Breite (in Pixel) ein, die die Methoden des Steuerelements zeichnen festgelegt.

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>Parameter

*nDrawWidth*<br/>
Die neue Breite auf, die vom Steuerelement verwendet werden, die Methoden zeichnen.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_enabled"></a>  CStockPropImpl::put_Enabled

Rufen Sie diese Methode, um den Wert des Flags festlegen, die angibt, ob das Steuerelement aktiviert ist.

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>Parameter

*bEnabled*<br/>
TRUE, wenn das Steuerelement aktiviert ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_fillcolor"></a>  CStockPropImpl::put_FillColor

Rufen Sie diese Methode, um die Füllfarbe des Steuerelements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>Parameter

*clrFillColor*<br/>
Die neue Füllfarbe für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_fillstyle"></a>  CStockPropImpl::put_FillStyle

Rufen Sie diese Methode, um das Füllformat des Steuerelements, legen Sie z. B. solid, transparente oder schraffiert.

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>Parameter

*nFillStyle*<br/>
Die neue Füllformat für das Steuerelement.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_font"></a>  CStockPropImpl::put_Font

Rufen Sie diese Methode, um die Schriftarteigenschaften des Steuerelements festgelegt.

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
Ein Zeiger auf die Schriftarteigenschaften des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_forecolor"></a>  CStockPropImpl::put_ForeColor

Rufen Sie diese Methode zum Festlegen der Vordergrundfarbe des Steuerelements.

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>Parameter

*clrForeColor*<br/>
Die neue Vordergrundfarbe des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_hwnd"></a>  CStockPropImpl::put_HWND

Diese Methode gibt E_FAIL zurück.

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
Reserviert.

### <a name="return-value"></a>Rückgabewert

Returns E_FAIL.

### <a name="remarks"></a>Hinweise

Das Handle des Fensters ist ein schreibgeschützter Wert.

##  <a name="put_mouseicon"></a>  CStockPropImpl::put_MouseIcon

Rufen Sie diese Methode zum Festlegen der Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, wenn der Mauszeiger über dem Steuerelement befindet.

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*pPicture*<br/>
Ein Zeiger auf die Bildeigenschaften der Grafik.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_mousepointer"></a>  CStockPropImpl::put_MousePointer

Rufen Sie diese Methode, um den Typ des Mauszeiger-auf, die angezeigt wird, wenn der Mauszeiger über dem Steuerelement, z. B., Pfeil, übergreifende oder Sanduhr dargestellt.

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>Parameter

*nMousePointer*<br/>
Der Typ des Mauszeigers.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_picture"></a>  CStockPropImpl::put_Picture

Rufen Sie diese Methode zum Festlegen der Bildeigenschaften, der eine Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden.

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*pPicture*<br/>
Ein Zeiger auf das Bild der Eigenschaften. Finden Sie unter [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_readystate"></a>  CStockPropImpl::put_ReadyState

Rufen Sie diese Methode, um den Zustand des Steuerelements bereit, legen Sie z. B. Laden oder geladen.

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>Parameter

*nReadyState*<br/>
Der Zustand des Steuerelements bereit.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_tabstop"></a>  CStockPropImpl::put_TabStop

Rufen Sie diese Methode, um das Flag festgelegt, die angibt, ob das Steuerelement einen Tabstopp oder nicht.

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>Parameter

*bTabStop*<br/>
TRUE, wenn das Steuerelement einen Tabstopp darstellt.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_text"></a>  CStockPropImpl::put_Text

Rufen Sie diese Methode, um den Text festlegen, der mit dem Steuerelement angezeigt wird.

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>Parameter

*bstrText*<br/>
Der Text, der mit dem Steuerelement angezeigt wird.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_valid"></a>  CStockPropImpl::putvalid

Rufen Sie diese Methode, um das Flag festgelegt, die angibt, ob das Steuerelement gültig oder nicht ist.

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>Parameter

*bValid*<br/>
TRUE, wenn das Steuerelement gültig ist.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

##  <a name="put_window"></a>  CStockPropImpl::put_Window

Diese Methode ruft [CStockPropImpl::put_HWND](#put_hwnd), E_FAIL zurückgegeben.

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>Parameter

*hWnd*<br/>
Das Fensterhandle.

### <a name="return-value"></a>Rückgabewert

Returns E_FAIL.

### <a name="remarks"></a>Hinweise

Das Handle des Fensters ist ein schreibgeschützter Wert.

##  <a name="putref_font"></a>  CStockPropImpl::putref_Font

Rufen Sie diese Methode, um die Schriftarteigenschaften des Steuerelements, mit einer Verweisanzahl festgelegt.

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>Parameter

*pFont*<br/>
Ein Zeiger auf die Schriftarteigenschaften des Steuerelements.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Identisch mit [CStockPropImpl::put_Font](#put_font), jedoch mit einer Verweisanzahl.

##  <a name="putref_mouseicon"></a>  CStockPropImpl::putref_MouseIcon

Rufen Sie diese Methode zum Festlegen der Bildeigenschaften der Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, wenn der Mauszeiger über dem Steuerelement, mit einer Verweisanzahl ein.

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*pPicture*<br/>
Ein Zeiger auf die Bildeigenschaften der Grafik.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Identisch mit [CStockPropImpl::put_MouseIcon](#put_mouseicon), jedoch mit einer Verweisanzahl.

##  <a name="putref_picture"></a>  CStockPropImpl::putref_Picture

Rufen Sie diese Methode zum Festlegen der Bildeigenschaften, der eine Grafik (Symbol, Bitmap oder Metadatei) angezeigt werden, mit einer Verweisanzahl ein.

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>Parameter

*pPicture*<br/>
Ein Zeiger auf das Bild der Eigenschaften. Finden Sie unter [IPictureDisp](/windows/desktop/api/ocidl/nn-ocidl-ipicturedisp) Weitere Details.

### <a name="return-value"></a>Rückgabewert

Gibt S_OK bei Erfolg oder einen HRESULT-Fehler bei einem Fehler zurück.

### <a name="remarks"></a>Hinweise

Identisch mit [CStockPropImpl::put_Picture](#put_picture), jedoch mit einer Verweisanzahl.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[IDispatchImpl-Klasse](../../atl/reference/idispatchimpl-class.md)
