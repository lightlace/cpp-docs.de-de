---
title: CMFCHeaderCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: 86674e086da482e59b2711f5ba9154848ff05a6f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269434"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class

Die `CMFCHeaderCtrl` Klasse unterstützt die Sortierung mehrere Spalten in einem Kopfzeilen-Steuerelement.

## <a name="syntax"></a>Syntax

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Erstellt ein `CMFCHeaderCtrl`-Objekt.|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Aktiviert oder deaktiviert die *Sortieren mehrerer Spalten* Modus für das aktuelle Kopfzeilen-Steuerelement.|
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Gibt an, ob eine Spalte nicht sortiert in aufsteigender oder absteigender Reihenfolge sortiert wird.|
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Ruft ab, der nullbasierte Index der ersten Spalte sortiert in das Kopfzeilen-Steuerelement.|
|`CMFCHeaderCtrl::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CMFCHeaderCtrl::IsAscending](#isascending)|Gibt an, ob eine Spalte in dem Kopfzeilen-Steuerelement in aufsteigender Reihenfolge sortiert wird.|
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Gibt an, ob das übergeordnete Fenster des die aktuelle Kopfzeilen-Steuerelement ein Dialogfeld ist.|
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Gibt an, ob das aktuelle Kopfzeilen-Steuerelement in *Sortieren mehrerer Spalten* Modus.|
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Entfernt die angegebene Spalte aus der Liste der Sortierspalten.|
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Legt die Sortierreihenfolge einer angegebenen Spalte in einem Kopfzeilen-Steuerelement fest.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Wird aufgerufen, durch das Framework, um eine Spalte des Header-Steuerelement zu zeichnen.|
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Wird aufgerufen, durch das Framework zum Zeichnen des Pfeils sortieren.|
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Wird aufgerufen, durch das Framework, um den Hintergrund des Steuerelements Headerspalte zu füllen.|

## <a name="example"></a>Beispiel

Im folgende Beispiel wird veranschaulicht, wie zum Erstellen eines Objekts von der `CMFCHeaderCtrl` -Klasse, und aktivieren *Sortieren mehrerer Spalten* Modus für das aktuelle Kopfzeilen-Steuerelement.

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>Hinweise

Die `CMFCHeaderCtrl` Klasse zeichnet einen Pfeil Sortierreihenfolge für eine Spalte des Header-Steuerelement, um anzugeben, dass die Spalte sortiert wird. Verwendung *Sortieren mehrerer Spalten* Modus, wenn eine Gruppe von Spalten im übergeordneten Steuerelement ( [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)) können zur gleichen Zeit sortiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxheaderctrl.h

##  <a name="cmfcheaderctrl"></a>  CMFCHeaderCtrl::CMFCHeaderCtrl

Erstellt ein `CMFCHeaderCtrl`-Objekt.

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>Hinweise

Dieser Konstruktor initialisiert die folgenden Membervariablen auf die angegebenen Werte an:

|Membervariable|Wert|
|---------------------|-----------|
|`m_bIsMousePressed`|false|
|`m_bMultipleSort`|false|
|`m_bAscending`|true|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|false|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

##  <a name="enablemultiplesort"></a>  CMFCHeaderCtrl::EnableMultipleSort

Aktiviert oder deaktiviert die *Sortieren mehrerer Spalten* Modus für das aktuelle Kopfzeilen-Steuerelement.

```
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] True, um mehrere Spalten sortieren-Modus zu aktivieren. "False", um mehrere Spalten sortieren-Modus deaktivieren und entfernen Sie alle Spalten aus der Liste der sortierten Spalten. Der Standardwert ist "true".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode zum Aktivieren oder Deaktivieren von mehreren Spalten sortieren-Modus. Zwei oder mehr Spalten können in einer Art teilnehmen, wenn es sich bei das Kopfzeilen-Steuerelement in mehreren Spalten sortieren-Modus befindet.

##  <a name="getcolumnstate"></a>  CMFCHeaderCtrl::GetColumnState

Gibt an, ob eine Spalte ist nicht sortiert in aufsteigender oder absteigender Reihenfolge sortiert wird.

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>Parameter

*iColumn*<br/>
[in] Der nullbasierte Index einer Spalte.

### <a name="return-value"></a>Rückgabewert

Ein Wert, der den Status der Sortierung der angegebenen Spalte anzugeben. In der folgende Tabelle sind die möglichen Werte aufgeführt:

|Wert|Beschreibung|
|-----------|-----------------|
|-1|In absteigender Reihenfolge sortiert.|
|0|Nicht sortiert.|
|1|In aufsteigender Reihenfolge sortiert.|

### <a name="remarks"></a>Hinweise

##  <a name="getsortcolumn"></a>  CMFCHeaderCtrl::GetSortColumn

Ruft ab, der nullbasierte Index der ersten Spalte sortiert in das Kopfzeilen-Steuerelement.

```
int GetSortColumn() const;
```

### <a name="return-value"></a>Rückgabewert

Der Index der Sortierung einer Spalte oder -1, wenn keine sortierte Spalte gefunden wird.

### <a name="remarks"></a>Hinweise

Ist das Kopfzeilen-Steuerelement in *Sortieren mehrerer Spalten* Modus, und Sie die Anwendung im Debugmodus kompiliert, diese Methode bestätigt und weist Ihnen die Verwendung der [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) Methode stattdessen. Wenn das Kopfzeilen-Steuerelement befindet sich in mehreren Spalten sortieren-Modus, und Sie die Anwendung im Einzelhandel-Modus kompiliert, gibt diese Methode-1 zurück.

##  <a name="isascending"></a>  CMFCHeaderCtrl::IsAscending

Gibt an, ob eine Spalte in dem Kopfzeilen-Steuerelement in aufsteigender Reihenfolge sortiert wird.

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Kopfzeilen-Steuerelement eine beliebige andere Spalte in aufsteigender Reihenfolge sortiert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Wert, den Rückgabe dieser Methode wird verwendet, um den entsprechenden Sortierpfeil auf das Headerelement-Steuerelement anzuzeigen. Verwenden der [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) Methode, um die Sortierreihenfolge festzulegen.

##  <a name="isdialogcontrol"></a>  CMFCHeaderCtrl::IsDialogControl

Gibt an, ob das übergeordnete Fenster des die aktuelle Kopfzeilen-Steuerelement ein Dialogfeld ist.

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das übergeordnete Fenster des die aktuelle Kopfzeilen-Steuerelement ein Dialogfeld. andernfalls "false".

##  <a name="ismultiplesort"></a>  CMFCHeaderCtrl::IsMultipleSort

Gibt an, ob das aktuelle Kopfzeilen-Steuerelement in *Sortieren mehrerer Spalten* Modus.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn mehrere Spalten sortieren-Modus aktiviert ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Verwenden der [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) zu aktivieren oder Deaktivieren von mehreren Spalten sortieren-Modus. Zwei oder mehr Spalten können in einer Art teilnehmen, wenn es sich bei das Kopfzeilen-Steuerelement in mehreren Spalten sortieren-Modus befindet.

##  <a name="ondrawitem"></a>  CMFCHeaderCtrl::OnDrawItem

Wird aufgerufen, durch das Framework, um eine Spalte des Header-Steuerelement zu zeichnen.

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*iItem*<br/>
[in] Der nullbasierte Index des Elements, das gezeichnet werden soll.

*rect*<br/>
[in] Das umschließende Rechteck des Elements, das gezeichnet werden soll.

*bIsPressed*<br/>
[in] TRUE zum Zeichnen des Elements im gedrückten Zustand andernfalls "false".

*bIsHighlighted*<br/>
[in] "True" zum Zeichnen des Elements in der markierten Status; andernfalls "false".

##  <a name="ondrawsortarrow"></a>  CMFCHeaderCtrl::OnDrawSortArrow

Wird aufgerufen, durch das Framework zum Zeichnen des Pfeils sortieren.

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

*rectArrow*<br/>
[in] Das umschließende Rechteck des Pfeils sortieren.

##  <a name="onfillbackground"></a>  CMFCHeaderCtrl::OnFillBackground

Wird aufgerufen, durch das Framework, um den Hintergrund des Steuerelements Headerspalte zu füllen.

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Ein Zeiger auf einen Gerätekontext.

### <a name="remarks"></a>Hinweise

##  <a name="removesortcolumn"></a>  CMFCHeaderCtrl::RemoveSortColumn

Entfernt die angegebene Spalte aus der Liste der Sortierspalten.

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parameter

*iColumn*<br/>
[in] Der nullbasierte Index des zu entfernenden Spalte.

##  <a name="setsortcolumn"></a>  CMFCHeaderCtrl::SetSortColumn

Legt die Sortierreihenfolge einer angegebenen Spalte in einem Kopfzeilen-Steuerelement fest.

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>Parameter

*iColumn*<br/>
[in] Der nullbasierte Index, der eine Header-Steuerelement-Spalte. Wenn dieser Parameter ist kleiner als 0 (null), entfernt diese Methode alle Spalten aus der Liste der Sortierspalten.

*bAscending*<br/>
[in] Gibt die Sortierreihenfolge der Spalte, die die *der iColumn* angegeben wird. "True" festlegen, aufsteigend; "False" festlegen, absteigend. Der Standardwert ist "true".

*bAdd*<br/>
[in] True, wenn in der Sortierreihenfolge der Spalte festlegen, die *der iColumn* Parameter gibt an.

Ist das aktuelle Kopfzeilen-Steuerelement in *Sortieren mehrerer Spalten* Modus, diese Methode fügt die angegebene Spalte zur Liste der Sortierspalten. Verwendung [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) mehreren Spalten sortieren-Modus festgelegt.

Wenn mehrere Spalten sortieren-Modus nicht festgelegt ist, und diese Methode wird im Debugmodus kompiliert, bestätigt diese Methode. Wenn mehrere Spalten sortieren-Modus nicht festgelegt ist, und diese Methode wird im Einzelhandel Modus kompiliert, wird diese Methode entfernt zuerst alle Spalten aus der Liste der Sortierspalten, und klicken Sie dann fügt die angegebene Spalte der Liste hinzu.

"False", um erst entfernen Sie alle Spalten aus der Liste der Sortierspalten, und klicken Sie dann die angegebene Spalte zur Liste hinzufügen. Der Standardwert ist "false".

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um die Sortierreihenfolge einer Spalte festzulegen. Falls erforderlich, fügt diese Methode die Spalte der Liste der Sortierspalten. Das Kopfzeilen-Steuerelement verwendet die Sortierreihenfolge, um einen Sortierpfeil zu zeichnen, der nach oben oder unten zeigt.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)
