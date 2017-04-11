---
title: CTabCtrl-Klasse | Microsoft Docs
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
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 150b11e4989cd45ba2a8065c86c07510d00c346c
ms.lasthandoff: 04/01/2017

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
|[CTabCtrl::AdjustRect](#adjustrect)|Ein Registerkarten-Steuerelement Anzeigebereich erhält ein Rechteck Fenster berechnet, oder berechnet das fensterrechtecke aus, das einen bestimmten Anzeigebereich entsprechen würden.|  
|[CTabCtrl::Create](#create)|Erstellt ein Registerkarten-Steuerelement, und fügt ihn mit einer Instanz von einem `CTabCtrl` Objekt.|  
|[CTabCtrl::CreateEx](#createex)|Erstellt ein Registerkarten-Steuerelement mit der angegebenen erweiterten Fensterstile und fügt Sie ihn mit einer Instanz von einem `CTabCtrl` Objekt.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|Entfernt alle Elemente aus einem Registerkarten-Steuerelement.|  
|[CTabCtrl::DeleteItem](#deleteitem)|Entfernt ein Element aus einem Registerkarten-Steuerelement.|  
|[CTabCtrl::DeselectAll](#deselectall)|Setzt die Elemente in einem Registerkarten-Steuerelement, und deaktivieren, die gedrückt wurden.|  
|[CTabCtrl::DrawItem](#drawitem)|Zeichnet ein angegebenes Element ein Registerkarten-Steuerelements an.|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|Ruft die Registerkarte mit der aktuelle Fokus des Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetCurSel](#getcursel)|Bestimmt, die derzeit ausgewählte Registerkarte in einem Registerkarten-Steuerelement.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|Ruft die erweiterten Stile, die derzeit für das Registerkarten-Steuerelement verwendet werden.|  
|[CTabCtrl::GetImageList](#getimagelist)|Ruft die einem Registerkarten-Steuerelement zugeordnete Bildliste ab.|  
|[CTabCtrl::GetItem](#getitem)|Ruft Informationen zu einer Registerkarte in einem Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetItemCount](#getitemcount)|Ruft die Anzahl der Registerkarten im Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetItemRect](#getitemrect)|Ruft das umschließende Rechteck für eine Registerkarte in einem Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetItemState](#getitemstate)|Ruft den Zustand des angegebenen Steuerelements Registerkartenelements ab.|  
|[CTabCtrl::GetRowCount](#getrowcount)|Ruft die aktuelle Anzahl der Zeilen mit Registerkarten im Registerkarten-Steuerelement ab.|  
|[CTabCtrl::GetToolTips](#gettooltips)|Ruft das Handle für das Registerkarten-Steuerelement zugeordneten QuickInfo-Steuerelement ab.|  
|[CTabCtrl::HighlightItem](#highlightitem)|Legt den Status Hervorhebung ein Registerkartenelement an.|  
|[CTabCtrl::HitTest](#hittest)|Bestimmt die Registerkarte ", sofern vorhanden, an eine angegebene Bildschirmposition befindet.|  
|[CTabCtrl:: InsertItem](#insertitem)|Fügt eine neue Registerkarte in einem Registerkarten-Steuerelement.|  
|[CTabCtrl::RemoveImage](#removeimage)|Entfernt ein Bild aus einer Bildliste ein Registerkarten-Steuerelement.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|Legt den Fokus auf eine angegebene Registerkarte in einem Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetCurSel](#setcursel)|Wählt eine Registerkarte in einem Registerkarten-Steuerelement aus.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|Legt die erweiterte Formate für ein Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetImageList](#setimagelist)|Ein Registerkarten-Steuerelement mit einer Bildliste zugewiesen.|  
|[CTabCtrl::SetItem](#setitem)|Legt fest, einige oder alle Attribute für eine Registerkarte.|  
|[CTabCtrl::SetItemExtra](#setitemextra)|Legt die Anzahl der Bytes / Registerkarte für die Anwendung definierte Daten in einem Registerkarten-Steuerelement reserviert.|  
|[CTabCtrl::SetItemSize](#setitemsize)|Legt die Breite und Höhe eines Elements.|  
|[CTabCtrl::SetItemState](#setitemstate)|Legt den Zustand des angegebenen Steuerelements Registerkartenelements fest.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|Legt die minimale Breite der Elemente in einem Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetPadding](#setpadding)|Legt die Größe des Speicherplatzes (Auffüllung) aus, um jede Registerkarte Symbol und Bezeichnung in einem Registerkarten-Steuerelement fest.|  
|[CTabCtrl::SetToolTips](#settooltips)|Ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zugewiesen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "Registerkarten-Steuerelement" ist analog zu den Trennblättern in einem Notizbuch oder die Bezeichnungen in einer CAB-Datei. Durch Verwenden eines Registerkarten-Steuerelements können in einer Anwendung mehrere Seiten für denselben Bereich in einem Fenster oder Dialogfeld definiert werden. Jede Seite besteht aus einem Satz von Informationen oder eine Gruppe von Steuerelementen, die die Anwendung zeigt an, wenn der Benutzer die entsprechende Registerkarte auswählt. Eine besondere Art von Registerkarten-Steuerelement zeigt die Registerkarten, die Schaltflächen aussehen. Klicken auf eine Schaltfläche sollte sofort zum Ausführen eines Befehls anstelle eine Seite anzeigen.  
  
 Dieses Steuerelement (und somit die `CTabCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Weitere Informationen zur Verwendung von `CTabCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CTabCtrl](../../mfc/using-ctabctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="adjustrect"></a>CTabCtrl::AdjustRect  
 Ein Registerkarten-Steuerelement Anzeigebereich erhält ein Rechteck Fenster berechnet, oder berechnet das fensterrechtecke aus, das einen bestimmten Anzeigebereich entsprechen würden.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `bLarger`  
 Gibt an, welcher Vorgang ausgeführt. Wenn dieser Parameter ist **"true"**, `lpRect` gibt ein Anzeigerechteck und das entsprechende Fenster Rechteck empfängt. Wenn dieser Parameter ist **"false"**, `lpRect` gibt ein Rechteck Fenster und die entsprechenden Anzeigerechteck empfängt.  
  
 `lpRect`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, gibt das angegebene Rechteck und das berechnete Rechteck empfängt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl Nr. 1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="create"></a>CTabCtrl::Create  
 Erstellt ein Registerkarten-Steuerelement, und fügt ihn mit einer Instanz von einem `CTabCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Registerkarten-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Steuerelementtypen für die Registerkarte](http://msdn.microsoft.com/library/windows/desktop/bb760549), beschrieben, in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Finden Sie unter **"Hinweise"** eine Liste der Fensterstile, die auch auf das Steuerelement angewendet werden können.  
  
 `rect`  
 Gibt an, Größe und Position des Steuerelements. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Registerkarten-Steuerelement übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt das Registerkarten-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn die Initialisierung des Objekts erfolgreich, andernfalls war **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CTabCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend **erstellen**, die das Registerkarten-Steuerelement erstellt, und fügt es der `CTabCtrl` Objekt.  
  
 Zusätzlich zu Steuerelementtypen für die Registerkarte können Sie die folgenden Fensterstile auf ein Registerkarten-Steuerelement anwenden:  
  
- **WS_CHILD** erstellt ein untergeordnetes Fenster, das das Registerkarten-Steuerelement darstellt. Kann nicht mit dem `WS_POPUP`-Stil verwendet werden.  
  
- **WS_VISIBLE** erstellt ein Registerkarten-Steuerelement, das anfänglich sichtbar ist.  
  
- **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist.  
  
- **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen in der der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten wechseln kann. Alle Steuerelemente, die definiert, mit der **WS_GROUP** formatieren, nachdem das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** Stil beendet die Style-Gruppe und startet die nächste Gruppe (d. h. eine Gruppe endet, an die nächste beginnt).  
  
- **WS_TABSTOP** gibt eines von beliebig vielen Steuerelementen, zwischen denen der Benutzer mit der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer auf das nächste Steuerelement gemäß der **WS_TABSTOP** Stil.  
  
 Rufen Sie zum Erstellen eines Registerkartensteuerelements mit erweiterten Fensterstile [CTabCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl #2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CTabCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CTabCtrl` Objekt.  
  
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
 Gibt das Registerkarten-Steuerelement-Stil. Wenden Sie eine beliebige Kombination von [Steuerelementtypen für die Registerkarte](http://msdn.microsoft.com/library/windows/desktop/bb760549), beschrieben, in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Finden Sie unter **"Hinweise"** in [erstellen](#create) eine Liste der Fensterstile, die auch auf das Steuerelement angewendet werden können.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
 `CreateEx`das Steuerelement erstellt, mit der erweiterten Fensterstile gemäß `dwExStyle`. Erweiterte Formate, die spezifisch für ein Steuerelement mit Set [SetExtendedStyle](#setextendedstyle). Verwenden Sie z. B. `CreateEx` festzulegende Stile als **WS_EX_CONTEXTHELP**, verwenden jedoch `SetExtendedStyle` festzulegende Stile als **TCS_EX_FLATSEPARATORS**. Weitere Informationen finden Sie unter die Stile, die in beschriebenen [Registerkarte Steuerelementtypen erweiterte](http://msdn.microsoft.com/library/windows/desktop/bb760546) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="ctabctrl"></a>CTabCtrl::CTabCtrl  
 Erstellt ein `CTabCtrl`-Objekt.  
  
```  
CTabCtrl();
```  
  
##  <a name="deleteallitems"></a>CTabCtrl::DeleteAllItems  
 Entfernt alle Elemente aus einem Registerkarten-Steuerelement.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="deleteitem"></a>CTabCtrl::DeleteItem  
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
 [!code-cpp[NVC_MFC_CTabCtrl Nr. 3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="deselectall"></a>CTabCtrl::DeselectAll  
 Setzt die Elemente in einem Registerkarten-Steuerelement, und deaktivieren, die gedrückt wurden.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>Parameter  
 *fExcludeFocus*  
 Flag, die den Rahmen der Deaktivierung des Elements angibt. Wenn dieser Parameter, um festgelegt wird **"false"**, alle Schaltflächen der Registerkarte "zurückgesetzt werden. Wenn sie, um festgelegt ist **"true"**, und klicken Sie dann alle Elemente der Registerkarte mit Ausnahme der aktuell ausgewählte zurückgesetzt werden.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="drawitem"></a>CTabCtrl::DrawItem  
 Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Registerkarte Steuerelements ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) Struktur, die das Element zu zeichnenden beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll.  
  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CTabCtrl` Objekt.  
  
 Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor diesem Element Funktion beendet wird.  
  
##  <a name="getcurfocus"></a>CTabCtrl::GetCurFocus  
 Ruft den Index der Registerkarte mit dem aktuellen Fokus ab.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Registerkarte mit dem aktuellen Fokus.  
  
##  <a name="getcursel"></a>CTabCtrl::GetCurSel  
 Ruft die derzeit ausgewählte Registerkarte in einem Registerkarten-Steuerelement ab.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index des ausgewählten Registerkarte im Erfolgsfall oder -1, wenn keine Registerkarte ausgewählt wird.  
  
##  <a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle  
 Ruft die erweiterten Stile, die derzeit für das Registerkarten-Steuerelement verwendet werden.  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Stellt die erweiterten Stile aktuell in Verwendung für das Registerkarten-Steuerelement dar. Dieser Wert ist eine Kombination von [Registerkarten-Steuerelement, die erweiterten Stile](http://msdn.microsoft.com/library/windows/desktop/bb760546)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getimagelist"></a>CTabCtrl::GetImageList  
 Ruft die einem Tab-Steuerelement zugeordnete Bildliste ab.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg, ein Zeiger auf der Registerkarte die Bildliste steuern. andernfalls **NULL**.  
  
##  <a name="getitem"></a>CTabCtrl::GetItem  
 Ruft Informationen zu einer Registerkarte in einem Registerkarten-Steuerelement ab.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierter Index der Registerkarte.  
  
 `pTabCtrlItem`  
 Zeiger auf eine [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Struktur verwendet, um die abzurufenden Informationen anzugeben. Auch verwendet zum Empfangen von Informationen über die Registerkarte. Diese Struktur wird verwendet, mit der `InsertItem`, `GetItem`, und `SetItem` Memberfunktionen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg; **"False"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Nachricht gesendet wird, die **Maske** Element gibt an, welche Attribute zurück. Wenn der **Maske** Element gibt an, der `TCIF_TEXT` Wert, der **PszText** Datenmember muss die Adresse des Puffers, der den Elementtext empfängt enthalten und die **CchTextMax** Datenmember muss die Größe des Puffers angeben.  
  
 **Maske**  
 Wert, der angibt, welche `TCITEM` Strukturmember abgerufen oder festgelegt. Dieser Member kann 0 (null) oder eine Kombination der folgenden Werte sein:  
  
- `TCIF_TEXT`Die **PszText** Member ist gültig.  
  
- `TCIF_IMAGE`Die `iImage` Element ist ungültig.  
  
- `TCIF_PARAM`Die **lParam** Member ist gültig.  
  
- `TCIF_RTLREADING`Der Text der **PszText** mit Lesefolge von rechts nach links in Hebräisch und Arabisch-Systemen angezeigt wird.  
  
- `TCIF_STATE`Die **dwState-Datenmember** Member ist gültig.  
  
 **pszText**  
 Ein Zeiger auf eine Null endende Zeichenfolge, die den Registerkartentext ein enthält, wenn die Struktur Informationen zu einer Registerkarte enthält. Wenn die Struktur Informationen empfängt, gibt dieses Elements die Adresse des Puffers, in den Registerkartentext ein geschrieben.  
  
 **cchTextMax**  
 Größe des Puffers verweist **PszText**. Bei diesem Member wird ignoriert, wenn die Struktur Informationen nicht empfangen wird.  
  
 `iImage`  
 Index in des Registerkarten-Steuerelements Bildliste oder -1, wenn kein für die Registerkarte Bild.  
  
 **lParam**  
 Die Registerkarte zugeordnete anwendungsdefinierte Daten. Wenn mehr als vier Bytes der Anwendung definierte Daten pro Registerkarte vorhanden sind, eine Anwendung muss eine Struktur definieren und verwenden sie anstelle der `TCITEM` Struktur. Das erste Element der Anwendung definierte Struktur muss eine [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)Struktur. Die **TCITEMHEADER** Struktur ist identisch mit der `TCITEM` Struktur, aber ohne die **lParam** Member. Der Unterschied zwischen der Größe der Struktur und die Größe der **TCITEMHEADER** Struktur sollte die Anzahl der zusätzlichen Bytes pro Registerkarte entsprechen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl #4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="getitemcount"></a>CTabCtrl::GetItemCount  
 Ruft die Anzahl der Registerkarten im Registerkarten-Steuerelement ab.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Elemente im Registerkarten-Steuerelement.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemrect"></a>CTabCtrl::GetItemRect  
 Ruft das umschließende Rechteck für die angegebene Registerkarte in einem Registerkarten-Steuerelement ab.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierte Index des Registerkartenelements.  
  
 `lpRect`  
 Zeiger auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die das umschließende Rechteck der Registerkarte empfängt. Diese Koordinaten verwenden aktuelle Zuordnungsmodus des Viewports an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
##  <a name="getitemstate"></a>CTabCtrl::GetItemState  
 Ruft den Zustand des Steuerelements Registerkartenelements identifizierten `nItem`.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Die nullbasierte Indexnummer des Elements, für das Informationen abgerufen werden sollen.  
  
 `dwMask`  
 Maske, die angeben, welche der Zustand des Elements zurückgeben flags. Eine Liste von Werten, finden Sie unter der Maske Mitglied der [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) strukturieren, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine `DWORD` Wert empfangen die Statusinformationen. Kann einer der folgenden Werte sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Das Registerkartenelement-Steuerelement ausgewählt ist.|  
|**TCIS_HIGHLIGHTED**|Das Registerkartenelement-Steuerelement wird hervorgehoben, und die Registerkarte und Text mit der aktuellen Hervorhebungsfarbe gezeichnet werden. Bei der Verwendung der Hervorhebungsfarbe wird dies eine "true" Interpolation, keine Ditheringfarbe sein.|  
  
### <a name="remarks"></a>Hinweise  
 Zustand eines Elements wird angegeben, indem die **dwState-Datenmember** Mitglied der `TCITEM` Struktur.  
  
##  <a name="getrowcount"></a>CTabCtrl::GetRowCount  
 Ruft die aktuelle Anzahl der Zeilen in einem Registerkarten-Steuerelement ab.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen mit Registerkarten im Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Registerkarte nur Steuerelemente, die die **TCS_MULTILINE** können mehrere Zeilen mit Registerkarten sind.  
  
##  <a name="gettooltips"></a>CTabCtrl::GetToolTips  
 Ruft das Handle für das Registerkarten-Steuerelement zugeordneten QuickInfo-Steuerelement ab.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für das QuickInfo-Steuerelement im Erfolgsfall; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Ein Registerkarten-Steuerelement wird ein QuickInfo-Steuerelement erstellt, ist die **TCS_TOOLTIPS** Stil. Sie können auch ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zuweisen der `SetToolTips` Memberfunktion.  
  
##  <a name="highlightitem"></a>CTabCtrl::HighlightItem  
 Legt den Status Hervorhebung ein Registerkartenelement an.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `idItem`  
 Nullbasierte Index des ein Registerkartenelement-Steuerelement.  
  
 `fHighlight`  
 -Wert, der die Hervorhebung Zustand festgelegt werden. Wenn dieser Wert ist **"true"**, die Registerkarte hervorgehoben; Wenn **"false"**, auf den Standardzustand die Registerkarte "festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert die Win32-Meldung [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="hittest"></a>CTabCtrl::HitTest  
 Bestimmt, welche Registerkarte gegebenenfalls an der angegebenen Bildschirmposition ist.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pHitTestInfo`  
 Zeiger auf eine [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) strukturieren, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], gibt die Bildschirmposition, um zu testen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den nullbasierten Index der Registerkarte "oder"-1 zurück, wenn keine Registerkarte an der angegebenen Position befindet.  
  
##  <a name="insertitem"></a>CTabCtrl:: InsertItem  
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
 Nullbasierte Index der neuen Registerkarte.  
  
 `pTabCtrlItem`  
 Zeiger auf eine [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) -Struktur, die die Attribute der Registerkarte angibt.  
  
 `lpszItem`  
 Adresse des eine auf Null endende Zeichenfolge, die den Text der Registerkarte "enthält.  
  
 `nImage`  
 Der nullbasierte Index des ein Bild aus einer Bildliste eingefügt werden soll.  
  
 `nMask`  
 Gibt an, welche `TCITEM` Struktur Attribute festlegen. 0 (null) oder eine Kombination der folgenden Werte kann sein:  
  
- `TCIF_TEXT`Die **PszText** Member ist gültig.  
  
- `TCIF_IMAGE`Die `iImage` Element ist ungültig.  
  
- `TCIF_PARAM`Die **lParam** Member ist gültig.  
  
- `TCIF_RTLREADING`Der Text der **PszText** mit Lesefolge von rechts nach links in Hebräisch und Arabisch-Systemen angezeigt wird.  
  
- `TCIF_STATE`Die **dwState-Datenmember** Member ist gültig.  
  
 `lParam`  
 Die Registerkarte zugeordnete anwendungsdefinierte Daten.  
  
 `dwState`  
 Gibt Werte für die Element-Zustände. Weitere Informationen finden Sie unter [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *den dwStateMask*  
 Gibt an, welche Zustände festgelegt werden. Weitere Informationen finden Sie unter [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Index der neuen Registerkarte im Erfolgsfall, andernfalls andernfalls - 1.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CTabCtrl Nr. 5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="removeimage"></a>CTabCtrl::RemoveImage  
 Entfernt das angegebene Image aus einer Bildliste ein Registerkarten-Steuerelement.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>Parameter  
 `nImage`  
 Nullbasierte Index des Bilds zu entfernen.  
  
### <a name="remarks"></a>Hinweise  
 Das Registerkarten-Steuerelement aktualisiert jede Registerkarte Abbildindex aus, sodass jede Registerkarte dasselbe Bild zugeordnet ist.  
  
##  <a name="setcurfocus"></a>CTabCtrl::SetCurFocus  
 Legt den Fokus auf eine angegebene Registerkarte in einem Registerkarten-Steuerelement fest.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Gibt den Index der Registerkarte, die den Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setcursel"></a>CTabCtrl::SetCurSel  
 Wählt eine Registerkarte in einem Registerkarten-Steuerelement aus.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Der nullbasierte Index des Elements, das ausgewählt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierten Index des zuvor ausgewählten Registerkarte im Erfolgsfall, andernfalls - 1.  
  
### <a name="remarks"></a>Hinweise  
 Ein Registerkarten-Steuerelement sendet keine **TCN_SELCHANGING** oder **TCN_SELCHANGE** Benachrichtigung, wenn eine Registerkarte ausgewählt wird mit dieser Funktion. Diese Benachrichtigungen gesendet werden, mithilfe von **WM_NOTIFY**, wenn der Benutzer klickt oder die Tastatur verwendet, um Registerkarten zu ändern.  
  
##  <a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle  
 Legt die erweiterte Formate für ein Registerkarten-Steuerelement fest.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `dwNewStyle`  
 Wert, der eine Kombination der Registerkarte angibt steuern die erweiterten Stile.  
  
 `dwExMask`  
 Ein `DWORD` -Wert, der gibt an, welche Formate in `dwNewStyle` betroffen sein werden. Nur die erweiterten Stile in `dwExMask` geändert werden. Alle anderen Arten werden unverändert beibehalten. Wenn dieser Parameter 0 (null), und klicken Sie dann alle Formate in `dwNewStyle` beeinflusst werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` -Wert, der vorherige enthält [Registerkarten-Steuerelement, die erweiterten Stile](http://msdn.microsoft.com/library/windows/desktop/bb760546)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setimagelist"></a>CTabCtrl::SetImageList  
 Ein Registerkarten-Steuerelement mit einer Bildliste zugewiesen.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>Parameter  
 `pImageList`  
 Zeiger auf die Bildliste des Registersteuerelements zugewiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die vorherige Bildliste oder **NULL** , wenn keine vorherige Image-Liste vorhanden ist.  
  
##  <a name="setitem"></a>CTabCtrl::SetItem  
 Legt fest, einige oder alle Attribute für eine Registerkarte.  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>Parameter  
 `nItem`  
 Nullbasierter Index des Elements.  
  
 `pTabCtrlItem`  
 Zeiger auf eine [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Struktur, die das neue Elementattribute enthält. Die **Maske** Element gibt an, welche Attribute festgelegt. Wenn die **Maske** Element angibt der `TCIF_TEXT` Wert, der **PszText** Element ist die Adresse einer Null-terminierte Zeichenfolge und der **CchTextMax** Element wird ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetItem](#getitem).  
  
##  <a name="setitemextra"></a>CTabCtrl::SetItemExtra  
 Legt die Anzahl der Bytes / Registerkarte für die Anwendung definierte Daten in einem Registerkarten-Steuerelement reserviert.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die Anzahl der zusätzlichen Bytes festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setitemsize"></a>CTabCtrl::SetItemSize  
 Legt die Breite und Höhe des Registerkarten-Steuerelements fest.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Die neue Breite und Höhe des Registerkarten-Steuerelements in Pixeln.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die alte Breite und Höhe des Registerkarten-Steuerelements zurück.  
  
##  <a name="setitemstate"></a>CTabCtrl::SetItemState  
 Legt den Zustand des dem Registerkartenelement-Steuerelement identifizierten `nItem`.  
  
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
 Maske, die angeben, welche der Zustand des Elements flags festgelegt. Eine Liste von Werten, finden Sie unter der Maske Mitglied der [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) strukturieren, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwState`  
 Ein Verweis auf eine `DWORD` Wert, der die Zustandsinformationen enthält. Kann einer der folgenden Werte sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|Das Registerkartenelement-Steuerelement ausgewählt ist.|  
|**TCIS_HIGHLIGHTED**|Das Registerkartenelement-Steuerelement wird hervorgehoben, und die Registerkarte und Text mit der aktuellen Hervorhebungsfarbe gezeichnet werden. Bei der Verwendung der Hervorhebungsfarbe wird dies eine "true" Interpolation, keine Ditheringfarbe sein.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
##  <a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth  
 Legt die minimale Breite der Elemente in einem Registerkarten-Steuerelement fest.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>Parameter  
 `cx`  
 Die Mindestbreite für ein Registerkartenelement-Steuerelement festgelegt werden. Wenn dieser Parameter auf-1 festgelegt ist, wird das Steuerelement die Standardbreite der Registerkarte verwenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherige Registerkarte minimale Breite.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637)gemäß der Beschreibung in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setpadding"></a>CTabCtrl::SetPadding  
 Legt die Größe des Speicherplatzes (Auffüllung) aus, um jede Registerkarte Symbol und Bezeichnung in einem Registerkarten-Steuerelement fest.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>Parameter  
 `size`  
 Legt die Größe des Speicherplatzes (Auffüllung) aus, um jede Registerkarte Symbol und Bezeichnung in einem Registerkarten-Steuerelement fest.  
  
##  <a name="settooltips"></a>CTabCtrl::SetToolTips  
 Ein Registerkarten-Steuerelement ein QuickInfo-Steuerelement zugewiesen.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndTip`  
 Das Handle des QuickInfo-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Sie erhalten das QuickInfo-Steuerelement ein Registerkarten-Steuerelement zugeordnet sind, von einem Aufruf an `GetToolTips`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol).  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl-Klasse](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl-Klasse](../../mfc/reference/clistctrl-class.md)

