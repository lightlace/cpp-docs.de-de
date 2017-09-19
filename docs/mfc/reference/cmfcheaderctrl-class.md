---
title: Klasse CMFCHeaderCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCHeaderCtrl class
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c49ee61b6441e79a0c3c4c1aa133b4bce1578103
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class
Die `CMFCHeaderCtrl` Klasse unterstützt Sortieren mehrerer Spalten in einem Header-Steuerelement.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](#cmfcheaderctrl)|Erstellt ein `CMFCHeaderCtrl`-Objekt.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)|Aktiviert oder deaktiviert die *Sortieren mehrerer Spalten* Modus für das aktuelle Kopfzeilen-Steuerelement.|  
|[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)|Gibt an, ob eine Spalte ist nicht sortiert in aufsteigender oder absteigender Reihenfolge sortiert wird.|  
|[CMFCHeaderCtrl::GetSortColumn](#getsortcolumn)|Ruft den nullbasierten Index der ersten sortierte Spalte im Kopfzeilen-Steuerelement ab.|  
|`CMFCHeaderCtrl::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCHeaderCtrl::IsAscending](#isascending)|Gibt an, ob eine Spalte in dem Kopfzeilen-Steuerelement in aufsteigender Reihenfolge sortiert wird.|  
|[CMFCHeaderCtrl::IsDialogControl](#isdialogcontrol)|Gibt an, ob das übergeordnete Fenster des aktuellen Headersteuerelements ein Dialogfeld.|  
|[CMFCHeaderCtrl::IsMultipleSort](#ismultiplesort)|Gibt an, ob das aktuelle Kopfzeilen-Steuerelement in *Sortieren mehrerer Spalten* Modus.|  
|[CMFCHeaderCtrl::RemoveSortColumn](#removesortcolumn)|Entfernt die angegebene Spalte aus der Liste der Sortierspalten.|  
|[CMFCHeaderCtrl::SetSortColumn](#setsortcolumn)|Legt die Sortierreihenfolge einer angegebenen Spalte in einem Header-Steuerelement fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCHeaderCtrl::OnDrawItem](#ondrawitem)|Aufgerufen, um Kopfzeilen-Steuerelement für Spalten zu zeichnen.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](#ondrawsortarrow)|Vom Framework aufgerufen wird zum Zeichnen des Pfeils sortieren.|  
|[CMFCHeaderCtrl::OnFillBackground](#onfillbackground)|Vom Framework zum Ausfüllen der Spalte eine Header-Steuerelement aufgerufen.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCHeaderCtrl` -Klasse, und aktivieren *Sortieren mehrerer Spalten* Modus für das aktuelle Kopfzeilen-Steuerelement.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#24;](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCHeaderCtrl` Klasse zeichnet einen Pfeil Sortierreihenfolge für eine Spalte des Header-Steuerelement an, dass die Spalte sortiert wird. Verwendung *Sortieren mehrerer Spalten* Modus, wenn eine Gruppe von Spalten im übergeordneten Steuerelement ( [CMFCListCtrl Klasse](../../mfc/reference/cmfclistctrl-class.md)) zur gleichen Zeit sortiert werden können.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxheaderctrl.h  
  
##  <a name="cmfcheaderctrl"></a>CMFCHeaderCtrl::CMFCHeaderCtrl  
 Erstellt ein `CMFCHeaderCtrl`-Objekt.  
  
```  
CMFCHeaderCtrl::CMFCHeaderCtrl()  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Konstruktor initialisiert die folgenden Membervariablen auf die angegebenen Werte:  
  
|Membervariable|Wert|  
|---------------------|-----------|  
|`m_bIsMousePressed`|`FALSE`|  
|`m_bMultipleSort`|`FALSE`|  
|`m_bAscending`|`TRUE`|  
|`m_nHighlightedItem`|-1|  
|`m_bTracked`|`FALSE`|  
|`m_bIsDlgControl`|`FALSE`|  
|`m_hFont`|`NULL`|  
  
##  <a name="enablemultiplesort"></a>CMFCHeaderCtrl::EnableMultipleSort  
 Aktiviert oder deaktiviert die *Sortieren mehrerer Spalten* Modus für das aktuelle Kopfzeilen-Steuerelement.  
  
```  
void EnableMultipleSort(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Um mehrere Spalte sortieren-Modus zu aktivieren; `FALSE` um mehrere Spalte Sortiermodus deaktivieren und entfernen Sie alle Spalten aus der Liste der sortierten Spalten. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Aktivieren oder deaktivieren mehrere Sortiermodus der Spalte. Zwei oder mehr Spalten können eine Sortierung teilnehmen, ist das Kopfzeilen-Steuerelement im Modus für mehrere Spalten sortieren.  
  
##  <a name="getcolumnstate"></a>CMFCHeaderCtrl::GetColumnState  
 Gibt an, ob eine Spalte ist nicht sortiert in aufsteigender oder absteigender Reihenfolge sortiert wird.  
  
```  
int GetColumnState(int iColumn) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Der nullbasierte Index der Spalte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der der Sort-Status der angegebenen Spalte an. In der folgenden Tabelle sind die möglichen Werte aufgeführt:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|-1|In absteigender Reihenfolge sortiert.|  
|0|Nicht sortiert.|  
|1|In aufsteigender Reihenfolge sortiert.|  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsortcolumn"></a>CMFCHeaderCtrl::GetSortColumn  
 Ruft den nullbasierten Index der ersten sortierte Spalte im Kopfzeilen-Steuerelement ab.  
  
```  
int GetSortColumn() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Sortierung einer Spalte oder -1, wenn keine sortierte Spalte gefunden wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Header-Steuerelement ist im *Sortieren mehrerer Spalten* Modus, und Sie die Anwendung im Debugmodus kompiliert, diese Methode bestätigt und empfiehlt Ihnen die Verwendung der [CMFCHeaderCtrl::GetColumnState](#getcolumnstate) Methode stattdessen. Wenn das Kopfzeilen-Steuerelement im Modus für mehrere Spalten sortieren ist, und Sie die Anwendung im Retail-Modus kompiliert, gibt diese Methode-1 zurück.  
  
##  <a name="isascending"></a>CMFCHeaderCtrl::IsAscending  
 Gibt an, ob eine Spalte in dem Kopfzeilen-Steuerelement in aufsteigender Reihenfolge sortiert wird.  
  
```  
BOOL IsAscending() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine Spalte in dem Kopfzeilen-Steuerelement in aufsteigender Reihenfolge sortiert sind; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert, den diese Methode gibt wird verwendet, um die entsprechende Sortierung Pfeil auf die Header-Steuerelement ein Element anzuzeigen. Verwenden der [CMFCHeaderCtrl::SetSortColumn](#setsortcolumn) Methode, um die Sortierreihenfolge festzulegen.  
  
##  <a name="isdialogcontrol"></a>CMFCHeaderCtrl::IsDialogControl  
 Gibt an, ob das übergeordnete Fenster des aktuellen Headersteuerelements ein Dialogfeld.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das übergeordnete Fenster des aktuellen Headersteuerelement ein Dialogfeld ist. andernfalls `FALSE`.  
  
##  <a name="ismultiplesort"></a>CMFCHeaderCtrl::IsMultipleSort  
 Gibt an, ob das aktuelle Kopfzeilen-Steuerelement in *Sortieren mehrerer Spalten* Modus.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn mehrere Spalten sortiert ist Modus aktiviert. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) Methode aktivieren oder Deaktivieren des Modus für mehrere Spalten sortieren. Zwei oder mehr Spalten können eine Sortierung teilnehmen, ist das Kopfzeilen-Steuerelement im Modus für mehrere Spalten sortieren.  
  
##  <a name="ondrawitem"></a>CMFCHeaderCtrl::OnDrawItem  
 Aufgerufen, um Kopfzeilen-Steuerelement für Spalten zu zeichnen.  
  
```  
virtual void OnDrawItem(
    CDC* pDC,  
    int iItem,  
    CRect rect,  
    BOOL bIsPressed,  
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `iItem`  
 Der nullbasierte Index des Elements, das gezeichnet werden soll.  
  
 [in] `rect`  
 Das umschließende Rechteck des Elements, das gezeichnet werden soll.  
  
 [in] `bIsPressed`  
 `TRUE`zum Zeichnen des Elements im gedrückten Zustand befindet; andernfalls `FALSE`.  
  
 [in] `bIsHighlighted`  
 `TRUE`zum Zeichnen des Elements im markierten Status; andernfalls `FALSE`.  
  
##  <a name="ondrawsortarrow"></a>CMFCHeaderCtrl::OnDrawSortArrow  
 Vom Framework aufgerufen wird zum Zeichnen des Pfeils sortieren.  
  
```  
virtual void OnDrawSortArrow(
    CDC* pDC,  
    CRect rectArrow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectArrow`  
 Das umschließende Rechteck des Pfeils sortieren.  
  
##  <a name="onfillbackground"></a>CMFCHeaderCtrl::OnFillBackground  
 Vom Framework zum Ausfüllen der Spalte eine Header-Steuerelement aufgerufen.  
  
```  
virtual void OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="removesortcolumn"></a>CMFCHeaderCtrl::RemoveSortColumn  
 Entfernt die angegebene Spalte aus der Liste der Sortierspalten.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Der nullbasierte Index des zu entfernenden Spalte.  
  
##  <a name="setsortcolumn"></a>CMFCHeaderCtrl::SetSortColumn  
 Legt die Sortierreihenfolge einer angegebenen Spalte in einem Header-Steuerelement fest.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending=TRUE,  
    BOOL bAdd=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iColumn`  
 Der nullbasierte Index der Spalte eine Header-Steuerelement. Wenn dieser Parameter ist kleiner als&0; (null), entfernt diese Methode alle Spalten aus der Liste der Sortierspalten.  
  
 [in] `bAscending`  
 Gibt die Sortierreihenfolge der Spalte, die die `iColumn` angibt. `TRUE`Festlegen der aufsteigend; `FALSE` absteigend festlegen. Der Standardwert ist `TRUE`.  
  
 [in] `bAdd`  
 `TRUE`zum Festlegen der Sortierreihenfolge der Spalte, die die `iColumn` Parameter gibt.  
  
 Das aktuelle Kopfzeilen-Steuerelement ist im *Sortieren mehrerer Spalten* Modus, diese Methode fügt die angegebene Spalte der Liste der Sortierspalten. Verwendung [CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort) mehrere Spalte Sortiermodus festgelegt.  
  
 Wenn mehrere Spalte sortieren-Modus nicht festgelegt ist und diese Methode im Debugmodus kompiliert wurde, überprüft diese Methode auf. Wenn mehrere Spalte sortieren-Modus nicht festgelegt ist und diese Methode in Retail-Modus kompiliert wird, gibt diese Methode entfernt zuerst alle Spalten aus der Liste der Sortierspalten und dann die Liste die angegebene Spalte hinzugefügt.  
  
 `FALSE`zuerst entfernen Sie alle Spalten aus der Liste der Sortierspalten, und klicken Sie dann fügen Sie die angegebene Spalte zur Liste hinzu. Der Standardwert ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Sortierreihenfolge einer Spalte festzulegen. Falls erforderlich, fügt diese Methode die Spalte zur Liste der Sortierspalten. Das Kopfzeilen-Steuerelement verwendet die Sortierreihenfolge, um einen Sortierpfeil zu zeichnen, der nach oben oder unten zeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)

