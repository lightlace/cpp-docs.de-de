---
title: CMFCToolBarFontSizeComboBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::GetTwipSize
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::RebuildFontSizes
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontSizeComboBox::SetTwipSize
helpviewer_keywords:
- CMFCToolBarFontSizeComboBox [MFC], CMFCToolBarFontSizeComboBox
- CMFCToolBarFontSizeComboBox [MFC], GetTwipSize
- CMFCToolBarFontSizeComboBox [MFC], RebuildFontSizes
- CMFCToolBarFontSizeComboBox [MFC], SetTwipSize
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
ms.openlocfilehash: 43832f6c9b02c43fbe4a05cbea3add8783150113
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767664"
---
# <a name="cmfctoolbarfontsizecombobox-class"></a>CMFCToolBarFontSizeComboBox-Klasse

Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement, die dem Benutzer ermöglicht enthält, wählen Sie einen Schriftgrad.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](#cmfctoolbarfontsizecombobox)|Erstellt ein `CMFCToolBarFontSizeComboBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize)|Gibt die Größe der ausgewählten Schriftart in Twips zurück.|
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes)|Füllt die Liste des Kombinationsfelds mit allen unterstützten Schriftgrade für eine angegebene Schriftart an.|
|[CMFCToolBarFontSizeComboBox::SetTwipSize](#settwipsize)|Legt den Schriftgrad in Twips fest.|

## <a name="remarks"></a>Hinweise

Können Sie eine `CMFCToolBarFontSizeComboBox` -Objekt zusammen mit einem [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Objekt, das einen Benutzer die Auswahl einer Schriftart und Schriftgröße zu aktivieren.

Sie können eine Font-Size-kombinationsfeldschaltfläche zu einer Symbolleiste hinzufügen, genau, wie Sie eine Schriftart Kombinationsfelds-Schaltfläche hinzufügen. Weitere Informationen finden Sie unter [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

Wenn der Benutzer wählt eine neue Schriftart in eine `CMFCToolBarFontComboBox` Objekt ist, können Sie das schriftartkombinationsfeld für die Größe mit füllen die unterstützten Größen für die Schriftart mithilfe der [CMFCToolBarFontSizeComboBox::RebuildFontSizes](#rebuildfontsizes) Methode.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarFontSizeComboBox` Klasse zum Konfigurieren einer `CMFCToolBarFontSizeComboBox` Objekt. Das Beispiel veranschaulicht, wie Sie den Schriftgrad, in Twips, aus dem Textfeld abzurufen, geben Sie das schriftartkombinationsfeld für Größe alle gültige Größen der angegebenen Schriftart und geben Sie den Schriftgrad in Twips. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontsizecombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarfontcombobox.h

##  <a name="cmfctoolbarfontsizecombobox"></a>  CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox

Erstellt ein `CMFCToolBarFontSizeComboBox`-Objekt.

```
CMFCToolBarFontSizeComboBox();
```

##  <a name="gettwipsize"></a>  CMFCToolBarFontSizeComboBox::GetTwipSize

Ruft den Schriftgrad, in Twips, aus dem Textfeld eines Kombinationsfelds Größe Schriftart ab.

```
int GetTwipSize() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn der Rückgabewert positiv ist, ist es der Schriftgrad in Twips. Es ist -1, wenn das Textfeld des Kombinationsfelds leer ist. Es ist – 2, wenn ein Fehler auftritt.

##  <a name="rebuildfontsizes"></a>  CMFCToolBarFontSizeComboBox::RebuildFontSizes

Füllt das Kombinationsfeld Größe Schriftart alle gültige Größen der angegebenen Schriftart.

```
void RebuildFontSizes(const CString& strFontName);
```

### <a name="parameters"></a>Parameter

*strFontName*<br/>
[in] Gibt den Namen einer Schriftart an.

### <a name="remarks"></a>Hinweise

Wenn Sie z. B. zwischen Auswahl in einem Schriftarten-Kombinationsfeld und ein Font-Size-Kombinationsfeld, synchronisieren möchten, rufen Sie diese Funktion eine [CMFCToolBarFontComboBox-Klasse](../../mfc/reference/cmfctoolbarfontcombobox-class.md).

##  <a name="settwipsize"></a>  CMFCToolBarFontSizeComboBox::SetTwipSize

Rundet den angegebenen die Größe (in Twips) auf die nächstgelegene Größe in Punkten, und dann wird der ausgewählten Größe auf diesen Wert im Kombinationsfeld.

```
void SetTwipSize(int nSize);
```

### <a name="parameters"></a>Parameter

*nSize*<br/>
[in] Gibt die Größe (in Twips) entsprechend an.

### <a name="remarks"></a>Hinweise

Sie können den vorherigen gültigen Schriftgrad später abrufen, durch den Aufruf der [CMFCToolBarFontSizeComboBox::GetTwipSize](#gettwipsize) Methode.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf der Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
