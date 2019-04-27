---
title: CMFCRibbonComboBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: 89007ea3eb7fd0aef28caadf439195b4090a05d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237324"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox-Klasse

Die `CMFCRibbonComboBox` -Klasse implementiert ein Kombinationsfeld-Steuerelement, das einer menübandleiste, einem Menübandbereich oder einem Menüband-Popupmenü hinzugefügt werden können.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|Erstellt ein CMFCRibbonComboBox-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCRibbonComboBox::AddItem](#additem)|Fügt ein eindeutiges Element in das Listenfeld an.|
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|Löscht ein angegebenes Element aus dem Listenfeld aus.|
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|Gibt an, ob das Listenfeld Größe ändern kann, wenn es angezeigt wird.|
|[CMFCRibbonComboBox::FindItem](#finditem)|Gibt den Index des ersten Elements in das Listenfeld, das einer angegebenen Zeichenfolge übereinstimmt.|
|[CMFCRibbonComboBox::GetCount](#getcount)|Gibt die Anzahl der Elemente im Listenfeld zurück.|
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.|
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|Ruft die Höhe des ListBox-Felds ab, wenn im Listenfeld nach unten gelöscht wird.|
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|Gibt die Größe des Kombinationsfelds zurück, wie im Zwischenstatus angezeigt.|
|[CMFCRibbonComboBox::GetItem](#getitem)|Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.|
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.|
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|Gibt an, ob das Steuerelement ein Bearbeitungsfeld enthält.|
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|Gibt an, und zwar unabhängig davon, ob das Listenfeld geändert werden kann.|
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|Wird vom Framework aufgerufen, wenn der Benutzer ein Element im Listenfeld auswählt.|
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|Löscht alle Elemente aus dem Listenfeld aus, und löscht das Bearbeitungsfeld.|
|[CMFCRibbonComboBox::SelectItem](#selectitem)|Wählt ein Element im Listenfeld an.|
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|Legt die Höhe des Listenfelds fest, wenn sie nach unten gelöscht wird.|

## <a name="remarks"></a>Hinweise

Die Menüband-Kombinationsfeld besteht aus einem Listenfeld, kombiniert mit einem statische Bezeichnung oder Beschriftung, die vom Benutzer bearbeitet werden kann. Sie müssen angeben, welche Art Sie möchten bei der Erstellung der Menüband-Kombinationsfeld.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCRibbonComboBox` Klasse, ein Element im Kombinationsfeld hinzufügen, wählen Sie ein Element im Kombinationsfeld und fügen Sie ein Kombinationsfeld, um einen Bereich.

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxribboncombobox.h

##  <a name="additem"></a>  CMFCRibbonComboBox::AddItem

Fügt ein eindeutiges Element in das Listenfeld an.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parameter

*lpszItem*<br/>
[in] Die Zeichenfolge des hinzuzufügenden Elements.

*dwData*<br/>
[in] Die Daten, die das hinzuzufügende Element zugeordnet wird.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des hinzugefügten Elements.

##  <a name="cmfcribboncombobox"></a>  CMFCRibbonComboBox::CMFCRibbonComboBox

Erstellt ein `CMFCRibbonComboBox`-Objekt.

```
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>Parameter

*nID*<br/>
[in] Die ID des Kombinationsfelds.

*bHasEditBox*<br/>
[in] True, wenn ein Bearbeitungsfeld innerhalb des Steuerelements verwendet werden soll. "False" andernfalls.

*nWidth*<br/>
[in] Die Breite des Kombinationsfelds in Pixel; oder -1 für die Standardbreite.

*lpszLabel*<br/>
[in] Die Bezeichnung der Anzeige des Kombinationsfelds.

*nImage*<br/>
[in] Der Index der Miniaturansicht des Kombinationsfelds.

### <a name="remarks"></a>Hinweise

Die Standardbreite beträgt 108 Pixel.

##  <a name="deleteitem"></a>  CMFCRibbonComboBox::DeleteItem

Löscht ein angegebenes Element aus dem Listenfeld aus.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index des Elements, das gelöscht werden.

*dwData*<br/>
[in] Die Daten, die zu löschenden Elements zugeordnet.

*lpszText*<br/>
[in] Die Zeichenfolge des Elements, das gelöscht werden. Wenn mehrere Elemente mit derselben Zeichenfolge vorhanden sind, wird das erste Element gelöscht.

### <a name="return-value"></a>Rückgabewert

True, wenn das angegebene Element gelöscht wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="enabledropdownlistresize"></a>  CMFCRibbonComboBox::EnableDropDownListResize

Gibt an, ob das Listenfeld Größe ändern kann, wenn es angezeigt wird.

```
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] "True" Ändern der Größe von aktivieren; So deaktivieren Sie das Ändern der Größe wird false ZURÜCKGEGEBEN.

### <a name="remarks"></a>Hinweise

Beim Ändern der Größe aktiviert ist, ändert das Listenfeld Größe der Elemente, die angezeigt.

##  <a name="finditem"></a>  CMFCRibbonComboBox::FindItem

Gibt den Index des ersten Elements in das Listenfeld, das einer angegebenen Zeichenfolge übereinstimmt.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
[in] Die Zeichenfolge ein Element im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des Elements ist; oder -1, wenn das Element nicht gefunden wird.

### <a name="remarks"></a>Hinweise

##  <a name="getcount"></a>  CMFCRibbonComboBox::GetCount

Gibt die Anzahl der Elemente im Listenfeld zurück.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in das Listenfeld oder 0, wenn das Listenfeld keine Elemente enthält.

### <a name="remarks"></a>Hinweise

##  <a name="getcursel"></a>  CMFCRibbonComboBox::GetCurSel

Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index des derzeit ausgewählten Elements im Listenfeld; oder -1, wenn kein Element ausgewählt ist.

##  <a name="getdropdownheight"></a>  CMFCRibbonComboBox::GetDropDownHeight

Ruft die Höhe des ListBox-Felds ab, wenn im Listenfeld nach unten gelöscht wird.

```
int GetDropDownHeight();
```

### <a name="return-value"></a>Rückgabewert

Die Höhe in Pixel des Listenfelds.

### <a name="remarks"></a>Hinweise

##  <a name="getintermediatesize"></a>  CMFCRibbonComboBox::GetIntermediateSize

Gibt die Größe des Kombinationsfelds zurück, wie im Zwischenstatus angezeigt.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Zeiger auf einen Gerätekontext für das Kombinationsfeld.

### <a name="return-value"></a>Rückgabewert

Die Größe des Kombinationsfelds.

### <a name="remarks"></a>Hinweise

Die zurückgegebene Größe basiert auf die Größe des Kombinationsfelds, wenn es sich um kleine Bilder eingeblendet.

##  <a name="getitem"></a>  CMFCRibbonComboBox::GetItem

Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.

```
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist; andernfalls, NULL, wenn der Indexparameter ungültig ist, oder wenn der Indexparameter ist-1, und es ist kein Element im Kombinationsfeld ausgewählt.

### <a name="remarks"></a>Hinweise

##  <a name="getitemdata"></a>  CMFCRibbonComboBox::GetItemData

Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.

```
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Die Daten, die dem Element zugeordnet, oder 0, wenn das Element nicht vorhanden ist oder wenn der Indexparameter ist-1 und gibt es kein ausgewähltes Element im Listenfeld ist.

##  <a name="haseditbox"></a>  CMFCRibbonComboBox::HasEditBox

Gibt an, ob das Steuerelement ein Bearbeitungsfeld enthält.

```
BOOL HasEditBox() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Steuerelement ein Bearbeitungsfeld enthält. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="isresizedropdownlist"></a>  CMFCRibbonComboBox::IsResizeDropDownList

Gibt an, und zwar unabhängig davon, ob das Listenfeld geändert werden kann.

```
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Listenfeld geändert werden kann. andernfalls "false". [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>Hinweise

Können Liste Feld Größe ändern, indem Sie mit der [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) Methode.

##  <a name="onselectitem"></a>  CMFCRibbonComboBox::OnSelectItem

Wird vom Framework aufgerufen, wenn ein Benutzer ein Element im Listenfeld auswählt.

```
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
[in] Der Index des ausgewählten Elements.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, wenn Sie eine Eingabe Benutzerauswahl verarbeiten möchten.

##  <a name="removeallitems"></a>  CMFCRibbonComboBox::RemoveAllItems

Löscht alle Elemente aus dem Listenfeld aus, und löscht das Bearbeitungsfeld.

```
void RemoveAllItems();
```

### <a name="remarks"></a>Hinweise

##  <a name="selectitem"></a>  CMFCRibbonComboBox::SelectItem

Wählt ein Element im Listenfeld an.

```
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

*dwData*<br/>
[in] Die Daten, die einem Element im Listenfeld zugeordnet wird.

*lpszText*<br/>
[in] Die Zeichenfolge ein Element im Listenfeld.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="setdropdownheight"></a>  CMFCRibbonComboBox::SetDropDownHeight

Legt die Höhe des Listenfelds fest, wenn sie nach unten gelöscht wird.

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parameter

*nHeight*<br/>
[in] Die Höhe in Pixel des Listenfelds.

### <a name="remarks"></a>Hinweise

Die Standardhöhe ist 150 Pixel.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonEdit-Klasse](../../mfc/reference/cmfcribbonedit-class.md)
