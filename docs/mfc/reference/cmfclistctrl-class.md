---
title: CMFCListCtrl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 495bf2a3eab9ceee4ca0bab337d590c1820905e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369621"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl-Klasse
Die `CMFCListCtrl` Klasse erweitert die Funktionalität der [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md) Klasse durch die Unterstützung der Funktion der erweiterten Zugriffskontrolle von der [CMFCHeaderCtrl-Klasse](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Bietet die Möglichkeit zum Markieren einer sortierten Spalteninhalts mit einer anderen Hintergrundfarbe.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Ermöglicht es mehreren Sortiermodus aus.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Gibt einen Verweis auf das unterstrichene Headersteuerelement zurück.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Überprüft, ob das Strukturelement-Steuerelement in mehrere Sortiermodus ist.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Vom Framework aufgerufen, wenn zwei Listenelemente Steuerelement verglichen werden muss.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Vom Framework aufgerufen, wenn die Farbe des Hintergrunds einer einzelnen Zelle nicht bestimmt werden muss.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Vom Framework aufgerufen, wenn sie die Schriftart für die Zelle gezeichnet werden abrufen muss.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Vom Framework aufgerufen, wenn die Textfarbe für eine einzelne Zelle bestimmt werden muss.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Entfernt eine Sortierspalte aus der Liste der sortierten Spalten.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Legt die aktuelle sortierte Spalte und die Sortierreihenfolge fest.|  
|[CMFCListCtrl::Sort](#sort)|Sortiert das Strukturelement-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 `CMFCListCtrl` bietet zwei Erweiterungen [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md) Klasse. Zuerst, bedeutet dies, dass es sich bei eine verfügbare Option erfolgt die spaltensortierung nach Zeichnen automatisch einen Sortierpfeil in der Kopfzeile. Zweitens wird gleichzeitig für mehrere Spalten beim Sortieren von Daten unterstützt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCListCtrl` Klasse. Das Beispiel zeigt, wie ein Listenfeld-Steuerelement erstellen, Einfügen von Spalten, Elemente eingefügt, Festlegen des Texts eines Elements, und legen Sie die Schriftart des Listensteuerelements. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
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
 Markiert die sortierten Spalten mit einer anderen Hintergrundfarbe.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMark`  
 Ein boolescher Parameter, der bestimmt, ob eine andere Hintergrundfarbe aktiviert.  
  
 [in] `bRedraw`  
 Ein boolescher Parameter, der bestimmt, ob das Steuerelement sofort neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 `EnableMarkSortedColumn` Mithilfe der Methode `CDrawingManager::PixelAlpha` so berechnen, welche Farbe mit einer sortierten Spalten. Die Farbe ausgewählt basiert darauf, dass die regulären Hintergrundfarbe.  
  
##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort  
 Aktiviert die Datenzeilen im Listensteuerelement nach mehreren Spalten sortieren.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Wert, der angibt, ob mehrere Spalte Sortiermodus aktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die Sortierung basierend auf mehrere Spalten aktivieren, müssen die Spalten eine Hierarchie. Die Datenzeilen werden zuerst durch die primäre Spalte sortiert werden. Alle entsprechenden Werte werden dann nach jeder nachfolgenden Spalte basierend auf Priorität sortiert.  
  
##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl  
 Gibt einen Verweis auf die Headersteuerelement zurück.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die zugrunde liegende [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Headersteuerelement für ein Listenfeld-Steuerelement ist das Fenster, das die Titel für die Spalten enthält. Es ist in der Regel direkt über die Spalten positioniert.  
  
##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort  
 Überprüft, ob das Strukturelement-Steuerelement unterstützt derzeit die Sortierung für mehrere Spalten.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Strukturelement-Steuerelement Sortieren mehrerer unterstützt; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine [CMFCListCtrl Klasse](../../mfc/reference/cmfclistctrl-class.md) unterstützt mehrere sortieren, die Benutzer kann die Daten in das Strukturelement-Steuerelement nach mehreren Spalten sortieren. Rufen Sie zum Aktivieren der Sortierung mehrerer [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems  
 Das Framework ruft diese Methode auf, wenn es sich um zwei Elemente vergleicht.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lParam1`  
 Das erste zu vergleichende Element.  
  
 [in] `lParam2`  
 Das zweite zu vergleichende Element.  
  
 [in] `iColumn`  
 Der Index der Spalte, die diese Methode sortiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die die relative Position der beiden Elemente angibt. Ein negativer Wert gibt an, dass das erste Element sollte die zweite vorausgehen, positiver Wert gibt an, dass das erste Element sollte die zweite folgen, und 0 (null) bedeutet, dass die beiden Elemente äquivalent sind.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung immer zurückgegeben 0. Sie müssen diese Funktion zum Bereitstellen eines Sortieralgorithmus überschreiben.  
  
##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor  
 Das Framework ruft diese Methode aus, wenn sie die Farbe des Hintergrunds einer einzelnen Zelle festlegen muss.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRow`  
 Die Zeile für die betreffende Zelle.  
  
 [in] `nColumn`  
 Die Spalte die betreffende Zelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COLOREF` Wert, der die Hintergrundfarbe der Zelle angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des `OnGetCellBkColor` verwendet nicht die angegebenen Eingabeparameter und ruft Sie stattdessen einfach `GetBkColor`. Aus diesem Grund wird das gesamte Strukturelement-Steuerelement wird standardmäßig dieselbe Hintergrundfarbe haben. Sie können außer Kraft setzen `OnGetCellBkColor` in einer abgeleiteten Klasse, um einzelne Zellen mit einer separaten Hintergrundfarbe zu markieren.  
  
##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont  
 Das Framework ruft diese Methode auf, wenn sie die Schriftart für eine einzelne Zelle abruft.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRow`  
 Die Zeile für die betreffende Zelle.  
  
 [in] `nColumn`  
 Die Spalte die betreffende Zelle.  
  
 [in] `dwData`  
 Benutzerdefinierte Daten. Die Standardimplementierung verwendet diesen Parameter nicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die Schriftart, die für die aktuelle Zelle verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode `NULL`. Alle Zellen in einem Listensteuerelement haben dieselbe Schriftart. Überschreiben Sie diese Methode, um unterschiedliche Schriftarten für verschiedene Zellen zu gewährleisten.  
  
##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor  
 Das Framework ruft diese Methode auf, wenn die Textfarbe für eine einzelne Zelle bestimmt werden muss.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRow`  
 Die Zeile für die betreffende Zelle.  
  
 [in] `nColumn`  
 Die Spalte die betreffende Zelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COLOREF` Wert, der die Textfarbe der Zelle angibt.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ruft diese Methode `GetTextColor` unabhängig von der Eingabeparameter. Das gesamte Strukturelement-Steuerelement hat die gleiche Textfarbe. Sie können außer Kraft setzen `OnGetCellTextColor` in einer abgeleiteten Klasse, um einzelne Zellen mit einer separaten Textfarbe zu markieren.  
  
##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn  
 Entfernt eine Sortierspalte aus der Liste der sortierten Spalten.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Die zu entfernende Spalte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Sortierspalte aus dem Headersteuerelement. Sie ruft [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn  
 Legt die aktuelle sortierte Spalte und die Sortierreihenfolge fest.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Die Spalte zu sortieren.  
  
 [in] `bAscending`  
 Ein boolescher Wert, der die Sortierreihenfolge angibt.  
  
 [in] `bAdd`  
 Ein boolescher Wert, der angibt, ob die Methode die Spalte erkennbar fügt `iColumn` zur Liste der Sortierspalten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode übergibt die Eingabeparameter an das Header-Steuerelement mithilfe der Methode [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="sort"></a>  CMFCListCtrl::Sort  
 Sortiert das Strukturelement-Steuerelement.  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Die Spalte zu sortieren.  
  
 [in] `bAscending`  
 Ein boolescher Wert, der die Sortierreihenfolge angibt.  
  
 [in] `bAdd`  
 Ein boolescher Wert, der angibt, ob diese Methode die Spalte erkennbar fügt `iColumn` zur Liste der Sortierspalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)
