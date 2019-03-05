---
title: CMFCRibbonSlider-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: 85c646e2fa524268e4559b587f90c5e06971b765
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300325"
---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider-Klasse

Die `CMFCRibbonSlider` -Klasse implementiert ein Schieberegler-Steuerelement, das einer menübandleiste oder einer Menüband-Statusleiste hinzugefügt werden können. Das Schieberegler-Steuerelement im Menüband ähnelt den Zoomschiebereglern, die in Office 2007-Anwendungen verwendet werden.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Erstellt und initialisiert ein Menüband-Schieberegler-Steuerelement.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonSlider::GetPos](#getpos)|Gibt die aktuelle Position des Schieberegler-Steuerelements zurück.|
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Gibt zurück, den maximalen Wert des Schiebereglers.|
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Gibt den minimalen Wert des Slider-Elements zurück.|
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Gibt die Größe der Zoomschritt für das Schieberegler-Steuerelement zurück.|
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Gibt an, ob der Schieberegler Zoomschaltflächen verfügt.|
|[CMFCRibbonSlider::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das Menübandelement zu zeichnen. (Überschreibt [cmfcribbonbaseelement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonSlider::SetPos](#setpos)|Legt die aktuelle Position des Schieberegler-Steuerelements fest.|
|[CMFCRibbonSlider::SetRange](#setrange)|Gibt den Bereich des Schieberegler-Steuerelements durch Festlegen der minimalen und maximalen Werte an.|
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Anzeigen oder Ausblenden der Zoomschaltflächen.|
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Legt die Größe der Zoomschritt für das Schieberegler-Steuerelement fest.|

## <a name="remarks"></a>Hinweise

Sie können die `SetRange` Methode zum Konfigurieren des Bereichs von einer Zoomschritte für den Schieberegler. Sie können die aktuelle Position des Schiebereglers festlegen, mit der `SetPos` Methode.

Sie können auch zirkuläre Zoomschaltflächen auf der linken und rechten Seite des Schieberegler-Steuerelements anzeigen, mit der `SetZoomButtons` Methode. Standardmäßig der Schieberegler ist horizontal, die linken Zoom-Schaltfläche wird ein Minuszeichen (-) angezeigt, und die richtigen zoomschaltfläche zeigt ein Pluszeichen (+).

Die `SetZoomIncrement` Methode definiert den inkrementellen Wert hinzufügen oder von der aktuellen Position subtrahiert werden soll, wenn ein Benutzer die Zoom-Schaltflächen klickt.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonSlider` Klasse zum Festlegen der Eigenschaften des Schiebereglers. Das Beispiel zeigt, wie zum Erstellen einer `CMFCRibbonSlider` Objekt Zoomschaltflächen anzuzeigen, legen Sie die aktuelle Position des Schieberegler-Steuerelements und Festlegen des Bereichs der Werte für das Schieberegler-Steuerelement.

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribbonslider.h

##  <a name="cmfcribbonslider"></a>  CMFCRibbonSlider::CMFCRibbonSlider

Erstellen Sie einen Schieberegler Menüband.

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>Parameter

*nID*<br/>
[in] Schieberegler-ID.

[in]. *nWidth* Schieberegler Breite in Pixel.

### <a name="remarks"></a>Hinweise

Erstellt einen Menüband-Schieberegler, der *nWidth* Pixel breit ist, in der Kategorie "Bereich", in dem der Schieberegler wird hinzugefügt. Standardmäßig ist der Schieberegler horizontal.

##  <a name="getpos"></a>  CMFCRibbonSlider::GetPos

Gibt die aktuelle Position des Schieberegler-Steuerelements zurück.

```
int GetPos() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Position des Schieberegler-Steuerelements, das eine Position relativ zum Anfang des Slider-Elements ist.

##  <a name="getrangemax"></a>  CMFCRibbonSlider::GetRangeMax

Ruft das maximale Inkrement des Slider-Elements, das der Schieberegler auf das Schieberegler-Steuerelement übertragen werden kann.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Rückgabewert

Das maximale Inkrement des Slider-Elements, das der Schieberegler auf das Schieberegler-Steuerelement übertragen werden kann.

##  <a name="getrangemin"></a>  CMFCRibbonSlider::GetRangeMin

Gibt das minimale Inkrement, das der Schieberegler auf das Schieberegler-Steuerelement übertragen werden kann.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Rückgabewert

Das minimale Inkrement, das der Schieberegler auf das Schieberegler-Steuerelement übertragen werden kann.

##  <a name="getregularsize"></a>  CMFCRibbonSlider::GetRegularSize

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="getzoomincrement"></a>  CMFCRibbonSlider::GetZoomIncrement

Rufen Sie den Zoomschritt für das Schieberegler-Steuerelement.

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>Rückgabewert

Der Zoomschritt für das Schieberegler-Steuerelement.

##  <a name="haszoombuttons"></a>  CMFCRibbonSlider::HasZoomButtons

Gibt an, ob der Schieberegler Zoomschaltflächen verfügt.

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Schieberegler Zoomschaltflächen hat. "False" andernfalls.

##  <a name="ondraw"></a>  CMFCRibbonSlider::OnDraw

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parameter

[in] *pDC*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="setpos"></a>  CMFCRibbonSlider::SetPos

Legen Sie die aktuelle Position des Schieberegler-Steuerelements.

```
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
[in] Gibt die Position, die für den Schieberegler festgelegt. Die Position ist relativ zum Anfang des Schiebereglers.

*bRedraw*<br/>
[in] Wenn TRUE, wird der Schieberegler neu gezeichnet werden.

##  <a name="setrange"></a>  CMFCRibbonSlider::SetRange

Legen Sie den Bereich der Werte für das Schieberegler-Steuerelement.

```
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parameter

*nMin*<br/>
[in] Gibt die minimalen Wert des Slider-Steuerelements an.

*nMax*<br/>
[in] Gibt die maximale Wert des Slider-Steuerelements an.

### <a name="remarks"></a>Hinweise

Gibt den Bereich der Werte für das Schieberegler-Steuerelement durch Festlegen der minimalen und maximalen Werte an.

##  <a name="setzoombuttons"></a>  CMFCRibbonSlider::SetZoomButtons

Ein- oder Ausblenden von Zoom-Schaltflächen.

```
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>Parameter

[in]. *bSet* "true" Anzeige Zoomschaltflächen; "False", um sie auszublenden.

##  <a name="setzoomincrement"></a>  CMFCRibbonSlider::SetZoomIncrement

Legen Sie den Zoomschritt für das Schieberegler-Steuerelement.

```
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>Parameter

*nZoomIncrement*<br/>
[in] Gibt den Zoomschritt des Schieberegler-Steuerelements an.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)
