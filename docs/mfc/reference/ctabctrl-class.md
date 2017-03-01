---
title: CTabCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabCtrl
dev_langs:
- C++
helpviewer_keywords:
- tab controls
- CTabCtrl class, common controls
- CTabCtrl class
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 21
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
ms.openlocfilehash: e1d8497b444e4dd5ee1e2803c1a763f67e2e0054
ms.lasthandoff: 02/24/2017

---
# <a name="ctabctrl-class"></a>CTabCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Registerkarten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|Erstellt ein `CTabCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|Ein Registerkarten-Steuerelement Anzeigebereich ein Rechteck Fenster berechnet oder berechnet das Fenster Rechteck, das die einen bestimmten Anzeigebereich entsprechen würde.|  
|[CTabCtrl::Create](#create)|Ein Registerkarten-Steuerelement erstellt und mit einer Instanz von einem `CTabCtrl` Objekt.|  
|[CTabCtrl::CreateEx](#createex)|Erstellt ein Registerkarten-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt Sie es mit einer Instanz von einem `CTabCtrl` Objekt.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Entfernt alle Elemente aus einem Registerkarten-Steuerelement.|  
|[CTabCtrl::DeleteItem](#deleteitem)|Entfernt ein Element aus einem Registerkarten-Steuerelement.|  
|[CTabCtrl::DeselectAll](#deselectall)|Setzt die Elemente in einem Registersteuerelement deaktivieren, die gedrückt wurden.|  
|[CTabCtrl::DrawItem](#drawitem)|Zeichnet ein angegebenes Element ein Registerkarten-Steuerelements.|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|Ruft die Registerkarte mit dem aktuellen Fokus des Registerkarten-Steuerelements ab.|  
|[CTabCtrl::GetCurSel](#getcursel)|Bestimmt, die derzeit ausgewählte Registerkarte in einem Registersteuerelement.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die derzeit für das Registerkarten-Steuerelement verwendet werden.|  
|[CTabCtrl::GetImageList](#getimagelist)|Ruft die einem Registerkarten-Steuerelement zugeordnete Bildliste ab.|  
|[CTabCtrl::GetItem](#getitem)|Ruft Informationen zu einer Registerkarte in einem Registerkarten-Steuerelement.|  
|[CTabCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Registerkarten im Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck für eine Registerkarte in einem Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetItemState](#getitemstate)|Ruft den Zustand des angegebenen Steuerelements Registerelements.|  
|[CTabCtrl::GetRowCount](#getrowcount)|Ruft die aktuelle Anzahl der Zeilen mit Registerkarten in einem Registersteuerelement ab.|  
|[CTabCtrl::GetToolTips](#gettooltips)|Ruft das Handle für das ein Registerkarten-Steuerelement zugeordneten QuickInfo-Steuerelement ab.|  
|[CTabCtrl::HighlightItem](#highlightitem)|Legt den Status markieren Sie ein Registerkartenelement fest.|  
|[CTabCtrl::HitTest](#hittest)|Bestimmt, welche Registerkarte ggf. an einer angegebenen Bildschirmposition.|  
|[CTabCtrl:: InsertItem](#insertitem)|Fügt eine neue Registerkarte in einem Registersteuerelement an.|  
|[CTabCtrl::RemoveImage](#removeimage)|Entfernt ein Bild aus einem Registerkarten-Steuerelement.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|Setzt den Fokus auf eine angegebene Registerkarte in einem Registersteuerelement.|  
|[CTabCtrl::SetCurSel](#setcursel)|Wählt eine Registerkarte in einem Registerkarten-Steuerelement aus.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterten Stile für ein Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetImageList](#setimagelist)|Ein Registerkarten-Steuerelement mit einer Bildliste zugewiesen.|  
|[CTabCtrl::SetItem](#setitem)|Legt fest, einige oder alle Attribute einer Registerkarte.|  
|[CTabCtrl::SetItemExtra](#setitemextra)|Legt die Anzahl von Bytes pro Registerkarte für die Anwendung definierte Daten in einem Registersteuerelement reserviert.|  
|[CTabCtrl::SetItemSize](#setitemsize)|Legt die Breite und Höhe eines Elements.|  
|[CTabCtrl::SetItemState](#setitemstate)|Legt den Zustand des angegebenen Steuerelements Registerelements.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Legt die minimale Breite der Elemente in einem Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetPadding](#setpadding)|Legt den Abstand (Auffüllung) aus, um jede Registerkarte Symbol und eine Bezeichnung in einem Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetToolTips](#settooltips)|Ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Registerkarten-Steuerelement" ist vergleichbar mit den Trennblättern in einem Notizbuch oder die Bezeichnungen in eine CAB-Datei. Durch Verwenden eines Registerkarten-Steuerelements können in einer Anwendung mehrere Seiten für denselben Bereich in einem Fenster oder Dialogfeld definiert werden. Jede Seite besteht aus einem Satz von Informationen oder eine Gruppe von Steuerelementen, die von der Anwendung bei der Auswahl der entsprechenden Registerkarte angezeigt. Eine besondere Art von Registerkarten-Steuerelement zeigt die Registerkarten, die Schaltflächen aussehen. Klicken auf eine Schaltfläche sollte sofort zum Ausführen eines Befehls anstelle eine Seite anzeigt.  
  
 Dieses Steuerelement (und somit die `CTabCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen zur Verwendung von `CTabCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-nameadjustrecta--ctabctrladjustrect"></a><a name="adjustrect"></a>CTabCtrl::AdjustRect  
 Ein Registerkarten-Steuerelement Anzeigebereich ein Rechteck Fenster berechnet oder berechnet das Fenster Rechteck, das die einen bestimmten Anzeigebereich entsprechen würde.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `bLarger`  
 Gibt an, welcher Vorgang ausgeführt. Wenn dieser Parameter **TRUE**, `lpRect` gibt ein Rechteck angezeigt und empfängt das entsprechende Fenster Rechteck. Wenn dieser Parameter **FALSE**, `lpRect` gibt ein Rechteck Fenster und das entsprechende Anzeigerechteck empfängt.  
  
 `lpRect`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, gibt das angegebene Rechteck und das berechnete Rechteck empfängt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl&#1;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="a-namecreatea--ctabctrlcreate"></a><a name="create"></a>CTabCtrl::Create  
 Ein Registerkarten-Steuerelement erstellt und mit einer Instanz von einem `CTabCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Registerkarten-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Registerkarte Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760549), beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Finden Sie unter **Hinweise** eine Liste der Window-Stile, die auch auf das Steuerelement angewendet werden können.  
  
 `rect`  
 Gibt an, Größe und Position des Steuerelements. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Registerkarten-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Registerkarten-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die Initialisierung des Objekts erfolgreich, andernfalls war **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CTabCtrl` Objekt in zwei Schritten. Zuerst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die das Registerkarten-Steuerelement erstellt, und fügt es der `CTabCtrl` Objekt.  
  
 Neben der Registerkarte Steuerelementtypen können Sie die folgenden Fensterstile auf ein Registerkarten-Steuerelement anwenden:  
  
- **WS_CHILD** erstellt ein untergeordnetes Fenster, das das Registerkarten-Steuerelement darstellt. Kann nicht mit dem `WS_POPUP`-Stil verwendet werden.  
  
- **WS_VISIBLE** erstellt ein Registerkarten-Steuerelement, das anfänglich sichtbar ist.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen in der der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten wechseln kann. Alle Steuerelemente, die mit definiert die **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Style-Gruppe und startet die nächste Gruppe (d. h. eine Gruppe endet, an dem die nächste beginnt).  
  
- **WS_TABSTOP** gibt eine Reihe von Steuerelementen, die über die der Benutzer mithilfe der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer zum nächsten Steuerelement angegeben, indem die **WS_TABSTOP** Stil.  
  
 Rufen Sie zum Erstellen eines Registerkarten-Steuerelements mit erweiterten Fensterstile [CTabCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl&#2;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="a-namecreateexa--ctabctrlcreateex"></a><a name="createex"></a>CTabCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CTabCtrl` Objekt.  
  
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
 Gibt das Registerkarten-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Registerkarte Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb760549), beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Finden Sie unter **Hinweise** in [erstellen](#create) eine Liste der Window-Stile, die auch auf das Steuerelement angewendet werden können.  
  
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
  
 `CreateEx`das Steuerelement erstellt, mit der erweiterten Fensterstile angegebenen `dwExStyle`. Gruppe, die erweiterten Stile, die spezifisch für ein Steuerelement mit [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` solche Stile als festlegen **WS_EX_CONTEXTHELP**, jedoch verwenden `SetExtendedStyle` solche Stile als festlegen **TCS_EX_FLATSEPARATORS**. Weitere Informationen finden Sie die Stile in der beschriebenen [Registerkarte Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb760546) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namectabctrla--ctabctrlctabctrl"></a><a name="ctabctrl"></a>CTabCtrl::CTabCtrl  
 Erstellt ein `CTabCtrl`-Objekt.  
  
```  
CTabCtrl();
```  
  
##  <a name="a-namedeleteallitemsa--ctabctrldeleteallitems"></a><a name="deleteallitems"></a>CTabCtrl::DeleteAllItems  
 Entfernt alle Elemente aus einem Registerkarten-Steuerelement.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namedeleteitema--ctabctrldeleteitem"></a><a name="deleteitem"></a>CTabCtrl::DeleteItem  
 Entfernt das angegebene Element aus einem Registerkarten-Steuerelement.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierter Wert, der das zu löschende Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl&3;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="a-namedeselectalla--ctabctrldeselectall"></a><a name="deselectall"></a>CTabCtrl::DeselectAll  
 Setzt die Elemente in einem Registersteuerelement deaktivieren, die gedrückt wurden.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>Parameter  
 *fExcludeFocus*  
 Flag, die den Rahmen der Deaktivierung des Elements angibt. Wenn dieser Parameter, um festgelegt ist **FALSE**, alle Registerkartenschaltflächen zurückgesetzt werden. Wenn sie, um festgelegt ist **TRUE**, dann alle Registerkartenelemente mit Ausnahme derjenigen, die aktuell ausgewählte zurückgesetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Meldung, [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namedrawitema--ctabctrldrawitem"></a><a name="drawitem"></a>CTabCtrl::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Registerkarte Steuerelements ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) Struktur, die Beschreibung des Artikels gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CTabCtrl` Objekt.  
  
 Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
##  <a name="a-namegetcurfocusa--ctabctrlgetcurfocus"></a><a name="getcurfocus"></a>CTabCtrl::GetCurFocus  
 Ruft den Index der Registerkarte mit dem aktuellen Fokus ab.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Registerkarte mit dem aktuellen Fokus.  
  
##  <a name="a-namegetcursela--ctabctrlgetcursel"></a><a name="getcursel"></a>CTabCtrl::GetCurSel  
 Ruft die derzeit ausgewählte Registerkarte in einem Registersteuerelement ab.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ausgewählten Registerkarte bei Erfolg oder – 1, wenn keine Registerkarte ausgewählt ist.  
  
##  <a name="a-namegetextendedstylea--ctabctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle  
 Ruft die erweiterten Stile, die derzeit für das Registerkarten-Steuerelement verwendet werden.  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Stellt die erweiterten Stile für das Registerkarten-Steuerelement verwendet. Dieser Wert ist eine Kombination von [Registersteuerelement Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb760546), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetimagelista--ctabctrlgetimagelist"></a><a name="getimagelist"></a>CTabCtrl::GetImageList  
 Ruft die einem Tab-Steuerelement zugeordnete Bildliste ab.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf die Bildliste der Registerkarte steuern. andernfalls **NULL**.  
  
##  <a name="a-namegetitema--ctabctrlgetitem"></a><a name="getitem"></a>CTabCtrl::GetItem  
 Ruft Informationen zu einer Registerkarte in einem Registerkarten-Steuerelement.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index der Registerkarte.  
  
 `pTabCtrlItem`  
 Zeiger auf eine [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Struktur, die zur Angabe der Informationen abgerufen werden sollen. Außerdem verwendet erhalten Sie Informationen zur Registerkarte. Diese Struktur wird verwendet, mit der `InsertItem`, `GetItem`, und `SetItem` Memberfunktionen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg; **FALSE** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Nachricht gesendet wird, die **Maske** -Member gibt an, welche Attribute zurück. Wenn die **Maske** Member gibt an, die `TCIF_TEXT` Wert, der **PszText** Element muss die Adresse des Puffers, in dem Text geschrieben enthalten und die **CchTextMax** Element muss die Größe des Puffers angeben.  
  
 **Subnetzmaske**  
 Wert, der angibt, welche `TCITEM` Strukturmember abgerufen oder festgelegt. Dieser Member kann NULL oder eine Kombination der folgenden Werte sein:  
  
- `TCIF_TEXT`Die **PszText** Member ist gültig.  
  
- `TCIF_IMAGE`Der `iImage` Member ist gültig.  
  
- `TCIF_PARAM`Die **lParam** Member ist gültig.  
  
- `TCIF_RTLREADING`Der Text der **PszText** mit rechts-nach-Links-Lesefolge auf Systemen mit Hebräisch oder Arabisch angezeigt wird.  
  
- `TCIF_STATE`Die **dwState-Datenmember** Member ist gültig.  
  
 **pszText**  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge den Registerkartentext ein die Struktur enthält Informationen über eine Registerkarte. Wenn die Struktur Informationen empfängt, gibt dieser Member die Adresse des Puffers, in den Registerkartentext geschrieben.  
  
 **cchTextMax**  
 Größe des Puffers auf den **PszText**. Dieser Member wird ignoriert, wenn die Struktur nicht mit Informationen versorgt wird.  
  
 `iImage`  
 Index für des Registerkarten-Steuerelements Bildliste oder – 1, wenn kein für die Registerkarte Bild.  
  
 **lParam**  
 Die Registerkarte zugeordnete anwendungsspezifische Daten. Es sind mehr als vier Bytes anwendungsspezifische Daten pro Registerkarte, eine Anwendung eine Struktur definieren und muss anstelle der `TCITEM` Struktur. Das erste Element der Anwendung definierte Struktur muss eine [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)Struktur. Die **TCITEMHEADER** Struktur ist identisch mit der `TCITEM` Struktur, jedoch ohne die **lParam** Member. Der Unterschied zwischen der Größe der Struktur und die Größe der **TCITEMHEADER** Struktur sollte die Anzahl der zusätzlichen Bytes pro Registerkarte entsprechen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl&4;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="a-namegetitemcounta--ctabctrlgetitemcount"></a><a name="getitemcount"></a>CTabCtrl::GetItemCount  
 Ruft die Anzahl der Registerkarten im Registerkarten-Steuerelement ab.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Elemente im Registerkarten-Steuerelement.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-namegetitemrecta--ctabctrlgetitemrect"></a><a name="getitemrect"></a>CTabCtrl::GetItemRect  
 Ruft das umschließende Rechteck für die angegebene Registerkarte in einem Registersteuerelement ab.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index des Registerelements.  
  
 `lpRect`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck der Registerkarte empfängt. Diese Koordinaten verwenden des Viewports aktuelle Zuordnungsmodus.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="a-namegetitemstatea--ctabctrlgetitemstate"></a><a name="getitemstate"></a>CTabCtrl::GetItemState  
 Ruft den Zustand des Steuerelements Registerelements identifizierten `nItem`.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Die nullbasierte Indexnummer des Elements, für die die Statusinformationen abzurufen.  
  
 `dwMask`  
 Die Maske angeben, der den Zustand des Elements flags zurückgegeben. Eine Liste der Werte finden Sie unter dem Mask-Member der [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf einen `DWORD` Wert empfangen von Informationen über den Zustand. Kann einer der folgenden Werte sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Das Registerkartenelement-Steuerelement ausgewählt ist.|  
|**TCIS_HIGHLIGHTED**|Das Registersteuerelement markiert ist, und die Registerkarte und den Text mit der aktuellen Hervorhebungsfarbe gezeichnet werden. Wenn Hervorhebungsfarbe verwenden, wird dies eine true-Interpolation keine geditherte Farbe sein.|  
  
### <a name="remarks"></a>Hinweise  
 Der Zustand eines Elements wird angegeben, indem die **dwState-Datenmember** Mitglied der `TCITEM` Struktur.  
  
##  <a name="a-namegetrowcounta--ctabctrlgetrowcount"></a><a name="getrowcount"></a>CTabCtrl::GetRowCount  
 Ruft die aktuelle Anzahl der Zeilen in einem Registerkarten-Steuerelement ab.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen mit Registerkarten im Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Registerkarte nur Steuerelemente, die die **TCS_MULTILINE** Formatvorlage kann mehrere Zeilen mit Registerkarten aufweisen.  
  
##  <a name="a-namegettooltipsa--ctabctrlgettooltips"></a><a name="gettooltips"></a>CTabCtrl::GetToolTips  
 Ruft das Handle für das ein Registerkarten-Steuerelement zugeordneten QuickInfo-Steuerelement ab.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das QuickInfo-Steuerelement bei Erfolg; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement erstellt, es wurde die **TCS_TOOLTIPS** Stil. Sie können auch ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zuweisen der `SetToolTips` Member-Funktion.  
  
##  <a name="a-namehighlightitema--ctabctrlhighlightitem"></a><a name="highlightitem"></a>CTabCtrl::HighlightItem  
 Legt den Status markieren Sie ein Registerkartenelement fest.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `idItem`  
 Nullbasierte Index des ein Registersteuerelement.  
  
 `fHighlight`  
 Wert, der die Hervorhebung Status angibt. Wenn dieser Wert **TRUE**, die Registerkarte hervorgehoben wird, wenn **FALSE**, wird auf den Standardzustand festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Win32-Meldung [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namehittesta--ctabctrlhittest"></a><a name="hittest"></a>CTabCtrl::HitTest  
 Bestimmt, welche Registerkarte gegebenenfalls an der angegebenen Bildschirmposition befindet.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pHitTestInfo`  
 Zeiger auf eine [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) Struktur, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], gibt die Bildschirmposition zum Testen an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den nullbasierten Index der Registerkarte oder – 1 zurück, wenn keine Registerkarte an der angegebenen Position befindet.  
  
##  <a name="a-nameinsertitema--ctabctrlinsertitem"></a><a name="insertitem"></a>CTabCtrl:: InsertItem  
 Fügt eine neue Registerkarte in einer vorhandenen Registerkarten-Steuerelement.  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index des neuen.  
  
 `pTabCtrlItem`  
 Zeiger auf eine [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) -Struktur, die die Attribute der Registerkarte angibt.  
  
 `lpszItem`  
 Eine Null-terminierte Zeichenfolge mit dem Text der Registerkarte Adresse.  
  
 `nImage`  
 Der nullbasierte Index eines Bilds aus einer Bildliste einfügen.  
  
 `nMask`  
 Gibt an, welche `TCITEM` Struktur Attribute festlegen. 0 (null) oder eine Kombination der folgenden Werte sind möglich:  
  
- `TCIF_TEXT`Die **PszText** Member ist gültig.  
  
- `TCIF_IMAGE`Der `iImage` Member ist gültig.  
  
- `TCIF_PARAM`Die **lParam** Member ist gültig.  
  
- `TCIF_RTLREADING`Der Text der **PszText** mit rechts-nach-Links-Lesefolge auf Systemen mit Hebräisch oder Arabisch angezeigt wird.  
  
- `TCIF_STATE`Die **dwState-Datenmember** Member ist gültig.  
  
 `lParam`  
 Die Registerkarte zugeordnete anwendungsspezifische Daten.  
  
 `dwState`  
 Gibt Werte für die Element-Zustände. Weitere Informationen finden Sie unter [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *den dwStateMask*  
 Gibt an, welche Zustände festgelegt werden. Weitere Informationen finden Sie unter [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des neuen bei Erfolg; andernfalls – 1.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl&5;](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="a-nameremoveimagea--ctabctrlremoveimage"></a><a name="removeimage"></a>CTabCtrl::RemoveImage  
 Entfernt das angegebene Bild aus einem Registerkarten-Steuerelement.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des zu entfernenden Bildes.  
  
### <a name="remarks"></a>Hinweise  
 Das Registerkarten-Steuerelement aktualisiert jede Registerkarte Abbildindex, sodass jede Registerkarte dasselbe Bild zugeordnet bleibt.  
  
##  <a name="a-namesetcurfocusa--ctabctrlsetcurfocus"></a><a name="setcurfocus"></a>CTabCtrl::SetCurFocus  
 Setzt den Fokus auf eine angegebene Registerkarte in einem Registersteuerelement.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Gibt den Index der Registerkarte, die den Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetcursela--ctabctrlsetcursel"></a><a name="setcursel"></a>CTabCtrl::SetCurSel  
 Wählt eine Registerkarte in einem Registerkarten-Steuerelement aus.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Der nullbasierte Index des Elements, das ausgewählt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index der zuvor ausgewählten Registerkarte bei Erfolg, andernfalls – 1.  
  
### <a name="remarks"></a>Hinweise  
 Ein Registerkarten-Steuerelement sendet kein **TCN_SELCHANGING** oder **TCN_SELCHANGE** Benachrichtigung, wenn eine Registerkarte ausgewählt wird mit dieser Funktion. Diese Benachrichtigungen gesendet werden, mithilfe von **WM_NOTIFY**, wenn der Benutzer klickt oder die Tastatur verwendet, um Registerkarten zu ändern.  
  
##  <a name="a-namesetextendedstylea--ctabctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle  
 Legt die erweiterten Stile für ein Registerkarten-Steuerelement fest.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `dwNewStyle`  
 Angabe einer Kombination aus der Registerkarte Wert steuern Erweiterte Stile.  
  
 `dwExMask`  
 Ein `DWORD` -Wert, der gibt an, welche Stile im `dwNewStyle` betroffen sind. Nur die erweiterten Stile in `dwExMask` geändert werden. Alle anderen Arten werden unverändert beibehalten. Wenn dieser Parameter&0; (null), und klicken Sie dann alle Formatvorlagen in `dwNewStyle` betroffen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` -Wert, der vorherigen enthält [Registersteuerelement Erweiterte Stile](http://msdn.microsoft.com/library/windows/desktop/bb760546), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetimagelista--ctabctrlsetimagelist"></a><a name="setimagelist"></a>CTabCtrl::SetImageList  
 Ein Registerkarten-Steuerelement mit einer Bildliste zugewiesen.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Ein Zeiger auf die Bildliste des Registersteuerelements zugewiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die vorherige Bildliste oder **NULL** Wenn keine vorherigen Bildliste vorhanden ist.  
  
##  <a name="a-namesetitema--ctabctrlsetitem"></a><a name="setitem"></a>CTabCtrl::SetItem  
 Legt fest, einige oder alle Attribute einer Registerkarte.  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index des Elements.  
  
 `pTabCtrlItem`  
 Zeiger auf eine [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) -Struktur, die das neue Elementattribute enthält. Die **Maske** -Member gibt an, welche Attribute festgelegt. Wenn die **Maske** Member gibt an, die `TCIF_TEXT` Wert der **PszText** Member ist die Adresse einer Null-terminierte Zeichenfolge und die **CchTextMax** Member wird ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetItem](#getitem).  
  
##  <a name="a-namesetitemextraa--ctabctrlsetitemextra"></a><a name="setitemextra"></a>CTabCtrl::SetItemExtra  
 Legt die Anzahl von Bytes pro Registerkarte für die Anwendung definierte Daten in einem Registersteuerelement reserviert.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die Anzahl der zusätzlichen Bytes festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich&0;, wenn erfolgreich, andernfalls&0;.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetitemsizea--ctabctrlsetitemsize"></a><a name="setitemsize"></a>CTabCtrl::SetItemSize  
 Legt die Breite und Höhe des Registerkarten-Steuerelements fest.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Die neue Breite und Höhe des Registerkarten-Steuerelements in Pixeln.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die alte Breite und Höhe des Registerkarten-Steuerelements zurück.  
  
##  <a name="a-namesetitemstatea--ctabctrlsetitemstate"></a><a name="setitemstate"></a>CTabCtrl::SetItemState  
 Legt den Status der identifizierten Registersteuerelement `nItem`.  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Die nullbasierte Indexnummer des Elements, für die Zustandsinformationen festgelegt.  
  
 `dwMask`  
 Die Maske angeben, der den Zustand des Elements flags festgelegt. Eine Liste der Werte finden Sie unter dem Mask-Member der [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwState`  
 Ein Verweis auf einen `DWORD` -Wert, der Informationen über den Zustand enthält. Kann einer der folgenden Werte sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Das Registerkartenelement-Steuerelement ausgewählt ist.|  
|**TCIS_HIGHLIGHTED**|Das Registersteuerelement markiert ist, und die Registerkarte und den Text mit der aktuellen Hervorhebungsfarbe gezeichnet werden. Wenn Hervorhebungsfarbe verwenden, wird dies eine true-Interpolation keine geditherte Farbe sein.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="a-namesetmintabwidtha--ctabctrlsetmintabwidth"></a><a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth  
 Legt die minimale Breite der Elemente in einem Registerkarten-Steuerelement fest.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Minimale Breite für ein Registersteuerelement festgelegt werden. Wenn dieser Parameter auf-1 festgelegt ist, wird das Steuerelement die Registerkarte Standardbreite verwenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Registerkarte minimale Breite.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namesetpaddinga--ctabctrlsetpadding"></a><a name="setpadding"></a>CTabCtrl::SetPadding  
 Legt den Abstand (Auffüllung) aus, um jede Registerkarte Symbol und eine Bezeichnung in einem Registerkarten-Steuerelement fest.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Legt den Abstand (Auffüllung) aus, um jede Registerkarte Symbol und eine Bezeichnung in einem Registerkarten-Steuerelement fest.  
  
##  <a name="a-namesettooltipsa--ctabctrlsettooltips"></a><a name="settooltips"></a>CTabCtrl::SetToolTips  
 Ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zugewiesen.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndTip`  
 Handle für das QuickInfo-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Sie erhalten das QuickInfo-Steuerelement ein Registerkarten-Steuerelement zugeordnet sind, durch einen Aufruf an `GetToolTips`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl-Klasse](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)

