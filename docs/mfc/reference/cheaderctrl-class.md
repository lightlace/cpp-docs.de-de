---
title: CHeaderCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class
- Windows common controls [C++], CHeaderCtrl
- header controls, CHeaderCtrl class
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
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
ms.openlocfilehash: ab3cef5d72bad004832cb85ca4b1b3604eb3a18c
ms.lasthandoff: 02/24/2017

---
# <a name="cheaderctrl-class"></a>CHeaderCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Headersteuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Erstellt ein `CHeaderCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Löscht alle Filter für ein Steuerelement.|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|Löscht den Filter für ein Steuerelement.|  
|[CHeaderCtrl](#create)|Erstellt ein Steuerelement und fügt es ein `CHeaderCtrl` Objekt.|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Erstellt eine transparente Version eines Elements Bild in einem Headersteuerelement.|  
|[CHeaderCtrl::CreateEx](#createex)|Erstellt ein Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CListCtrl` Objekt.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|Löscht ein Element aus einem Kopfzeilen-Steuerelement.|  
|[CHeaderCtrl::DrawItem](#drawitem)|Zeichnet das angegebene Element von einem Kopfzeilen-Steuerelement.|  
|[CHeaderCtrl::EditFilter](#editfilter)|Startet den angegebenen Filter von einem Kopfzeilen-Steuerelement bearbeiten.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Ruft die Breite des Rands einer Bitmap in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Ruft den Bezeichner des Elements im aktuellen Kopfzeilen-Steuerelement den Fokus hat.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|Ruft das Handle einer Bildliste zum Zeichnen Headerelemente in einem Headersteuerelement ab.|  
|[CHeaderCtrl:: GetItem](#getitem)|Ruft Informationen über ein Element in einem Header-Steuerelement.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Elemente in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Ruft das umschließende Rechteck Informationen für die angegebene Dropdown-Schaltfläche in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck für ein bestimmtes Element in einem Headersteuerelement ab.|  
|[CHeaderCtrl:: GetOrderArray](#getorderarray)|Ruft die links-nach-rechts-Reihenfolge der Elemente in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Ruft das umschließende Rechteck für der Überlaufschaltfläche für das aktuelle Kopfzeilen-Steuerelement ab.|  
|[CHeaderCtrl::HitTest](#hittest)|Bestimmt, welches Headerelement ggf. an einem angegebenen Punkt befindet.|  
|[InsertItem](#insertitem)|Fügt ein neues Element in einem Header-Steuerelement.|  
|[CHeaderCtrl:: Layout](#layout)|Ruft die Größe und Position von einem Kopfzeilen-Steuerelement in einem bestimmten Rechteck.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Ruft den Indexwert für ein Element basierend auf der Reihenfolge, in dem Kopfzeilen-Steuerelement ab.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Legt die Breite des Rands einer Bitmap in einem Header-Steuerelement fest.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Legt das Timeout-Intervall zwischen dem Zeitpunkt, der eine Änderung in die FilterAttribute erfolgt und die Buchung eine `HDN_FILTERCHANGE` Benachrichtigung.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Setzt den Fokus auf ein Element der angegebenen Header im aktuellen Kopfzeilen-Steuerelement.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Ändert den Unterteiler zwischen Header-Elemente an, dass eine manuelle Ziehen und Ablegen des Headerelements.|  
|[:: SetImageList](#setimagelist)|Weist eine Bildliste einem Kopfzeilen-Steuerelement.|  
|[CHeaderCtrl::SetItem](#setitem)|Legt die Attribute des angegebenen Elements in einem Header-Steuerelement fest.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Legt die links-nach-rechts-Reihenfolge der Elemente in einem Kopfzeilen-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Headersteuerelement ist ein Fenster, das in der Regel über einen Satz von Spalten von Text oder Zahlen positioniert ist. Es enthält einen Titel für jede Spalte, und es kann in Bereiche unterteilt werden. Der Benutzer kann die Trennblättern ziehen, die Trennung der Teile, um die Breite der einzelnen Spalten festzulegen. Zur Veranschaulichung von einem Kopfzeilen-Steuerelement finden Sie unter [Headersteuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Dieses Steuerelement (und somit die `CHeaderCtrl` Klasse) ist nur für Programme, die Ausführung unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Funktionen, die für allgemeine Steuerelemente von Windows 95/Internet Explorer 4.0 hinzugefügt umfasst Folgendes:  
  
-   Header Element benutzerdefinierte Reihenfolge.  
  
-   Headerelement- Drag & drop für Header-Elemente neu anordnen. Verwenden der `HDS_DRAGDROP` formatieren bei der Erstellung der `CHeaderCtrl` Objekt.  
  
-   Spalte Headertext ständig bei der Spalte angezeigt werden kann. Verwenden der `HDS_FULLDRAG` formatieren, wenn Sie erstellen ein `CHeaderCtrl` Objekt.  
  
-   Header hot Track, das Headerelement hervorgehoben, wenn der Mauszeiger darüber bewegt wird. Verwenden der `HDS_HOTTRACK` formatieren bei der Erstellung der `CHeaderCtrl` Objekt.  
  
-   Bildlisten unterstützt. Header-Elemente können in gespeicherte Bilder enthalten ein `CImageList` Objekt oder Text.  
  
 Weitere Informationen zur Verwendung von `CHeaderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CHeaderCtrl](../../mfc/using-cheaderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl  
 Erstellt ein `CHeaderCtrl`-Objekt.  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#1;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 Löscht alle Filter für ein Steuerelement.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) mit einem Spaltenwert der Wert –&1;, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#2;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 Löscht den Filter für ein Steuerelement.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>Parameter  
 `nColumn`  
 Spaltenwert, der angibt, welcher filter deaktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&3;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="create"></a>CHeaderCtrl  
 Erstellt ein Steuerelement und fügt es ein `CHeaderCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Kopfzeilen-Steuerelement-Stil. Eine Beschreibung der Header Steuerelementtypen, finden Sie unter [Steuerelementtypen für die Header](http://msdn.microsoft.com/library/windows/desktop/bb775241) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Gibt des Kopfzeilen-Steuerelements Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Kopfzeilen-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Kopfzeilen-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CHeaderCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die das Kopfzeilen-Steuerelement erstellt, und fügt es der `CHeaderCtrl` Objekt.  
  
 Zusätzlich zu den Steuerelementtypen für die Header können Sie die folgenden allgemeinen Steuerelementtypen bestimmt, wie das Kopfzeilen-Steuerelement positioniert und angepasst (finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) für Weitere Informationen):  
  
- `CCS_BOTTOM`Bewirkt, dass das Steuerelement selbst am unteren Rand des übergeordneten Fensters Clientbereich positionieren und die Breite ist identisch mit dem übergeordneten Breite des Fensters.  
  
- `CCS_NODIVIDER`Verhindert, dass ein zwei Pixel hervorheben, die am oberen Rand des Steuerelements gezeichnet werden.  
  
- `CCS_NOMOVEY`Bewirkt, dass das Steuerelement verschieben selbst horizontal, aber nicht vertikal als Antwort auf eine `WM_SIZE` Nachricht. Wenn die `CCS_NORESIZE` -Format wird verwendet, gilt dieses Format nicht. Header-Steuerelemente haben dieses Format standardmäßig.  
  
- `CCS_NOPARENTALIGN`Verhindert, dass das Steuerelement automatisch an den oberen oder unteren Rand des übergeordneten Fensters verschieben. Stattdessen wird das Steuerelement seine Position innerhalb des übergeordneten Fensters trotz Änderungen auf die Größe des übergeordneten Fensters. Wenn die `CCS_TOP` oder `CCS_BOTTOM` Format wird auch verwendet, ist die Höhe der standardmäßigen angepasst, aber die Position und die Breite unverändert bleibt.  
  
- `CCS_NORESIZE`Verhindert, dass das Steuerelement die Standardhöhe und-Breite verwenden, wenn Sie die anfängliche Größe oder eine neue Größe festlegen. Stattdessen verwendet das Steuerelement an die angegebene Breite und Höhe in der Anforderung für die Erstellung oder anpassen.  
  
- `CCS_TOP`Bewirkt, dass das Steuerelement selbst am oberen Rand des übergeordneten Fensters Clientbereich positionieren und die Breite ist identisch mit dem übergeordneten Breite des Fensters.  
  
 Sie können auch die folgenden Fensterstile anwenden, um ein Steuerelement (siehe [Fensterstile](../../mfc/reference/window-styles.md) für Weitere Informationen):  
  
- **WS_CHILD** erstellt ein untergeordnetes Fenster. Kann nicht mit dem `WS_POPUP`-Stil verwendet werden.  
  
- **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen in der der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten wechseln kann. Alle Steuerelemente, die mit definiert die **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Style-Gruppe und startet die nächste Gruppe (d. h. eine Gruppe endet, an dem die nächste beginnt).  
  
- **WS_TABSTOP** gibt eine Reihe von Steuerelementen, die über die der Benutzer mithilfe der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer zum nächsten Steuerelement angegeben, indem die **WS_TABSTOP** Stil.  
  
 Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="createex"></a>CHeaderCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnen sie die `CHeaderCtrl` Objekt.  
  
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
 Format des Headersteuerelements. Eine Beschreibung der Header Steuerelementtypen, finden Sie unter [Steuerelementtypen für die Header](http://msdn.microsoft.com/library/windows/desktop/bb775241) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Finden Sie unter [erstellen](#create) eine Liste der zusätzlichen Formatvorlagen.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="createdragimage"></a>CHeaderCtrl::CreateDragImage  
 Erstellt eine transparente Version eines Elements Bild in einem Headersteuerelement.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Elements in dem Kopfzeilen-Steuerelement. Das Bild, das diesem Element zugeordnet ist die Grundlage für das transparente Bild.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, wenn erfolgreich, andernfalls **NULL**. Die zurückgegebene Liste enthält nur ein Bild.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Es wird zur Unterstützung von Header-Element ziehen und Ablegen bereitgestellt.  
  
 Das `CImageList` Objekt, dem der zurückgegebene Zeiger ist ein temporäres Objekt und wird in der nächsten Zeit im Leerlauf Verarbeitung gelöscht.  
  
##  <a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
 Löscht ein Element aus einem Kopfzeilen-Steuerelement.  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt den nullbasierten Index des zu löschenden Elements.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&5;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="drawitem"></a>CHeaderCtrl::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Header-Steuerelements ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) Struktur, die Beschreibung des Artikels gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CHeaderCtrl` Objekt.  
  
 Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="editfilter"></a>CHeaderCtrl::EditFilter  
 Startet den angegebenen Filter von einem Kopfzeilen-Steuerelement bearbeiten.  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>Parameter  
 `nColumn`  
 Die Spalte zu bearbeiten.  
  
 `bDiscardChanges`  
 Ein Wert, der angibt, wie den Benutzer behandelt die Änderungen bearbeiten, wenn der Benutzer gerade den Filter bearbeiten bei der [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312) Nachricht gesendet wird.  
  
 Geben Sie `true` , die vom Benutzer vorgenommenen Änderungen zu verwerfen oder `false` , die vom Benutzer vorgenommenen Änderungen zu akzeptieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#7;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 Ruft die Breite des Rands einer Bitmap in einem Headersteuerelement ab.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Bitmap Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#8;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 Ruft den Index des Elements, das in der aktuellen Kopfzeilen-Steuerelement den Fokus besitzt.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Headerelements, das den Fokus besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. auf dem aktuellen Kopfzeilen-Steuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `SetFocusedItem` und `GetFocusedItem` Methoden. In einem früheren Abschnitt des Codes haben wir ein Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. Im folgenden Beispiel legt fest, und bestätigen, dass die letzte Spaltenüberschrift wie das Element den Fokus.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 Ruft das Handle einer Bildliste zum Zeichnen Headerelemente in einem Headersteuerelement ab.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Das `CImageList` Objekt, dem der zurückgegebene Zeiger ist ein temporäres Objekt und wird in der nächsten Zeit im Leerlauf Verarbeitung gelöscht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#9;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="getitem"></a>CHeaderCtrl:: GetItem  
 Ruft Informationen über ein Steuerelement-Headerelement.  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt den nullbasierten Index des abzurufenden Elements.  
  
 `pHeaderItem`  
 Zeiger auf eine [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) -Struktur, die das neue Element empfängt. Diese Struktur wird verwendet, mit der `InsertItem` und `SetItem` Memberfunktionen. Legen Sie Attribute in der **Maske** Element stellen Sie sicher, dass die Werte in die entsprechenden Elemente bei der Rückgabe ordnungsgemäß ausgefüllt sind. Wenn die **Maske** Element auf&0; (null) festgelegt ist, Werte in anderen Strukturelemente sind bedeutungslos.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#10;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 Ruft die Anzahl der Elemente in einem Headersteuerelement ab.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Header-Steuerelemente bei Erfolg; andernfalls – 1.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl::DeleteItem](#deleteitem).  
  
##  <a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 Ruft das umschließende Rechteck der Dropdown-Schaltfläche für ein Headerelement im aktuellen Kopfzeilen-Steuerelement ab.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iItem`|Nullbasierte Index des Headerelements, dessen Stil ist `HDF_SPLITBUTTON`. Weitere Informationen finden Sie unter der `fmt` Mitglied der [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) Struktur.|  
|[out] `lpRect`|Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die umschließende Rechteck Informationen zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Funktion erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. auf dem aktuellen Kopfzeilen-Steuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `GetItemDropDownRect` Methode. In einem früheren Abschnitt des Codes haben wir ein Steuerelement mit fünf Spalten erstellt. Im folgenden Codebeispiel zeichnet ein 3D Rechteck um die Position in der ersten Spalte, die für die Header Dropdown-Schaltfläche reserviert ist.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 Ruft das umschließende Rechteck für ein bestimmtes Element in einem Headersteuerelement ab.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Headerelements-Steuerelement.  
  
 `lpRect`  
 Ein Zeiger auf die Adresse einer [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die umschließende Rechteck Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert das Verhalten der Win32-Nachricht [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getorderarray"></a>CHeaderCtrl:: GetOrderArray  
 Ruft die links-nach-rechts-Reihenfolge der Elemente in einem Headersteuerelement ab.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>Parameter  
 `piArray`  
 Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Kopfzeilen-Steuerelement in der Reihenfolge empfängt, in dem sie von links nach rechts angezeigt werden.  
  
 `iCount`  
 Die Anzahl der Header-Steuerelemente. Darf nicht negativ sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Es wird zur Unterstützung Header Elementreihenfolge bereitgestellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#11;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 Ruft das umschließende Rechteck der Überlaufschaltfläche des aktuellen Headersteuerelements ab.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpRect`|Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die umschließende Rechteck Informationen erhält.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Funktion erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Enthält das Kopfzeilen-Steuerelement mehr Elemente als gleichzeitig angezeigt werden können, kann das Steuerelement eine Überlaufschaltfläche, die Verschiebt Elemente angezeigt, die nicht sichtbar sind. Das Header-Steuerelement müssen die `HDS_OVERFLOW` und `HDF_SPLITBUTTON` , das der Überlaufschaltfläche angezeigt. Das umschließende Rechteck die Überlaufschaltfläche einschließt und existiert nur, wenn der Überlaufschaltfläche angezeigt wird. Weitere Informationen finden Sie unter [Steuerelementtypen für die Header](http://msdn.microsoft.com/library/windows/desktop/bb775241).  
  
 Diese Methode sendet die [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. auf dem aktuellen Kopfzeilen-Steuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `GetOverflowRect` Methode. In einem früheren Abschnitt des Codes haben wir ein Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. Wenn einige Spalten nicht sichtbar sind, zeichnet das Kopfzeilen-Steuerelement eine Überlaufschaltfläche. Im folgenden Codebeispiel zeichnet ein 3D Rechteck, um die Position der Schaltfläche "Überlauf".  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&3;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="hittest"></a>CHeaderCtrl::HitTest  
 Bestimmt, welches Headerelement ggf. an einem angegebenen Punkt befindet.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in, out] `phdhti`|Zeiger auf eine [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) -Struktur, gibt den Punkt zu testen und die Ergebnisse des Tests empfängt.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Header-Elements, sofern vorhanden, an der angegebenen Position; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. auf dem aktuellen Kopfzeilen-Steuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `HitTest` Methode. In einem früheren Abschnitt dieses Codebeispiels haben wir ein Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. In diesem Beispiel gibt den Index der Spalte, wenn es sichtbar ist, und&1;, wenn die Spalte nicht sichtbar ist.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4;1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="insertitem"></a>InsertItem  
 Fügt ein neues Element in einem Header-Steuerelement am angegebenen Index.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Der nullbasierte Index des einzufügenden Elements. Wenn der Wert&0; (null) ist, wird das Element am Anfang des Headersteuerelements eingefügt. Wenn der Wert größer als der maximale Wert ist, wird das Element am Ende des Headersteuerelements eingefügt.  
  
 *phdi*  
 Zeiger auf eine [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) -Struktur, die Informationen über das Element eingefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des neuen Elements, wenn erfolgreich; andernfalls – 1.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#12;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="layout"></a>CHeaderCtrl:: Layout  
 Ruft die Größe und Position von einem Kopfzeilen-Steuerelement in einem bestimmten Rechteck.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>Parameter  
 *pHeaderLayout*  
 Zeiger auf eine [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) -Struktur, die Informationen zum Festlegen der Größe und Position von einem Kopfzeilen-Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um den entsprechenden Dimensionen für ein neues Steuerelement zu bestimmen, die das angegebene Rechteck einnehmen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#13;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 Ruft den Indexwert für ein Element basierend auf der Reihenfolge, in dem Kopfzeilen-Steuerelement ab.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nOrder*  
 Die nullbasierte Reihenfolge, die das Element in das Kopfzeilen-Steuerelement von links nach rechts angezeigt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Elements, basierend auf der Reihenfolge, in dem Kopfzeilen-Steuerelement. Der Index zählt von links nach rechts, beginnend mit 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten des Makros Win32 [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Es wird zur Unterstützung Header Elementreihenfolge bereitgestellt.  
  
##  <a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 Legt die Breite des Rands einer Bitmap in einem Header-Steuerelement fest.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Breite in Pixel, der den Rand, der eine Bitmap in einem vorhandenen Header umgibt angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Bitmap Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&14;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 Legt das Timeout-Intervall zwischen dem Zeitpunkt, der eine Änderung in die FilterAttribute erfolgt und die Buchung von einer [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) Benachrichtigung.  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeOut*  
 Der Timeoutwert in Millisekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Steuerelements Filter geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl&#15;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 Setzt den Fokus auf ein Element der angegebenen Header im aktuellen Kopfzeilen-Steuerelement.  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iItem`|Nullbasierte Index des Headerelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. auf dem aktuellen Kopfzeilen-Steuerelement verwendet. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&6;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `SetFocusedItem` und `GetFocusedItem` Methoden. In einem früheren Abschnitt des Codes haben wir ein Steuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. Im folgenden Beispiel legt fest, und bestätigen, dass die letzte Spaltenüberschrift wie das Element den Fokus.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4&4;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 Ändert den Unterteiler zwischen Header-Elemente an, dass eine manuelle Ziehen und Ablegen des Headerelements.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Die Position des Zeigers. Das Header-Steuerelement werden die entsprechenden Unterteilung anhand des Zeigers Position hervorgehoben.  
  
 `nIndex`  
 Der Index des Unterteilers hervorgehoben.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Unterteilers hervorgehoben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Es wird zur Unterstützung von Header-Element ziehen und Ablegen bereitgestellt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl Nr.&16;](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="setimagelist"></a>:: SetImageList  
 Weist eine Bildliste einem Kopfzeilen-Steuerelement.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf ein `CImageList` Objekt enthält die Liste der Images, die dem Kopfzeilen-Steuerelement zugewiesen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CImageList](../../mfc/reference/cimagelist-class.md) Objekt zuvor dem Kopfzeilen-Steuerelement zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Das `CImageList` Objekt, dem der zurückgegebene Zeiger ist ein temporäres Objekt und wird in der nächsten Zeit im Leerlauf Verarbeitung gelöscht.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl::GetImageList](#getimagelist).  
  
##  <a name="setitem"></a>CHeaderCtrl::SetItem  
 Legt die Attribute des angegebenen Elements in einem Header-Steuerelement fest.  
  
```  
BOOL SetItem(
    int nPos,  
    HDITEM* pHeaderItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Der nullbasierte Index des Elements, das bearbeitet werden.  
  
 `pHeaderItem`  
 Zeiger auf eine [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) -Struktur, die Informationen über das neue Element enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl:: GetItem](#getitem).  
  
##  <a name="setorderarray"></a>CHeaderCtrl::SetOrderArray  
 Legt die links-nach-rechts-Reihenfolge der Elemente in einem Kopfzeilen-Steuerelement fest.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>Parameter  
 `iCount`  
 Die Anzahl der Header-Steuerelemente.  
  
 `piArray`  
 Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Kopfzeilen-Steuerelement in der Reihenfolge empfängt, in dem sie von links nach rechts angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten des Makros Win32 [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Es wird zur Unterstützung Header Elementreihenfolge bereitgestellt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl:: GetOrderArray](#getorderarray).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)   
 [CImageList-Klasse](../../mfc/reference/cimagelist-class.md)

