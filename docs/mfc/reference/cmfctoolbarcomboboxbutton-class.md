---
title: Cmfctoolbarcomboboxbutton-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::AddSortedItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::Compare
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::CreateEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::DeleteItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::FindItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetByCmd
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetComboBox
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCount
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCountAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSel
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetCurSelAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetEditCtrl
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemData
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetItemDataPtrAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetText
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::GetTextAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::IsFlatMode
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::RemoveAllItems
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItem
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SelectItemAll
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetCenterVert
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetDropDownHeight
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxButton::SetFlatMode
helpviewer_keywords:
- CMFCToolBarComboBoxButton [MFC], CMFCToolBarComboBoxButton
- CMFCToolBarComboBoxButton [MFC], AddItem
- CMFCToolBarComboBoxButton [MFC], AddSortedItem
- CMFCToolBarComboBoxButton [MFC], Compare
- CMFCToolBarComboBoxButton [MFC], CreateEdit
- CMFCToolBarComboBoxButton [MFC], DeleteItem
- CMFCToolBarComboBoxButton [MFC], FindItem
- CMFCToolBarComboBoxButton [MFC], GetByCmd
- CMFCToolBarComboBoxButton [MFC], GetComboBox
- CMFCToolBarComboBoxButton [MFC], GetCount
- CMFCToolBarComboBoxButton [MFC], GetCountAll
- CMFCToolBarComboBoxButton [MFC], GetCurSel
- CMFCToolBarComboBoxButton [MFC], GetCurSelAll
- CMFCToolBarComboBoxButton [MFC], GetEditCtrl
- CMFCToolBarComboBoxButton [MFC], GetItem
- CMFCToolBarComboBoxButton [MFC], GetItemAll
- CMFCToolBarComboBoxButton [MFC], GetItemData
- CMFCToolBarComboBoxButton [MFC], GetItemDataAll
- CMFCToolBarComboBoxButton [MFC], GetItemDataPtrAll
- CMFCToolBarComboBoxButton [MFC], GetText
- CMFCToolBarComboBoxButton [MFC], GetTextAll
- CMFCToolBarComboBoxButton [MFC], IsCenterVert
- CMFCToolBarComboBoxButton [MFC], IsFlatMode
- CMFCToolBarComboBoxButton [MFC], RemoveAllItems
- CMFCToolBarComboBoxButton [MFC], SelectItem
- CMFCToolBarComboBoxButton [MFC], SelectItemAll
- CMFCToolBarComboBoxButton [MFC], SetCenterVert
- CMFCToolBarComboBoxButton [MFC], SetDropDownHeight
- CMFCToolBarComboBoxButton [MFC], SetFlatMode
ms.assetid: 32fa39f7-8e4e-4f0a-a31d-7b540d969a6c
ms.openlocfilehash: 639a5f98ff4780bd26388796039e85b812621b36
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915968"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>Cmfctoolbarcomboboxbutton-Klasse

Eine Symbolleisten-Schaltfläche, die ein Kombinations Feld-Steuerelement ( [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)) enthält.

## <a name="syntax"></a>Syntax

```
class CMFCToolBarComboBoxButton : public CMFCToolBarButton
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton](#cmfctoolbarcomboboxbutton)|Erstellt ein Objekt vom Typ `CMFCToolBarComboBoxButton`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Fügt am Ende der Kombinations Feld Liste ein Element hinzu.|
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Fügt der Kombinations Feld Liste ein Element hinzu. Die Reihenfolge der Elemente in der Liste wird durch `Compare`angegeben.|
|[CMFCToolBarComboBoxButton::Compare](#compare)|Vergleicht zwei Elemente. Wird aufgerufen, um Elemente `AddSortedItems` zu sortieren, die der Kombinations Feld Liste hinzugefügt werden.|
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Erstellt ein neues Bearbeitungs Steuerelement für die Kombinations Feld Schaltfläche.|
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Löscht ein Element aus der Kombinations Feld Liste.|
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Gibt den Index des Elements zurück, das eine angegebene Zeichenfolge enthält.|
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Gibt einen Zeiger auf die Kombinations Feld Schaltfläche mit einer angegebenen Befehls-ID zurück.|
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Gibt einen Zeiger auf das Kombinations Feld-Steuerelement zurück, das in die Kombinations Feld Schaltfläche eingebettet ist.|
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Gibt die Anzahl der Elemente in der Kombinations Feld Liste zurück.|
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt. Gibt die Anzahl der Elemente in der Kombinations Feld Liste dieser Schaltfläche zurück.|
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Gibt den Index des ausgewählten Elements in der Kombinations Feld Liste zurück.|
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt, und gibt den Index des ausgewählten Elements in der Kombinations Feld Liste dieser Schaltfläche zurück.|
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Gibt einen Zeiger auf das Bearbeitungs Steuerelement zurück, das in die Kombinations Feld Schaltfläche eingebettet ist.|
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Gibt die Zeichenfolge zurück, die einem angegebenen Index in der Kombinations Feld Liste zugeordnet ist.|
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt, und gibt die Zeichenfolge zurück, die einem Index in der Kombinations Feld Liste dieser Schaltfläche zugeordnet ist.|
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Gibt den 32-Bit-Wert zurück, der einem angegebenen Index in der Kombinations Feld Liste zugeordnet ist.|
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt, und gibt den 32-Bit-Wert zurück, der einem Index in der Kombinations Feld Liste dieser Schaltfläche zugeordnet ist.|
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt. Ruft den 32-Bit-Wert ab, der einem Index in der Kombinations Feld Liste dieser Schaltfläche zugeordnet ist, und gibt den 32-Bit-Wert als Zeiger zurück.|
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Gibt den Text aus dem Bearbeitungs Steuerelement des Kombinations Felds zurück.|
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt, und gibt den Text aus dem Bearbeitungs Steuerelement dieser Schaltfläche zurück.|
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Bestimmt, ob Kombinations Feld-Schaltflächen in der Anwendung zentriert oder am oberen Rand der Symbolleiste ausgerichtet werden.|
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob Kombinations Feld-Schaltflächen in der Anwendung flach dargestellt werden.|
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Entfernt alle Elemente aus dem Listenfeld und das Bearbeitungs Steuerelement des Kombinations Felds.|
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Wählt ein Element im Kombinations Feld gemäß dem Index, dem 32-Bit-Wert oder der Zeichenfolge aus und benachrichtigt das Kombinations Feld-Steuerelement über die Auswahl.|
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Sucht die Kombinations Feld Schaltfläche, die über eine angegebene Befehls-ID verfügt. Ruft `SelectItem` auf, um ein Element im Kombinations Feld dieser Schaltfläche entsprechend der Zeichenfolge, des Indexes oder des 32-Bit-Werts auszuwählen.|
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Gibt an, ob Kombinations Feld-Schaltflächen in der Anwendung vertikal zentriert oder am oberen Rand der Symbolleiste ausgerichtet werden.|
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Legt die Höhe des Dropdown-Listen Felds fest.|
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Gibt an, ob Kombinations Feld-Schaltflächen in der Anwendung flach dargestellt werden.|

## <a name="remarks"></a>Hinweise

Führen Sie die folgenden Schritte aus, um einer Symbolleiste eine Kombinations Feld Schaltfläche hinzuzufügen:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.

2. Konstruieren Sie ein `CMFCToolBarComboBoxButton`-Objekt.

3. Ersetzen Sie im Meldungs Handler, der die AFX_WM_RESETTOOLBAR-Nachricht verarbeitet, die Dummy-Schaltfläche durch die Schaltfläche Neues Kombinations Feld, indem Sie [cmfctoolbar:: replacebutton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)verwenden.

Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in](../../mfc/walkthrough-putting-controls-on-toolbars.md)Symbolleisten. Ein Beispiel für eine Kombinations Feld-Symbolleisten Schaltfläche finden Sie im Beispiel Projekt visualstudiodemo.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCToolBarComboBoxButton` -Klasse. Das Beispiel zeigt, wie Sie die Bearbeitungs-und Kombinations Felder aktivieren, die vertikale Position von Kombinations Feld-Schaltflächen in der Anwendung festlegen, die Höhe des Listen Felds beim Ablegen festlegen, die Darstellung der Kombinations Feld Schaltflächen in der Anwendung festlegen. , und legen Sie den Text im Bearbeitungsfeld der Kombinations Feld Schaltfläche fest. Dieser Code Ausschnitt ist Teil des [Visual Studio-Demo](../../overview/visual-cpp-samples.md)Beispiels.

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarcomboboxbutton. h

##  <a name="additem"></a>Cmfctoolbarcomboboxbutton:: AddItem

Fügt ein eindeutiges Element an das Listenfeld an.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parameter

*lpszItem*<br/>
in Der Text des Elements, das dem Listenfeld hinzugefügt werden soll.

*dwData*<br/>
in Die Daten, die dem Element zugeordnet sind, das dem Listenfeld hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des letzten Elements im Listenfeld.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nicht, wenn das Listenfeld Format sortiert ist.

Wenn sich der Element Text bereits im Listenfeld befindet, werden die neuen Daten mit dem vorhandenen Element gespeichert. Beim Suchen nach dem Element wird die Groß-/Kleinschreibung beachtet.

##  <a name="addsorteditem"></a>Cmfctoolbarcomboboxbutton:: addsorteditem

Fügt dem Listenfeld ein Element in der Reihenfolge hinzu, die durch die [Compare](#compare) -Methode definiert wird.

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parameter

*lpszItem*<br/>
in Der Text des Elements, das dem Listenfeld hinzugefügt werden soll.

*dwData*<br/>
in Die Daten, die dem Element zugeordnet sind, das dem Listenfeld hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des Elements, das dem Listenfeld hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion, um dem Listenfeld Elemente in einer bestimmten Reihenfolge hinzuzufügen.

##  <a name="canbestretched"></a>Cmfctoolbarcomboboxbutton:: canbegestreckt

Gibt an, ob die Kombinations Feld-Schaltflächen Größe geändert werden kann.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück.

##  <a name="cmfctoolbarcomboboxbutton"></a>Cmfctoolbarcomboboxbutton:: cmfctoolbarcomboboxbutton

Erstellt ein [cmfctoolbarcomboboxbutton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) -Objekt.

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
in Die Befehls-ID der neuen Schaltfläche.

*iImage*<br/>
in Der Bildindex des Bilds, das der neuen Schaltfläche zugeordnet ist.

*dwStyle*<br/>
in Der Stil der neuen Schaltfläche.

*iWidth*<br/>
in Die Breite der neuen Schaltfläche in Pixel.

### <a name="remarks"></a>Hinweise

Die Standardbreite beträgt 150 Pixel.

Eine Liste der Symbolleisten-Schaltflächen Stile finden Sie unter [Toolbar-Steuer](../../mfc/reference/toolbar-control-styles.md) Element

##  <a name="cleardata"></a>Cmfctoolbarcomboboxbutton:: ClearData

Löscht benutzerdefinierte Daten.

```
virtual void ClearData();
```

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion aus. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie benutzerdefinierte Daten löschen möchten.

##  <a name="compare"></a>Cmfctoolbarcomboboxbutton:: Compare

Vergleicht zwei Zeichenfolgen.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>Parameter

*lpszItem1*<br/>
in Die erste zu vergleichende Zeichenfolge.

*lpszItem2*<br/>
in Die zweite zu vergleichende Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Ein Wert, der die zwischen Groß-und Kleinschreibung abhängige lexikografische Beziehung zwischen den Zeichen folgen angibt. In der folgenden Tabelle sind die möglichen Werte aufgeführt:

|Wert|Beschreibung|
|-----------|-----------------|
|\<0|Die erste Zeichenfolge ist kleiner als die zweite Zeichenfolge.|
|0|Die erste Zeichenfolge ist mit der zweiten Zeichenfolge.|
|>0|Die erste Zeichenfolge ist größer als die zweite Zeichenfolge.|

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode, um zu ändern, wie Elemente im Listenfeld sortiert werden.

Beim Vergleich wird die Groß-/Kleinschreibung beachtet.

Diese Methode wird nur von der [addsorteditem](#addsorteditem) -Methode aufgerufen.

##  <a name="copyfrom"></a>Cmfctoolbarcomboboxbutton:: CopyFrom

Kopiert den Zustand des angegebenen `CMFCToolBarComboBoxButton` in das aktuelle-Objekt.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
in Das Quell `CMFCToolBarComboBoxButton` Objekt.

##  <a name="createcombo"></a>Cmfctoolbarcomboboxbutton:: comatecombo

Erstellt ein neues Kombinations Feld für die Kombinations Feld Schaltfläche.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Ein Zeiger auf das übergeordnete Fenster der Schaltfläche.

*Rect*<br/>
in Begrenzungs Rechteck des Kombinations Felds.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neue Kombinations Feld, wenn die Methode erfolgreich war. andernfalls NULL.

##  <a name="createedit"></a>Cmfctoolbarcomboboxbutton:: kreateedit

Erstellt ein neues Bearbeitungsfeld für die Kombinations Feld Schaltfläche.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Ein Zeiger auf das übergeordnete Fenster der Schaltfläche.

*Rect*<br/>
in Begrenzungs Rechteck des neuen Bearbeitungs Felds.

*dwEditStyle*<br/>
in Steuerelement Stil des neuen Bearbeitungs Felds.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neue Bearbeitungsfeld, wenn die Methode erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn ein neues Bearbeitungsfeld für eine Kombinations Feld Schaltfläche erstellt wird. Überschreiben Sie diese Methode, um zu ändern, wie [cmfctoolbarcomboboxedit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) erstellt wird.

##  <a name="deleteitem"></a>Cmfctoolbarcomboboxbutton::D eleteitem

Löscht ein angegebenes Element aus dem Listenfeld.

```
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);
BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index des zu löschenden Elements.

*dwData*<br/>
in Die Daten, die dem zu löschenden Element zugeordnet sind.

*lpszText*<br/>
in Der Text des zu löschenden Elements. Wenn mehrere Elemente mit demselben Text vorhanden sind, wird das erste Element gelöscht.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Element gefunden und erfolgreich gelöscht wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="duplicatedata"></a>Cmfctoolbarcomboboxbutton::D uplicatedata

Dupliziert benutzerdefinierte Daten.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion aus. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie benutzerdefinierte Daten kopieren möchten.

##  <a name="enablewindow"></a>Cmfctoolbarcomboboxbutton:: EnableWindow

Aktiviert oder deaktiviert die Bearbeitungs-und Kombinations Felder.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
in "True", um die Bearbeitungs-und Kombinations Felder zu aktivieren. FALSE zum Deaktivieren der Bearbeitungs-und Kombinations Felder.

### <a name="remarks"></a>Hinweise

Wenn diese Option deaktiviert ist, können die Steuerelemente nicht aktiviert werden und können keine Benutzereingaben akzeptieren.

##  <a name="exporttomenubutton"></a>Cmfctoolbarcomboboxbutton:: exporttomendubutton

Kopiert eine Zeichenfolge aus der Anwendungs Zeichen folgen Tabelle in das angegebene Menü mithilfe der Befehls-ID für die Kombinations Feld-Schaltfläche.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parameter

*menuButton*<br/>
vorgenommen Verweis auf eine Menü Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Immer true.

##  <a name="finditem"></a>Cmfctoolbarcomboboxbutton:: FindItem

Gibt den Index des ersten Elements im Listenfeld zurück, das eine angegebene Zeichenfolge enthält.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
in Der Text, für den im Listenfeld gesucht werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des Elements. oder CB_ERR, wenn das Element nicht gefunden wird.

### <a name="remarks"></a>Hinweise

##  <a name="getbycmd"></a>Cmfctoolbarcomboboxbutton:: getbycmd

Ruft einen Zeiger auf die Kombinations Feld-Schaltfläche ab, die über eine angegebene Befehls-ID verfügt.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID einer Kombinations Feld Schaltfläche.

*bIsFocus*<br/>
in TRUE, wenn nur fokussierte Schaltflächen gesucht werden sollen. FALSE zum Durchsuchen aller Schaltflächen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine Kombinations Feld Schaltfläche. oder NULL, wenn die Schaltfläche nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

##  <a name="getcombobox"></a>Cmfctoolbarcomboboxbutton:: getcombobox

Gibt einen Zeiger auf das Kombinations Feld in der Kombinations Feld Schaltfläche zurück.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das [CComboBox-Klassen](../../mfc/reference/ccombobox-class.md) Objekt, wenn die Methode erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="getcontextmenuid"></a>Cmfctoolbarcomboboxbutton:: getContextMenuId

Ruft die Ressourcen-ID des Kontextmenüs für die Kombinations Feld Schaltfläche ab.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Rückgabewert

Die Ressourcen-ID des Kontextmenüs.

##  <a name="getcount"></a>Cmfctoolbarcomboboxbutton:: GetCount

Gibt die Anzahl der Elemente im Listenfeld zurück.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listenfeld.

### <a name="remarks"></a>Hinweise

##  <a name="getcountall"></a>Cmfctoolbarcomboboxbutton:: getgräfin

Ruft die Anzahl der Elemente im Listenfeld einer Kombinations Feld-Schaltfläche ab, die über eine angegebene Befehls-ID verfügt.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID einer Kombinations Feld Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listenfeld. Andernfalls CB_ERR, wenn die Kombinations Feld Schaltfläche nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

##  <a name="getcursel"></a>Cmfctoolbarcomboboxbutton:: getcurrsel

Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Der Index des derzeit ausgewählten Elements im Listenfeld. oder CB_ERR, wenn kein Element ausgewählt ist.

### <a name="remarks"></a>Hinweise

Der Listenfeld Index ist NULL basiert.

##  <a name="getcurselall"></a>Cmfctoolbarcomboboxbutton:: getcurrselall

Gibt den Index des derzeit ausgewählten Elements im Listenfeld einer Kombinations Feld Schaltfläche zurück, die über eine angegebene Befehls-ID verfügt.

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID einer Kombinations Feld Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Der Index des derzeit ausgewählten Elements im Listenfeld. Andernfalls CB_ERR, wenn kein Element ausgewählt ist oder eine Kombinations Feld-Schaltfläche nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Der Listenfeld Index ist NULL basiert.

##  <a name="geteditctrl"></a>Cmfctoolbarcomboboxbutton:: geteditctrl

Gibt einen Zeiger auf das Bearbeitungsfeld in der Kombinations Feld Schaltfläche zurück.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Bearbeitungsfeld, wenn die Methode erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="gethwnd"></a>Cmfctoolbarcomboboxbutton:: GetHwnd

Gibt das Fenster Handle für das Kombinations Feld zurück.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Rückgabewert

Das Fenster Handle oder NULL, wenn das Kombinations Feld nicht mit einem Window-Objekt verknüpft ist.

##  <a name="getitem"></a>Cmfctoolbarcomboboxbutton:: GetItem

Gibt die Zeichenfolge zurück, die mit einem Element an einem angegebenen Index im Listenfeld verknüpft ist.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in NULL basierter Index eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist. andernfalls NULL, wenn der Index Parameter ungültig ist, oder wenn der Index Parameter-1 ist und kein ausgewähltes Element im Kombinations Feld vorhanden ist.

### <a name="remarks"></a>Hinweise

Der Index-Parameter-1 gibt die Zeichenfolge des aktuell ausgewählten Elements zurück.

##  <a name="getitemall"></a>Cmfctoolbarcomboboxbutton:: getitemall

Gibt die Zeichenfolge zurück, die einem Element an einem angegebenen Index im Listenfeld einer Kombinations Feld-Schaltfläche zugeordnet ist, die über eine angegebene Befehls-ID verfügt.

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID einer Kombinations Feld Schaltfläche.

*iIndex*<br/>
in Der null basierte Index eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Zeichenfolge des Elements, wenn die Methode erfolgreich war. andernfalls NULL, wenn der Index ungültig ist, eine Kombinations Feld Schaltfläche nicht gefunden wird oder wenn der Index-1 ist und kein ausgewähltes Element im Kombinations Feld vorhanden ist.

### <a name="remarks"></a>Hinweise

Der Indexwert-1 gibt die Zeichenfolge des aktuell ausgewählten Elements zurück.

##  <a name="getitemdata"></a>Cmfctoolbarcomboboxbutton:: GetItemData

Gibt die Daten zurück, die einem Element an einem bestimmten Index im Listenfeld zugeordnet sind.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Die Daten, die dem Element zugeordnet sind. oder 0, wenn das Element nicht vorhanden ist.

### <a name="remarks"></a>Hinweise

Der Index-Parameter-1 gibt die Daten zurück, die dem aktuell ausgewählten Element zugeordnet sind.

##  <a name="getitemdataall"></a>Cmfctoolbarcomboboxbutton:: getitemdataall

Gibt die Daten zurück, die mit einem Element an einem bestimmten Index im Listenfeld einer Kombinations Feld Schaltfläche mit einer bestimmten Befehls-ID verknüpft sind.

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID einer Kombinations Feld Schaltfläche.

*iIndex*<br/>
in Der null basierte Index eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Die Daten, die dem Element zugeordnet sind, wenn die Methode erfolgreich war. andernfalls 0, wenn der angegebene Index ungültig ist, oder CB_ERR, wenn die Kombinations Feld Schaltfläche nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

Der Index-Parameter-1 gibt die Daten zurück, die dem aktuell ausgewählten Element zugeordnet sind.

##  <a name="getitemdataptrall"></a>Cmfctoolbarcomboboxbutton:: getitemdataptrall

Gibt die Daten zurück, die mit einem Element an einem bestimmten Index im Listenfeld einer Kombinations Feld Schaltfläche mit einer bestimmten Befehls-ID verknüpft sind. Diese Daten werden als Zeiger zurückgegeben.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID der Kombinations Feld Schaltfläche.

*iIndex*<br/>
in Der null basierte Index eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger, der dem Element zugeordnet ist, wenn die Methode erfolgreich war. andernfalls-1, wenn ein Fehler auftritt, oder NULL, wenn die Kombinations Feld Schaltfläche nicht gefunden wurde.

### <a name="remarks"></a>Hinweise

##  <a name="getprompt"></a>Cmfctoolbarcomboboxbutton:: getPrompt

Gibt die Aufforderungs Zeichenfolge für die Kombinations Feld Schaltfläche zurück

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>Rückgabewert

Die Zeichenfolge der Eingabeaufforderung.

### <a name="remarks"></a>Hinweise

Diese Methode ist zurzeit nicht implementiert.

##  <a name="gettext"></a>Cmfctoolbarcomboboxbutton:: gettext

Ruft den Text im Bearbeitungsfeld ab.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>Rückgabewert

Der Text im Bearbeitungsfeld.

### <a name="remarks"></a>Hinweise

##  <a name="gettextall"></a>Cmfctoolbarcomboboxbutton:: gettextall

Ruft den Text im Bearbeitungsfeld einer Kombinations Feld-Schaltfläche ab, die über eine angegebene Befehls-ID verfügt.

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID einer bestimmten Kombinations Feld Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Der Text im Bearbeitungsfeld, wenn die Methode erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="hasfocus"></a>Cmfctoolbarcomboboxbutton:: HasFocus

Gibt an, ob das Kombinations Feld aktuell den Fokus besitzt.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Kombinations Feld derzeit den Fokus besitzt. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode gibt auch true zurück, wenn ein untergeordnetes Fenster des Kombinations Felds aktuell den Fokus besitzt.

##  <a name="iscentervert"></a>Cmfctoolbarcomboboxbutton:: iscentervert

Gibt die vertikale Position von Kombinations Feld-Schaltflächen in der Anwendung zurück.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltflächen zentriert sind. FALSE, wenn die Schaltflächen am oberen Rand ausgerichtet sind.

### <a name="remarks"></a>Hinweise

##  <a name="isflatmode"></a>Cmfctoolbarcomboboxbutton:: isflatmode

Gibt die flache Darstellung von Kombinations Feld-Schaltflächen in der Anwendung zurück.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Schaltflächen einen flachen Stil aufweisen. andernfalls false.

### <a name="remarks"></a>Hinweise

Der standardmäßige flache Stil für Kombinations Feld-Schaltflächen ist false.

##  <a name="isownerof"></a>Cmfctoolbarcomboboxbutton:: isownerof

Gibt an, ob das angegebene Handle der Kombinations Feld Schaltfläche oder einem untergeordneten Element zugeordnet ist.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>Parameter

*HWND*<br/>
in Ein Fenster handle.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Handle mit der Kombinations Feld Schaltfläche oder einem seiner untergeordneten Elemente zugeordnet ist. andernfalls false.

##  <a name="isribbonbutton"></a>Cmfctoolbarcomboboxbutton:: isribbonbutton

Gibt an, ob sich die Kombinations Feld Schaltfläche in einem Menü Band Bereich befindet.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>Rückgabewert

Immer false.

### <a name="remarks"></a>Hinweise

Standardmäßig gibt diese Methode immer false zurück, was bedeutet, dass die Schaltfläche Kombinations Feld nie in einem Menü Band Bereich angezeigt wird.

##  <a name="iswindowvisible"></a>Cmfctoolbarcomboboxbutton:: iswindowvisible

Gibt den Sichtbarkeits Zustand der Kombinations Feld Schaltfläche zurück.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>Rückgabewert

Der Sichtbarkeits Zustand der Kombinations Feld Schaltfläche.

##  <a name="notifycommand"></a>Cmfctoolbarcomboboxbutton:: notifycommand

Gibt an, ob die Kombinations Feld-Schaltfläche die Meldung verarbeitet.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parameter

*iNotifyCode*<br/>
in Die Benachrichtigungs Meldung, die dem Befehl zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

Gibt an, ob die Kombinations Feld-Schaltfläche die Meldung verarbeitet.

##  <a name="onaddtocustomizepage"></a>Cmfctoolbarcomboboxbutton:: onaddto customizepage

Wird von Framework aufgerufen, wenn die Schaltfläche zum Dialogfeld **Anpassen** hinzugefügt wird.

```
virtual void OnAddToCustomizePage();
```

##  <a name="oncalculatesize"></a>Cmfctoolbarcomboboxbutton:: oncalculatesize

Wird von Framework aufgerufen, um die Größe der Schaltfläche zu berechnen.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Kombinations Feld Schaltfläche anzeigt.

*sizeDefault*<br/>
in Die Standardgröße der Kombinations Feld Schaltfläche.

*bHorz*<br/>
in Der Andock Zustand der übergeordneten Symbolleiste. TRUE, wenn die Symbolleiste horizontal angedockt ist, und false, wenn die Symbolleiste vertikal angedockt ist.

### <a name="return-value"></a>Rückgabewert

Eine `SIZE` -Struktur, die die Dimensionen der Kombinations Feld Schaltfläche in Pixel enthält.

##  <a name="onchangeparentwnd"></a>Cmfctoolbarcomboboxbutton:: onchangeparameentwnd

Wird von Framework aufgerufen, wenn die Kombinations Feld Schaltfläche in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Ein Zeiger auf die neue übergeordnete Symbolleiste.

##  <a name="onclick"></a>Cmfctoolbarcomboboxbutton:: OnClick

Wird von Framework aufgerufen, wenn der Benutzer auf die Schaltfläche Kombinations Feld klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
in Zeiger auf das übergeordnete Fenster der Kombinations Feld Schaltfläche.

*bDelay*<br/>
in Reserviert für die Verwendung in einer abgeleiteten Klasse.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode das Ereignis behandelt. andernfalls false.

##  <a name="onctlcolor"></a>Cmfctoolbarcomboboxbutton:: onctlcolor

Wird von Framework aufgerufen, wenn der Benutzer die übergeordnete Symbolleisten Farbe ändert, um die Kombinations Feld-Schaltflächen Farbe festzulegen.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Kombinations Feld Schaltfläche anzeigt.

*nCtlColor*<br/>
in Genutzt.

### <a name="return-value"></a>Rückgabewert

Handle für den Pinsel, den das Framework zum Zeichnen des Hintergrunds der Kombinations Feld Schaltfläche verwendet.

### <a name="remarks"></a>Hinweise

Diese Methode legt auch die Textfarbe der Kombinations Feld Schaltfläche fest.

##  <a name="ondraw"></a>Cmfctoolbarcomboboxbutton:: OnDraw

Wird von Framework aufgerufen, um die Kombinations Feld Schaltfläche mithilfe der angegebenen Stile und Optionen zu zeichnen.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Parameter

*Pdc*<br/>
in Der Gerätekontext, der die Schaltfläche anzeigt.

*Rect*<br/>
in Das umgebende Rechteck der Schaltfläche.

*pimages*<br/>
in Die Auflistung von Bildern, die der Schaltfläche zugeordnet ist.

*bHorz*<br/>
in Der Andock Zustand der übergeordneten Symbolleiste. TRUE, wenn die Symbolleiste horizontal angedockt ist, und false, wenn die Symbolleiste vertikal angedockt ist.

*bcustomizemode*<br/>
in Gibt an, ob sich die Anwendung im Anpassungsmodus befindet.

*bHighlight*<br/>
in Gibt an, ob die Kombinations Feld Schaltfläche hervorgehoben wird.

*bDrawBorder*<br/>
in Ob die Kombinations Feld Schaltfläche mit einem Rahmen gezeichnet werden soll.

*bGrayDisabledButtons*<br/>
in TRUE zum Zeichnen schattierter deaktivierter Schaltflächen. FALSE, um die deaktivierte Bilder Auflistung zu verwenden.

##  <a name="ondrawoncustomizelist"></a>Cmfctoolbarcomboboxbutton:: ondrawoncustomizelist

Wird von Framework aufgerufen, um die Kombinations Feld-Schaltfläche im **Befehls** Bereich des Dialog Felds **Anpassen** zu zeichnen.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
in Der Gerätekontext, der die Kombinations Feld Schaltfläche anzeigt.

*Rect*<br/>
in Das umgebende Rechteck der Kombinations Feld Schaltfläche.

*bausgewählt*<br/>
in TRUE, wenn die Schaltfläche Kombinations Feld ausgewählt ist. andernfalls false.

### <a name="return-value"></a>Rückgabewert

Die Breite der Kombinations Feld Schaltfläche in Pixel.

##  <a name="onglobalfontschanged"></a>Cmfctoolbarcomboboxbutton:: onglobalfontschge

Wird von Framework aufgerufen, um die Schriftart der Kombinations Feld-Schaltfläche beim Ändern der Schriftart der Anwendung festzulegen.

```
virtual void OnGlobalFontsChanged();
```

##  <a name="onmove"></a>Cmfctoolbarcomboboxbutton:: OnMove

Wird von Framework aufgerufen, um den Speicherort der Kombinations Feld Schaltfläche zu ändern, wenn die übergeordnete Symbolleiste verschoben wird.

```
virtual void OnMove();
```

##  <a name="onshow"></a>Cmfctoolbarcomboboxbutton:: onShow

Wird von Framework aufgerufen, wenn die Kombinations Feld Schaltfläche ausgeblendet oder angezeigt wird.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
in Ob die Kombinations Feld Schaltfläche ausgeblendet oder angezeigt werden soll.

##  <a name="onsize"></a>Cmfctoolbarcomboboxbutton:: OnSize

Wird von Framework aufgerufen, um die Größe der Kombinations Feld Schaltfläche zu ändern, wenn die Größe der übergeordneten Symbolleiste geändert wird.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parameter

*iSize*<br/>
in Die neue Breite der Kombinations Feld Schaltfläche.

##  <a name="onupdatetooltip"></a>Cmfctoolbarcomboboxbutton:: onupdatetooltip

Wird von Framework aufgerufen, wenn der Benutzer die QuickInfo für die Kombinations Feld Schaltfläche ändert.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
in Zeiger auf das übergeordnete Fenster für die Kombinations Feld Schaltfläche.

*iButtonIndex*<br/>
in Die ID der Kombinations Feld Schaltfläche.

*wndToolTip*<br/>
in Die QuickInfo, die der Kombinations Feld Schaltfläche zugeordnet werden soll.

*str*<br/>
in Der QuickInfo-Text.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode das Ereignis behandelt. andernfalls false.

##  <a name="removeallitems"></a>Cmfctoolbarcomboboxbutton:: RemoveAllItems

Löscht alle Elemente aus den Feldern "Liste" und "Bearbeiten".

```
void RemoveAllItems();
```

### <a name="remarks"></a>Hinweise

Entfernt alle Elemente aus dem Listenfeld und bearbeitet das Steuerelement eines Kombinations Felds.

##  <a name="selectitem"></a>Cmfctoolbarcomboboxbutton:: SelectItem

Wählt ein Element im Listenfeld aus.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index eines Elements im Listenfeld.

*bNotify*<br/>
in TRUE, um die Kombinations Feld-Schaltfläche der Auswahl zu benachrichtigen. andernfalls false.

*dwData*<br/>
in Die Daten, die einem Element im Listenfeld zugeordnet sind.

*lpszText*<br/>
in Der Text eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich war. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="selectitemall"></a>Cmfctoolbarcomboboxbutton:: selectitemall

Wählt ein Element im Listenfeld einer Kombinations Feld-Schaltfläche aus, die über eine angegebene Befehls-ID verfügt.

```
static BOOL SelectItemAll(
    UINT uiCmd,
    int iIndex);

static BOOL SelectItemAll(
    UINT uiCmd,
    DWORD_PTR dwData);

static BOOL SelectItemAll(
    UINT uiCmd,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
in Die Befehls-ID der Kombinations Feld-Schaltfläche, die das Listenfeld enthält.

*iIndex*<br/>
in Der null basierte Index des Elements im Listenfeld. Mit dem Wert-1 wird die aktuelle Auswahl im Listenfeld entfernt, und das Bearbeitungsfeld wird gelöscht.

*dwData*<br/>
in Die Daten eines Elements im Listenfeld.

*lpszText*<br/>
in Der Text eines Elements im Listenfeld.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich war. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="serialize"></a>Cmfctoolbarcomboboxbutton:: Serialize

Liest dieses Objekt aus einem Archiv oder schreibt es in ein Archiv.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
[in, out] Das `CArchive` zu serialisierende Objekt.

### <a name="remarks"></a>Hinweise

Einstellungen im `CArchive` -Objekt bestimmen, ob diese Methode das Archiv liest oder schreibt.

##  <a name="setaccdata"></a>Cmfctoolbarcomboboxbutton:: setaccdata

Füllt das angegebene `CAccessibilityData` -Objekt mithilfe von Barrierefreiheits Daten aus der Kombinations Feld Schaltfläche auf.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parameter

*pParent*<br/>
in Das übergeordnete Fenster der Kombinations Feld Schaltfläche.

*data*<br/>
vorgenommen Ein `CAccessibilityData` -Objekt, das die Barrierefreiheits Daten von der Kombinations Feld Schaltfläche empfängt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Methode erfolgreich war. andernfalls false.

##  <a name="setcentervert"></a>Cmfctoolbarcomboboxbutton:: setcentervert

Legt die vertikale Position von Kombinations Feld-Schaltflächen in der Anwendung fest.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>Parameter

*bCenterVert*<br/>
in TRUE, um die Kombinations Feld Schaltfläche auf der Symbolleiste zu zentrieren FALSE, um die Kombinations Feld-Schaltfläche am oberen Rand der Symbolleiste auszurichten.

### <a name="remarks"></a>Hinweise

Standardmäßig werden Kombinations Feld Schaltflächen am oberen Rand ausgerichtet.

##  <a name="setcontextmenuid"></a>Cmfctoolbarcomboboxbutton:: setcontextmenuid

Legt die Ressourcen-ID des Kontextmenüs für die Kombinations Feld Schaltfläche fest.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parameter

*uiResID*<br/>
in Die Ressourcen-ID des Kontextmenüs.

##  <a name="setdropdownheight"></a>Cmfctoolbarcomboboxbutton:: setdropdownheight

Legt die Höhe des Listen Felds fest, wenn es gelöscht wird.

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parameter

*nheight*<br/>
in Die Höhe des Listen Felds in Pixel.

### <a name="remarks"></a>Hinweise

Die Standardhöhe beträgt 150 Pixel.

##  <a name="setflatmode"></a>Cmfctoolbarcomboboxbutton:: setflatmode

Legt die flache Darstellung von Kombinations Feld-Schaltflächen in der Anwendung fest.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parameter

*bFlat*<br/>
in TRUE für eine flache Darstellung; andernfalls false.

### <a name="remarks"></a>Hinweise

Der standardmäßige flache Stil für Kombinations Feld-Schaltflächen ist false.

##  <a name="setstyle"></a>Cmfctoolbarcomboboxbutton:: SetStyle

Legt den angegebenen Stil für die Kombinations Feld Schaltfläche fest und zeichnet das Steuerelement neu, wenn es nicht deaktiviert ist.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nStyle*<br/>
in Eine bitweise Kombination (or) von Symbolleisten Stilen.

### <a name="remarks"></a>Hinweise

Eine Liste der Symbolleisten-Schaltflächen Stile finden Sie unter [Toolbar-Steuer](../../mfc/reference/toolbar-control-styles.md) Element

##  <a name="settext"></a>Cmfctoolbarcomboboxbutton:: SetText

Legt den Text im Bearbeitungsfeld der Kombinations Feld Schaltfläche fest.

```
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
in Ein Zeiger auf eine Zeichenfolge, die den Text für das Bearbeitungsfeld enthält.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen in eine Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
