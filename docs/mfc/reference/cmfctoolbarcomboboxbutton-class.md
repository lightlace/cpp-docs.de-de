---
title: CMFCToolBarComboBoxButton-Klasse
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
ms.openlocfilehash: e3c124103aa95d9db5095e438a6b21d46c7cb35d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218405"
---
# <a name="cmfctoolbarcomboboxbutton-class"></a>CMFCToolBarComboBoxButton-Klasse

Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement enthält ( [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)).

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
|[CMFCToolBarComboBoxButton::AddItem](#additem)|Fügt ein Element am Ende der Liste des Kombinationsfelds.|
|[CMFCToolBarComboBoxButton::AddSortedItem](#addsorteditem)|Fügt ein Element auf der Liste des Kombinationsfelds. Die Reihenfolge der Elemente in der Liste wird angegeben, indem `Compare`.|
|[CMFCToolBarComboBoxButton::Compare](#compare)|Vergleicht zwei Elemente. Wird aufgerufen, zum Sortieren von Elementen, `AddSortedItems` fügt der Liste des Kombinationsfelds hinzu.|
|[CMFCToolBarComboBoxButton::CreateEdit](#createedit)|Erstellt ein neues Bearbeitungssteuerelement für die Kombinationsfelds-Schaltfläche.|
|[CMFCToolBarComboBoxButton::DeleteItem](#deleteitem)|Löscht ein Element aus der Liste des Kombinationsfelds.|
|[CMFCToolBarComboBoxButton::FindItem](#finditem)|Gibt den Index des Elements, das eine angegebene Zeichenfolge enthält.|
|[CMFCToolBarComboBoxButton::GetByCmd](#getbycmd)|Gibt einen Zeiger auf die Kombinationsfelds-Schaltfläche mit einem angegebenen Befehls-ID|
|[CMFCToolBarComboBoxButton::GetComboBox](#getcombobox)|Gibt einen Zeiger auf das Kombinationsfeld-Steuerelement, das in der kombinationsfeldschaltfläche eingebettet ist.|
|[CMFCToolBarComboBoxButton::GetCount](#getcount)|Gibt die Anzahl der Elemente in das Kombinationsfeld-Liste zurück.|
|[CMFCToolBarComboBoxButton::GetCountAll](#getcountall)|Das Kombinationsfeld für den Box-Schaltfläche, die eine angegebenen Befehls-ID gesucht. Gibt die Anzahl der Elemente in das Kombinationsfeld für Liste der Schaltfläche zurück.|
|[CMFCToolBarComboBoxButton::GetCurSel](#getcursel)|Gibt den Index des ausgewählten Elements in das Kombinationsfeld-Liste zurück.|
|[CMFCToolBarComboBoxButton::GetCurSelAll](#getcurselall)|Sucht das Kombinationsfeld für Kontrollkästchen-Schaltfläche, die eine angegebene Befehls-ID und gibt den Index des ausgewählten Elements in das Kombinationsfeld für Liste der Schaltfläche.|
|[CMFCToolBarComboBoxButton::GetEditCtrl](#geteditctrl)|Gibt einen Zeiger auf das Steuerelement zum Bearbeiten, das in der kombinationsfeldschaltfläche eingebettet ist.|
|[CMFCToolBarComboBoxButton::GetItem](#getitem)|Gibt die Zeichenfolge, die mit einem angegebenen Index in das Kombinationsfeld für den zugeordneten Liste zurück.|
|[CMFCToolBarComboBoxButton::GetItemAll](#getitemall)|Sucht das Kombinationsfeld für Kontrollkästchen-Schaltfläche, die eine angegebene Befehls-ID und gibt die Zeichenfolge, die einen Index in der Liste des Kombinationsfelds der Schaltfläche zugeordnet ist.|
|[CMFCToolBarComboBoxButton::GetItemData](#getitemdata)|Gibt die 32-Bit-Wert, der mit einem angegebenen Index in das Kombinationsfeld für den verknüpft ist Liste zurück.|
|[CMFCToolBarComboBoxButton::GetItemDataAll](#getitemdataall)|Sucht das Kombinationsfeld für Kontrollkästchen-Schaltfläche, die eine angegebene Befehls-ID und gibt zurück, die 32-Bit-Wert, der einen Index in der Liste des Kombinationsfelds der Schaltfläche zugeordnet ist.|
|[CMFCToolBarComboBoxButton::GetItemDataPtrAll](#getitemdataptrall)|Das Kombinationsfeld für den Box-Schaltfläche, die eine angegebenen Befehls-ID gesucht. Ruft zugeordnete der 32-Bit-Wert, der einen Index in der Liste des Kombinationsfelds dieser Schaltfläche, und gibt die 32-Bit-Wert als Zeiger zurück.|
|[CMFCToolBarComboBoxButton::GetText](#gettext)|Gibt den Text in das Bearbeitungssteuerelement des Kombinationsfelds.|
|[CMFCToolBarComboBoxButton::GetTextAll](#gettextall)|Sucht das Kombinationsfeld für Kontrollkästchen-Schaltfläche, die eine angegebene Befehls-ID und gibt den Text aus der Edit-Steuerelements der Schaltfläche.|
|[CMFCToolBarComboBoxButton::IsCenterVert](#iscentervert)|Bestimmt, ob Schaltflächen in der Anwendung zentriert oder am oberen Rand der Symbolleiste ausgerichtet sind.|
|[CMFCToolBarComboBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob Schaltflächen in der Anwendung eine flache Darstellung haben.|
|[CMFCToolBarComboBoxButton::RemoveAllItems](#removeallitems)|Entfernt, die alle Elemente aus der Liste ein und Bearbeitungssteuerelement des Kombinationsfelds.|
|[CMFCToolBarComboBoxButton::SelectItem](#selectitem)|Wählt ein Element nach dessen Index, eine 32-Bit-Wert oder eine Zeichenfolge im Kombinationsfeld und benachrichtigt das Kombinationsfeld-Steuerelement zur Auswahl.|
|[CMFCToolBarComboBoxButton::SelectItemAll](#selectitemall)|Das Kombinationsfeld für den Box-Schaltfläche, die eine angegebenen Befehls-ID gesucht. Aufrufe `SelectItem` um ein Element der Schaltfläche entsprechend der Zeichenfolge, einem Index oder einer 32-Bit-Wert im Kombinationsfeld auszuwählen.|
|[CMFCToolBarComboBoxButton::SetCenterVert](#setcentervert)|Gibt an, ob Schaltflächen in der Anwendung vertikal zentriert oder am oberen Rand der Symbolleiste ausgerichtet sind.|
|[CMFCToolBarComboBoxButton::SetDropDownHeight](#setdropdownheight)|Legt die Höhe des im Dropdown-Listenfeld an.|
|[CMFCToolBarComboBoxButton::SetFlatMode](#setflatmode)|Gibt an, ob Schaltflächen in der Anwendung eine flache Darstellung verfügen.|

## <a name="remarks"></a>Hinweise

Um eine Kombinationsfelds-Schaltfläche einer Symbolleiste hinzuzufügen, gehen Sie folgendermaßen vor:

1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.

2. Konstruieren Sie ein `CMFCToolBarComboBoxButton`-Objekt.

3. Ersetzen Sie in der Message-Handler, die die AFX_WM_RESETTOOLBAR-Nachricht verarbeitet, die Schaltfläche "dummy" mit der neuen kombinationsfeldschaltfläche mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf der Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md). Ein Beispiel für eine Symbolleiste kombinationsfeldschaltfläche finden Sie das Beispielprojekt VisualStudioDemo.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCToolBarComboBoxButton` -Klasse. Das Beispiel zeigt, wie Sie die Felder bearbeiten und das Kombinationsfeld zu aktivieren, legen die vertikale Position des Kombinationsfeld-Schaltflächen in der Anwendung, die Höhe des Listenfelds festlegen, wenn er, nach unten gelöscht wird, die flache Darstellung der Schaltflächen in der Anwendung festgelegt , und legen Sie den Text im Eingabefeld des Kombinationsfeld-Schaltfläche. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#36](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_1.cpp)]
[!code-cpp[NVC_MFC_VisualStudioDemo#37](../../mfc/codesnippet/cpp/cmfctoolbarcomboboxbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxtoolbarcomboboxbutton.h

##  <a name="additem"></a>  CMFCToolBarComboBoxButton::AddItem

Fügt ein eindeutiges Element in das Listenfeld an.

```
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parameter

*lpszItem*<br/>
[in] Der Text des Elements, das im Listenfeld hinzugefügt werden soll.

*dwData*<br/>
[in] Die Daten, die dem Element im Listenfeld hinzuzufügende zugeordnet.

### <a name="return-value"></a>Rückgabewert

Der Index des letzten Elements im Listenfeld.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nicht aus, wenn die Knotenart Liste sortiert wird.

Wenn der Elementtext bereits im Listenfeld ist, werden die neuen Daten mit dem vorhandenen Element gespeichert. Der Suche für das Element wird Groß-/Kleinschreibung beachtet.

##  <a name="addsorteditem"></a>  CMFCToolBarComboBoxButton::AddSortedItem

Fügt ein Element in das Listenfeld in der Reihenfolge, die durch definiert die [vergleichen](#compare) Methode.

```
virtual INT_PTR AddSortedItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>Parameter

*lpszItem*<br/>
[in] Der Text des Elements, das im Listenfeld hinzugefügt werden soll.

*dwData*<br/>
[in] Die Daten, die dem Element im Listenfeld hinzuzufügende zugeordnet.

### <a name="return-value"></a>Rückgabewert

Der Index des Elements, das im Listenfeld hinzugefügt wurde.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Funktion in einer bestimmten Reihenfolge in die Liste Elemente hinzuzufügen.

##  <a name="canbestretched"></a>  CMFCToolBarComboBoxButton::CanBeStretched

Gibt an, ob die Größe des Kombinationsfelds Schaltfläche ändern kann.

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück.

##  <a name="cmfctoolbarcomboboxbutton"></a>  CMFCToolBarComboBoxButton::CMFCToolBarComboBoxButton

Erstellt eine [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) Objekt.

```
CMFCToolBarComboBoxButton(
    UINT uiID,
    int iImage,
    DWORD dwStyle=CBS_DROPDOWNLIST,
    int iWidth=0);
```

### <a name="parameters"></a>Parameter

*uiID*<br/>
[in] Die Befehls-ID von der Schaltfläche "Neu".

*iImage*<br/>
[in] Der Bildindex des Bilds der Schaltfläche "Neu" zugeordnet.

*dwStyle*<br/>
[in] Die Darstellung der Schaltfläche "Neu".

*iWidth*<br/>
[in] Die Breite in Pixel der Schaltfläche "Neu".

### <a name="remarks"></a>Hinweise

Die Standardbreite beträgt 150 Pixel.

Eine Liste der Formatvorlagen für Symbolleistenschaltflächen finden Sie unter [ToolBar-Steuerelement-Stile](../../mfc/reference/toolbar-control-styles.md)

##  <a name="cleardata"></a>  CMFCToolBarComboBoxButton::ClearData

Löscht den benutzerdefinierten Daten.

```
virtual void ClearData();
```

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie eine benutzerdefinierte Daten löschen möchten.

##  <a name="compare"></a>  CMFCToolBarComboBoxButton::Compare

Vergleicht zwei Zeichenfolgen.

```
virtual int Compare(
    LPCTSTR lpszItem1,
    LPCTSTR lpszItem2);
```

### <a name="parameters"></a>Parameter

*lpszItem1*<br/>
[in] Die erste zu vergleichende Zeichenfolge.

*lpszItem2*<br/>
[in] Die zweite zu vergleichende Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Ein Wert, der die Groß-/Kleinschreibung lexikografische Beziehung zwischen den Zeichenfolgen angibt. In der folgende Tabelle sind die möglichen Werte aufgeführt:

|Wert|Beschreibung|
|-----------|-----------------|
|\<0|Die erste Zeichenfolge ist kleiner als der zweite.|
|0|Die erste Zeichenfolge gleich der zweiten ist.|
|>0|Die erste Zeichenfolge ist größer als der zweite.|

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode zum Ändern der Sortierung der Elemente im Listenfeld ein.

Beim Vergleich wird Groß-/Kleinschreibung beachtet.

Diese Methode wird aufgerufen, nur über die [AddSortedItem](#addsorteditem) Methode.

##  <a name="copyfrom"></a>  CMFCToolBarComboBoxButton::CopyFrom

Kopiert den Zustand des angegebenen `CMFCToolBarComboBoxButton` auf das aktuelle Objekt.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parameter

*src*<br/>
[in] Die Quelle `CMFCToolBarComboBoxButton` Objekt.

##  <a name="createcombo"></a>  CMFCToolBarComboBoxButton::CreateCombo

Erstellt ein neues Kombinationsfeld für den Kombinationsfelds-Schaltfläche.

```
virtual CComboBox* CreateCombo(
    CWnd* pWndParent,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster der Schaltfläche.

*rect*<br/>
[in] Umschließende Rechteck des Kombinationsfelds.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das neue Kombinationsfeld, wenn die Methode erfolgreich war; andernfalls NULL.

##  <a name="createedit"></a>  CMFCToolBarComboBoxButton::CreateEdit

Erstellt ein neues Eingabefeld für den Kombinationsfelds-Schaltfläche.

```
virtual CMFCToolBarComboBoxEdit* CreateEdit(
    CWnd* pWndParent,
    const CRect& rect,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster der Schaltfläche.

*rect*<br/>
[in] Umschließende Rechteck des neuen im Bearbeitungsfeld.

*dwEditStyle*<br/>
[in] Format des neuen Steuerelements im Bearbeitungsfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den neuen Eingabefeld zurück, wenn die Methode erfolgreich war; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn es sich um ein neues Eingabefeld für eine kombinationsfeldschaltfläche erstellt. Überschreiben Sie diese Methode so ändern Sie wie [CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md) erstellt wird.

##  <a name="deleteitem"></a>  CMFCToolBarComboBoxButton::DeleteItem

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
[in] Der Text des Elements, das gelöscht werden. Wenn mehrere Elemente mit dem gleichen Text vorhanden sind, wird das erste Element gelöscht.

### <a name="return-value"></a>Rückgabewert

True, wenn das Element gefunden und erfolgreich gelöscht wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="duplicatedata"></a>  CMFCToolBarComboBoxButton::DuplicateData

Duplikate mit benutzerdefinierten Daten.

```
virtual void DuplicateData();
```

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn keine benutzerdefinierten Daten kopiert werden sollen.

##  <a name="enablewindow"></a>  CMFCToolBarComboBoxButton::EnableWindow

Aktiviert oder deaktiviert die Felder bearbeiten und Kombinationsfelder.

```
virtual void EnableWindow(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] True, um die Felder bearbeiten und das Kombinationsfeld zu aktivieren. So deaktivieren Sie die Felder bearbeiten und Kombinationsfeld wird false ZURÜCKGEGEBEN.

### <a name="remarks"></a>Hinweise

Wenn deaktiviert, werden die Steuerelemente können nicht aktiv und können keine Benutzereingaben akzeptieren.

##  <a name="exporttomenubutton"></a>  CMFCToolBarComboBoxButton::ExportToMenuButton

Kopiert eine Zeichenfolge aus der Anwendung Zeichenfolgentabelle auf das angegebene Menü mithilfe des Kombinationsfeld-Box-Schaltfläche-Befehls-ID.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Parameter

*menuButton*<br/>
[out] Verweis auf eine Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Immer "true".

##  <a name="finditem"></a>  CMFCToolBarComboBoxButton::FindItem

Gibt den Index des ersten Elements in das Listenfeld, das eine angegebene Zeichenfolge enthält.

```
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
[in] Der Text für die Sie in das Listenfeld gesucht werden soll.

### <a name="return-value"></a>Rückgabewert

Der Index des Elements, andernfalls oder CB_ERR, wenn das Element nicht gefunden wird.

### <a name="remarks"></a>Hinweise

##  <a name="getbycmd"></a>  CMFCToolBarComboBoxButton::GetByCmd

Ruft einen Zeiger auf die Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID.

```
static CMFCToolBarComboBoxButton* GetByCmd(
    UINT uiCmd,
    BOOL bIsFocus=FALSE);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID des Kombinationsfelds-Schaltfläche.

*bIsFocus*<br/>
[in] Konzentrieren Schaltflächen, "true" nur gesucht; "False", um alle Schaltflächen zu suchen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine kombinationsfeldschaltfläche; oder NULL, wenn die Schaltfläche "nicht gefunden wird.

### <a name="remarks"></a>Hinweise

##  <a name="getcombobox"></a>  CMFCToolBarComboBoxButton::GetComboBox

Gibt einen Zeiger zurück auf das Kombinationsfeld in das Kombinationsfeld für Kontrollkästchen-Schaltfläche.

```
CComboBox* GetComboBox() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die [CComboBox-Klasse](../../mfc/reference/ccombobox-class.md) Objekt, wenn die Methode erfolgreich war; andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="getcontextmenuid"></a>  CMFCToolBarComboBoxButton::GetContextMenuID

Ruft die Tastenkombination im Menü-Ressourcen-ID für die Kombinationsfelds-Schaltfläche ab.

```
UINT GetContextMenuID();
```

### <a name="return-value"></a>Rückgabewert

Die Verknüpfung im Menü-Ressourcen-ID.

##  <a name="getcount"></a>  CMFCToolBarComboBoxButton::GetCount

Gibt die Anzahl der Elemente im Listenfeld zurück.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listenfeld.

### <a name="remarks"></a>Hinweise

##  <a name="getcountall"></a>  CMFCToolBarComboBoxButton::GetCountAll

Ruft die Anzahl der Elemente in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID.

```
static int GetCountAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID des Kombinationsfelds-Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listenfeld; Andernfalls wird CB_ERR, wenn das Kombinationsfeld für den Schaltfläche Feld nicht gefunden.

### <a name="remarks"></a>Hinweise

##  <a name="getcursel"></a>  CMFCToolBarComboBoxButton::GetCurSel

Ruft den Index des derzeit ausgewählten Elements im Listenfeld ab.

```
int GetCurSel() const;
```

### <a name="return-value"></a>Rückgabewert

Der Index des derzeit ausgewählten Elements im Listenfeld; oder CB_ERR, wenn kein Element ausgewählt ist.

### <a name="remarks"></a>Hinweise

Die listenfeldindex ist nullbasiert.

##  <a name="getcurselall"></a>  CMFCToolBarComboBoxButton::GetCurSelAll

Gibt den Index des derzeit ausgewählten Elements in das Listenfeld eines Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID.

```
static int GetCurSelAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID des Kombinationsfelds-Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Der Index des derzeit ausgewählten Elements im Listenfeld; CB_ERR, wenn kein Element ausgewählt ist oder ein kombinationsfeldschaltfläche ist, andernfalls nicht gefunden.

### <a name="remarks"></a>Hinweise

Die listenfeldindex ist nullbasiert.

##  <a name="geteditctrl"></a>  CMFCToolBarComboBoxButton::GetEditCtrl

Gibt einen Zeiger zurück in das Bearbeitungsfeld in das Kombinationsfeld für Kontrollkästchen-Schaltfläche.

```
virtual CEdit* GetEditCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das Bearbeitungsfeld, wenn die Methode erfolgreich war; andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="gethwnd"></a>  CMFCToolBarComboBoxButton::GetHwnd

Gibt das Fensterhandle für das Kombinationsfeld zurück.

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>Rückgabewert

Das Fensterhandle oder NULL, wenn das Kombinationsfeld kein Window-Objekt zugeordnet ist.

##  <a name="getitem"></a>  CMFCToolBarComboBoxButton::GetItem

Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld zugeordnet.

```
LPCTSTR GetItem(int iIndex=-1) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Zeichenfolge, die dem Element zugeordnet ist; andernfalls, NULL, wenn der Indexparameter ungültig ist, oder wenn der Indexparameter ist-1 und gibt es kein ausgewähltes Element im Kombinationsfeld ist.

### <a name="remarks"></a>Hinweise

Indexparameter von-1 gibt die Zeichenfolge des Elements, das derzeit ausgewählt ist.

##  <a name="getitemall"></a>  CMFCToolBarComboBoxButton::GetItemAll

Gibt die Zeichenfolge, die ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID zugeordnet

```
static LPCTSTR GetItemAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID des Kombinationsfelds-Schaltfläche.

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf Zeichenfolge des Elements, wenn die Methode erfolgreich war; andernfalls, NULL, wenn der Indexwert ungültig ist, eine kombinationsfeldschaltfläche nicht gefunden wird, oder wenn der Index ist 1, und es ist kein ausgewählte Element im Kombinationsfeld.

### <a name="remarks"></a>Hinweise

Ein Indexwert von 1, gibt die Zeichenfolge des Elements, das derzeit ausgewählt ist.

##  <a name="getitemdata"></a>  CMFCToolBarComboBoxButton::GetItemData

Gibt ein Element am angegebenen Index in das Listenfeld zugeordneten Daten zurück.

```
DWORD_PTR GetItemData(int iIndex=-1) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Die Daten, die dem Element zugeordnet, oder 0, wenn das Element nicht vorhanden ist.

### <a name="remarks"></a>Hinweise

Ein Indexparameter von-1 gibt das aktuell ausgewählte Element zugeordneten Daten zurück.

##  <a name="getitemdataall"></a>  CMFCToolBarComboBoxButton::GetItemDataAll

Gibt zurück, die ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine bestimmte Befehls-ID zugeordneten Daten

```
static DWORD_PTR GetItemDataAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID des Kombinationsfelds-Schaltfläche.

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Die Daten, die dem Element zugeordnet, wenn die Methode erfolgreich war; andernfalls 0, wenn der angegebene Index nicht gültig ist oder CB_ERR, wenn das Kombinationsfeld für den Schaltfläche Feld wurde nicht gefunden.

### <a name="remarks"></a>Hinweise

Ein Indexparameter von-1 gibt das aktuell ausgewählte Element zugeordneten Daten zurück.

##  <a name="getitemdataptrall"></a>  CMFCToolBarComboBoxButton::GetItemDataPtrAll

Gibt zurück, die ein Element am angegebenen Index in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine bestimmte Befehls-ID zugeordneten Daten Diese Daten werden als Zeiger zurückgegeben.

```
static void* GetItemDataPtrAll(
    UINT uiCmd,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID des Kombinationsfelds-Schaltfläche.

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger, der dem Element zugeordnet, wenn die Methode erfolgreich war; andernfalls-1, wenn ein Fehler auftritt, oder NULL, wenn das Kombinationsfeld für den Schaltfläche Feld wurde nicht gefunden.

### <a name="remarks"></a>Hinweise

##  <a name="getprompt"></a>  CMFCToolBarComboBoxButton::GetPrompt

Gibt die eingabeaufforderungs-Zeichenfolge für das Kombinationsfeld-Schaltfläche im zurück.

```
virtual CString GetPrompt() const;
```

### <a name="return-value"></a>Rückgabewert

Die eingabeaufforderungs-Zeichenfolge.

### <a name="remarks"></a>Hinweise

Diese Methode wird derzeit nicht implementiert.

##  <a name="gettext"></a>  CMFCToolBarComboBoxButton::GetText

Ruft den Text im Eingabefeld.

```
LPCTSTR GetText() const;
```

### <a name="return-value"></a>Rückgabewert

Der Text im Eingabefeld.

### <a name="remarks"></a>Hinweise

##  <a name="gettextall"></a>  CMFCToolBarComboBoxButton::GetTextAll

Ruft den Text im Eingabefeld des eine Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID ab

```
static LPCTSTR GetTextAll(UINT uiCmd);
```

### <a name="parameters"></a>Parameter

*uiCmd*<br/>
[in] Die Befehls-ID von einer bestimmten Kombinationsfelds-Schaltfläche.

### <a name="return-value"></a>Rückgabewert

Der Text im Bearbeitungsfeld, wenn die Methode erfolgreich war. andernfalls NULL.

### <a name="remarks"></a>Hinweise

##  <a name="hasfocus"></a>  CMFCToolBarComboBoxButton::HasFocus

Gibt an, ob das Kombinationsfeld zurzeit den Fokus besitzt.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Kombinationsfeld zurzeit den Fokus besitzt. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode gibt auch "true" zurück, wenn beliebige untergeordnete Fenster des Kombinationsfelds aktuell den Fokus besitzt.

##  <a name="iscentervert"></a>  CMFCToolBarComboBoxButton::IsCenterVert

Gibt die vertikale Position der Schaltflächen in der Anwendung zurück.

```
static BOOL IsCenterVert();
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Schaltflächen zentriert werden. "False", wenn die Schaltflächen oben ausgerichtet sind.

### <a name="remarks"></a>Hinweise

##  <a name="isflatmode"></a>  CMFCToolBarComboBoxButton::IsFlatMode

Gibt die flache Darstellung der Schaltflächen in der Anwendung zurück.

```
static BOOL IsFlatMode();
```

### <a name="return-value"></a>Rückgabewert

True, wenn Schaltflächen flach sind; andernfalls "false".

### <a name="remarks"></a>Hinweise

Die flache Standardstil für Schaltflächen ist "false".

##  <a name="isownerof"></a>  CMFCToolBarComboBoxButton::IsOwnerOf

Gibt an, ob das angegebene Handle der kombinationsfeldschaltfläche oder eines seiner untergeordneten Elemente zugeordnet ist.

```
virtual BOOL IsOwnerOf(HWND hwnd);
```

### <a name="parameters"></a>Parameter

*hwnd*<br/>
[in] Ein Fensterhandle.

### <a name="return-value"></a>Rückgabewert

True, wenn das Handle zugeordnetes mit der kombinationsfeldschaltfläche oder eines seiner untergeordneten Elemente. andernfalls "false".

##  <a name="isribbonbutton"></a>  CMFCToolBarComboBoxButton::IsRibbonButton

Gibt an, ob die Kombinationsfelds-Schaltfläche in einem Menübandbereich befindet.

```
BOOL IsRibbonButton() const;
```

### <a name="return-value"></a>Rückgabewert

Immer "false".

### <a name="remarks"></a>Hinweise

Standardmäßig gibt diese Methode immer "false", was bedeutet, dass der kombinationsfeldschaltfläche niemals in einem Menübandbereich angezeigt wird.

##  <a name="iswindowvisible"></a>  CMFCToolBarComboBoxButton::IsWindowVisible

Gibt den Sichtbarkeitszustand des Kombinationsfeld-Schaltfläche im zurück.

```
virtual BOOL IsWindowVisible();
```

### <a name="return-value"></a>Rückgabewert

Der Sichtbarkeitszustand des Kombinationsfelds-Schaltfläche.

##  <a name="notifycommand"></a>  CMFCToolBarComboBoxButton::NotifyCommand

Gibt an, ob der kombinationsfeldschaltfläche die Nachricht verarbeitet.

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>Parameter

*iNotifyCode*<br/>
[in] Die Benachrichtigung, die mit dem Befehl zugeordnet ist.

### <a name="return-value"></a>Rückgabewert

Gibt an, ob der kombinationsfeldschaltfläche die Nachricht verarbeitet.

##  <a name="onaddtocustomizepage"></a>  CMFCToolBarComboBoxButton::OnAddToCustomizePage

Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird die **anpassen** Dialogfeld.

```
virtual void OnAddToCustomizePage();
```

##  <a name="oncalculatesize"></a>  CMFCToolBarComboBoxButton::OnCalculateSize

Wird aufgerufen, durch das Framework, um die Größe der Schaltfläche zu berechnen.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Der Gerätekontext, in dem der kombinationsfeldschaltfläche angezeigt.

*sizeDefault*<br/>
[in] Die Standardgröße des Kombinationsfelds-Schaltfläche.

*bHorz*<br/>
[in] Der Status der Andocken der übergeordneten Symbolleiste. TRUE, wenn die Symbolleiste horizontal und "false" verankert ist, wenn die Symbolleiste vertikal verankert ist.

### <a name="return-value"></a>Rückgabewert

Ein `SIZE` Struktur, die die Abmessungen der Schaltfläche im Kombinationsfeld in Pixel enthält.

##  <a name="onchangeparentwnd"></a>  CMFCToolBarComboBoxButton::OnChangeParentWnd

Vom Framework aufgerufen, wenn der kombinationsfeldschaltfläche in eine neue Symbolleiste eingefügt wird.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Zeiger auf den neuen übergeordneten Symbolleiste.

##  <a name="onclick"></a>  CMFCToolBarComboBoxButton::OnClick

Vom Framework aufgerufen, wenn der Benutzer die Kombinationsfelds-Schaltfläche klickt.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Parameter

*pWnd*<br/>
[in] Zeiger auf das übergeordnete Fenster des Kombinationsfelds-Schaltfläche.

*bDelay*<br/>
[in] Für die Verwendung in einer abgeleiteten Klasse reserviert.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode das Ereignis behandelt. andernfalls "false".

##  <a name="onctlcolor"></a>  CMFCToolBarComboBoxButton::OnCtlColor

Vom Framework aufgerufen, wenn der Benutzer die Farbe des übergeordneten-Symbolleiste an, legen Sie das Kombinationsfeld für den Box-Farbe für Schaltfläche ändert.

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Der Gerätekontext, in dem der kombinationsfeldschaltfläche angezeigt.

*nCtlColor*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Handle für den Pinsel aus, dem das Framework verwendet, um den Hintergrund der kombinationsfeldschaltfläche zu zeichnen.

### <a name="remarks"></a>Hinweise

Diese Methode wird auch die Textfarbe einer Schaltfläche der Combo Box.

##  <a name="ondraw"></a>  CMFCToolBarComboBoxButton::OnDraw

Wird aufgerufen, durch das Framework der kombinationsfeldschaltfläche zu zeichnen, indem Sie mit der angegebenen Formate und -Optionen.

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
[in] Der Gerätekontext, in dem die Schaltfläche angezeigt.

*rect*<br/>
[in] Das umschließende Rechteck der Schaltfläche.

*pImages*<br/>
[in] Die Auflistung der Bilder, die mit der Schaltfläche zugeordnet ist.

*bHorz*<br/>
[in] Der Status der Andocken der übergeordneten Symbolleiste. TRUE, wenn die Symbolleiste horizontal und "false" verankert ist, wenn die Symbolleiste vertikal verankert ist.

*bCustomizeMode*<br/>
[in] Gibt an, ob die Anwendung im Anpassungsmodus aktiviert ist.

*bHighlight*<br/>
[in] Angibt, ob zum Zeichnen der kombinationsfeldschaltfläche hervorgehoben.

*bDrawBorder*<br/>
[in] Ob der kombinationsfeldschaltfläche mit einem Rahmen gezeichnet werden soll.

*bGrayDisabledButtons*<br/>
[in] Deaktivierte Schaltflächen schattiert ist "true" Draw; FALSE, wenn die Auflistung der deaktivierten Bilder verwendet werden soll.

##  <a name="ondrawoncustomizelist"></a>  CMFCToolBarComboBoxButton::OnDrawOnCustomizeList

Wird aufgerufen, durch das Framework für das Zeichnen der kombinationsfeldschaltfläche der **Befehle** im Bereich der **anpassen** Dialogfeld.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Der Gerätekontext, in dem der kombinationsfeldschaltfläche angezeigt.

*rect*<br/>
[in] Das umschließende Rechteck des Kombinationsfelds-Schaltfläche.

*bSelected*<br/>
[in] True, wenn der kombinationsfeldschaltfläche ausgewählt ist. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Die Breite des Kombinationsfelds-Schaltfläche in Pixel.

##  <a name="onglobalfontschanged"></a>  CMFCToolBarComboBoxButton::OnGlobalFontsChanged

Wird aufgerufen, durch das Framework das Kombinationsfeld für den Schaltfläche Schriftart festgelegt, wenn die Anwendungsschriftart geändert wird.

```
virtual void OnGlobalFontsChanged();
```

##  <a name="onmove"></a>  CMFCToolBarComboBoxButton::OnMove

Wird aufgerufen, durch das Framework zum Ändern der Position der kombinationsfeldschaltfläche, wechselt die übergeordneten Symbolleiste.

```
virtual void OnMove();
```

##  <a name="onshow"></a>  CMFCToolBarComboBoxButton::OnShow

Vom Framework aufgerufen, wenn der kombinationsfeldschaltfläche angezeigt oder ausgeblendet wird.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
[in] Ob der kombinationsfeldschaltfläche anzeigen oder ausblenden.

##  <a name="onsize"></a>  CMFCToolBarComboBoxButton::OnSize

Wird aufgerufen, durch das Framework zum Ändern der Größe der kombinationsfeldschaltfläche, wenn die übergeordneten Symbolleiste Größe ändert.

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>Parameter

*iSize*<br/>
[in] Die neue Breite des Kombinationsfelds-Schaltfläche.

##  <a name="onupdatetooltip"></a>  CMFCToolBarComboBoxButton::OnUpdateToolTip

Vom Framework aufgerufen, wenn der Benutzer die QuickInfo für die kombinationsfeldschaltfläche ändert.

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>Parameter

*pWndParent*<br/>
[in] Zeiger auf das übergeordnete Fenster für die Kombinationsfelds-Schaltfläche.

*iButtonIndex*<br/>
[in] ID des Kombinationsfelds-Schaltfläche.

*wndToolTip*<br/>
[in] Die QuickInfo der kombinationsfeldschaltfläche zugeordnet werden soll.

*str*<br/>
[in] Der QuickInfo-Text.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode das Ereignis behandelt. andernfalls "false".

##  <a name="removeallitems"></a>  CMFCToolBarComboBoxButton::RemoveAllItems

Löscht alle Elemente aus der Liste "und" Bearbeiten-Feldern.

```
void RemoveAllItems();
```

### <a name="remarks"></a>Hinweise

Entfernt, die alle Elemente aus der Liste ein, und bearbeiten die Kontrolle über ein Kombinationsfeld.

##  <a name="selectitem"></a>  CMFCToolBarComboBoxButton::SelectItem

Wählt ein Element im Listenfeld an.

```
BOOL SelectItem(
    int iIndex,
    BOOL bNotify=TRUE);

BOOL SelectItem(DWORD_PTR dwData);
BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index eines Elements in das Listenfeld.

*bNotify*<br/>
[in] True, um der Auswahl der kombinationsfeldschaltfläche zu benachrichtigen. andernfalls "false".

*dwData*<br/>
[in] Die Daten, die einem Element im Listenfeld zugeordnet wird.

*lpszText*<br/>
[in] Der Text eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="selectitemall"></a>  CMFCToolBarComboBoxButton::SelectItemAll

Wählt ein Element in das Listenfeld ein Kombinationsfelds-Schaltfläche, die eine angegebenen Befehls-ID.

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
[in] Die Befehls-ID von der kombinationsfeldschaltfläche, die im Listenfeld enthält.

*iIndex*<br/>
[in] Der nullbasierte Index des Elements im Listenfeld. Der Wert-1 wird eine aktuelle Auswahl im Listenfeld entfernt und löscht im Bearbeitungsfeld.

*dwData*<br/>
[in] Die Daten eines Elements in das Listenfeld.

*lpszText*<br/>
[in] Der Text eines Elements in das Listenfeld.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="serialize"></a>  CMFCToolBarComboBoxButton::Serialize

Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parameter

*ar*<br/>
[in, out] Die `CArchive` zu serialisierende Objekt.

### <a name="remarks"></a>Hinweise

Einstellungen in der `CArchive` Objekt zu ermitteln, ob diese Methode liest oder schreibt in das Archiv.

##  <a name="setaccdata"></a>  CMFCToolBarComboBoxButton::SetACCData

Füllt das angegebene `CAccessibilityData` -Objekt mithilfe von barrierefreiheitsdaten aus dem Kombinationsfelds-Schaltfläche.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parameter

*pParent*<br/>
[in] Das übergeordnete Fenster von der kombinationsfeldschaltfläche.

*data*<br/>
[out] Ein `CAccessibilityData` Objekt, das die barrierefreiheitsdaten aus der kombinationsfeldschaltfläche empfängt.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

##  <a name="setcentervert"></a>  CMFCToolBarComboBoxButton::SetCenterVert

Legt die vertikale Position der Schaltflächen in der Anwendung fest.

```
static void SetCenterVert(BOOL bCenterVert=TRUE);
```

### <a name="parameters"></a>Parameter

*bCenterVert*<br/>
[in] "True" Center die Kombinationsfelds-Schaltfläche auf der Symbolleiste "False" an das die Kombinationsfelds-Schaltfläche am oberen Rand der Symbolleiste.

### <a name="remarks"></a>Hinweise

Standardmäßig werden die Schaltflächen oben ausgerichtet.

##  <a name="setcontextmenuid"></a>  CMFCToolBarComboBoxButton::SetContextMenuID

Legt die Verknüpfung im Menü-Ressourcen-ID für das Kombinationsfeld-Schaltfläche im fest.

```
void SetContextMenuID(UINT uiResID);
```

### <a name="parameters"></a>Parameter

*uiResID*<br/>
[in] Die Verknüpfung im Menü-Ressourcen-ID.

##  <a name="setdropdownheight"></a>  CMFCToolBarComboBoxButton::SetDropDownHeight

Legt die Höhe des Listenfelds fest, wenn sie nach unten gelöscht wird.

```
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>Parameter

*nHeight*<br/>
[in] Die Höhe in Pixel des Listenfelds.

### <a name="remarks"></a>Hinweise

Die Standardhöhe ist 150 Pixel.

##  <a name="setflatmode"></a>  CMFCToolBarComboBoxButton::SetFlatMode

Legt die flache Darstellung der Schaltflächen in der Anwendung fest.

```
static void SetFlatMode(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>Parameter

*bFlat*<br/>
[in] "True" für eine flache Darstellung; andernfalls "false".

### <a name="remarks"></a>Hinweise

Die flache Standardstil für Schaltflächen ist "false".

##  <a name="setstyle"></a>  CMFCToolBarComboBoxButton::SetStyle

Legt das angegebene Format für das Kombinationsfeld für den-Schaltfläche im und zeichnet das Steuerelement neu, wenn es nicht deaktiviert ist.

```
virtual void SetStyle(UINT nStyle);
```

### <a name="parameters"></a>Parameter

*nStyle*<br/>
[in] Eine bitweise Kombination (OR) von Toolbar-Stile.

### <a name="remarks"></a>Hinweise

Eine Liste der Formatvorlagen für Symbolleistenschaltflächen finden Sie unter [ToolBar-Steuerelement-Stile](../../mfc/reference/toolbar-control-styles.md)

##  <a name="settext"></a>  CMFCToolBarComboBoxButton::SetText

Legt den Text im Eingabefeld des Kombinationsfeld-Schaltfläche im fest.

```
void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
[in] Zeiger auf eine Zeichenfolge, die den Text für das Bearbeitungsfeld enthält.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Exemplarische Vorgehensweise: Einfügen von Steuerelementen in eine Symbolleiste](../../mfc/walkthrough-putting-controls-on-toolbars.md)
