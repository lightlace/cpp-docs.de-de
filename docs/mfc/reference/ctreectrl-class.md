---
title: CTreeCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeCtrl class
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
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
ms.openlocfilehash: 5341367b44540e2d0991fd61e52611826bbdcda1
ms.lasthandoff: 02/24/2017

---
# <a name="ctreectrl-class"></a>CTreeCtrl Class
Stellt die Funktionalität des allgemeinen Windows-Strukturansicht-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTreeCtrl::CTreeCtrl](#ctreectrl)|Erstellt ein `CTreeCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTreeCtrl::Create](#create)|Erstellt ein Strukturansicht-Steuerelement und fügt es ein `CTreeCtrl` Objekt.|  
|[CTreeCtrl::CreateDragImage](#createdragimage)|Erstellt eine Drag & Drop-Bitmap für das Element der angegebenen Struktur anzeigen.|  
|[CTreeCtrl::CreateEx](#createex)|Erstellt ein Strukturansicht-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CTreeCtrl` Objekt.|  
|[CTreeCtrl::DeleteAllItems](#deleteallitems)|Löscht alle Elemente in einem Strukturansicht-Steuerelement.|  
|[CTreeCtrl::DeleteItem](#deleteitem)|Löscht ein neues Element in einem Strukturansicht-Steuerelement.|  
|[CTreeCtrl::EditLabel](#editlabel)|Eine angegebene Struktur Ansicht Element direkt bearbeitet wird.|  
|[CTreeCtrl::EndEditLabelNow](#endeditlabelnow)|Bricht den Bearbeitungsvorgang an die Bezeichnung eines Strukturansicht Elements im aktuellen Strukturansicht Steuerelement ab.|  
|[CTreeCtrl::EnsureVisible](#ensurevisible)|Gewährleistet, dass ein Strukturansichtselement in der Strukturansicht-Steuerelement angezeigt wird.|  
|[CTreeCtrl::Expand](#expand)|Erweitert oder reduziert, die untergeordneten Elemente des angegebenen Strukturelements anzeigen.|  
|[CTreeCtrl::GetBkColor](#getbkcolor)|Ruft die aktuelle Hintergrundfarbe des Steuerelements ab.|  
|[CTreeCtrl::GetCheck](#getcheck)|Ruft den Aktivierungszustand eines Elements Strukturansicht-Steuerelement ab.|  
|[CTreeCtrl::GetChildItem](#getchilditem)|Ruft das untergeordnete Element des angegebenen Struktur das Element anzeigen.|  
|[CTreeCtrl::GetCount](#getcount)|Ruft die Anzahl der Elemente der Konsolenstruktur ein Strukturansicht-Steuerelement zugeordnet.|  
|[CTreeCtrl::GetDropHilightItem](#getdrophilightitem)|Ruft das Ziel eines Drag & Drop-Vorgangs ab.|  
|[CTreeCtrl::GetEditControl](#geteditcontrol)|Ruft das Handle des Bearbeitungssteuerelements verwendet, um die angegebene Ansicht Strukturelement bearbeiten.|  
|[CTreeCtrl::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die das aktuelle Strukturansicht Steuerelement verwendet wird.|  
|[CTreeCtrl::GetFirstVisibleItem](#getfirstvisibleitem)|Ruft das erste sichtbare Element der angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetImageList](#getimagelist)|Ruft das Handle der einem Strukturansicht-Steuerelement zugeordnete Bildliste ab.|  
|[CTreeCtrl::GetIndent](#getindent)|Ruft den Offset (in Pixel) der Struktur das Element anzeigen aus seinem übergeordneten Element ab.|  
|[CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)|Ruft die Farbe für die Einfügemarke für die Strukturansicht gezeichnet werden soll.|  
|[CTreeCtrl::GetItem](#getitem)|Ruft die Attribute eines Elements der angegebenen Struktur Ansicht ab.|  
|[CTreeCtrl::GetItemData](#getitemdata)|Gibt den 32-Bit-anwendungsspezifische Wert eines Elements.|  
|[CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex)|Ruft den Index des Bilds angezeigt, wenn das angegebene Element des aktuellen Strukturansicht Steuerelements im erweiterten Zustand befindet.|  
|[CTreeCtrl::GetItemHeight](#getitemheight)|Ruft die aktuelle Höhe der Struktur Ansichtselemente ab.|  
|[CTreeCtrl::GetItemImage](#getitemimage)|Ruft die Bilder, die einem Element zugeordnet.|  
|[CTreeCtrl::GetItemPartRect](#getitempartrect)|Ruft das umschließende Rechteck für den angegebenen Teil eines bestimmten Elements in der aktuellen Strukturansicht Steuerelement ab.|  
|[CTreeCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck der Struktur das Element anzeigen.|  
|[CTreeCtrl::GetItemState](#getitemstate)|Gibt den Status eines Elements zurück.|  
|[CTreeCtrl::GetItemStateEx](#getitemstateex)|Ruft den erweiterten Zustand des angegebenen Elements im aktuellen Strukturansicht Steuerelement.|  
|[CTreeCtrl::GetItemText](#getitemtext)|Gibt den Text eines Elements zurück.|  
|[CTreeCtrl::GetLastVisibleItem](#getlastvisibleitem)|Ruft den letzten erweiterten Element im aktuellen Strukturansicht Steuerelement ab.|  
|[CTreeCtrl::GetLineColor](#getlinecolor)|Ruft die aktuelle Farbe für das Strukturansicht-Steuerelement ab.|  
|[CTreeCtrl::GetNextItem](#getnextitem)|Ruft das nächste Element des Typs Struktur anzeigen, das eine bestimmte Beziehung entspricht.|  
|[CTreeCtrl::GetNextSiblingItem](#getnextsiblingitem)|Ruft das nächste gleichgeordnete Element des angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetNextVisibleItem](#getnextvisibleitem)|Ruft das nächste sichtbare Element der angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetParentItem](#getparentitem)|Ruft das übergeordnete Element des angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetPrevSiblingItem](#getprevsiblingitem)|Ruft das vorherige gleichgeordnete Element des angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetPrevVisibleItem](#getprevvisibleitem)|Ruft das vorherige sichtbare Element der angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetRootItem](#getrootitem)|Ruft den Stamm des angegebenen Ansicht Strukturelements ab.|  
|[CTreeCtrl::GetScrollTime](#getscrolltime)|Ruft die maximale Scroll-Zeit für das Strukturansicht-Steuerelement ab.|  
|[CTreeCtrl::GetSelectedCount](#getselectedcount)|Ruft die Anzahl der ausgewählten Elemente im aktuellen Strukturansicht Steuerelement ab.|  
|[CTreeCtrl::GetSelectedItem](#getselecteditem)|Ruft die Strukturansicht derzeit ausgewählten Elements ab.|  
|[CTreeCtrl::GetTextColor](#gettextcolor)|Ruft die aktuelle Textfarbe des Steuerelements ab.|  
|[CTreeCtrl::GetToolTips](#gettooltips)|Ruft das Handle für das untergeordnete Element von einem Strukturansicht-Steuerelement verwendeten ToolTip-Steuerelement ab.|  
|[CTreeCtrl::GetVisibleCount](#getvisiblecount)|Ruft die Anzahl der sichtbaren Strukturelemente einem Strukturansicht-Steuerelement ab.|  
|[CTreeCtrl::HitTest](#hittest)|Gibt die aktuelle Position des Cursors im Zusammenhang mit der `CTreeCtrl` Objekt.|  
|[CTreeCtrl::InsertItem](#insertitem)|Fügt ein neues Element in einem Strukturansicht-Steuerelement.|  
|[CTreeCtrl::ItemHasChildren](#itemhaschildren)|Gibt einen Wert ungleich NULL, wenn das angegebene Element über untergeordnete Elemente verfügt.|  
|[CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)|Ordnet den angegebenen Eingabehilfen-Bezeichner auf das Handle für ein Strukturansicht Element in der aktuellen Strukturansicht Steuerelement.|  
|[CTreeCtrl::MapItemToAccID](#mapitemtoaccid)|Ordnet das angegebene Handle für ein Strukturansicht Element im aktuellen Strukturansicht Steuerelement auf einen Bezeichner für Eingabehilfen.|  
|[CTreeCtrl::Select](#select)|Wählt, Bildlauf sichtbar oder aktualisiert ein Element der angegebenen Struktur anzeigen.|  
|[CTreeCtrl::SelectDropTarget](#selectdroptarget)|Zeichnet das Strukturelement als Ziel eines Drag & Drop-Vorgangs.|  
|[CTreeCtrl::SelectItem](#selectitem)|Wählt ein Element der angegebenen Struktur anzeigen.|  
|[CTreeCtrl::SelectSetFirstVisible](#selectsetfirstvisible)|Ein Element der angegebenen Struktur anzeigen als das erste sichtbare Element ausgewählt.|  
|[CTreeCtrl::SetAutoscrollInfo](#setautoscrollinfo)|Legt die Autoscroll-Rate des aktuellen Strukturansicht Steuerelements fest.|  
|[CTreeCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe des Steuerelements fest.|  
|[CTreeCtrl::SetCheck](#setcheck)|Legt den Aktivierungszustand eines Elements Strukturansicht-Steuerelement fest.|  
|[CTreeCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile für das aktuelle Strukturansicht Steuerelement fest.|  
|[CTreeCtrl::SetImageList](#setimagelist)|Legt das Handle für die Bildliste einem Strukturansicht-Steuerelement zugeordnet.|  
|[CTreeCtrl::SetIndent](#setindent)|Legt den Offset (in Pixel) ein Strukturansichtselement aus dem übergeordneten Element fest.|  
|[CTreeCtrl::SetInsertMark](#setinsertmark)|Legt die Einfügemarke in einem Strukturansicht-Steuerelement fest.|  
|[CTreeCtrl::SetInsertMarkColor](#setinsertmarkcolor)|Wird verwendet, um die Einfügemarke für die Strukturansicht gezeichnet werden soll.|  
|[CTreeCtrl::SetItem](#setitem)|Legt die Attribute eines Elements der angegebenen Struktur anzeigen.|  
|[CTreeCtrl::SetItemData](#setitemdata)|Legt den 32-Bit-anwendungsspezifische Wert eines Elements.|  
|[CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex)|Legt den Index des Bilds angezeigt, wenn das angegebene Element des aktuellen Strukturansicht Steuerelements im erweiterten Zustand befindet.|  
|[CTreeCtrl::SetItemHeight](#setitemheight)|Legt die Höhe der Struktur Elemente anzeigen.|  
|[CTreeCtrl::SetItemImage](#setitemimage)|Ordnet ein Element Bilder hinzu.|  
|[CTreeCtrl::SetItemState](#setitemstate)|Legt den Zustand eines Elements.|  
|[CTreeCtrl::SetItemStateEx](#setitemstateex)|Legt den erweiterten Status des angegebenen Elements im aktuellen Strukturansicht Steuerelement fest.|  
|[CTreeCtrl::SetItemText](#setitemtext)|Legt den Text eines Elements fest.|  
|[CTreeCtrl::SetLineColor](#setlinecolor)|Legt die aktuelle Farbe für das Strukturansicht-Steuerelement fest.|  
|[CTreeCtrl::SetScrollTime](#setscrolltime)|Legt die maximale Scroll-Zeit für das Strukturansicht-Steuerelement fest.|  
|[CTreeCtrl::SetTextColor](#settextcolor)|Legt die Textfarbe des Steuerelements fest.|  
|[CTreeCtrl::SetToolTips](#settooltips)|Legt ein Strukturansichtsteuerelement untergeordneten QuickInfo-Steuerelement fest.|  
|[CTreeCtrl::ShowInfoTip](#showinfotip)|Zeigt die QuickInfo für das angegebene Element im aktuellen Strukturansicht Steuerelement.|  
|[CTreeCtrl::SortChildren](#sortchildren)|Sortiert die untergeordneten Elemente eines angegebenen übergeordneten Elements.|  
|[CTreeCtrl::SortChildrenCB](#sortchildrencb)|Sortiert die untergeordneten Elemente eines angegebenen übergeordneten Elements eine anwendungsdefinierte Sortierfunktion verwenden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Strukturansicht-Steuerelement" ist ein Fenster, in dem eine hierarchische Liste von Elementen, z. B. die Überschriften in einem Dokument die Einträge in einem Index oder die Dateien und Verzeichnisse auf einem Datenträger angezeigt. Jedes Element besteht aus einer Bezeichnung und einem optionalen als Bitmap verfügbares Bild aus kann, und jedes Element eine Liste von Unterelementen zugeordnet. Durch Klicken auf ein Element, kann der Benutzer erweitern und reduzieren die zugehörige Liste der Unterelemente.  
  
 Dieses Steuerelement (und somit die `CTreeCtrl` Klasse) ist nur für Programme, die unter Windows 98 und Windows NT, Version 4 und höher.  
  
 Weitere Informationen zur Verwendung von `CTreeCtrl`, finden Sie unter:  
  
- [Steuerelemente](../../mfc/controls-mfc.md)  
  
- [Verwenden von CTreeCtrl](../../mfc/using-ctreectrl.md)  
  
- [Strukturansicht-Steuerelementverweis](http://msdn.microsoft.com/library/windows/desktop/bb759988) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   Knowledge Base-Artikel Q222905: So wird's gemacht: Anzeigen eines Kontextmenüs für CTreeCtrl  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-namecreatea--ctreectrlcreate"></a><a name="create"></a>CTreeCtrl::Create  
 Wenn Sie das Strukturansicht-Steuerelement in einer Dialogfeldvorlage angeben oder bei Verwendung von [CTreeView](../../mfc/reference/ctreeview-class.md), Strukturansicht-Steuerelement wird automatisch erstellt, wenn das Dialogfeld oder eine Sicht erstellt wird.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Strukturansicht-Steuerelement Stil. Anwenden von Window-Stile in beschriebenen [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679), und eine beliebige Kombination von [Struktur Steuerelementtypen für die Ansicht](http://msdn.microsoft.com/library/windows/desktop/bb760013) wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Gibt des Strukturansicht-Steuerelements die Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Strukturansicht-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Strukturansicht-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das Strukturansicht-Steuerelement als untergeordnetes Fenster eines anderen Fensters erstellen möchten, verwenden Sie die **erstellen** Member-Funktion. Wenn Sie das Strukturansicht-Steuerelement mit erstellen **erstellen**, müssen Sie es übergeben **WS_VISIBLE**, zusätzlich zu anderen Arten der Struktur anzeigen.  
  
 Erstellen Sie eine `CTreeCtrl` in zwei Schritten. Rufen Sie dann beim ersten Aufruf der Konstruktor **erstellen**, die das Strukturansicht-Steuerelement erstellt, und fügt es der `CTreeCtrl` Objekt.  
  
 Rufen Sie zum Erstellen einer Strukturansicht mit erweiterten Fensterstile [CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--ctreectrlcreateex"></a><a name="createex"></a>CTreeCtrl::CreateEx  
 Rufen Sie diese Funktion zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CTreeCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Gibt das Strukturansicht-Steuerelement Stil. Anwenden von Window-Stile in beschriebenen [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679), und eine beliebige Kombination von [Struktur Steuerelementtypen für die Ansicht](http://msdn.microsoft.com/library/windows/desktop/bb760013) wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="a-namecreatedragimagea--ctreectrlcreatedragimage"></a><a name="createdragimage"></a>CTreeCtrl::CreateDragImage  
 Rufen Sie diese Funktion zum Erstellen einer Drag & Drop-Bitmap für das angegebene Element in einem Strukturansicht-Steuerelement, eine Bildliste für die Bitmap erstellen und die Bitmap auf die Bildliste hinzufügen.  
  
```  
CImageList* CreateDragImage(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle des Strukturelements gezogen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die Bildliste, die Bitmap für die Drag & Drop hinzugefügt wurde, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Eine Anwendung verwendet die Bildliste Funktionen zur Anzeige des Bilds, wenn das Element gezogen wird.  
  
 Das `CImageList` Objekt ist dauerhaft und müssen Sie es nach Abschluss löschen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#2;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_2.cpp)]  
  
##  <a name="a-namectreectrla--ctreectrlctreectrl"></a><a name="ctreectrl"></a>CTreeCtrl::CTreeCtrl  
 Erstellt ein `CTreeCtrl`-Objekt.  
  
```  
CTreeCtrl();
```  
  
##  <a name="a-namedeleteallitemsa--ctreectrldeleteallitems"></a><a name="deleteallitems"></a>CTreeCtrl::DeleteAllItems  
 Rufen Sie diese Funktion, um alle Elemente aus der Strukturansicht löschen.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&3;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_3.cpp)]  
  
##  <a name="a-namedeleteitema--ctreectrldeleteitem"></a><a name="deleteitem"></a>CTreeCtrl::DeleteItem  
 Rufen Sie diese Funktion, um ein Element aus der Strukturansicht löschen.  
  
```  
BOOL DeleteItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle des Strukturelements gelöscht werden soll. Wenn *Hitem* hat die **TVI_ROOT** Wert, werden alle Elemente aus dem Strukturansicht-Steuerelement gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_4.cpp)]  
  
##  <a name="a-nameeditlabela--ctreectrleditlabel"></a><a name="editlabel"></a>CTreeCtrl::EditLabel  
 Rufen Sie diese Funktion, um die direkte Bearbeitung von Text für das angegebene Element zu beginnen.  
  
```  
CEdit* EditLabel(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle des Strukturelements bearbeitet werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf die `CEdit` -Objekt, das den Elementtext bearbeiten verwendet wird; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Die Bearbeitung erfolgt durch den Text des Elements mit einem einzeiligen Edit-Steuerelement, das mit dem Text ersetzen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_5.cpp)]  
  
##  <a name="a-nameendeditlabelnowa--ctreectrlendeditlabelnow"></a><a name="endeditlabelnow"></a>CTreeCtrl::EndEditLabelNow  
 Beendet den Bearbeitungsvorgang an die Bezeichnung eines Strukturansicht Elements im aktuellen Strukturansicht Steuerelement.  
  
```  
BOOL EndEditLabelNow(BOOL fCancelWithoutSave);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `fCancelWithoutSave`|`true`Änderungen an dem Strukturansicht Element vor dem Abschluss des Bearbeitungsvorgangs verwerfen oder `false` um Änderungen vor dem Abschluss des Vorgangs zum Strukturansicht Element zu speichern.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_ENDEDITLABELNOW](http://msdn.microsoft.com/library/windows/desktop/bb773564) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameensurevisiblea--ctreectrlensurevisible"></a><a name="ensurevisible"></a>CTreeCtrl::EnsureVisible  
 Rufen Sie diese Funktion, um sicherzustellen, dass ein Element der Struktur anzeigen angezeigt wird.  
  
```  
BOOL EnsureVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle des Strukturelements sichtbar gemacht wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** das System nach einem Bildlauf durch die Elemente in der Strukturansicht Steuerelement um sicherzustellen, dass das angegebene Element angezeigt wird. Andernfalls der Rückgabewert ist **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Falls erforderlich, wird die Funktion erweitert das übergeordnete Element oder führt einen Bildlauf im Strukturansicht-Steuerelement, sodass das Element sichtbar ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_6.cpp)]  
  
##  <a name="a-nameexpanda--ctreectrlexpand"></a><a name="expand"></a>CTreeCtrl::Expand  
 Rufen Sie diese Funktion zum Erweitern oder reduzieren die Liste der untergeordneten Elemente, wenn vorhanden, mit dem angegebenen übergeordneten Element verknüpft sind.  
  
```  
BOOL Expand(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle des Strukturelements erweitert wird.  
  
 `nCode`  
 Ein Flag, das den Typ der auszuführende Aktion angibt. Dieses Flag kann einen der folgenden Werte aufweisen:  
  
- `TVE_COLLAPSE`Blendet die Liste.  
  
- `TVE_COLLAPSERESET`Blendet die Liste, und die untergeordneten Elemente werden entfernt. Die **TVIS_EXPANDEDONCE** Statusflag wird zurückgesetzt. Dieses Flag muss zusammen mit der `TVE_COLLAPSE` Flag.  
  
- `TVE_EXPAND`Wird die Liste erweitert.  
  
- `TVE_TOGGLE`Die Liste reduziert, wird derzeit erweitert oder ihn zu erweitern, wenn es derzeit reduziert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::EnsureVisible](#ensurevisible).  
  
##  <a name="a-namegetbkcolora--ctreectrlgetbkcolor"></a><a name="getbkcolor"></a>CTreeCtrl::GetBkColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773570), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** -Wert, der die aktuelle Fenster Hintergrundfarbe für das Steuerelement darstellt. Wenn dieser Wert-1 ist, wird das Steuerelement die Systemfarbe für Fenster verwenden. In diesem Fall können Sie `::GetSysColor(COLOR_WINDOW)` um die aktuelle Systemfarbe abzurufen, die das Steuerelement verwendet wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="a-namegetchecka--ctreectrlgetcheck"></a><a name="getcheck"></a>CTreeCtrl::GetCheck  
 Rufen Sie diese Memberfunktion zum Abrufen der Aktivierungszustand eines Elements.  
  
```  
BOOL GetCheck(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Die **HTREEITEM** , für die die Statusinformationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Strukturansicht-Steuerelement ein Element aktiviert ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="a-namegetchilditema--ctreectrlgetchilditem"></a><a name="getchilditem"></a>CTreeCtrl::GetChildItem  
 Aufruf dieser Funktion zum Abrufen der Struktur anzeigen, die das untergeordnete Element des angegebenen Elements ist `hItem`.  
  
```  
HTREEITEM GetChildItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das untergeordnete Element, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#7;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_7.cpp)]  
  
##  <a name="a-namegetcounta--ctreectrlgetcount"></a><a name="getcount"></a>CTreeCtrl::GetCount  
 Rufen Sie diese Funktion zum Abrufen der Anzahl der Elemente in einem Strukturansicht-Steuerelement.  
  
```  
UINT GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Strukturansicht-Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#8;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_8.cpp)]  
  
##  <a name="a-namegetdrophilightitema--ctreectrlgetdrophilightitem"></a><a name="getdrophilightitem"></a>CTreeCtrl::GetDropHilightItem  
 Rufen Sie diese Funktion zum Abrufen des Elements, das Ziel eines Drag & Drop-Vorgangs ist.  
  
```  
HTREEITEM GetDropHilightItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Elements gelöscht, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="a-namegeteditcontrola--ctreectrlgeteditcontrol"></a><a name="geteditcontrol"></a>CTreeCtrl::GetEditControl  
 Rufen Sie diese Funktion, um das Handle des Bearbeitungssteuerelements verwendet wird, um ein Strukturansichtselement Text zu bearbeiten.  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Edit-Steuerelement verwendet, um den Elementtext im Erfolgsfall bearbeiten; andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#10;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_10.cpp)]  
  
##  <a name="a-namegetextendedstylea--ctreectrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTreeCtrl::GetExtendedStyle  
 Ruft die erweiterten Stile, die das aktuelle Strukturansicht Steuerelement verwendet wird.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der eine bitweise Kombination (OR) die aktuelle Strukturansicht Steuerelement enthält die Formate erweitert. Weitere Informationen finden Sie unter [Strukturansicht Steuerelement Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb759981).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773580) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetfirstvisibleitema--ctreectrlgetfirstvisibleitem"></a><a name="getfirstvisibleitem"></a>CTreeCtrl::GetFirstVisibleItem  
 Rufen Sie diese Funktion zum Abrufen des ersten sichtbaren Elements des Strukturansicht-Steuerelement.  
  
```  
HTREEITEM GetFirstVisibleItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des ersten sichtbaren Elements andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="a-namegetimagelista--ctreectrlgetimagelist"></a><a name="getimagelist"></a>CTreeCtrl::GetImageList  
 Rufen Sie diese Funktion, um den Handle der normalen oder Status Bildliste, die dem Strukturansicht-Steuerelement zugeordnete abzurufen.  
  
```  
CImageList* GetImageList(UINT nImageList) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nImageList`  
 Typ der Bildliste abgerufen. Die Bildliste kann eine der folgenden Werte sein:  
  
- `TVSIL_NORMAL`Ruft den normalen Bildliste, enthält die ausgewählten und nicht ausgewählten Bilder für das Element der Struktur anzeigen.  
  
- `TVSIL_STATE`Ruft die Bildliste Zustand, mit der Bilder für die Elemente der Struktur anzeigen, die in einem benutzerdefinierten Zustand befinden.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die Bildliste des Steuerelements, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Element in einem Strukturansicht-Steuerelement kann ein Paar von Bitmapbildern zugeordnet haben. Ein Bild wird angezeigt, wenn das Element ausgewählt ist, und der andere wird angezeigt, wenn das Element nicht ausgewählt ist. Beispielsweise kann ein Element anzeigen einen Ordner öffnen, wenn diese Option ausgewählt ist und einen geschlossenen Ordner, wenn es nicht aktiviert ist.  
  
 Weitere Informationen zu Bildlisten, finden Sie unter der [CImageList](../../mfc/reference/cimagelist-class.md) Klasse.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#11;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_11.cpp)]  
  
##  <a name="a-namegetindenta--ctreectrlgetindent"></a><a name="getindent"></a>CTreeCtrl::GetIndent  
 Rufen Sie diese Funktion, um den Betrag in Pixel, dass untergeordnete Elemente relativ zum ihre übergeordneten Elemente eingezogen werden abzurufen.  
  
```  
UINT GetIndent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Einzugs in Pixel gemessen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#12;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_12.cpp)]  
  
##  <a name="a-namegetinsertmarkcolora--ctreectrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CTreeCtrl::GetInsertMarkColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773590)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die Farbe der aktuellen Einfügemarke enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#13;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_13.cpp)]  
  
##  <a name="a-namegetitema--ctreectrlgetitem"></a><a name="getitem"></a>CTreeCtrl::GetItem  
 Mit dieser Funktion werden die Attribute des angegebenen Strukturelements Ansicht abzurufen.  
  
```  
BOOL GetItem(TVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf eine [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::DeleteItem](#deleteitem).  
  
##  <a name="a-namegetitemdataa--ctreectrlgetitemdata"></a><a name="getitemdata"></a>CTreeCtrl::GetItemData  
 Rufen Sie diese Funktion zum Abrufen des 32-Bit-anwendungsspezifische-Wertes, die mit dem angegebenen Element zugeordnet ist.  
  
```  
DWORD_PTR GetItemData(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Daten abgerufen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine 32-Bit-Anwendungsspezifischer Wert dem angegebenen Element zugeordneten `hItem`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&14;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_14.cpp)]  
  
##  <a name="a-namegetitemexpandedimageindexa--ctreectrlgetitemexpandedimageindex"></a><a name="getitemexpandedimageindex"></a>CTreeCtrl::GetItemExpandedImageIndex  
 Ruft den Index des Bilds angezeigt, wenn das angegebene Element des aktuellen Strukturansicht Steuerelements im erweiterten Zustand befindet.  
  
```  
int GetItemExpandedImageIndex(HTREEITEM hItem)const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Handle für ein Strukturansicht Steuerelement ein Element.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Bilds angezeigt, wenn das angegebene Element im erweiterten Zustand befindet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Nachricht gibt die [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur, die dem Strukturansicht Steuerelement ein Element, und klicken Sie dann diese Methode ruft die `iExpandedImage` Element aus dieser Struktur.  
  
##  <a name="a-namegetitemheighta--ctreectrlgetitemheight"></a><a name="getitemheight"></a>CTreeCtrl::GetItemHeight  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773599), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
SHORT GetItemHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Elements in Pixel.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#15;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_15.cpp)]  
  
##  <a name="a-namegetitemimagea--ctreectrlgetitemimage"></a><a name="getitemimage"></a>CTreeCtrl::GetItemImage  
 Jedes Element in einem Strukturansicht-Steuerelement kann ein Paar von Bitmapbildern zugeordnet haben.  
  
```  
BOOL GetItemImage(
    HTREEITEM hItem,  
    int& nImage,  
    int& nSelectedImage) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Bild abgerufen werden soll.  
  
 `nImage`  
 Eine ganze Zahl, die den Index für das Bild des Elements in der Strukturansicht Bildliste empfängt.  
  
 `nSelectedImage`  
 Eine ganze Zahl, die den Index des Elements ausgewählten Bilds innerhalb der Strukturansicht Bildliste empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Bilder auf der linken Seite der Bezeichnung eines Elements angezeigt werden. Ein Bild wird angezeigt, wenn das Element ausgewählt ist, und der andere wird angezeigt, wenn das Element nicht ausgewählt ist. Beispielsweise kann ein Element anzeigen einen Ordner öffnen, wenn diese Option ausgewählt ist und einen geschlossenen Ordner, wenn es nicht aktiviert ist.  
  
 Rufen Sie diese Funktion, um den Index des Elements und ausgewählte Bild in der Strukturansicht Bildliste abzurufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl Nr.&16;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_16.cpp)]  
  
##  <a name="a-namegetitempartrecta--ctreectrlgetitempartrect"></a><a name="getitempartrect"></a>CTreeCtrl::GetItemPartRect  
 Ruft das umschließende Rechteck für den angegebenen Teil eines bestimmten Elements in der aktuellen Strukturansicht Steuerelement ab.  
  
```  
BOOL GetItemPartRect(
    HTREEITEM hItem,   
    int nPart,   
    LPRECT lpRect)const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Handle für ein Strukturansicht Steuerelement ein Element.|  
|[in] `nPart`|Der Bezeichner für das Teil. Muss festgelegt werden, um `TVGIPR_BUTTON`.|  
|[out] `lpRect`|Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur. Wenn diese Methode erfolgreich ist, empfängt die Struktur die Rechteck-Koordinaten für die Komponente, `hItem` und `nPart`.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Jede Struktur-Steuerelement ein Element wird durch ein Rechteck Grafiken begrenzt. Bei jedem Klicken auf ein Punkt in das Rechteck das Element wird als bezeichnet, *erreicht*. Diese Methode gibt die größte Rechteck, wenn ein Punkts in das Rechteck geklickt wird, wird das Element von identifiziert die `hItem` Parameter erreicht wird.  
  
 Diese Methode sendet die `TVM_GETITEMPARTRECT` -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen finden Sie unter der [TreeView_GetItemPartRect](http://msdn.microsoft.com/library/windows/desktop/bb773847) Makro.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel verwendet einen Eingabehilfen-Bezeichner und die [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) Methode, um ein Handle für das Strukturansicht Stammelement abzurufen. Das Handle wird verwendet, und die [CTreeCtrl::GetItemPartRect](#getitempartrect) Methode, um ein 3D Rechteck um das Element zu zeichnen. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht. Verwendet die [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) Methode des Strukturansicht Stammelements mit einer ID, Eingabehilfen zuordnen.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="a-namegetitemrecta--ctreectrlgetitemrect"></a><a name="getitemrect"></a>CTreeCtrl::GetItemRect  
 Rufen Sie diese Funktion zum Abrufen des umschließenden Rechtecks für `hItem` und bestimmen, ob es angezeigt oder nicht wird.  
  
```  
BOOL GetItemRect(
    HTREEITEM hItem,  
    LPRECT lpRect,  
    BOOL bTextOnly) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Steuerelements Element Struktur anzeigen.  
  
 `lpRect`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck empfängt. Die Koordinaten sind relativ zur oberen linken Ecke des Strukturansicht-Steuerelement.  
  
 *bTextOnly*  
 Wenn dieser Parameter einen Wert ungleich NULL ist, enthält das umschließende Rechteck nur den Text des Elements. Andernfalls enthält sie die gesamte Zeile, die das Element befindet sich in der Strukturansicht-Steuerelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Element sichtbar ist, mit das umschließende Rechteck in enthaltenen `lpRect`. Andernfalls wird 0 mit `lpRect` nicht initialisiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&17;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_19.cpp)]  
  
##  <a name="a-namegetitemstatea--ctreectrlgetitemstate"></a><a name="getitemstate"></a>CTreeCtrl::GetItemState  
 Gibt den Status des angegebenen Elements zurück `hItem`.  
  
```  
UINT GetItemState(
    HTREEITEM hItem,  
    UINT nStateMask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Status abgerufen werden soll.  
  
 `nStateMask`  
 Eine Bitmaske zurück, die einem oder mehreren Staaten abgerufen werden sollen. Weitere Informationen zu den möglichen Werten für `nStateMask`, finden Sie in der Erläuterung der **Status** und **StateMask** Mitglieder der [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **UINT** , die das bitweise OR nStateMask angegebenen Werte enthält. Informationen zu den möglichen Werten finden Sie unter [CTreeCtrl::GetItem](#getitem). Führen Sie eine bitweise AND-Operation von der Status-Wert und der Rückgabewert, um den Wert für einen bestimmten Status zu ermitteln, wie im folgenden Beispiel gezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&18;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_20.cpp)]  
  
##  <a name="a-namegetitemstateexa--ctreectrlgetitemstateex"></a><a name="getitemstateex"></a>CTreeCtrl::GetItemStateEx  
 Ruft den erweiterten Zustand des angegebenen Elements im aktuellen Strukturansicht Steuerelement.  
  
```  
UINT GetItemStateEx(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Handle für ein Strukturansicht Steuerelement ein Element.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der erweiterte Zustand des Elements. Weitere Informationen finden Sie unter der `uStateEx` Mitglied der [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Nachricht gibt die [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur, die dem Strukturansicht Steuerelement ein Element, und diese Methode ruft die `uStateEx` Element aus dieser Struktur.  
  
##  <a name="a-namegetitemtexta--ctreectrlgetitemtext"></a><a name="getitemtext"></a>CTreeCtrl::GetItemText  
 Gibt den Text des Elements, angegeben durch `hItem`.  
  
```  
CString GetItemText(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Text abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Text des Elements enthält.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetNextItem](#getnextitem).  
  
##  <a name="a-namegetlastvisibleitema--ctreectrlgetlastvisibleitem"></a><a name="getlastvisibleitem"></a>CTreeCtrl::GetLastVisibleItem  
 Ruft das letzte nicht erweiterten Knotenelement im aktuellen Strukturansicht Steuerelement ab.  
  
```  
HTREEITEM GetLastVisibleItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle, das letzte nicht erweiterten Knotenelement, wenn die Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_GETNEXTITEM](http://msdn.microsoft.com/library/windows/desktop/bb773622) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen finden Sie unter der `TVGN_LASTVISIBLE` -flag in der `flag` Parameter der Nachricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Im folgenden Beispiel werden eine oder mehrere dieser Variablen verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft ein Handle für das letzte Element des nicht erweiterten Strukturansicht-Knoten ab und zeichnet dann ein 3D Rechteck um das Element. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_21.cpp)]  
  
##  <a name="a-namegetlinecolora--ctreectrlgetlinecolor"></a><a name="getlinecolor"></a>CTreeCtrl::GetLineColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773619), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetLineColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Farbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl Nr.&19;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_22.cpp)]  
  
##  <a name="a-namegetnextitema--ctreectrlgetnextitem"></a><a name="getnextitem"></a>CTreeCtrl::GetNextItem  
 Aufruf dieser Funktion zum Abrufen der Struktur anzeigen, die die angegebene Beziehung erkennbar ist die `nCode` Parameter in `hItem`.  
  
```  
HTREEITEM GetNextItem(
    HTREEITEM hItem,  
    UINT nCode) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
 `nCode`  
 Ein Flag, das die Art der Beziehung zu `hItem`. Dieses Flag kann einen der folgenden Werte sein:  
  
- `TVGN_CARET`Ruft das derzeit ausgewählte Element ab.  
  
- `TVGN_CHILD`Ruft das erste untergeordnete Element des angegebenen Elements durch den `hItem` Parameter.  
  
- `TVGN_DROPHILITE`Ruft das Element, das das Ziel eines Drag & Drop-Vorgangs ab.  
  
- `TVGN_FIRSTVISIBLE`Ruft das erste sichtbare Element ab.  
  
- `TVGN_LASTVISIBLE`Ruft die erweiterten letzten Element in der Struktur ab. Dies ist das letzte Element in der Strukturansicht im Fenster sichtbar nicht abgerufen werden.  
  
- `TVGN_NEXT`Ruft das nächste nebengeordnete Element.  
  
- `TVGN_NEXTVISIBLE`Ruft das nächste sichtbare Element, das das angegebene Element folgt.  
  
- `TVGN_PARENT`Ruft das übergeordnete Element des angegebenen Elements ab.  
  
- `TVGN_PREVIOUS`Ruft das vorherige gleichgeordnete Element ab.  
  
- `TVGN_PREVIOUSVISIBLE`Ruft das erste sichtbare Element, das vor dem angegebenen Element ab.  
  
- `TVGN_ROOT`Ruft das erste untergeordnete Element des Stammelements, der das angegebene Element gehört.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des nächsten Elements, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zurück **NULL** das Element abgerufen werden, ist der Stammknoten der Struktur. Angenommen, Sie verwenden, diese Nachricht mit der `TVGN_PARENT` auf einem untergeordneten Ebene der Stammknoten der Strukturansicht zu kennzeichnen, wird die Meldung zurückgegeben **NULL**.  
  
### <a name="example"></a>Beispiel  
 Ein Beispiel für `GetNextItem` in einer Schleife finden Sie unter [CTreeCtrl::DeleteItem](#deleteitem).  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&20;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_23.cpp)]  
  
##  <a name="a-namegetnextsiblingitema--ctreectrlgetnextsiblingitem"></a><a name="getnextsiblingitem"></a>CTreeCtrl::GetNextSiblingItem  
 Rufen Sie diese Funktion zum Abrufen des nächsten gleichgeordneten Knoten des `hItem`.  
  
```  
HTREEITEM GetNextSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des nächsten nebengeordneten Elements andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&21;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_24.cpp)]  
  
##  <a name="a-namegetnextvisibleitema--ctreectrlgetnextvisibleitem"></a><a name="getnextvisibleitem"></a>CTreeCtrl::GetNextVisibleItem  
 Rufen Sie diese Funktion zum Abrufen der nächsten sichtbaren Elements des `hItem`.  
  
```  
HTREEITEM GetNextVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des nächsten Elements sichtbar; andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="a-namegetparentitema--ctreectrlgetparentitem"></a><a name="getparentitem"></a>CTreeCtrl::GetParentItem  
 Rufen Sie diese Funktion rufen Sie das übergeordnete Element des `hItem`.  
  
```  
HTREEITEM GetParentItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des übergeordneten Elements andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion zurück **NULL** ist das übergeordnete Element des angegebenen Elements den Stammknoten der Struktur.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::EnsureVisible](#ensurevisible).  
  
##  <a name="a-namegetprevsiblingitema--ctreectrlgetprevsiblingitem"></a><a name="getprevsiblingitem"></a>CTreeCtrl::GetPrevSiblingItem  
 Mit dieser Funktion können Sie das vorherige gleichgeordnete abrufen `hItem`.  
  
```  
HTREEITEM GetPrevSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des vorhergehenden gleichgeordneten andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#22;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_25.cpp)]  
  
##  <a name="a-namegetprevvisibleitema--ctreectrlgetprevvisibleitem"></a><a name="getprevvisibleitem"></a>CTreeCtrl::GetPrevVisibleItem  
 Rufen Sie diese Funktion zum Abrufen des vorherigen sichtbaren Elements des `hItem`.  
  
```  
HTREEITEM GetPrevVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des vorherigen sichtbaren Elements andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&23;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_26.cpp)]  
  
##  <a name="a-namegetrootitema--ctreectrlgetrootitem"></a><a name="getrootitem"></a>CTreeCtrl::GetRootItem  
 Rufen Sie diese Funktion zum Abrufen des Stammelements der Strukturansicht-Steuerelement.  
  
```  
HTREEITEM GetRootItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des dem Stammelement andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::EditLabel](#editlabel).  
  
##  <a name="a-namegetscrolltimea--ctreectrlgetscrolltime"></a><a name="getscrolltime"></a>CTreeCtrl::GetScrollTime  
 Rufen Sie diese Memberfunktion zum Abrufen der maximalen Scroll Uhrzeit für das Strukturansicht-Steuerelement.  
  
```  
UINT GetScrollTime() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Scroll-Zeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773625), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetselectedcounta--ctreectrlgetselectedcount"></a><a name="getselectedcount"></a>CTreeCtrl::GetSelectedCount  
 Ruft die Anzahl der ausgewählten Elemente im aktuellen Strukturansicht Steuerelement ab.  
  
```  
UINT GetSelectedCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der ausgewählten Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_GETSELECTEDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb773629) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetselecteditema--ctreectrlgetselecteditem"></a><a name="getselecteditem"></a>CTreeCtrl::GetSelectedItem  
 Rufen Sie diese Funktion zum Abrufen des derzeit ausgewählten Elements des Strukturansicht-Steuerelement.  
  
```  
HTREEITEM GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des ausgewählten Elements andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#24;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_27.cpp)]  
  
##  <a name="a-namegettextcolora--ctreectrlgettextcolor"></a><a name="gettextcolor"></a>CTreeCtrl::GetTextColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773633), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die aktuelle Textfarbe darstellt. Wenn dieser Wert-1 ist, verwendet das Steuerelement die Systemfarbe für die Textfarbe.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="a-namegettooltipsa--ctreectrlgettooltips"></a><a name="gettooltips"></a>CTreeCtrl::GetToolTips  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773729), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) Objekt, das durch das Strukturansicht-Steuerelement verwendet werden. Wenn die [erstellen](#create) Member-Funktion verwendet das Format **TVS_NOTOOLTIPS**, keine QuickInfos verwendet werden, und **NULL** zurückgegeben wird.  
  
### <a name="remarks"></a>Hinweise  
 Die MFC-Implementierung von `GetToolTips` gibt ein `CToolTipCtrl` -Objekt, das ein Handle für ein QuickInfo-Steuerelement, anstatt das Strukturansicht-Steuerelement verwendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#25;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_28.cpp)]  
  
##  <a name="a-namegetvisiblecounta--ctreectrlgetvisiblecount"></a><a name="getvisiblecount"></a>CTreeCtrl::GetVisibleCount  
 Rufen Sie diese Funktion, um die Anzahl der sichtbaren Elemente in einem Strukturansicht-Steuerelement abzurufen.  
  
```  
UINT GetVisibleCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der sichtbaren Elemente in der Strukturansicht-Steuerelement; andernfalls – 1.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetCheck](#setcheck).  
  
##  <a name="a-namehittesta--ctreectrlhittest"></a><a name="hittest"></a>CTreeCtrl::HitTest  
 Rufen Sie diese Funktion, um die Position des angegebenen Punktes relativ zum Clientbereich des einem Strukturansicht-Steuerelement zu bestimmen.  
  
```  
HTREEITEM HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
  
HTREEITEM HitTest(TVHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Clientkoordinaten des Punkts zu testen.  
  
 `pFlags`  
 Zeiger auf eine ganze Zahl, die Informationen über die Ergebnisse des Treffertests empfängt. Kann eine oder mehrere der Werte aufgeführt, unter der **Flags** Element im Abschnitt "Hinweise".  
  
 `pHitTestInfo`  
 Adresse einer [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) Struktur, die die Position zum Test und die Treffer enthält Informationen über die Ergebnisse des Treffertests empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für das Strukturelement für die Ansicht, die den angegebenen Punkt zu belegen oder **NULL** Wenn kein Element den Punkt einnimmt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion aufgerufen wird, die `pt` Parameter gibt die Koordinaten des Punkts zu testen. Die Funktion gibt das Handle des Elements am angegebenen Punkt zurück oder **NULL** Wenn kein Element den Punkt einnimmt. Darüber hinaus die `pFlags` Parameter enthält einen Wert, der die Position des angegebenen Punkt angibt. Dabei sind folgende Werte möglich:  
  
|||  
|-|-|  
|Wert|Bedeutung|  
|TVHT_ABOVE|Oberhalb des Clientbereichs.|  
|TVHT_BELOW|Unterhalb des Clientbereichs.|  
|TVHT_NOWHERE|Im Clientbereich, jedoch unterhalb des letzten Elements.|  
|TVHT_ONITEM|Auf die Bitmap oder die Bezeichnung eines Elements.|  
|TVHT_ONITEMBUTTON|Klicken Sie auf die Schaltfläche, die einem Element zugeordnet wird.|  
|TVHT_ONITEMICON|Klicken Sie auf die Bitmap, die einem Element zugeordnet wird.|  
|TVHT_ONITEMINDENT|In den Einzug, der einem Element zugeordnet wird.|  
|TVHT_ONITEMLABEL|Klicken Sie auf die Bezeichnung (Zeichenfolge) eines Elements.|  
|TVHT_ONITEMRIGHT|Im Bereich rechts neben einem Element.|  
|TVHT_ONITEMSTATEICON|Auf das Statussymbol für eine Strukturansicht-Element, das in einem benutzerdefinierten Zustand befindet.|  
|TVHT_TOLEFT|Auf der linken Seite des Clientbereichs.|  
|TVHT_TORIGHT|Auf der rechten Seite des Clientbereichs.|  
|||  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="a-nameinsertitema--ctreectrlinsertitem"></a><a name="insertitem"></a>CTreeCtrl::InsertItem  
 Rufen Sie diese Funktion, um ein neues Element in einem Strukturansicht-Steuerelement einfügen.  
  
```  
HTREEITEM InsertItem(LPTVINSERTSTRUCT lpInsertStruct);

 
HTREEITEM InsertItem(
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam,  
    HTREEITEM hParent,  
    HTREEITEM hInsertAfter);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);
```  
  
### <a name="parameters"></a>Parameter  
 *lpInsertStruct*  
 Ein Zeiger auf eine `TVINSERTSTRUCT` , die die Attribute der Struktur Ansicht einzufügenden Elements angibt.  
  
 `nMask`  
 Ganze Zahl, welche Attribute festgelegt. Finden Sie unter der `TVITEM` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpszItem`  
 Die Adresse einer Zeichenfolge, die den Text des Elements enthält.  
  
 `nImage`  
 Index, der das Bild des Elements in der Strukturansicht Bildliste.  
  
 `nSelectedImage`  
 Der Index des Elements ausgewählten Bilds in der Strukturansicht Bildliste.  
  
 `nState`  
 Gibt Werte für die Element-Zustände. Siehe Struktur anzeigen Elementzustände des Steuerelements in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Liste der entsprechenden Status.  
  
 `nStateMask`  
 Gibt an, welche Zustände festgelegt werden. Finden Sie unter der `TVITEM` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lParam`  
 Ein 32-Bit-anwendungsspezifische-Wert mit dem Element verknüpft sind.  
  
 `hParent`  
 Das Handle des übergeordneten für das eingefügte Element.  
  
 *hInsertAfter*  
 Handle des Elements, nach dem das neue Element eingefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das neue Element, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Das Beispiel zeigt die Situationen, in denen Sie jede Version der Funktion verwenden, wenn ein Strukturansicht-Steuerelement ein Element einfügen möchten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#27;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_30.cpp)]  
  
##  <a name="a-nameitemhaschildrena--ctreectrlitemhaschildren"></a><a name="itemhaschildren"></a>CTreeCtrl::ItemHasChildren  
 Mit dieser Funktion können Sie bestimmen, ob das Strukturelement angegeben `hItem` über untergeordnete Elemente verfügt.  
  
```  
BOOL ItemHasChildren(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Strukturelement angegeben `hItem` enthält untergeordnete Elemente; 0, wenn dies nicht der Fall.  
  
### <a name="remarks"></a>Hinweise  
 Wenn also, Sie verwenden können [CTreeCtrl::GetChildItem](#getchilditem) die untergeordneten Elemente abgerufen werden sollen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetSelectedItem](#getselecteditem).  
  
##  <a name="a-namemapaccidtoitema--ctreectrlmapaccidtoitem"></a><a name="mapaccidtoitem"></a>CTreeCtrl::MapAccIdToItem  
 Ordnet den angegebenen Eingabehilfen-Bezeichner auf das Handle eines Strukturansicht Elements im aktuellen Strukturansicht Steuerelement.  
  
```  
HTREEITEM MapAccIdToItem(UINT uAccId) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `uAccId`|Ein Eingabehilfen-Bezeichner für ein Element in der Strukturansicht Element.|  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für ein Strukturansicht Element ( `HTREEITEM`), entspricht die `uAccId` Parameter. Weitere Informationen finden Sie unter der `hItem` Mitglied der [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Eingabehilfen sind Programme, mit denen Personen mit Behinderung Computer verwenden. Ein Bezeichner Eingabehilfen werden die `IAccessible` Schnittstelle, um ein Element in einem Fenster eindeutig anzugeben. Für Weitere Informationen zu Eingabehilfen-IDs, suchen Sie nach dem Thema "Zu Active Accessibility-Unterstützung" unter [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Diese Methode sendet die [TVM_MAPACCIDTOHTREEITEM](http://msdn.microsoft.com/library/windows/desktop/bb773734) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel verwendet einen Eingabehilfen-Bezeichner und die [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) Methode, um ein Handle für das Strukturansicht Stammelement abzurufen. Im Beispiel wird das Handle und die [CTreeCtrl::GetItemPartRect](#getitempartrect) Methode, um ein 3D Rechteck um das Element zu zeichnen. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht. Verwendet die [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) Methode des Strukturansicht Stammelements mit einer ID, Eingabehilfen zuordnen.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="a-namemapitemtoaccida--ctreectrlmapitemtoaccid"></a><a name="mapitemtoaccid"></a>CTreeCtrl::MapItemToAccID  
 Ordnet das angegebene Handle eines Strukturansicht Elements im aktuellen Strukturansicht Steuerelement auf einen Bezeichner für Eingabehilfen.  
  
```  
UINT MapItemToAccID(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Ein Handle eines Strukturansicht Elements im Steuerelement. Weitere Informationen finden Sie unter der `hItem` Mitglied der [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Eingabehilfen-Identifier, entspricht der `hItem` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Eingabehilfen sind Programme, mit denen Personen mit Behinderung Computer verwenden. Ein Bezeichner Eingabehilfen werden die `IAccessible` Schnittstelle, um ein Element in einem Fenster eindeutig anzugeben. Für Weitere Informationen zu Eingabehilfen-IDs, suchen Sie nach dem Thema "Zu Active Accessibility-Unterstützung" unter [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Diese Methode sendet die [TVM_MAPHTREEITEMTOACCID](http://msdn.microsoft.com/library/windows/desktop/bb773735) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel ruft eine ID für ein Strukturansicht Steuerelement ab. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht. Dieses Codebeispiel ruft eine eindeutige Identifikationsnummer für den Stammknoten des Landes bzw. der Region ab.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/ctreectrl-class_31.cpp)]  
  
##  <a name="a-nameselecta--ctreectrlselect"></a><a name="select"></a>CTreeCtrl::Select  
 Rufen Sie diese Funktion Wählen Sie das Element der angegebenen Struktur anzeigen, scrollen das Element in die Ansicht oder das Element neu zeichnen, das Format verwendet, um das Ziel eines Drag & Drop-Vorgangs anzugeben.  
  
```  
BOOL Select(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
 `nCode`  
 Der Typ der auszuführenden Aktion. Dieser Parameter kann einen der folgenden Werte sein:  
  
- `TVGN_CARET`Legt die Auswahl auf das angegebene Element fest.  
  
- `TVGN_DROPHILITE`Zeichnet das angegebene Element im Format verwendet, um das Ziel eines Drag & Drop-Vorgangs anzugeben.  
  
- `TVGN_FIRSTVISIBLE`Die Strukturansicht gerollt, so dass das angegebene Element das erste sichtbare Element ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nCode` enthält den Wert `TVGN_CARET`, empfängt das übergeordnete Fenster der **TVN_SELCHANGING** und **eine TVN_SELCHANGED** Benachrichtigung. Wenn das angegebene Element das untergeordnete Element eines reduzierten übergeordneten Elements ist, wird darüber hinaus Liste untergeordneter Elemente des übergeordneten Elements erweitert, um das angegebene Element anzuzeigen. Das übergeordnete Fenster in diesem Fall erhält der **TVN_ITEMEXPANDING** und **TVN_ITEMEXPANDED** Benachrichtigung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::HitTest](#hittest).  
  
##  <a name="a-nameselectdroptargeta--ctreectrlselectdroptarget"></a><a name="selectdroptarget"></a>CTreeCtrl::SelectDropTarget  
 Rufen Sie diese Funktion, um das Element neu gezeichnet werden im entsprechenden Stil verwendet, um das Ziel eines Drag & Drop-Vorgangs anzugeben.  
  
```  
BOOL SelectDropTarget(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="a-nameselectitema--ctreectrlselectitem"></a><a name="selectitem"></a>CTreeCtrl::SelectItem  
 Mit dieser Funktion wird das Element der angegebenen Struktur anzeigen aus.  
  
```  
BOOL SelectItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle für ein Strukturelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn `hItem` ist **NULL**, und klicken Sie dann diese Funktion kein Element ausgewählt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="a-nameselectsetfirstvisiblea--ctreectrlselectsetfirstvisible"></a><a name="selectsetfirstvisible"></a>CTreeCtrl::SelectSetFirstVisible  
 Rufen Sie diese Funktion, um die Strukturansicht vertikaler Bildlauf durchgeführt wird, damit das angegebene Element das erste sichtbare Element ist.  
  
```  
BOOL SelectSetFirstVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Handle des Strukturelements als das erste sichtbare Element festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion sendet eine Nachricht an das Fenster mit den `TVM_SELECTITEM` und `TVGN_FIRSTVISIBLE` message-Parameter.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#28;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_32.cpp)]  
  
##  <a name="a-namesetautoscrollinfoa--ctreectrlsetautoscrollinfo"></a><a name="setautoscrollinfo"></a>CTreeCtrl::SetAutoscrollInfo  
 Legt die Autoscroll-Rate des aktuellen Strukturansicht Steuerelements fest.  
  
```  
BOOL SetAutoscrollInfo(
    UINT uPixelsPerSec,   
    UINT uUpdateTime);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `uPixelsPerSec`|Die Anzahl der Pixel pro Sekunde, um einen Bildlauf durchzuführen.|  
|[in] `uUpdateTime`|Das Zeitintervall zwischen den Aktualisierungen des Steuerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer `true` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Autoscroll-Parameter werden verwendet, um ein Element durch einen Bildlauf anzuzeigende, die derzeit nicht sichtbar ist. Das Strukturansicht Steuerelement müssen die `TVS_EX_AUTOHSCROLL` erweiterten Stil, der in beschrieben wird [Strukturansicht Steuerelement Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb759981).  
  
 Diese Methode sendet die [TVM_SETAUTOSCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb773738) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die automatischen Bildlauf-Verhalten des aktuellen Strukturansicht Steuerelements. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht. Wir haben absichtlich das Strukturansicht Steuerelement eng, damit er automatisch einen Bildlauf durchführen muss zur Anzeige des Strukturelements, den Fokus besitzt. Im Codebeispiel wird des Strukturansicht Steuerelements zum Ausführen eines automatischen Bildlaufs 30 Pixel pro Sekunde alle 5 Sekunden, bis das Strukturelement angezeigt wird.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_33.cpp)]  
  
##  <a name="a-namesetbkcolora--ctreectrlsetbkcolor"></a><a name="setbkcolor"></a>CTreeCtrl::SetBkColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773741)wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Ein **COLORREF** Wert, der die neue Hintergrundfarbe enthält. Wenn der Wert-1 ist, wird das Steuerelement auf die Systemfarbe für die Farbe des Hintergrunds zurückgesetzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die aktuelle Textfarbe darstellt. Wenn dieser Wert-1 ist, verwendet das Steuerelement die Systemfarbe für die Textfarbe.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::SetTextColor](#settextcolor).  
  
##  <a name="a-namesetchecka--ctreectrlsetcheck"></a><a name="setcheck"></a>CTreeCtrl::SetCheck  
 Rufen Sie diese Memberfunktion zum Festlegen des Aktivierungszustands für ein Strukturelement-Steuerelement.  
  
```  
BOOL SetCheck(
    HTREEITEM hItem,  
    BOOL fCheck = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Die **HTREEITEM** Änderung des Kontrollkästchen empfangen.  
  
 `fCheck`  
 Gibt an, ob das Strukturelement-Steuerelement aktiviert oder deaktiviert werden soll. In der Standardeinstellung `SetCheck` legt das Element überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Strukturansicht-Steuerelement ein Element aktiviert wird ( `fCheck` festgelegt **TRUE**), das Element mit einem Häkchen neben angezeigt wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#29;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_34.cpp)]  
  
### <a name="example"></a>Beispiel  
 Um Kontrollkästchen zu verwenden, legen Sie TVS_CHECKBOXES vor dem Auffüllen des Strukturansicht-Steuerelements.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl&#30;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_35.cpp)]  
  
##  <a name="a-namesetextendedstylea--ctreectrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTreeCtrl::SetExtendedStyle  
 Legt die erweiterten Stile für das aktuelle Strukturansicht Steuerelement fest.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,   
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `dwExMask`|Eine Bitmaske, die angibt, welche Stile im aktuellen Strukturansicht Steuerelement von dieser Methode betroffen sind. Wenn dieser Parameter NULL ist, wird er ignoriert und der Wert der `dwExStyles` Parameter der Strukturansicht Steuerelement zugewiesen ist.<br /><br /> Geben Sie&0; (null) oder eine bitweise Kombination (OR) von Formatvorlagen in beschriebenen [Strukturansicht Steuerelement Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb759981).|  
|[in] `dwExStyles`|Eine Bitmaske, die angibt, welche Stile in der aktuellen Strukturansicht oder löschen zu steuern.<br /><br /> Geben Sie zum Festlegen einer Kombination von Stilen eine bitweise Kombination (OR) von Formatvorlagen in beschriebenen [Strukturansicht Steuerelement Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb759981). Um einen Satz von Formatvorlagen zu löschen, geben Sie&0; (null).|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der die vorherige enthält erweiterte Steuerelementtypen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht die Stile der `dwExMask` Parameter legt dann die Stile der `dwExStyles` Parameter. Nur die erweiterten Stile, die die Bits im entsprechen `dwExMask` ändern.  
  
 Diese Methode sendet die [TVM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773744) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel fügt die `TVS_EX_AUTOHSCROLL` erweiterten Stil auf das aktuelle Strukturansicht Steuerelement. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht. Wir haben absichtlich das Strukturansicht Steuerelement eng, damit er automatisch einen Bildlauf durchführen muss zur Anzeige des Strukturelements, den Fokus besitzt.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s1&3;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_36.cpp)]  
  
##  <a name="a-namesetimagelista--ctreectrlsetimagelist"></a><a name="setimagelist"></a>CTreeCtrl::SetImageList  
 Rufen Sie diese Funktion, um den normalen festzulegen, oder Status Bildliste für eine Struktur Steuerelements und Clientbereich des Steuerelements mithilfe der neuen Abbilder.  
  
```  
CImageList* SetImageList(
    CImageList* pImageList,  
    int nImageListType);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf die Bildliste zuweisen. Wenn `pImageList` ist **NULL**, alle Bilder aus der Strukturansicht entfernt.  
  
 `nImageListType`  
 Typ der Bildliste festgelegt. Die Bildliste kann eine der folgenden Werte sein:  
  
- `TVSIL_NORMAL`Stellt die normale Bild-Liste, enthält die ausgewählten und nicht ausgewählten Bilder für das Element der Struktur anzeigen. Sie müssen diesen Status für Overlay-Images verwenden.  
  
- `TVSIL_STATE`Legt die Bildliste Zustand, mit der Bilder für die Elemente der Struktur anzeigen, die in einem benutzerdefinierten Zustand befinden.  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die vorherige Bildliste, sofern vorhanden. andernfalls **NULL**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetImageList](#getimagelist).  
  
##  <a name="a-namesetindenta--ctreectrlsetindent"></a><a name="setindent"></a>CTreeCtrl::SetIndent  
 Rufen Sie diese Funktion, um die Breite des Einzugs für ein Strukturansicht-Steuerelement und Clientbereich des Steuerelements, um die neue Breite widerzuspiegeln.  
  
```  
void SetIndent(UINT nIndent);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndent`  
 Breite in Pixel, der den Einzug. Wenn `nIndent` ist kleiner als die vom System vorgegebene minimale Breite, die neue Breite auf das System definierten Minimalwert festgelegt ist.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetIndent](#getindent).  
  
##  <a name="a-namesetinsertmarka--ctreectrlsetinsertmark"></a><a name="setinsertmark"></a>CTreeCtrl::SetInsertMark  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb773753), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
BOOL SetInsertMark(
    HTREEITEM hItem,  
    BOOL fAfter = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 **HTREEITEM** , der angibt, an welches Element die Einfügemarke platziert werden. Wenn dieses Argument **NULL**, die Einfügemarke wird entfernt.  
  
 *fAfter*  
 **BOOL** -Wert, der angibt, ob die Einfügemarke vor oder nach dem angegebenen Element befindet. Wenn dieses Argument einen Wert ungleich NULL ist, wird die Einfügemarke nach dem Element platziert werden. Wenn dieses Argument&0; (null) ist, wird die Einfügemarke vor dem Element platziert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#31;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_37.cpp)]  
  
##  <a name="a-namesetinsertmarkcolora--ctreectrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CTreeCtrl::SetInsertMarkColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773755), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>Parameter  
 `clrNew`  
 Ein **COLORREF** Wert, der die Farbe der neuen Einfügemarke enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** Wert, der die Farbe der vorherigen Einfügemarke enthält.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor).  
  
##  <a name="a-namesetitema--ctreectrlsetitem"></a><a name="setitem"></a>CTreeCtrl::SetItem  
 Rufen Sie diese Funktion, um die Attribute des angegebenen Strukturelements Ansicht festgelegt.  
  
```  
BOOL SetItem(TVITEM* pItem);

 
BOOL SetItem(
    HTREEITEM hItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 `pItem`  
 Ein Zeiger auf eine [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) -Struktur, die das neue Element enthält Attribute, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `hItem`  
 Das Handle des Artikels, dessen Attribute festgelegt werden. Finden Sie unter der **hItem** Mitglied der `TVITEM` -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nMask`  
 Ganze Zahl, welche Attribute festgelegt. Finden Sie unter der **Maske** Mitglied der `TVITEM` Struktur.  
  
 `lpszItem`  
 Die Adresse einer Zeichenfolge, die den Text des Elements enthält.  
  
 `nImage`  
 Index, der das Bild des Elements in der Strukturansicht Bildliste. Finden Sie unter der `iImage` Mitglied der `TVITEM` Struktur.  
  
 `nSelectedImage`  
 Der Index des Elements ausgewählten Bilds in der Strukturansicht Bildliste. Finden Sie unter der **iSelectedImage** Mitglied der `TVITEM` Struktur.  
  
 `nState`  
 Gibt Werte für die Element-Zustände. Finden Sie unter der **Status** Mitglied der `TVITEM` Struktur.  
  
 `nStateMask`  
 Gibt an, welche Zustände festgelegt werden. Finden Sie unter der **StateMask** Mitglied der `TVITEM` Struktur.  
  
 `lParam`  
 Ein 32-Bit-anwendungsspezifische-Wert mit dem Element verknüpft sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 In der `TVITEM` -Struktur, die **hItem** Element identifiziert das Element, und die **Maske** -Member gibt an, welche Attribute festgelegt.  
  
 Wenn der **Maske** Member oder die `nMask` Parameter gibt an der `TVIF_TEXT` -Wert, der **PszText** Member oder die `lpszItem` ist die Adresse einer Null-terminierte Zeichenfolge und die **CchTextMax** Member wird ignoriert. Wenn **Maske** (oder `nMask`) gibt an, die `TVIF_STATE` -Wert, der **StateMask** Member oder `nStateMask` Parameter gibt an, welches Element Status ändern und die **Status** Member oder `nState` Parameter enthält die Werte für die Bundesländer.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#32;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_38.cpp)]  
  
##  <a name="a-namesetitemdataa--ctreectrlsetitemdata"></a><a name="setitemdata"></a>CTreeCtrl::SetItemData  
 Rufen Sie diese Funktion zum Festlegen des 32-Bit-anwendungsspezifische-Wertes, die mit dem angegebenen Element zugeordnet ist.  
  
```  
BOOL SetItemData(
    HTREEITEM hItem,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Daten abgerufen werden.  
  
 `dwData`  
 Eine 32-Bit-Anwendungsspezifischer Wert dem angegebenen Element zugeordneten `hItem`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&33;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_39.cpp)]  
  
##  <a name="a-namesetitemexpandedimageindexa--ctreectrlsetitemexpandedimageindex"></a><a name="setitemexpandedimageindex"></a>CTreeCtrl::SetItemExpandedImageIndex  
 Legt den Index des Bilds angezeigt, wenn das angegebene Element des aktuellen Strukturansicht Steuerelements im erweiterten Zustand befindet.  
  
```  
BOOL SetItemExpandedImageIndex(
    HTREEITEM hItem,   
    int iExpandedImage);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Handle für ein Strukturansicht Steuerelement ein Element.|  
|[in] `iExpandedImage`|Der Index des Bilds angezeigt, wenn das angegebene Element im erweiterten Zustand befindet.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weist diese Methode die `iExpandedImage` Parameter, um die `iExpandedImage` Mitglied einer [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur, und klicken Sie dann verwendet, die Struktur in der Nachricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine einfache Prüfung zur Bestimmung, ob die [CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex) -Methode gibt den Wert festlegen, indem Sie die [CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex) Methode. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;8](../../mfc/reference/codesnippet/cpp/ctreectrl-class_40.cpp)]  
  
##  <a name="a-namesetitemheighta--ctreectrlsetitemheight"></a><a name="setitemheight"></a>CTreeCtrl::SetItemHeight  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773761), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
SHORT SetItemHeight(SHORT cyHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `cyHeight`  
 Gibt die neue Höhe jedes Elements in der Strukturansicht in Pixel an. Wenn dieses Argument kleiner als die Höhe der Bilder ist, wird es auf die Höhe der Bilder festgelegt werden. Wenn dieses Argument nicht gerade ist, wird es nach unten, um gerundet des nächsten geraden Wert. Wenn dieses Argument-1 ist, wird das Steuerelement mit seiner Standardelementhöhe zurückgesetzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Höhe der Elemente in Pixel.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetItemHeight](#getitemheight).  
  
##  <a name="a-namesetitemimagea--ctreectrlsetitemimage"></a><a name="setitemimage"></a>CTreeCtrl::SetItemImage  
 Ordnet ein Element Bilder hinzu.  
  
```  
BOOL SetItemImage(
    HTREEITEM hItem,  
    int nImage,  
    int nSelectedImage);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Bild festgelegt werden.  
  
 `nImage`  
 Index, der das Bild des Elements in der Strukturansicht Bildliste.  
  
 `nSelectedImage`  
 Der Index des Elements ausgewählten Bilds in der Strukturansicht Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Jedes Element in einem Strukturansicht-Steuerelement kann ein Paar von Bitmapbildern zugeordnet haben. Die Bilder auf der linken Seite der Bezeichnung eines Elements angezeigt werden. Ein Bild wird angezeigt, wenn das Element ausgewählt ist, und der andere wird angezeigt, wenn das Element nicht ausgewählt ist. Beispielsweise kann ein Element anzeigen einen Ordner öffnen, wenn diese Option ausgewählt ist und einen geschlossenen Ordner, wenn es nicht aktiviert ist.  
  
 Rufen Sie diese Funktion, um den Index des Elements und ausgewählte Bild in der Strukturansicht Bildliste festgelegt.  
  
 Weitere Informationen zu Images finden Sie unter [CImageList](../../mfc/reference/cimagelist-class.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetItemImage](#getitemimage).  
  
##  <a name="a-namesetitemstatea--ctreectrlsetitemstate"></a><a name="setitemstate"></a>CTreeCtrl::SetItemState  
 Legt den Zustand des angegebenen Elements `hItem`.  
  
```  
BOOL SetItemState(
    HTREEITEM hItem,  
    UINT nState,  
    UINT nStateMask);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Zustand festgelegt werden.  
  
 `nState`  
 Gibt neue Status für das Element an.  
  
 `nStateMask`  
 Gibt an, welche Zustände geändert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Informationen zu finden Sie unter [CTreeCtrl::GetItem](#getitem).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetItemState](#getitemstate).  
  
##  <a name="a-namesetitemstateexa--ctreectrlsetitemstateex"></a><a name="setitemstateex"></a>CTreeCtrl::SetItemStateEx  
 Legt den erweiterten Status des angegebenen Elements im aktuellen Strukturansicht Steuerelement fest.  
  
```  
BOOL SetItemStateEx(
    HTREEITEM hItem,   
    UINT uStateEx);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Handle für ein Strukturansicht Steuerelement ein Element.|  
|[in] `uStateEx`|Der erweiterte Zustand des Elements. Weitere Informationen finden Sie unter der `uStateEx` Mitglied der [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weist diese Methode die `uStateEx` Parameter, um die `uStateEx` Mitglied einer [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur, und klicken Sie dann verwendet, die Struktur in der Nachricht.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_treeCtrl`, d. h. auf das aktuelle Strukturansicht Steuerelement verwendet. Das Codebeispiel definiert auch eine Ganzzahl ohne Vorzeichen und mehreren HTREEITEM-Variablen. Diese Variablen werden im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Strukturansicht Element auf deaktiviert. In einem früheren Abschnitt des Codebeispiels, der nicht angezeigt wird, haben wir eine Strukturansicht, die einen Stammknoten für Land/Region für die Vereinigten Staaten, untergeordnete Knoten für die Staaten Pennsylvania und Washington und Strukturelemente für Städte in diesen Staaten besteht. Dieses Codebeispiel legt den Pennsylvania-Knoten auf deaktiviert fest.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;7](../../mfc/reference/codesnippet/cpp/ctreectrl-class_41.cpp)]  
  
##  <a name="a-namesetitemtexta--ctreectrlsetitemtext"></a><a name="setitemtext"></a>CTreeCtrl::SetItemText  
 Legt den Text des Elements, angegeben durch `hItem`.  
  
```  
BOOL SetItemText(
    HTREEITEM hItem,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des Elements, dessen Text festgelegt werden.  
  
 `lpszItem`  
 Adresse einer Zeichenfolge, die den neuen Text für das Element enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#34;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_42.cpp)]  
  
##  <a name="a-namesetlinecolora--ctreectrlsetlinecolor"></a><a name="setlinecolor"></a>CTreeCtrl::SetLineColor  
 Rufen Sie diese Memberfunktion zum Festlegen der aktuellen Zeile Farbe für das Strukturansicht-Steuerelement.  
  
```  
COLORREF SetLineColor(COLORREF clrNew = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>Parameter  
 `clrNew`  
 Die neue Farbe.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe der vorherigen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773764), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#35;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_43.cpp)]  
  
##  <a name="a-namesetscrolltimea--ctreectrlsetscrolltime"></a><a name="setscrolltime"></a>CTreeCtrl::SetScrollTime  
 Rufen Sie diese Memberfunktion zum Festlegen der maximalen Scroll Zeit für das Strukturansicht-Steuerelement.  
  
```  
UINT SetScrollTime(UINT uScrollTime);
```  
  
### <a name="parameters"></a>Parameter  
 *uScrollTime*  
 Die neue maximale Scroll Zeit in Millisekunden. Wenn dieser Wert kleiner als 100 ist, wird er auf 100 aufgerundet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Scroll maximale Zeit in Millisekunden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773767), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesettextcolora--ctreectrlsettextcolor"></a><a name="settextcolor"></a>CTreeCtrl::SetTextColor  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773769), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Ein **COLORREF** Wert, der die neue Farbe enthält. Wenn dieses Argument-1 ist, wird das Steuerelement auf die Systemfarbe für die Farbe des Texts zurückgesetzt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **COLORREF** -Wert, der die Textfarbe des vorherigen darstellt. Wenn dieser Wert-1 ist, wurde das Steuerelement die Systemfarbe für die Farbe des Texts verwenden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl Nr.&36;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_44.cpp)]  
  
##  <a name="a-namesettooltipsa--ctreectrlsettooltips"></a><a name="settooltips"></a>CTreeCtrl::SetToolTips  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773772), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndTip`  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) -Objekt, das das Strukturansicht-Steuerelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) -Objekt, das die QuickInfo, die zuvor vom Steuerelement verwendeten enthält oder **NULL** Wenn keine QuickInfos zuvor verwendet wurden.  
  
### <a name="remarks"></a>Hinweise  
 Um QuickInfos zu verwenden, geben die **TVS_NOTOOLTIPS** formatieren bei der Erstellung der `CTreeCtrl` Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CTreeCtrl::GetToolTips](#gettooltips).  
  
##  <a name="a-nameshowinfotipa--ctreectrlshowinfotip"></a><a name="showinfotip"></a>CTreeCtrl::ShowInfoTip  
 Zeigt die QuickInfo für das angegebene Element im aktuellen Strukturansicht Steuerelement.  
  
```  
void ShowInfoTip(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `hItem`|Ein Handle für ein Strukturansicht Element im Steuerelement. Weitere Informationen finden Sie unter der `hItem` Mitglied der [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) Struktur.|  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Unterschied zwischen QuickInfos und Infotipps suchen Sie nach dem Thema "QuickInfos und Infotipps" unter [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322).  
  
 Diese Methode sendet die [TVM_SHOWINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb773779) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesortchildrena--ctreectrlsortchildren"></a><a name="sortchildren"></a>CTreeCtrl::SortChildren  
 Rufen Sie diese Funktion, um die untergeordneten Elemente des angegebenen übergeordneten Elements in einem Strukturansicht-Steuerelement alphabetisch zu sortieren.  
  
```  
BOOL SortChildren(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>Parameter  
 `hItem`  
 Das Handle des übergeordneten Artikels, dessen untergeordnete Elemente sortiert werden sollen. Wenn `hItem` ist **NULL**, Sortierung vom Stamm der Struktur fort.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 `SortChildren`wird nicht durch die Struktur rekursiv; nur die unmittelbar untergeordneten Elemente des `hItem` sortiert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#37;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_45.cpp)]  
  
##  <a name="a-namesortchildrencba--ctreectrlsortchildrencb"></a><a name="sortchildrencb"></a>CTreeCtrl::SortChildrenCB  
 Rufen Sie diese Funktion zum Sortieren der Elemente in Struktur anzeigen, die über eine anwendungsdefinierte Rückruffunktion, die die Artikel vergleicht.  
  
```  
BOOL SortChildrenCB(LPTVSORTCB pSort);
```  
  
### <a name="parameters"></a>Parameter  
 *pSort*  
 Zeiger auf eine [TVSORTCB](http://msdn.microsoft.com/library/windows/desktop/bb773462) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Struktur der Vergleichsfunktion, **LpfnCompare**, müssen einen negativen Wert zurück, wenn das erste Element der zweiten steht, wird ein positiver Wert, wenn das erste Element muss die zweite oder NULL, wenn die beiden Elemente äquivalent sind.  
  
 Der `lParam1` und `lParam2` Parameter entsprechen den **lParam** Mitglied der [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) Struktur für die beiden verglichenen Elemente. Die `lParamSort` Parameter entspricht der **lParam** Mitglied der `TV_SORTCB` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTreeCtrl&#38;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_46.cpp)]  
  
 [!code-cpp[NVC_MFC_CTreeCtrl Nr.&39;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_47.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CImageList-Klasse](../../mfc/reference/cimagelist-class.md)

