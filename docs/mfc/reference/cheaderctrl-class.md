---
title: CHeaderCtrl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3731d6d7a1455dc51ee03ea942666cbfc0f48e27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Headersteuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|Erstellt ein `CHeaderCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|Löscht alle Filter für ein Headersteuerelement.|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|Löscht den Filter für ein Headersteuerelement.|  
|[CHeaderCtrl](#create)|Erstellt ein Headersteuerelement, und fügt es einer `CHeaderCtrl` Objekt.|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|Erstellt eine transparente Abbildversion, ein Element in einem Headersteuerelement an.|  
|[CHeaderCtrl::CreateEx](#createex)|Erstellt ein Headersteuerelement mit der angegebenen erweiterten Fensterstile und fügt es einer `CListCtrl` Objekt.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|Löscht ein Element aus einem Header-Steuerelement.|  
|[CHeaderCtrl::DrawItem](#drawitem)|Zeichnet das angegebene Element eines Steuerelements Header an.|  
|[CHeaderCtrl::EditFilter](#editfilter)|Startet den angegebenen Filter von einem Headersteuerelement bearbeiten.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|Ruft die Breite des Rands einer Bitmap in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|Ruft den Bezeichner des Elements im aktuellen Headersteuerelement, das Fokus besitzt.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|Ruft das Handle des einer Bildliste zum Zeichnen verwendeten Headerelemente in einem Headersteuerelement ab.|  
|[CHeaderCtrl:: GetItem](#getitem)|Ruft Informationen zu einem Element in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Elemente in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|Ruft das umschließende Rechteck-Informationen für die angegebene Dropdown-Schaltfläche in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck für ein bestimmtes Element in einem Headersteuerelement ab.|  
|[CHeaderCtrl:: GetOrderArray](#getorderarray)|Ruft die links-nach-rechts-Reihenfolge der Elemente in einem Headersteuerelement ab.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|Ruft das umschließende Rechteck der Überlaufschaltfläche für den aktuellen Header-Steuerelement ab.|  
|[CHeaderCtrl::HitTest](#hittest)|Bestimmt, welche Headerelement, sofern vorhanden, an einem bestimmten Punkt befindet.|  
|[InsertItem](#insertitem)|Fügt ein neues Element in einem Headersteuerelement an.|  
|[CHeaderCtrl:: Layout](#layout)|Ruft die Größe und Position eines Steuerelements Header innerhalb eines angegebenen Rechtecks.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|Ruft den Indexwert für ein Element basierend auf der Reihenfolge im Headersteuerelement ab.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|Legt die Breite des Rands einer Bitmap in einem Headersteuerelement fest.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|Legt das Timeout-Intervall zwischen dem Zeitpunkt, die eine Änderung in die FilterAttribute erfolgt und der Bereitstellung einer `HDN_FILTERCHANGE` Benachrichtigung.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|Legt den Fokus auf ein Element der angegebenen Header im aktuellen Headersteuerelement fest.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|Ziehen der Unterteiler zwischen Headerelemente an, dass eine manuelle Änderungen and -Drop ein Headerelement.|  
|[:: SetImageList](#setimagelist)|Ein Headersteuerelement eine Bildliste zugewiesen.|  
|[CHeaderCtrl::SetItem](#setitem)|Legt die Attribute des angegebenen Elements in einem Headersteuerelement fest.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|Legt die links-nach-rechts-Reihenfolge der Elemente in einem Headersteuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Headersteuerelement ist ein Fenster, das in der Regel über einen Satz von Spalten von Text oder Zahlen positioniert ist. Sie enthält einen Titel für jede Spalte, und sie können in Bereiche unterteilt werden. Benutzer können die Trennblättern ziehen, bei denen die Teile, um die Breite der einzelnen Spalten festzulegen. Eine Abbildung von einem Headersteuerelement, finden Sie unter [Headersteuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 Dieses Steuerelement (und somit die `CHeaderCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Funktionen für allgemeine Steuerelemente für Windows 95/Internet Explorer 4.0 umfasst Folgendes:  
  
-   Header Element benutzerdefinierte Reihenfolge.  
  
-   Headerelement- Drag & drop zum Neuordnen der Headerelemente. Verwenden der `HDS_DRAGDROP` formatieren, bei der Erstellung der `CHeaderCtrl` Objekt.  
  
-   Spalte Headertext ständig während der Größe der Spalte angezeigt werden kann. Verwenden der `HDS_FULLDRAG` Format zuzuweisen, wenn Sie erstellen ein `CHeaderCtrl` Objekt.  
  
-   Header hot Track für, die das Headerelement hervorgehoben wird, wenn der Mauszeiger darüber bewegt wird. Verwenden der `HDS_HOTTRACK` formatieren, bei der Erstellung der `CHeaderCtrl` Objekt.  
  
-   Unterstützung für Image-Liste. Header-Elemente können Images im enthalten eine `CImageList` Objekt oder Text.  
  
 Weitere Informationen zur Verwendung von `CHeaderCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CHeaderCtrl](../../mfc/using-cheaderctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 [!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 Löscht alle Filter für ein Headersteuerelement.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) mit einem Spaltenwert "-1", wie im Windows SDK beschrieben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 Löscht den Filter für ein Headersteuerelement.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>Parameter  
 `nColumn`  
 Der Spaltenwert, der angibt, welcher filter um zu löschen.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="create"></a>CHeaderCtrl  
 Erstellt ein Headersteuerelement, und fügt es einer `CHeaderCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Headersteuerelement-Stil. Eine Beschreibung der Steuerelementtypen für die Header, finden Sie unter [Steuerelementtypen für die Header](http://msdn.microsoft.com/library/windows/desktop/bb775241) im Windows SDK.  
  
 `rect`  
 Gibt an, Größe und Position des Headersteuerelements. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Das Headersteuerelement übergeordnetes Fenster, in der Regel gibt eine `CDialog`. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt die Header-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CHeaderCtrl` Objekt in zwei Schritten. Zuerst wird den Konstruktor aufrufen und dann **erstellen**, dem Headersteuerelement erstellt, und fügt es der `CHeaderCtrl` Objekt.  
  
 Zusätzlich zu den Steuerelementtypen für die Header können Sie die folgenden allgemeinen Steuerelementtypen bestimmt, wie das Header-Steuerelement positioniert und ändert die Größe selbst (finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) für Weitere Informationen):  
  
- `CCS_BOTTOM`Bewirkt, dass das Steuerelement selbst am unteren Rand des übergeordneten Fensters Clientbereich positionieren und die Breite als übergeordnetes Element identisch sein Breite des Fensters.  
  
- `CCS_NODIVIDER`Verhindert, dass eine zwei-Pixel-Hervorhebung, die am oberen Rand des Steuerelements gezeichnet werden.  
  
- `CCS_NOMOVEY`Bewirkt, dass das Steuerelement die Größe und Position selbst horizontal, aber nicht vertikal als Antwort auf eine `WM_SIZE` Nachricht. Wenn die `CCS_NORESIZE` Stil verwendet wird, wird dieses Format ist nicht gültig. Headersteuerelemente haben dieses Format wird standardmäßig an.  
  
- `CCS_NOPARENTALIGN`Verhindert, dass das Steuerelement automatisch an der oberen bzw. unteren Rand des übergeordneten Fensters verschieben. Stattdessen wird das Steuerelement seine Position innerhalb des übergeordneten Fensters trotz Änderungen auf die Größe des übergeordneten Fensters. Wenn die `CCS_TOP` oder `CCS_BOTTOM` Format wird auch verwendet, die Höhe wird auf den Standardwert ausgerichtet, aber die Position und die Breite, bleiben unverändert.  
  
- `CCS_NORESIZE`Verhindert, dass das Steuerelement die Standardbreite und-Höhe verwenden, wenn Sie die anfängliche Größe oder eine neue Größe festlegen. Stattdessen verwendet das Steuerelement an die Breite und Höhe, die in der Anforderung für die Erstellung oder Größe angegeben.  
  
- `CCS_TOP`Bewirkt, dass das Steuerelement selbst am oberen Rand des übergeordneten Fensters Clientbereich positionieren und die Breite als übergeordnetes Element identisch sein Breite des Fensters.  
  
 Sie können auch die folgenden Fensterstile anwenden, um einem Headersteuerelement (finden Sie unter [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) für Weitere Informationen):  
  
- **WS_CHILD** erstellt ein untergeordnetes Fenster. Kann nicht mit dem `WS_POPUP`-Stil verwendet werden.  
  
- **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen in der der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten wechseln kann. Alle Steuerelemente, die definiert, mit der **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Style-Gruppe und startet die nächste Gruppe (d. h. eine Gruppe endet, an die nächste beginnt).  
  
- **WS_TABSTOP** gibt eines von beliebig vielen Steuerelementen, zwischen denen der Benutzer mit der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer auf das nächste Steuerelement gemäß der **WS_TABSTOP** Stil.  
  
 Wenn Sie die erweiterten Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Das Headersteuerelement-Stil. Eine Beschreibung der Steuerelementtypen für die Header, finden Sie unter [Steuerelementtypen für die Header](http://msdn.microsoft.com/library/windows/desktop/bb775241) im Windows SDK. Finden Sie unter [erstellen](#create) eine Liste der zusätzlichen Formatvorlagen.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="createdragimage"></a>CHeaderCtrl::CreateDragImage  
 Erstellt eine transparente Abbildversion, ein Element in einem Headersteuerelement an.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Elements innerhalb des Headersteuerelements. Das Bild zu diesem Element zugewiesen bildet die Grundlage für das transparente Bild.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) -Objekt, wenn erfolgreich; andernfalls **NULL**. Die zurückgegebene Liste enthält nur ein Bild an.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308)gemäß der Beschreibung im Windows SDK. Es dient der Header Element Drag & Drop unterstützen.  
  
 Die `CImageList` Objekt, zu dem der zurückgegebene Zeiger weist, ist ein temporäres Objekt und wird in der nächsten Zeit im Leerlauf Verarbeitung gelöscht.  
  
##  <a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
 Löscht ein Element aus einem Header-Steuerelement.  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt den nullbasierten Index des Elements, das gelöscht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="drawitem"></a>CHeaderCtrl::DrawItem  
 Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Header-Steuerelements ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) Struktur, die das Element zu zeichnenden beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CHeaderCtrl` Objekt.  
  
 Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="editfilter"></a>CHeaderCtrl::EditFilter  
 So bearbeiten Sie die angegebenen Filter eines Steuerelements Header beginnt.  
  
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
  
 Geben Sie `true` , die vom Benutzer vorgenommenen Änderungen zu verwerfen oder `false` , die vom Benutzer vorgenommene Änderungen zu übernehmen.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 Ruft die Breite des Rands einer Bitmap in einem Headersteuerelement ab.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Bitmap Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 Ruft den Index des Elements, das in den aktuellen Header-Steuerelement den Fokus besitzt.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Headerelements, das den Fokus besitzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. verwendet, um die aktuellen Headersteuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `SetFocusedItem` und `GetFocusedItem` Methoden. In einem früheren Abschnitt des Codes wurde dem Headersteuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. Im folgende Beispiel legt fest, und anschließend vergewissert sich, dass die letzte Spaltenüberschrift wie das Element den Fokus.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 Ruft das Handle des einer Bildliste zum Zeichnen verwendeten Headerelemente in einem Headersteuerelement ab.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CImageList](../../mfc/reference/cimagelist-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332)gemäß der Beschreibung im Windows SDK. Die `CImageList` Objekt, zu dem der zurückgegebene Zeiger weist, ist ein temporäres Objekt und wird in der nächsten Zeit im Leerlauf Verarbeitung gelöscht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="getitem"></a>CHeaderCtrl:: GetItem  
 Ruft Informationen zu einem Headerelement-Steuerelement ab.  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt den nullbasierten Index des abzurufenden Elements.  
  
 `pHeaderItem`  
 Zeiger auf eine [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) -Struktur, die das neue Element empfängt. Diese Struktur wird verwendet, mit der `InsertItem` und `SetItem` Memberfunktionen. Flags festgelegt wird, der **Maske** Element stellen Sie sicher, dass die Werte in die entsprechenden Elemente nach der Rückgabe ordnungsgemäß ausgefüllt werden. Wenn die **Maske** Element auf 0 (null) festgelegt ist, sind bedeutungslos, Werte in den anderen Strukturelementen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 Ruft die Anzahl der Elemente in einem Headersteuerelement ab.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Header-Steuerelemente bei Erfolg; andernfalls - 1.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl::DeleteItem](#deleteitem).  
  
##  <a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 Ruft das umschließende Rechteck der Dropdown-Schaltfläche für ein Headerelement im aktuellen Headersteuerelement ab.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iItem`|Nullbasierten Index des ein Headerelement, dessen Format ist `HDF_SPLITBUTTON`. Weitere Informationen finden Sie unter der `fmt` Mitglied der [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) Struktur.|  
|[out] `lpRect`|Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, um die umschließende Rechteck Informationen zu erhalten.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Funktion erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. verwendet, um die aktuellen Headersteuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `GetItemDropDownRect` Methode. In einem früheren Abschnitt des Codes wurde dem Headersteuerelement mit fünf Spalten erstellt. Im folgenden Codebeispiel wird zeichnet ein 3D Rechteck an der Stelle, auf die erste Spalte, die für die Header Dropdown-Schaltfläche reserviert ist.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 Ruft das umschließende Rechteck für ein bestimmtes Element in einem Headersteuerelement ab.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index, der das Headerelement-Steuerelement.  
  
 `lpRect`  
 Ein Zeiger auf die Adresse einer [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck-Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode implementiert, das Verhalten der Win32-Nachricht [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="getorderarray"></a>CHeaderCtrl:: GetOrderArray  
 Ruft die links-nach-rechts-Reihenfolge der Elemente in einem Headersteuerelement ab.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>Parameter  
 `piArray`  
 Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Header-Steuerelement in der Reihenfolge empfängt in dem sie von links nach rechts angezeigt werden.  
  
 `iCount`  
 Die Anzahl der Header-Steuerelemente. Darf nicht negativ sein.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343)gemäß der Beschreibung im Windows SDK. Es dient der Elementreihenfolge Header unterstützen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 Ruft das umschließende Rechteck der Überlaufschaltfläche des aktuellen Headersteuerelements ab.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpRect`|Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck-Informationen erhält.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Funktion erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Enthält das Headersteuerelement mehr Elemente als gleichzeitig angezeigt werden können, kann das Steuerelement eine Überlaufschaltfläche, die einen Bildlauf durchführt für Elemente anzeigen, die nicht sichtbar sind. Das Headersteuerelement benötigen die `HDS_OVERFLOW` und `HDF_SPLITBUTTON` Stile dokumentüberlauf-Schaltfläche angezeigt. Das umschließende Rechteck die Überlaufschaltfläche einschließt und existiert nur, wenn die dokumentüberlauf-Schaltfläche angezeigt wird. Weitere Informationen finden Sie unter [Steuerelementtypen für die Header](http://msdn.microsoft.com/library/windows/desktop/bb775241).  
  
 Diese Methode sendet die [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. verwendet, um die aktuellen Headersteuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `GetOverflowRect` Methode. In einem früheren Abschnitt des Codes wurde dem Headersteuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. Wenn einige Spalten nicht sichtbar sind, zeichnet das Headersteuerelement eine Überlaufschaltfläche. Im folgenden Codebeispiel wird zeichnet ein 3D Rechteck, um den Speicherort der dokumentüberlauf-Schaltfläche.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="hittest"></a>CHeaderCtrl::HitTest  
 Bestimmt, welche Headerelement, sofern vorhanden, an einem bestimmten Punkt befindet.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in, out] `phdhti`|Zeiger auf eine [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) -Struktur, gibt den Punkt zu testen und erhält es die Ergebnisse des Tests.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Header-Elements, sofern vorhanden, an der angegebenen Position; andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. verwendet, um die aktuellen Headersteuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `HitTest` Methode. In einem früheren Abschnitt dieses Codebeispiels wurde dem Headersteuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. In diesem Beispiel gibt den Index der Spalte, wenn es sichtbar ist, und 1, wenn die Spalte nicht sichtbar ist.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="insertitem"></a>InsertItem  
 Fügt ein neues Element in einem Headersteuerelement am angegebenen Index.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Der nullbasierte Index des einzufügenden Elements. Wenn der Wert 0 (null) ist, wird das Element am Anfang des Headersteuerelements eingefügt. Wenn der Wert größer als der maximale Wert ist, wird das Element am Ende des Headersteuerelements eingefügt.  
  
 *phdi*  
 Zeiger auf eine [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) -Struktur, die Informationen zu den einzufügenden Elements enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des neuen Elements, wenn erfolgreich; andernfalls - 1.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="layout"></a>CHeaderCtrl:: Layout  
 Ruft die Größe und Position eines Steuerelements Header innerhalb eines angegebenen Rechtecks.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>Parameter  
 *pHeaderLayout*  
 Zeiger auf eine [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) -Struktur, die Informationen zum Festlegen der Größe und Position eines Steuerelements Header enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird verwendet, um den entsprechenden Dimensionen für einen neuen Header-Steuerelement zu bestimmen, die ein angegebene Rechteck einnehmen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 Ruft den Indexwert für ein Element basierend auf der Reihenfolge im Headersteuerelement ab.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *nOrder*  
 Die nullbasierte Reihenfolge, die das Element im Headersteuerelement, von links nach rechts angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Elements basierend auf der Reihenfolge im Headersteuerelement. Der Index zählt von links nach rechts angezeigt, beginnend mit 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten des Makros Win32 [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355)gemäß der Beschreibung im Windows SDK. Es dient der Elementreihenfolge Header unterstützen.  
  
##  <a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 Legt die Breite des Rands einer Bitmap in einem Headersteuerelement fest.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Breite in Pixel, der den Rand, der eine Bitmap in eine vorhandene Headersteuerelement umgibt angegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Bitmap Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 Legt das Timeout-Intervall zwischen dem Zeitpunkt, die eine Änderung in die FilterAttribute erfolgt und der Bereitstellung einer [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) Benachrichtigung.  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>Parameter  
 *dwTimeOut*  
 Der Timeoutwert in Millisekunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Steuerelements Filter geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 Legt den Fokus auf ein Element der angegebenen Header im aktuellen Headersteuerelement fest.  
  
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
 Diese Methode sendet die [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_headerCtrl`, d. h. verwendet, um die aktuellen Headersteuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel veranschaulicht die `SetFocusedItem` und `GetFocusedItem` Methoden. In einem früheren Abschnitt des Codes wurde dem Headersteuerelement mit fünf Spalten erstellt. Allerdings können Sie ein Spaltentrennzeichen ziehen, damit, dass die Spalte nicht sichtbar ist. Im folgende Beispiel legt fest, und anschließend vergewissert sich, dass die letzte Spaltenüberschrift wie das Element den Fokus.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 Ziehen der Unterteiler zwischen Headerelemente an, dass eine manuelle Änderungen and -Drop ein Headerelement.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Die Position des Zeigers. Das Headersteuerelement werden den entsprechenden Unterteiler basierend auf den Zeiger Position hervorgehoben.  
  
 `nIndex`  
 Der Index des Unterteilers hervorgehoben.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Unterteilers hervorgehoben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363)gemäß der Beschreibung im Windows SDK. Es dient der Header Element Drag & Drop unterstützen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="setimagelist"></a>:: SetImageList  
 Ein Headersteuerelement eine Bildliste zugewiesen.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf ein `CImageList` Objekt, das die Bildliste des Headersteuerelements zuzuweisenden enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CImageList](../../mfc/reference/cimagelist-class.md) Objekts zum Headersteuerelement zuvor zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365)gemäß der Beschreibung im Windows SDK. Die `CImageList` Objekt, zu dem der zurückgegebene Zeiger weist, ist ein temporäres Objekt und wird in der nächsten Zeit im Leerlauf Verarbeitung gelöscht.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl::GetImageList](#getimagelist).  
  
##  <a name="setitem"></a>CHeaderCtrl::SetItem  
 Legt die Attribute des angegebenen Elements in einem Headersteuerelement fest.  
  
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
 Legt die links-nach-rechts-Reihenfolge der Elemente in einem Headersteuerelement fest.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>Parameter  
 `iCount`  
 Die Anzahl der Header-Steuerelemente.  
  
 `piArray`  
 Ein Zeiger auf die Adresse eines Puffers, der die Indexwerte der Elemente im Header-Steuerelement in der Reihenfolge empfängt in dem sie von links nach rechts angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten des Makros Win32 [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369)gemäß der Beschreibung im Windows SDK. Es dient der Elementreihenfolge Header unterstützen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CHeaderCtrl:: GetOrderArray](#getorderarray).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CTabCtrl-Klasse](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)   
 [CImageList-Klasse](../../mfc/reference/cimagelist-class.md)
