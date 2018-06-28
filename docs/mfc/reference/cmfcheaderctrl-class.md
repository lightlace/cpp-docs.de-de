---
title: CMFCHeaderCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6af0859811ad4064c12f6e4ef8d470437fe3ded9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037660"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class
Die `CMFCHeaderCtrl` Klasse unterstützt Sortieren mehrerer Spalten in einem Headersteuerelement.  
  
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
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Aktiviert oder deaktiviert die *Sortieren mehrerer Spalten* Modus für das aktuelle Headersteuerelement.|  
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Gibt an, ob eine Spalte nicht sortiert ist, oder in aufsteigender oder absteigender Reihenfolge sortiert wird.|  
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Ruft den nullbasierten Index der ersten sortierte Spalte im Headersteuerelement ab.|  
|`CMFCHeaderCtrl::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCHeaderCtrl::IsAscending](#isascending)|Gibt an, ob jede Spalte im Headersteuerelement in aufsteigender Reihenfolge sortiert wird.|  
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Gibt an, ob das übergeordnete Fenster des aktuellen Headersteuerelements ein Dialogfeld ist.|  
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Gibt an, ob das aktuelle Headersteuerelement in *Sortieren mehrerer Spalten* Modus.|  
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Entfernt die angegebene Spalte aus der Liste der Sortierspalten.|  
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Legt die Sortierreihenfolge einer angegebenen Spalte in einem Headersteuerelement fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Wird aufgerufen, durch das Framework einen Header-Steuerelementspalte gezeichnet werden soll.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Wird aufgerufen, durch das Framework den Pfeil Sortierreihenfolge gezeichnet werden soll.|  
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Wird aufgerufen, durch das Framework zum Ausfüllen einer Spalte des Header-Steuerelement.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel veranschaulicht, wie ein Objekt vom Erstellen der `CMFCHeaderCtrl` -Klasse, und aktivieren *Sortieren mehrerer Spalten* Modus für das aktuelle Headersteuerelement.  
  
 [!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCHeaderCtrl` Klasse zeichnet einen Pfeil Sortierreihenfolge für eine Spalte des Header-Steuerelement, um anzugeben, dass die Spalte sortiert wird. Verwendung *Sortieren mehrerer Spalten* Modus, wenn eine Gruppe von Spalten in der übergeordneten Strukturelement-Steuerelement ( [CMFCListCtrl Klasse](../../mfc/reference/cmfclistctrl-class.md)) können zur selben Zeit sortiert werden.  
  
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
  
|Membervariablen|Wert|  
|---------------------|-----------|  
|`m_bIsMousePressed`|`FALSE`|  
|`m_bMultipleSort`|`FALSE`|  
|`m_bAscending`|`TRUE`|  
|`m_nHighlightedItem`|-1|  
|`m_bTracked`|`FALSE`|  
|`m_bIsDlgControl`|`FALSE`|  
|`m_hFont`|`NULL`|  
  
##  <a name="enablemultiplesort"></a>  CMFCHeaderCtrl::EnableMultipleSort  
 Aktiviert oder deaktiviert die *Sortieren mehrerer Spalten* Modus für das aktuelle Headersteuerelement.  
  
```  
void EnableMultipleSort(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 `TRUE` So aktivieren Sie mehrere Spalte Sortiermodus; `FALSE` Sortiermodus für mehrere Spalten zu deaktivieren und um alle Spalten aus der Liste der sortierten Spalten zu entfernen. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Aktivieren oder Deaktivieren von mehreren Spalte Sortiermodus. Eine Sortierung können zwei oder mehr Spalten teilnehmen, das Headersteuerelement ist in mehrere Spalte Sortiermodus.  
  
##  <a name="getcolumnstate"></a>  CMFCHeaderCtrl::GetColumnState  
 Gibt an, ob eine Spalte nicht sortiert ist, oder in aufsteigender oder absteigender Reihenfolge sortiert wird.  
  
```  
int GetColumnState(int iColumn) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *der iColumn*  
 Der nullbasierte Index der Spalte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der den Status der Sortierung der angegebenen Spalte anzugeben. In der folgenden Tabelle sind die möglichen Werte aufgeführt:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|-1|In absteigender Reihenfolge sortiert.|  
|0|Nicht sortiert.|  
|1|In aufsteigender Reihenfolge sortiert.|  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsortcolumn"></a>  CMFCHeaderCtrl::GetSortColumn  
 Ruft den nullbasierten Index der ersten sortierte Spalte im Headersteuerelement ab.  
  
```  
int GetSortColumn() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index einer sortierten Spalte oder-1 zurück, wenn keine sortierte Spalte gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Headersteuerelement ist in *Sortieren mehrerer Spalten* Modus, und Sie die Anwendung im Debugmodus befindet, kompiliert, diese Methode überprüft und informiert Sie verwenden die [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) Methode stattdessen. Wenn das Headersteuerelement in mehrere Spalte Sortiermodus ist und Sie die Anwendung im Einzelhandel Modus kompiliert wurde, gibt diese Methode-1 zurück.  
  
##  <a name="isascending"></a>  CMFCHeaderCtrl::IsAscending  
 Gibt an, ob jede Spalte im Headersteuerelement in aufsteigender Reihenfolge sortiert wird.  
  
```  
BOOL IsAscending() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn jede Spalte im Headersteuerelement in aufsteigender Reihenfolge sortiert sind; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert, den Rückgabe dieser Methode wird verwendet, den entsprechenden Sortierpfeil auf das Headerelement-Steuerelement angezeigt. Verwenden der [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) Methode, um die Sortierreihenfolge festzulegen.  
  
##  <a name="isdialogcontrol"></a>  CMFCHeaderCtrl::IsDialogControl  
 Gibt an, ob das übergeordnete Fenster des aktuellen Headersteuerelements ein Dialogfeld ist.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das übergeordnete Fenster des aktuellen Headersteuerelements ein Dialogfeld ist. andernfalls `FALSE`.  
  
##  <a name="ismultiplesort"></a>  CMFCHeaderCtrl::IsMultipleSort  
 Gibt an, ob das aktuelle Headersteuerelement in *Sortieren mehrerer Spalten* Modus.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn mehrere Spalte Sortiermodus aktiviert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) Methode zum Aktivieren oder Deaktivieren von mehreren Spalte Sortiermodus. Eine Sortierung können zwei oder mehr Spalten teilnehmen, das Headersteuerelement ist in mehrere Spalte Sortiermodus.  
  
##  <a name="ondrawitem"></a>  CMFCHeaderCtrl::OnDrawItem  
 Wird aufgerufen, durch das Framework einen Header-Steuerelementspalte gezeichnet werden soll.  
  
```  
virtual void OnDrawItem(
    CDC* pDC,  
    int iItem,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *iItem*  
 Der nullbasierte Index des Elements gezeichnet werden soll.  
  
 [in] *Rect*  
 Das umschließende Rechteck des Elements gezeichnet werden soll.  
  
 [in] *bIsPressed*  
 `TRUE` zum Zeichnen des Elements im Zustand "gedrückt"; andernfalls `FALSE`.  
  
 [in] *bIsHighlighted*  
 `TRUE` zum Zeichnen des Elements in der markierten Status; andernfalls `FALSE`.  
  
##  <a name="ondrawsortarrow"></a>  CMFCHeaderCtrl::OnDrawSortArrow  
 Wird aufgerufen, durch das Framework den Pfeil Sortierreihenfolge gezeichnet werden soll.  
  
```  
virtual void OnDrawSortArrow(
    CDC* pDC,  
    CRect rectArrow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] *RectArrow*  
 Das umschließende Rechteck des Pfeils sortieren.  
  
##  <a name="onfillbackground"></a>  CMFCHeaderCtrl::OnFillBackground  
 Wird aufgerufen, durch das Framework zum Ausfüllen einer Spalte des Header-Steuerelement.  
  
```  
virtual void OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removesortcolumn"></a>  CMFCHeaderCtrl::RemoveSortColumn  
 Entfernt die angegebene Spalte aus der Liste der Sortierspalten.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *der iColumn*  
 Der nullbasierte Index des zu entfernenden Spalte.  
  
##  <a name="setsortcolumn"></a>  CMFCHeaderCtrl::SetSortColumn  
 Legt die Sortierreihenfolge einer angegebenen Spalte in einem Headersteuerelement fest.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending=TRUE,  
    BOOL bAdd=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *der iColumn*  
 Der nullbasierte Index, der eine Spalte des Header-Steuerelement. Wenn dieser Parameter ist kleiner als 0 (null), entfernt diese Methode alle Spalten aus der Liste der Sortierspalten.  
  
 [in] *bAscending*  
 Gibt die Sortierreihenfolge der Spalte, die die *der iColumn* gibt Parameter an. `TRUE` festzulegende aufsteigend; `FALSE` absteigend festlegen. Der Standardwert ist `TRUE`.  
  
 [in] *hinzufügen*  
 `TRUE` zum Festlegen der Sortierreihenfolge der Spalte, die die *der iColumn* gibt Parameter an.  
  
 Ist die aktuelle Headersteuerelement *Sortieren mehrerer Spalten* Modus, diese Methode fügt die angegebene Spalte der Liste der Sortierspalten. Verwendung [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) Sortiermodus für mehrere Spalten festlegen.  
  
 Wenn mehrere Spalte sortieren-Modus nicht festgelegt ist, und diese Methode wird im Debugmodus kompiliert, überprüft diese Methode auf. Wenn mehrere Spalte sortieren-Modus nicht festgelegt ist, und diese Methode wird im Einzelhandel Modus kompiliert, wird diese Methode entfernt zuerst alle Spalten aus der Liste der Sortierspalten, und fügt dann der Liste die angegebene Spalte.  
  
 `FALSE` zuerst entfernen Sie alle Spalten aus der Liste der Sortierspalten, und klicken Sie dann fügen Sie die angegebene Spalte zur Liste hinzu. Der Standardwert ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Sortierreihenfolge einer Spalte festgelegt. Falls erforderlich, fügt diese Methode die Spalte zur Liste der Sortierspalten. Das Headersteuerelement verwendet die Sortierreihenfolge einen Pfeil Sortierreihenfolge gezeichnet werden soll, der nach oben oder unten zeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)
