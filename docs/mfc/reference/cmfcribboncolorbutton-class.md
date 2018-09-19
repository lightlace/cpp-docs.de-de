---
title: CMFCRibbonColorButton-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonColorButton [MFC], CMFCRibbonColorButton
- CMFCRibbonColorButton [MFC], AddColorsGroup
- CMFCRibbonColorButton [MFC], EnableAutomaticButton
- CMFCRibbonColorButton [MFC], EnableOtherButton
- CMFCRibbonColorButton [MFC], GetAutomaticColor
- CMFCRibbonColorButton [MFC], GetColor
- CMFCRibbonColorButton [MFC], GetColorBoxSize
- CMFCRibbonColorButton [MFC], GetColumns
- CMFCRibbonColorButton [MFC], GetHighlightedColor
- CMFCRibbonColorButton [MFC], RemoveAllColorGroups
- CMFCRibbonColorButton [MFC], SetColor
- CMFCRibbonColorButton [MFC], SetColorBoxSize
- CMFCRibbonColorButton [MFC], SetColorName
- CMFCRibbonColorButton [MFC], SetColumns
- CMFCRibbonColorButton [MFC], SetDocumentColors
- CMFCRibbonColorButton [MFC], SetPalette
- CMFCRibbonColorButton [MFC], UpdateColor
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb80e0e839169b0f78648cc2090f339b43f6360a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415335"
---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton-Klasse

Die `CMFCRibbonColorButton` -Klasse implementiert eine Farbenschaltfläche, die einer Menübandleiste hinzugefügt werden kann. Die Menüband-Farbenschaltfläche zeigt ein Dropdownmenü an, das eine oder mehrere Farbpaletten enthält.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonColorButton : public CMFCRibbonGallery
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Fügt dem normalen Farbbereich eine Gruppe Farben hinzu.|
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Gibt an, ob die Schaltfläche **Automatisch** aktiviert ist.|
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Aktiviert die Schaltfläche **Weitere** .|
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||
|[CMFCRibbonColorButton::GetColor](#getcolor)|Gibt die aktuell ausgewählte Farbe zurück.|
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Gibt die Größe der Farbelemente zurück, die in der Farbleiste angezeigt werden.|
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Gibt die Farbe des aktuell in der Popup-Farbpalette ausgewählten Elements zurück.|
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Entfernt alle Farbgruppen aus dem normalen Farbbereich.|
|[CMFCRibbonColorButton::SetColor](#setcolor)|Wählt eine Farbe aus dem normalen Farbbereich aus.|
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Legt die Größe aller Farbelemente fest, die in der Farbleiste angezeigt werden.|
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Gibt eine Liste mit RGB-Werten für die Anzeige im Farbbereich des Dokuments an.|
|[CMFCRibbonColorButton::SetPalette](#setpalette)||
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||

## <a name="remarks"></a>Hinweise

Die Farbenschaltfläche im Menüband zeigt eine Farbleiste an, wenn ein Benutzer drauf drückt. Standardmäßig enthält diese Farbleiste eine Farbauswahlpalette, die als normaler Farbbereich bezeichnet wird. Optional kann die Farbleiste eine Schaltfläche **Automatisch** , die dem Benutzer die Auswahl einer Standardfarbe ermöglicht, und eine Schaltfläche **Weitere** anzeigen, die eine Popupfarbpalette anzeigt, die weitere Farben enthält.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonColorButton` -Klasse. Im Beispiel wird gezeigt, wie ein `CMFCRibbonColorButton` -Objekt konstruiert wird, das große Bild festgelegt wird, die Schaltfläche **Automatisch** aktiviert wird, die Schaltfläche **Weitere** aktiviert wird, die Spaltenanzahl festgelegt wird, die Größe aller Farbelemente festgelegt wird, die auf der Farbleiste angezeigt werden, dem normalen Farbbereich eine Gruppe Farben hinzugefügt wird, und eine Liste mit RGB-Werten für die Anzeige im Farbbereich des Dokuments angegeben wird. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)

[CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribboncolorbutton.h

##  <a name="addcolorsgroup"></a>  CMFCRibbonColorButton::AddColorsGroup

Fügt dem normalen Farbbereich eine Gruppe Farben hinzu.

```
void AddColorsGroup(
    LPCTSTR lpszName,
    const CList<COLORREF,COLORREF>& lstColors,
    BOOL bContiguousColumns=FALSE);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
[in] Der Gruppenname.

*lstColors*<br/>
[in] Die Liste der Farben.

*bContiguousColumns*<br/>
[in] Steuert, wie die Farbe-Elemente in der Gruppe angezeigt werden. Bei "true", werden die Elemente der Farbe ohne einen vertikalen Abstand gezeichnet. Wenn "FALSE" werden die Color-Elemente mit einem vertikalen Abstand gezeichnet.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um die Farbe zu machen, das Popup anzeigen mehrere Gruppen von Farben. Sie können steuern, wie die Farben in der Gruppe angezeigt werden.

##  <a name="cmfcribboncolorbutton"></a>  CMFCRibbonColorButton::CMFCRibbonColorButton

Erstellt ein `CMFCRibbonColorButton`-Objekt.

```
CMFCRibbonColorButton();


CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    int nSmallImageIndex,
    COLORREF color = RGB(0, 0, 0));


CMFCRibbonColorButton(
    UINT nID,
    LPCTSTR lpszText,
    BOOL bSimpleButtonLook,
    int nSmallImageIndex,
    int nLargeImageIndex,
    COLORREF color = RGB(0, 0, 0));
```

### <a name="parameters"></a>Parameter

*nID*<br/>
[in] Gibt an, die Befehls-ID des Befehls, die ausgeführt werden, wenn ein Benutzer auf die Schaltfläche klickt.

*lpszText*<br/>
[in] Gibt den Text auf die Schaltfläche angezeigt werden.

*nSmallImageIndex*<br/>
[in] Der nullbasierte Index, der das kleine Bild auf die Schaltfläche angezeigt werden soll.

*Farbe*<br/>
[in] Die Farbe der Schaltfläche (Standardwert ist schwarz).

*bSimpleButtonLook*<br/>
[in] Wenn TRUE, wird die Schaltfläche als einfaches Rechteck gezeichnet.

*nLargeImageIndex*<br/>
[in] Der nullbasierte Index des großen Bilds auf die Schaltfläche angezeigt werden.

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="enableautomaticbutton"></a>  CMFCRibbonColorButton::EnableAutomaticButton

Gibt an, ob die Schaltfläche **Automatisch** aktiviert ist.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE,
    LPCTSTR lpszToolTip=NULL,
    BOOL bOnTop=TRUE,
    BOOL bDrawBorder=FALSE);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Die Bezeichnung für die **automatische** Schaltfläche.

*colorAutomatic*<br/>
[in] RGB-Wert, der angibt, die **automatische** Standardfarbe der Schaltfläche.

*bAktivieren*<br/>
[in] TRUE, wenn die **automatische** Schaltfläche aktiviert ist. "False", wenn er deaktiviert ist.

*lpszToolTip*<br/>
[in] Die QuickInfo von den **automatische** Schaltfläche.

*bOnTop*<br/>
[in] Gibt an, ob die **automatische** Schaltfläche ist im oberen Bereich vor der Farbpalette anzeigen.

*bDrawBorder*<br/>
[in] TRUE, wenn die Anwendung einen Rahmen um die Farbleiste auf die Menüband-farbenschaltfläche zeichnet. Farbleiste zeigt die zurzeit ausgewählte Farbe an. FALSE, wenn die Anwendung kein Rahmen gezeichnet wird

##  <a name="enableotherbutton"></a>  CMFCRibbonColorButton::EnableOtherButton

Aktiviert die Schaltfläche **Weitere** .

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    LPCTSTR lpszToolTip=NULL);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
Die Beschriftung der Schaltfläche.

*lpszToolTip*<br/>
Der QuickInfo-Text für die **andere** Schaltfläche.

### <a name="remarks"></a>Hinweise

Die **andere** Schaltfläche ist die Schaltfläche, die unter der Gruppe der Farben angezeigt werden. Klickt der Benutzer die **andere** Schaltfläche ein Dialogfeld Farbe angezeigt.

##  <a name="getautomaticcolor"></a>  CMFCRibbonColorButton::GetAutomaticColor

Ruft die aktuelle Farbe der Schaltfläche automatisch ab.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein RGB-Farbwert, der die aktuelle Farbe für die automatische Schaltfläche darstellt.

### <a name="remarks"></a>Hinweise

Die Farbe der Schaltfläche automatisch festgelegt ist, indem die `colorAutomatic` Parameter zu übergeben, um die `CMFCRibbonColorButton::EnableAutomaticButton` Methode.

##  <a name="getcolor"></a>  CMFCRibbonColorButton::GetColor

Gibt die aktuell ausgewählte Farbe zurück.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe, die durch Klicken auf die Schaltfläche ausgewählt wird.

##  <a name="getcolorboxsize"></a>  CMFCRibbonColorButton::GetColorBoxSize

Gibt die Größe der Farbelemente zurück, die in der Farbleiste angezeigt werden.

```
CSize GetColorBoxSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe der Schaltflächen Farbe in der Dropdown-Farben-Palette.

##  <a name="getcolumns"></a>  CMFCRibbonColorButton::GetColumns

Ruft die Anzahl der Elemente in einer Zeile die Menüband-farbenschaltfläche Katalog anzeigen.

```
int GetColumns() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Symbole in jeder Zeile zurück.

### <a name="remarks"></a>Hinweise

##  <a name="gethighlightedcolor"></a>  CMFCRibbonColorButton::GetHighlightedColor

Gibt die Farbe des aktuell ausgewählten Elements auf die Popup-Farbpalette zurück.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe des aktuell ausgewählten Elements in der Popup-Farbpalette.

##  <a name="removeallcolorgroups"></a>  CMFCRibbonColorButton::RemoveAllColorGroups

Entfernt alle Farbgruppen aus dem normalen Farbbereich.

```
void RemoveAllColorGroups();
```

##  <a name="setcolor"></a>  CMFCRibbonColorButton::SetColor

Wählt eine Farbe aus dem normalen Farbbereich aus.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
[in] Eine Farbe festgelegt.

##  <a name="setcolorboxsize"></a>  CMFCRibbonColorButton::SetColorBoxSize

Legt die Größe aller Farbelemente fest, die in der Farbleiste angezeigt werden.

```
void SetColorBoxSize(CSize sizeBox);
```

### <a name="parameters"></a>Parameter

*sizeBox*<br/>
[in] Die neue Größe der Schaltflächen Farbe in der Farbpalette.

##  <a name="setcolorname"></a>  CMFCRibbonColorButton::SetColorName

Legt einen neuen Namen für eine angegebene Farbe fest.

```
static void __stdcall SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
[in] Eine Farbe der RGB-Wert.

*strName*<br/>
[in] Der neue Name für die angegebene Farbe.

### <a name="remarks"></a>Hinweise

Da sie aufruft, `CMFCColorBar::SetColorName`, diese Methode ändert den Namen der angegebenen Farbe in allen `CMFCColorBar` Objekte in der Anwendung.

##  <a name="setcolumns"></a>  CMFCRibbonColorButton::SetColumns

Legt fest, die Anzahl der Spalten in der Tabelle der Farben, die dem Benutzer, beim Auswahlprozess für den Benutzer Farbe angezeigt werden angezeigt.

```
void SetColumns(int nColumns);
```

### <a name="parameters"></a>Parameter

*nColumns*<br/>
[in] Die Anzahl der Farbsymbole in jeder Zeile angezeigt.

### <a name="remarks"></a>Hinweise

##  <a name="setdocumentcolors"></a>  CMFCRibbonColorButton::SetDocumentColors

Gibt eine Liste mit RGB-Werten für die Anzeige im Farbbereich des Dokuments an.

```
void SetDocumentColors(
    LPCTSTR lpszLabel,
    CList<COLORREF,COLORREF>& lstColors);
```

### <a name="parameters"></a>Parameter

*lpszLabel*<br/>
[in] Der Text, der mit den Dokumentfarben angezeigt werden.

*lstColors*<br/>
[in] Ein Verweis auf eine Liste mit RGB-Werten.

##  <a name="setpalette"></a>  CMFCRibbonColorButton::SetPalette

Gibt an, die standardmäßigen Farben, die in der Tabelle anzuzeigen, die die farbenschaltfläche zeigt.

```
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Parameter

*pPalette*<br/>
[in] Ein Zeiger auf eine Farbpalette.

### <a name="remarks"></a>Hinweise

##  <a name="updatecolor"></a>  CMFCRibbonColorButton::UpdateColor

Vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Tabelle angezeigt wählt, wenn der Benutzer die Schaltfläche "Farbe" klickt.

```
void UpdateColor(COLORREF color);
```

### <a name="parameters"></a>Parameter

*Farbe*<br/>
[in] Eine Farbe, die vom Benutzer ausgewählt wurde.

### <a name="remarks"></a>Hinweise

Die `CMFCRibbonColorButton::UpdateColor` Methode ändert den aktuell ausgewählten die Farbe der Schaltfläche und benachrichtigt das übergeordnete Element durch Senden einer WM_COMMAND-Meldung mit einer standardmäßigen BN_CLICKED-Benachrichtigung. Verwenden der [CMFCRibbonColorButton::GetColor](#getcolor) Methode, um die ausgewählte Farbe abzurufen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonGallery-Klasse](../../mfc/reference/cmfcribbongallery-class.md)
