---
title: CMFCToolBarFontComboBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
ms.openlocfilehash: 28b2b77ed28453f148786ba7109743a0b7baf598
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429259"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox-Klasse

Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement, die dem Benutzer ermöglicht enthält, wählen Sie eine Schriftart aus einer Liste von Systemschriftarten.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Erstellt ein `CMFCToolBarFontComboBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Gibt einen Zeiger auf die `CMFCFontInfo` Objekt für einen angegebenen Index im Kombinationsfeld.|
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Wählt einer Schriftart in die Schriftarten-Kombinationsfeld entsprechend entweder den Namen der Schriftart oder die Gruppe Präfix und das Zeichen der Schriftart aus.|

### <a name="data-members"></a>Datenmember

[CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)<br/>
Die Höhe der Zeichen in der Schriftarten-Kombinationsfeld.

## <a name="remarks"></a>Hinweise

Um eine Schriftart Kombinationsfelds-Schaltfläche einer Symbolleiste hinzuzufügen, gehen Sie folgendermaßen vor:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.

1. Konstruieren Sie ein `CMFCToolBarFontComboBox`-Objekt.

1. Ersetzen Sie im Meldungshandler, die AFX_WM_RESETTOOLBAR-Nachricht verarbeitet, die ursprüngliche Schaltfläche mit der neuen kombinationsfeldschaltfläche mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

1. Synchronisieren Sie die Schriftart im Kombinationsfeld in die Schriftart im Dokument mit ausgewählt ist die [CMFCToolBarFontComboBox::SetFont](#setfont) Methode.

Verwenden Sie zum Synchronisieren des Dokuments Schriftart mit der Schriftart im Kombinationsfeld ausgewählte die [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) Methode, um die Attribute der ausgewählten Schriftart abrufen und verwenden diese Attribute zum Erstellen einer [ CFont-Klasse](../../mfc/reference/cfont-class.md) Objekt.

Der Schriftart kombinationsfeldschaltfläche Aufrufe die Win32-Funktion [EnumFontFamiliesEx](/windows/desktop/api/wingdi/nf-wingdi-enumfontfamiliesexa) um zu bestimmen, die Bildschirm- und Schriftarten, die für das System verfügbar.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox

Erstellt eine [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Objekt.

```
public:
CMFCToolBarFontComboBox(
    UINT uiID,
    int iImage,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    DWORD dwStyle = CBS_DROPDOWN,
    int iWidth = 0,
    BYTE nPitchAndFamily = DEFAULT_PITCH);

protected:
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,
    int nFontType,
    BYTE nCharSet,
    BYTE nPitchAndFamily);

CMFCToolBarFontComboBox();
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
[in] Die Befehls-ID des Kombinationsfelds.

*iImage*<br/>
[in] Der nullbasierte Index, der ein Symbolleistenbild werden soll. Das Image befindet sich in der [CMFCToolBarImages-Klasse](../../mfc/reference/cmfctoolbarimages-class.md) -Objekt, [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md) -Klasse verwaltet.

*nFontType*<br/>
[in] Die Typen der Schriftarten, die im Kombinationsfeld enthält. Dieser Parameter kann eine Kombination aus (boolesche OR) die folgenden Werte sein:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
[in] Wenn auf DEFAULT_CHARSET, das Kombinationsfeld festgelegt ist, alle eindeutig benannte Schriftarten in allen Zeichensätzen enthält. (Treten zwei Schriftarten mit dem gleichen Namen, enthält das Kombinationsfeld eine davon.) Wenn auf einen gültigen Zeichen festgelegten Wert, der im Kombinationsfeld nur die Schriftarten in den angegebenen Zeichensatz enthält. Finden Sie unter ["LogFont"](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta) für eine Liste der möglichen Zeichen festlegt.

*dwStyle*<br/>
[in] Das Format des Kombinationsfelds. (finden Sie unter [Kombinationsfeldstile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))

*iWidth*<br/>
[in] Die Breite in Pixel des Edit-Steuerelements.

*nPitchAndFamily*<br/>
[in] Wenn auf DEFAULT_PITCH, das Kombinationsfeld festgelegt, Schriftarten, unabhängig von der Schriftbreite enthält. Wenn FIXED_PITCH oder VARIABLE_PITCH festgelegt, der im Kombinationsfeld nur Schriftarten mit diesem Typ Tonhöhe enthält. Filterung basierend auf Schriftfamilie wird derzeit nicht unterstützt.

*pLstFontsExternal*<br/>
[out] Zeiger auf eine [CObList-Klasse](../../mfc/reference/coblist-class.md) Objekt, das die verfügbaren Schriftarten speichert.

### <a name="remarks"></a>Hinweise

In der Regel `CMFCToolBarFontComboBox` Objekte speichern die Liste der verfügbaren Schriftarten in einer einzelnen freigegebenen `CObList` Objekt. Wenn Sie die zweite Überladung des Konstruktors verwenden und einen gültigen Zeiger auf *pLstFontsExternal*, `CMFCToolBarFontComboBox` Objekt stattdessen füllt die `CObList` , *pLstFontsExternal* Zeigt auf, mit den verfügbaren Schriftarten.

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCToolBarFontComboBox` Objekt. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc

Gibt einen Zeiger auf die `CMFCFontInfo` Objekt für einen angegebenen Index im Kombinationsfeld.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Gibt an, der nullbasierte Index des eine ComboBoxItem-Steuerelement.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CMFCFontInfo` -Objekt. Wenn *iIndex* gibt keinen gültige Element-Index, der Rückgabewert ist NULL.

##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight

Gibt die Höhe in Pixel der Zeichen in der Schriftarten-Kombinationsfeld, wenn das Kombinationsfeld Stil zeichnen Besitzer hat.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Hinweise

Wenn die `m_nFontHeight` Variable gleich 0 ist, der die Höhe wird entsprechend die Standardschriftart des Kombinationsfelds automatisch berechnet. Die Höhe enthält sowohl die Versalhöhe der Zeichen über der Baseline und die Unterlänge der Zeichen unterhalb der Basislinie.

##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont

SELECT-Anweisungen, die die Schriftart im Kombinationsfeld Schriftart entsprechend den Schriftartnamen und den Zeichen, die festlegen, werden in den Parametern angegeben.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
[in] Gibt den Namen oder das Präfix.

*nCharSet*<br/>
[in] Gibt den Zeichensatz an.

*bExact*<br/>
[in] Gibt an, ob *Wert* enthält den Namen der Schriftart oder das Präfix für die Schriftart.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Schriftart erfolgreich ausgewählt wurde, andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn *bExact* "true", wird diese Methode wählt eine Schriftart, die genau mit dem Namen, die Sie übereinstimmt als angegeben *Wert*. Wenn *bExact* ist "false", diese Methode wählt eine Schriftart, die mit dem Text beginnt, angegeben als *Wert* und den Zeichensatz an, die Sie als angegeben verwendet *nCharSet*. Wenn *nCharSet* festgelegt ist, DEFAULT_CHARSET, der Zeichensatz wird ignoriert und nur *Wert* wird verwendet, um eine Schriftart auswählen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)

