---
title: Cmfctoolbarfontcombobox-Klasse
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
ms.openlocfilehash: 7e19fc9257c1fe986ff09a8bbc86bf2fb55af7ee
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504741"
---
# <a name="cmfctoolbarfontcombobox-class"></a>Cmfctoolbarfontcombobox-Klasse

Eine Symbolleisten-Schaltfläche, die ein Kombinations Feld-Steuerelement enthält, das es dem Benutzer ermöglicht, eine Schriftart aus einer Liste von System Schriftarten auszuwählen.

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
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Gibt einen Zeiger auf das `CMFCFontInfo` -Objekt für einen angegebenen Index im Kombinations Feld zurück.|
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Wählt eine Schriftart im Kombinations Feld Schriftart entweder entsprechend dem Namen der Schriftart oder dem Präfix und Zeichensatz der Schriftart aus.|

### <a name="data-members"></a>Datenmember

[CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)<br/>
Die Höhe der Zeichen im Kombinations Feld Schriftart.

## <a name="remarks"></a>Hinweise

Gehen Sie folgendermaßen vor, um einer Symbolleiste eine Schaltfläche mit einem Schriftart-Kombinations Feld hinzuzufügen:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.

1. Konstruieren Sie ein `CMFCToolBarFontComboBox`-Objekt.

1. Ersetzen Sie im Meldungs Handler, der die AFX_WM_RESETTOOLBAR-Nachricht verarbeitet, die ursprüngliche Schaltfläche durch die Schaltfläche Neues Kombinations Feld, indem Sie [cmfctoolbar:: replacebutton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)verwenden.

1. Synchronisieren Sie die im Kombinations Feld ausgewählte Schriftart mit der Schriftart im Dokument, indem Sie die [cmfctoolbarfontcombobox:: SetFont](#setfont) -Methode verwenden.

Um die Schriftart des Dokuments mit der im Kombinations Feld ausgewählten Schriftart zu synchronisieren, verwenden Sie die [cmfctoolbarfontcombobox:: getfontdesc](#getfontdesc) -Methode, um die Attribute der ausgewählten Schriftart abzurufen, und verwenden Sie diese Attribute zum Erstellen eines [CFont-Klassen](../../mfc/reference/cfont-class.md) Objekts.

Mit der Schaltfläche Schriftart-Kombinations Feld wird die Win32-Funktion [enumfontfamiliesex](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw) aufgerufen, um die für das System verfügbaren Bildschirme und Drucker Schriftarten zu ermitteln

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarfontcombobox. h

##  <a name="cmfctoolbarfontcombobox"></a>Cmfctoolbarfontcombobox:: cmfctoolbarfontcombobox

Erstellt ein [cmfctoolbarfontcombobox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) -Objekt.

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
in Die Befehls-ID des Kombinations Felds.

*iImage*<br/>
in Der null basierte Index eines Symbolleisten Bilds. Das Image befindet sich im [cmfctoolbarimages-Klassen](../../mfc/reference/cmfctoolbarimages-class.md) Objekt, das von der [cmfctoolbar-Klassen](../../mfc/reference/cmfctoolbar-class.md) Klasse verwaltet wird.

*nFontType*<br/>
in Die Schriftarten, die im Kombinations Feld enthalten sind. Dieser Parameter kann eine Kombination (boolescher Wert oder) der folgenden Werte sein:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
in Wenn DEFAULT_CHARSET festgelegt ist, enthält das Kombinations Feld alle eindeutig benannten Schriftarten in allen Zeichensätzen. (Wenn zwei Schriftarten mit demselben Namen vorhanden sind, enthält das Kombinations Feld eine davon.) Wenn der Wert auf einen gültigen Zeichensatz Wert festgelegt ist, enthält das Kombinations Feld nur Schriftarten im angegebenen Zeichensatz. Eine Auflistung möglicher Zeichensätze finden Sie unter [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) .

*dwStyle*<br/>
in Der Stil des Kombinations Felds. (siehe Kombinations [Feld-Stile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))

*iWidth*<br/>
in Die Breite des Bearbeitungs Steuer Elements in Pixel.

*nPitchAndFamily*<br/>
in Wenn DEFAULT_PITCH festgelegt ist, enthält das Kombinations Feld Schriftarten unabhängig von der Tonhöhe. Wenn FIXED_PITCH oder VARIABLE_PITCH festgelegt ist, enthält das Kombinations Feld nur Schriftarten mit diesem Typ. Das Filtern auf der Grundlage der Schriftfamilie wird derzeit nicht unterstützt.

*pLstFontsExternal*<br/>
vorgenommen Zeiger auf ein [CObList-Klassen](../../mfc/reference/coblist-class.md) Objekt, das die verfügbaren Schriftarten speichert.

### <a name="remarks"></a>Hinweise

In der Regel speichern- `CObList` ObjektedieListederverfügbarenSchriftartenineinemeinzelnenfreigegebenenObjekt.`CMFCToolBarFontComboBox` Wenn Sie die zweite Überladung des Konstruktors verwenden und einen gültigen Zeiger auf *plstfontsexternal*bereitstellen, `CMFCToolBarFontComboBox` lädt dieses Objekt stattdessen den `CObList` , auf den *plstfontsexternal* zeigt, mit verfügbaren Schriftarten.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie ein `CMFCToolBarFontComboBox` -Objekt erstellt wird. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

##  <a name="getfontdesc"></a>Cmfctoolbarfontcombobox:: getfontcsc

Gibt einen Zeiger auf das `CMFCFontInfo` -Objekt für einen angegebenen Index im Kombinations Feld zurück.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Gibt den NULL basierten Index eines Kombinations Feld Elements an.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `CMFCFontInfo` -Objekt. Wenn *iIndex* keinen gültigen Element Index angibt, ist der Rückgabewert NULL.

##  <a name="m_nfontheight"></a>Cmfctoolbarfontcombobox:: m_nFontHeight

Gibt die Höhe von Zeichen im Kombinations Feld "Schriftart" in Pixel an, wenn das Kombinations Feld über einen Besitzer Zeichnungs Stil verfügt.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Hinweise

Wenn die `m_nFontHeight` Variable den Wert 0 hat, wird die Höhe automatisch entsprechend der Standard Schriftart des Kombinations Felds berechnet. Die Höhe umfasst sowohl den Anstieg der Zeichen oberhalb der Baseline als auch den Abstieg der Zeichen unterhalb der Baseline.

##  <a name="setfont"></a>Cmfctoolbarfontcombobox:: SetFont

Wählt die Schriftart im Kombinations Feld Schriftart entsprechend dem in den Parametern angegebenen Schriftart Namen und Zeichensatz aus.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
in Gibt den Namen oder das Präfix der Schriftart an.

*nCharSet*<br/>
in Gibt den Zeichensatz an.

*bExact*<br/>
in Gibt an, ob *lpszname* den Schriftart Namen oder das Schriftart Präfix enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Schriftart erfolgreich ausgewählt wurde. andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn *bexact* auf true festgelegt ist, wählt diese Methode eine Schriftart aus, die exakt mit dem Namen übereinstimmt, den Sie als *lpszname*angegeben haben. Wenn *bexact* auf false festgelegt ist, wählt diese Methode eine Schriftart aus, die mit dem als *lpszname* angegebenen Text beginnt und den Zeichensatz verwendet, den Sie als *ncharset*angegeben haben. Wenn *ncharset* auf DEFAULT_CHARSET festgelegt ist, wird der Zeichensatz ignoriert, und nur *lpszname* wird verwendet, um eine Schriftart auszuwählen.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen in eine Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
