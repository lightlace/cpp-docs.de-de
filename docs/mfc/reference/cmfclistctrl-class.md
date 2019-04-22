---
title: CMFCListCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
ms.openlocfilehash: 4cd1bb7787f8797984bdce5f9a5b3080d69ea5f2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767937"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl-Klasse

Die `CMFCListCtrl` Klasse erweitert die Funktionalität von [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md) -Klasse durch die Unterstützung der Funktionalität des erweiterten Headersteuerelements von der [CMFCHeaderCtrl-Klasse](../../mfc/reference/cmfcheaderctrl-class.md).

## <a name="syntax"></a>Syntax

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Können die Möglichkeit, eine sortierte Spalte mit einer anderen Hintergrundfarbe zu markieren.|
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Ermöglicht mehrere Sortiermodus.|
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Gibt einen Verweis auf das unterstrichene Kopfzeilen-Steuerelement zurück.|
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Überprüft, ob das Listensteuerelement in mehrere Sortiermodus ist.|
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Vom Framework aufgerufen, wenn zwei Listenelemente Steuerelement verglichen werden muss.|
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Vom Framework aufgerufen, wenn sie die Hintergrundfarbe einer einzelnen Zelle bestimmen muss.|
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Vom Framework aufgerufen, wenn Sie erhalten ihn bei der die Schriftart für die Zelle gezeichnet werden muss.|
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Vom Framework aufgerufen, wenn sie die Textfarbe für eine einzelne Zelle bestimmen muss.|
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Entfernt eine Sortierspalte aus der Liste der sortierten Spalten.|
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Legt fest, die aktuellen sortierte Spalte und ihre Sortierreihenfolge aufgeführt.|
|[CMFCListCtrl::Sort](#sort)|Sortiert das Strukturelement-Steuerelement.|

## <a name="remarks"></a>Hinweise

`CMFCListCtrl` bietet zwei Verbesserungen an [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md) Klasse. Zunächst bedeutet dies, dass es sich bei spaltensortierung eine verfügbare Option ist durch einen Sortierpfeil automatisch für den Header zu zeichnen. Zweitens wird für mehrere Spalten gleichzeitig Sortieren von Daten unterstützt.

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCListCtrl` -Klasse. Das Beispiel zeigt, wie Sie ein Listensteuerelement erstellen, Einfügen von Spalten, Elemente eingefügt, legen Sie den Text eines Elements und legen Sie die Schriftart des Steuerelements. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxlistctrl.h

##  <a name="enablemarksortedcolumn"></a>  CMFCListCtrl::EnableMarkSortedColumn

Markiert die sortierten Spalten mit einer anderen Hintergrundfarbe an.

```
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parameter

*bMark*<br/>
[in] Ein boolescher Parameter, der bestimmt, ob eine andere Hintergrundfarbe zu aktivieren.

*bRedraw*<br/>
[in] Ein boolescher Parameter, der bestimmt, ob das Steuerelement sofort neu zu zeichnen.

### <a name="remarks"></a>Hinweise

`EnableMarkSortedColumn` verwendet die Methode `CDrawingManager::PixelAlpha` berechnen, welche Farbe für die Verwendung sortierte Spalten. Die Farbe ausgewählt basiert auf die normale Hintergrundfarbe.

##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort

Aktiviert die Datenzeilen im Listensteuerelement nach mehreren Spalten sortieren.

```
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bEnable*<br/>
[in] Ein boolescher Wert, der angibt, ob mehrere Spalten sortieren-Modus aktiviert.

### <a name="remarks"></a>Hinweise

Wenn Sie die Sortierung basierend auf mehrere Spalten aktivieren, müssen die Spalten eine Hierarchie. Zunächst werden die Datenzeilen durch die primäre Spalte sortiert. Alle entsprechenden Werte werden dann nach jeder nachfolgenden Spalte basierend auf Priorität sortiert.

##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl

Gibt einen Verweis auf das Kopfzeilen-Steuerelement zurück.

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf die zugrunde liegende [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Das Kopfzeilen-Steuerelement für ein Listensteuerelement ist das Fenster, das die Titel für die Spalten enthält. Es ist in der Regel direkt über die Spalten positioniert.

##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort

Überprüft, ob das Listensteuerelement unterstützt derzeit die Sortierung für mehrere Spalten.

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Strukturelement-Steuerelement mehrere Sortierung unterstützt. "False" andernfalls.

### <a name="remarks"></a>Hinweise

Wenn eine [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md) unterstützt mehrere sortieren, der Benutzer kann die Daten im Listensteuerelement nach mehreren Spalten sortieren. Rufen Sie zum Aktivieren der Sortierung von mehreren [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).

##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems

Das Framework ruft diese Methode auf, wenn es sich um zwei Elemente vergleicht.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Parameter

*lParam1*<br/>
[in] Die erste zu vergleichende Element.

*lParam2*<br/>
[in] Die zweite zu vergleichende Element.

*iColumn*<br/>
[in] Der Index der Spalte, die diese Methode sortiert wird.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die die relative Position der beiden Elemente angibt. Ein negativer Wert gibt an, dass das erste Element sollte die zweite vorangehen, positiver Wert gibt an, dass das erste Element sollte die zweite folgen, und 0 (null) bedeutet, dass die beiden Elemente äquivalent sind.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung gibt immer 0. Sie müssen diese Funktion, um einen Sortieralgorithmus bieten überschreiben.

##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor

Das Framework ruft diese Methode auf, wenn sie die Hintergrundfarbe einer einzelnen Zelle bestimmen muss.

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Parameter

*nRow*<br/>
[in] Die Zeile der fragliche Zelle.

*nColumn*<br/>
[in] Die Spalte die betreffende Zelle.

### <a name="return-value"></a>Rückgabewert

Ein COLOREF-Wert, der die Hintergrundfarbe der Zelle angibt.

### <a name="remarks"></a>Hinweise

Die standardmäßige Implementierung des `OnGetCellBkColor` verwendet nicht die angegebenen Parametern für die Eingabe und ruft Sie stattdessen einfach `GetBkColor`. Aus diesem Grund wird das gesamte Strukturelement-Steuerelement in der Standardeinstellung die gleiche Hintergrundfarbe haben. Sie können außer Kraft setzen `OnGetCellBkColor` in einer abgeleiteten Klasse, um einzelne Zellen mit einer separaten Hintergrundfarbe zu markieren.

##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont

Das Framework ruft diese Methode auf, wenn sie die Schriftart für eine einzelne Zelle abruft.

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>Parameter

*nRow*<br/>
[in] Die Zeile der fragliche Zelle.

*nColumn*<br/>
[in] Die Spalte die betreffende Zelle.

*dwData*<br/>
[in] Mit benutzerdefinierten Daten. Die Standardimplementierung wird dieser Parameter nicht verwendet werden.

### <a name="return-value"></a>Rückgabewert

Ein Handle für die Schriftart, die für die aktuelle Zelle verwendet wird.

### <a name="remarks"></a>Hinweise

Standardmäßig gibt diese Methode NULL zurück. Alle Zellen in einem Steuerelement haben dieselbe Schriftart. Überschreiben Sie diese Methode, um verschiedenen Zellen unterschiedliche Schriftarten bereit.

##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor

Das Framework ruft diese Methode auf, wenn sie die Textfarbe für eine einzelne Zelle bestimmen muss.

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>Parameter

*nRow*<br/>
[in] Die Zeile der fragliche Zelle.

*nColumn*<br/>
[in] Die Spalte die betreffende Zelle.

### <a name="return-value"></a>Rückgabewert

Ein COLOREF-Wert, der die Textfarbe der Zelle angibt.

### <a name="remarks"></a>Hinweise

Diese Methode ruft standardmäßig `GetTextColor` unabhängig von der Eingabeparameter. Das Steuerelement für die gesamte Liste müssen die gleiche Farbe des Texts. Sie können außer Kraft setzen `OnGetCellTextColor` in einer abgeleiteten Klasse, um einzelne Zellen mit einer separaten Textfarbe zu markieren.

##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn

Entfernt eine Sortierspalte aus der Liste der sortierten Spalten.

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>Parameter

*iColumn*<br/>
[in] Der zu entfernenden Spalte.

### <a name="remarks"></a>Hinweise

Diese Methode entfernt eine Sortierspalte aus dem Kopfzeilen-Steuerelement. Ruft [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).

##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn

Legt fest, die aktuellen sortierte Spalte und ihre Sortierreihenfolge aufgeführt.

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Parameter

*iColumn*<br/>
[in] Die zu sortierende Spalte.

*bAscending*<br/>
[in] Ein boolescher Wert, der die Sortierreihenfolge angibt.

*bAdd*<br/>
[in] Ein boolescher Wert, der angibt, ob die Methode durch angegebene Spalte hinzufügt *der iColumn* zur Liste der Sortierspalten.

### <a name="remarks"></a>Hinweise

Diese Methode übergibt die Eingabeparameter an das Kopfzeilen-Steuerelement, mit der Methode [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).

##  <a name="sort"></a>  CMFCListCtrl::Sort

Sortiert das Strukturelement-Steuerelement.

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>Parameter

*iColumn*<br/>
[in] Die zu sortierende Spalte.

*bAscending*<br/>
[in] Ein boolescher Wert, der die Sortierreihenfolge angibt.

*bAdd*<br/>
[in] Ein boolescher Wert, der angibt, ob diese Methode fügt hinzu, die durch angegebene Spalte *der iColumn* zur Liste der Sortierspalten.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)
