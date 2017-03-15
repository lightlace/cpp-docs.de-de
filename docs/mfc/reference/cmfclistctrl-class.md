---
title: Klasse CMFCListCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCListCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCListCtrl class
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a4c67b2d7ea2a5356f7c053403edf414319a928
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl-Klasse
Die `CMFCListCtrl` Klasse erweitert die Funktionalität von [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md) Klasse durch die Unterstützung der Funktionalität des erweiterten Headersteuerelements von der [CMFCHeaderCtrl Klasse](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|Ermöglicht die Sortierung eine Spalte mit einer anderen Hintergrundfarbe zu kennzeichnen.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|Ermöglicht mehrere Sortiermodus.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|Gibt einen Verweis auf das unterstrichene Kopfzeilen-Steuerelement zurück.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|Überprüft, ob das Listensteuerelement in mehrere Sortiermodus ist.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|Wird vom Framework aufgerufen, wenn sie zwei Listenelemente Steuerelement verglichen werden muss.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|Wird vom Framework aufgerufen, wenn die Hintergrundfarbe einer einzelnen Zelle ermittelt werden muss.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|Wird vom Framework aufgerufen, wenn es erhalten, die Schriftart für die Zelle gezeichnet werden.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|Wird vom Framework aufgerufen, wenn die Textfarbe für eine einzelne Zelle ermittelt werden muss.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|Entfernt eine Sortierspalte aus der Liste der sortierten Spalten.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|Legt die aktuelle sortierte Spalte und die Sortierreihenfolge fest.|  
|[CMFCListCtrl::Sort](#sort)|Sortiert die Listensteuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 `CMFCListCtrl`bietet zwei Verbesserungen zu [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md) Klasse. Erstens bedeutet dies, dass Sortierung eine verfügbare Option durch Zeichnen automatisch einen Sortierpfeil in der Kopfzeile. Zweitens unterstützt für mehrere Spalten gleichzeitig Sortieren von Daten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCListCtrl` Klasse. Das Beispiel zeigt, wie Sie ein Listenfeld-Steuerelement zu erstellen, fügen Sie Spalten, Elemente eingefügt, legen Sie den Text eines Elements und legen Sie die Schriftart des Steuerelements. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#25;](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#26;](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxlistctrl.h  
  
##  <a name="a-nameenablemarksortedcolumna--cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>CMFCListCtrl::EnableMarkSortedColumn  
 Markiert die sortierten Spalten mit einer anderen Hintergrundfarbe an.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMark`  
 Ein boolescher Parameter, der bestimmt, ob eine andere Hintergrundfarbe zu aktivieren.  
  
 [in] `bRedraw`  
 Ein boolescher Parameter, der bestimmt, ob das Steuerelement sofort neu gezeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 `EnableMarkSortedColumn`verwendet die Methode `CDrawingManager::PixelAlpha` so berechnen, welche Farbe mit einer sortierten Spalten. Die Farbe ausgewählt, basiert auf der regulären Hintergrundfarbe.  
  
##  <a name="a-nameenablemultiplesorta--cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>CMFCListCtrl::EnableMultipleSort  
 Aktiviert die Datenzeilen im Listensteuerelement nach mehreren Spalten sortieren.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Wert, der angibt, ob mehrere Spalte sortieren-Modus zu aktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Beim Sortieren mehrerer Spalten aktivieren, müssen die Spalten eine Hierarchie. Die Datenzeilen werden zunächst durch die primäre Spalte sortiert werden. Alle entsprechenden Werte werden dann nach jeder nachfolgenden Spalte auf Grundlage der Priorität sortiert.  
  
##  <a name="a-namegetheaderctrla--cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCListCtrl::GetHeaderCtrl  
 Gibt einen Verweis auf das Kopfzeilen-Steuerelement zurück.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die zugrunde liegende [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Header-Steuerelement für ein Listenfeld-Steuerelement ist das Fenster, das den Titel für die Spalten enthält. Es befindet sich in der Regel direkt oberhalb der Spalten.  
  
##  <a name="a-nameismultiplesorta--cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort  
 Überprüft, ob das Listensteuerelement unterstützt derzeit die Sortierung für mehrere Spalten.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Listensteuerelement Sortieren mehrerer unterstützt. `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein [CMFCListCtrl Klasse](../../mfc/reference/cmfclistctrl-class.md) unterstützt mehrere sortieren, die Benutzer kann die Daten im Steuerelement nach mehreren Spalten sortieren. Rufen Sie zum Aktivieren der Sortierung mehrerer [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort).  
  
##  <a name="a-nameoncompareitemsa--cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems  
 Das Framework ruft diese Methode auf, wenn zwei Elemente verglichen.  
  
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
 Eine ganze Zahl, die die relative Position der beiden Elemente angibt. Ein negativer Wert zeigt an, dass das erste Element sollte die zweite vorangehen positiver Wert gibt an, dass das erste Element sollte die zweite folgen, und&0; (null) bedeutet, dass die beiden Elemente äquivalent sind.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gibt immer 0. Sie müssen diese Funktion, um einen Sortieralgorithmus bieten überschreiben.  
  
##  <a name="a-nameongetcellbkcolora--cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor  
 Das Framework ruft diese Methode auf, wenn die Hintergrundfarbe einer einzelnen Zelle ermittelt werden muss.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRow`  
 Die Zeile für die betreffende Zelle.  
  
 [in] `nColumn`  
 Die Spalte die fragliche Zelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COLOREF` Wert, der die Hintergrundfarbe der Zelle angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung des `OnGetCellBkColor` nicht die bereitgestellten Parameter und ruft Sie stattdessen einfach `GetBkColor`. Standardmäßig wird das gesamte Listensteuerelement daher dieselbe Hintergrundfarbe haben. Sie können außer Kraft setzen `OnGetCellBkColor` in einer abgeleiteten Klasse, um einzelne Zellen mit einer separaten Hintergrundfarbe zu markieren.  
  
##  <a name="a-nameongetcellfonta--cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>CMFCListCtrl::OnGetCellFont  
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
 Die Spalte die fragliche Zelle.  
  
 [in] `dwData`  
 Benutzerdefinierte Daten. Die standardmäßige Implementierung wird dieser Parameter nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die Schriftart, die für die aktuelle Zelle verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode `NULL`. Alle Zellen in einem Listensteuerelement haben dieselbe Schriftart. Überschreiben Sie diese Methode, um verschiedene Schriftarten für unterschiedliche Zellen bereitzustellen.  
  
##  <a name="a-nameongetcelltextcolora--cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor  
 Das Framework ruft diese Methode auf, wenn die Textfarbe für eine einzelne Zelle ermittelt werden muss.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nRow`  
 Die Zeile für die betreffende Zelle.  
  
 [in] `nColumn`  
 Die Spalte die fragliche Zelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COLOREF` Wert, der die Textfarbe der Zelle angibt.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ruft diese Methode `GetTextColor` unabhängig von der Eingabeparameter. Das Steuerelement für die gesamte Liste müssen derselben Textfarbe. Sie können außer Kraft setzen `OnGetCellTextColor` in einer abgeleiteten Klasse, um einzelne Zellen mit einer eigenen Farbe zu kennzeichnen.  
  
##  <a name="a-nameremovesortcolumna--cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn  
 Entfernt eine Sortierspalte aus der Liste der sortierten Spalten.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Die zu entfernende Spalte.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode entfernt eine Sortierspalte aus dem Kopfzeilen-Steuerelement. Sie ruft [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn).  
  
##  <a name="a-namesetsortcolumna--cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>CMFCListCtrl::SetSortColumn  
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
 Ein boolescher Wert, der angibt, ob die Methode die durch angegebene Spalte fügt `iColumn` zur Liste der Sortierspalten.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode übergibt die Eingabeparameter an das Kopfzeilen-Steuerelement mithilfe der Methode [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn).  
  
##  <a name="a-namesorta--cmfclistctrlsort"></a><a name="sort"></a>CMFCListCtrl::Sort  
 Sortiert die Listensteuerelement.  
  
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
 Ein boolescher Wert, der angibt, ob diese Methode die durch angegebene Spalte fügt `iColumn` zur Liste der Sortierspalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)

