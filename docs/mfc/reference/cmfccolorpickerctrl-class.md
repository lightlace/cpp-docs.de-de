---
title: CMFCColorPickerCtrl-Klasse
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: 1977717ee590acb63655ba21bfa5eb6bfe7c9bd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403781"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl-Klasse

Die `CMFCColorPickerCtrl` -Klasse enthält Funktionen für ein Steuerelement, das verwendet wird, um Farben auszuwählen.

## <a name="syntax"></a>Syntax

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Erstellt ein `CMFCColorPickerCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Ruft die Farbe, die der Benutzer auswählt.|
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Ruft die Werte für Farbton, Intensität und Sättigung der Farbe, die der Benutzer auswählt.|
|[CMFCColorPickerCtrl::GetHue](#gethue)|Ruft ab, die Hue-Komponente, der die Farbe, die der Benutzer auswählt.|
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Ruft ab, die Luminanz-Komponente, der die Farbe, die der Benutzer auswählt.|
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Ruft ab, die Sättigungskomponente, der die Farbe, die der Benutzer auswählt.|
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Legt die aktuelle Farbe mit der Farbe, die durch die angegebenen Komponenten der RGB-Farbe oder die angegebene Zelle Sechseck definiert.|
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Legt die aktuelle Farbe auf den angegebenen RGB-Farbwert fest.|
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Legt die aktuelle Farbe auf den angegebenen HLS-Farbwert fest.|
|[CMFCColorPickerCtrl::SetHue](#sethue)|Ändert die Hue-Komponente von der zurzeit ausgewählte Farbe an.|
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Ändert die Luminanz-Komponente von der zurzeit ausgewählte Farbe an.|
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Legt die Breite der Leuchtdichte-Leiste in das Steuerelement für die Farbauswahl fest.|
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Legt die erste ausgewählte Farbe fest.|
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Legt die aktuelle Farbpalette fest.|
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Ändert die Sättigungskomponente von der zurzeit ausgewählte Farbe an.|
|[CMFCColorPickerCtrl::SetType](#settype)|Legt fest, den Typ von Steuerelement für die Farbauswahl angezeigt.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Vom Framework aufgerufen, bevor ein Cursor, der auf die ausgewählte Farbe verweist angezeigt wird.|

## <a name="remarks"></a>Hinweise

Standardfarben aus einer hexagonal Farbpalette ausgewählt sind, und benutzerdefinierte Farben werden von einem Balkendiagramm Leuchtdichte ausgewählt Farben mit Rot/Grün/Blau-Notation oder Farbton/Satuaration/Luminanz-Notation angegeben werden.

Die folgende Abbildung zeigt mehrere `CMFCColorPickerCtrl` Objekte.

![CMFCColorPickerCtrl-Dialogfeld](../../mfc/reference/media/colorpicker.png "CMFCColorPickerCtrl-Dialogfeld")

Die `CMFCColorPickerCtrl` unterstützt zwei Paare von Stilen. Die HEXADEZIMALE und HEX_GREYSCALE Stile eignen sich für standard-Auswahl. Die Auswahl und der LEUCHTDICHTE Stile eignen sich für benutzerdefinierte Farbauswahl.

Führen Sie die folgenden Schritte zum Integrieren der `CMFCColorPickerCtrl` Steuerelement in einem Dialogfeld:

1. Bei Verwendung der **ClassWizard**, legen Sie ein neue Schaltflächen-Steuerelement in Ihre Dialogfeldvorlage (da die `CMFCColorPickerCtrl` Klasse vererbt ist die `CButton` Klasse).

1. Fügen Sie eine Membervariable, die das neue Schaltflächen-Steuerelement in Ihre Dialogfeldklasse zugeordnet ist. Ändern Sie dann den Variablentyp aus `CButton` zu `CMFCColorPickerCtrl`.

1. Fügen Sie der `WM_INITDIALOG` Meldungshandler für die Dialogfeldklasse. Legen Sie in der Ereignishandler Typ, der Palette und der ersten ausgewählten Farbe des der `CMFCColorPickerCtrl` Steuerelement.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie konfigurieren eine `CMFCColorPickerCtrl` -Objekt unter Verwendung verschiedener Methoden in der `CMFCColorPickerCtrl` Klasse. Im Beispiel wird veranschaulicht, wie Sie den Typ der Datumsauswahl-Steuerelement festlegen, und wie die Farbe, Hue, Intensität und Überlastung des Netzwerks festgelegt. Im Beispiel ist Teil der [Beispiel neue Steuerelemente](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxcolorpickerctrl.h

##  <a name="cmfccolorpickerctrl"></a>  CMFCColorPickerCtrl::CMFCColorPickerCtrl

Erstellt ein `CMFCColorPickerCtrl`-Objekt.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="drawcursor"></a>  CMFCColorPickerCtrl::DrawCursor

Vom Framework aufgerufen, bevor ein Cursor, der auf die ausgewählte Farbe verweist angezeigt wird.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf einen Gerätekontext.

*rect*<br/>
[in] Gibt einen rechteckigen Rahmen um die ausgewählte Farbe an.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie die Form des Cursors zu ändern, die auf die ausgewählte Farbe verweist müssen.

##  <a name="getcolor"></a>  CMFCColorPickerCtrl::GetColor

Ruft die Farbe, die der Benutzer auswählt.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die RGB-Wert der ausgewählten Farbe.

### <a name="remarks"></a>Hinweise

##  <a name="gethls"></a>  CMFCColorPickerCtrl::GetHLS

Ruft die Werte für Farbton, Intensität und Sättigung der Farbe, die der Benutzer auswählt.

```
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>Parameter

*Hue*<br/>
[out] Zeiger auf eine Variable vom Typ double, das Hue-Informationen erhält.

*luminance*<br/>
[out] Zeiger auf eine Variable vom Typ double, der Leuchtdichte Informationen empfängt.

*saturation*<br/>
[out] Zeiger auf eine Variable vom Typ double, der Sättigung Informationen empfängt.

### <a name="remarks"></a>Hinweise

##  <a name="gethue"></a>  CMFCColorPickerCtrl::GetHue

Ruft ab, die Hue-Komponente, der die Farbe, die der Benutzer auswählt.

```
double GetHue() const;
```

### <a name="return-value"></a>Rückgabewert

Die Hue-Komponente der ausgewählten Farbe.

### <a name="remarks"></a>Hinweise

##  <a name="getluminance"></a>  CMFCColorPickerCtrl::GetLuminance

Ruft ab, die Luminanz-Komponente, der die Farbe, die der Benutzer auswählt.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Rückgabewert

Die Luminanz-Komponente der ausgewählten Farbe.

### <a name="remarks"></a>Hinweise

##  <a name="getsaturation"></a>  CMFCColorPickerCtrl::GetSaturation

Ruft ab, der Sättigungswert der die Farbe, die der Benutzer auswählt.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Rückgabewert

Die Sättigungskomponente der ausgewählten Farbe.

### <a name="remarks"></a>Hinweise

##  <a name="selectcellhexagon"></a>  CMFCColorPickerCtrl::SelectCellHexagon

Legt die aktuelle Farbe mit der Farbe, die durch die angegebenen Komponenten der RGB-Farbe oder die angegebene Zelle Sechseck definiert.

```
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>Parameter

*R*<br/>
[in] Die Farbe Rot-Komponente.

*G*<br/>
[in] Die Komponente grün.

*B*<br/>
[in] Die blaue Farbe-Komponente.

*w*<br/>
[in] Die X-Koordinate des Cursors, der auf eine Zelle Sechseck verweist.

*y*<br/>
[in] Die y-Koordinate des Cursors, der auf eine Zelle Sechseck verweist.

### <a name="return-value"></a>Rückgabewert

Die zweite Überladung dieser Methode gibt immer "false" zurück.

### <a name="remarks"></a>Hinweise

Die erste Überladung dieser Methode wird die aktuelle Farbe, die die Farbe, die das Steuerelement zur Auswahl Farbe entspricht, der Rot-, Grün- und Blau-Farbkomponenten angegeben.

Die zweite Überladung dieser Methode wird die aktuelle Farbe die Farbe von der Zelle Sechseck, auf das von der angegebenen Cursorposition.

##  <a name="setcolor"></a>  CMFCColorPickerCtrl::SetColor

Legt die aktuelle Farbe auf den angegebenen RGB-Farbwert fest.

```
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
[in] Ein RGB-Farbwert.

### <a name="remarks"></a>Hinweise

##  <a name="sethls"></a>  CMFCColorPickerCtrl::SetHLS

Legt die aktuelle Farbe auf den angegebenen HLS-Farbwert fest.

```
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>Parameter

*Hue*<br/>
[in] Ein Hue-Wert.

*luminance*<br/>
[in] Ein Luminanzwert.

*saturation*<br/>
[in] Der Wert eine Überlastung des Netzwerks.

*bInvalidate*<br/>
[in] True, um zu erzwingen, dass das Fenster, um die neue Farbe sofort zu aktualisieren. andernfalls "false". Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

##  <a name="sethue"></a>  CMFCColorPickerCtrl::SetHue

Ändert den Farbton der zurzeit ausgewählte Farbe an.

```
void SetHue(double Hue);
```

### <a name="parameters"></a>Parameter

*Hue*<br/>
[in] Ein Hue-Wert.

### <a name="remarks"></a>Hinweise

##  <a name="setluminance"></a>  CMFCColorPickerCtrl::SetLuminance

Ändert die Intensität der zurzeit ausgewählte Farbe an.

```
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>Parameter

*Sättigung*<br/>
[in] Ein Luminanzwert.

### <a name="remarks"></a>Hinweise

##  <a name="setluminancebarwidth"></a>  CMFCColorPickerCtrl::SetLuminanceBarWidth

Legt die Breite der Leuchtdichte-Leiste in das Steuerelement für die Farbauswahl fest.

```
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>Parameter

*w*<br/>
[in] Die Breite des Balkens Leuchtdichte gemessen in Pixel.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Ändern der Größe der Leuchtdichte-Leiste, die auf die **benutzerdefinierte** auf der Registerkarte das Steuerelement für die Farbauswahl. Die *w* Parameter gibt an, die neue Breite des Balkens Leuchtdichte. Der Wert für die Breite wird ignoriert, wenn drei Viertel der Breite des Clientbereichs überschritten.

##  <a name="setoriginalcolor"></a>  CMFCColorPickerCtrl::SetOriginalColor

Legt die erste ausgewählte Farbe fest.

```
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>Parameter

*ref*<br/>
[in] Ein RGB-Farbwert.

### <a name="remarks"></a>Hinweise

Aufgerufen Sie diese Methode wird, wenn das Steuerelement für die Farbauswahl initialisiert wird.

##  <a name="setpalette"></a>  CMFCColorPickerCtrl::SetPalette

Legt die aktuelle Farbpalette fest.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parameter

*pPalette*<br/>
[in] Zeiger auf eine Farbpalette.

### <a name="remarks"></a>Hinweise

Die Farbpalette definiert das Array der Farben, das angezeigt werden, in das Steuerelement für die Farbauswahl.

##  <a name="setsaturation"></a>  CMFCColorPickerCtrl::SetSaturation

Ändert die Sättigung der zurzeit ausgewählte Farbe an.

```
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>Parameter

*Sättigung*<br/>
[in] Der Wert eine Überlastung des Netzwerks.

### <a name="remarks"></a>Hinweise

##  <a name="settype"></a>  CMFCColorPickerCtrl::SetType

Legt fest, den Typ von Steuerelement für die Farbauswahl angezeigt.

```
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>Parameter

*colorType*<br/>
[in] Eine Farbe Picker-Steuerelementtyp.

Die Typen definiert sind, durch die `CMFCColorPickerCtrl::COLORTYPE` Enumeration. Die möglichen Typen sind LEUCHTDICHTE "," Auswahl "," HEX "und" HEX_GREYSCALE. Der Standardtyp ist die Auswahl.

### <a name="remarks"></a>Hinweise

Um eine Farbe Zeitauswahl-Steuerelement-Typ anzugeben, rufen Sie diese Methode auf, bevor das Windows-Steuerelement erstellt wird.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)
