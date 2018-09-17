---
title: CMFCTabCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl
- AFXTABCTRL/CMFCTabCtrl::ActivateMDITab
- AFXTABCTRL/CMFCTabCtrl::AllowDestroyEmptyTabbedPane
- AFXTABCTRL/CMFCTabCtrl::AutoSizeWindow
- AFXTABCTRL/CMFCTabCtrl::CalcRectEdit
- AFXTABCTRL/CMFCTabCtrl::Create
- AFXTABCTRL/CMFCTabCtrl::EnableActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::EnableInPlaceEdit
- AFXTABCTRL/CMFCTabCtrl::EnableTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::EnsureVisible
- AFXTABCTRL/CMFCTabCtrl::GetDocumentIcon
- AFXTABCTRL/CMFCTabCtrl::GetFirstVisibleTabNum
- AFXTABCTRL/CMFCTabCtrl::GetResizeMode
- AFXTABCTRL/CMFCTabCtrl::GetScrollBar
- AFXTABCTRL/CMFCTabCtrl::GetTabArea
- AFXTABCTRL/CMFCTabCtrl::GetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::GetTabsHeight
- AFXTABCTRL/CMFCTabCtrl::GetTabsRect
- AFXTABCTRL/CMFCTabCtrl::GetWndArea
- AFXTABCTRL/CMFCTabCtrl::HideActiveWindowHorzScrollBar
- AFXTABCTRL/CMFCTabCtrl::HideInactiveWindow
- AFXTABCTRL/CMFCTabCtrl::HideNoTabs
- AFXTABCTRL/CMFCTabCtrl::HideSingleTab
- AFXTABCTRL/CMFCTabCtrl::IsActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::IsActiveTabCloseButton
- AFXTABCTRL/CMFCTabCtrl::IsDrawFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatFrame
- AFXTABCTRL/CMFCTabCtrl::IsFlatTab
- AFXTABCTRL/CMFCTabCtrl::IsLeftRightRounded
- AFXTABCTRL/CMFCTabCtrl::IsMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::IsOneNoteStyle
- AFXTABCTRL/CMFCTabCtrl::IsSharedScroll
- AFXTABCTRL/CMFCTabCtrl::IsTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::IsVS2005Style
- AFXTABCTRL/CMFCTabCtrl::ModifyTabStyle
- AFXTABCTRL/CMFCTabCtrl::OnDragEnter
- AFXTABCTRL/CMFCTabCtrl::OnDragOver
- AFXTABCTRL/CMFCTabCtrl::OnShowTabDocumentsMenu
- AFXTABCTRL/CMFCTabCtrl::SetActiveInMDITabGroup
- AFXTABCTRL/CMFCTabCtrl::SetActiveTab
- AFXTABCTRL/CMFCTabCtrl::SetActiveTabBoldFont
- AFXTABCTRL/CMFCTabCtrl::SetDrawFrame
- AFXTABCTRL/CMFCTabCtrl::SetFlatFrame
- AFXTABCTRL/CMFCTabCtrl::SetImageList
- AFXTABCTRL/CMFCTabCtrl::SetResizeMode
- AFXTABCTRL/CMFCTabCtrl::SetTabMaxWidth
- AFXTABCTRL/CMFCTabCtrl::StopResize
- AFXTABCTRL/CMFCTabCtrl::SynchronizeScrollBar
- AFXTABCTRL/CMFCTabCtrl::m_bEnableActivate
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabCtrl [MFC], ActivateMDITab
- CMFCTabCtrl [MFC], AllowDestroyEmptyTabbedPane
- CMFCTabCtrl [MFC], AutoSizeWindow
- CMFCTabCtrl [MFC], CalcRectEdit
- CMFCTabCtrl [MFC], Create
- CMFCTabCtrl [MFC], EnableActiveTabCloseButton
- CMFCTabCtrl [MFC], EnableInPlaceEdit
- CMFCTabCtrl [MFC], EnableTabDocumentsMenu
- CMFCTabCtrl [MFC], EnsureVisible
- CMFCTabCtrl [MFC], GetDocumentIcon
- CMFCTabCtrl [MFC], GetFirstVisibleTabNum
- CMFCTabCtrl [MFC], GetResizeMode
- CMFCTabCtrl [MFC], GetScrollBar
- CMFCTabCtrl [MFC], GetTabArea
- CMFCTabCtrl [MFC], GetTabMaxWidth
- CMFCTabCtrl [MFC], GetTabsHeight
- CMFCTabCtrl [MFC], GetTabsRect
- CMFCTabCtrl [MFC], GetWndArea
- CMFCTabCtrl [MFC], HideActiveWindowHorzScrollBar
- CMFCTabCtrl [MFC], HideInactiveWindow
- CMFCTabCtrl [MFC], HideNoTabs
- CMFCTabCtrl [MFC], HideSingleTab
- CMFCTabCtrl [MFC], IsActiveInMDITabGroup
- CMFCTabCtrl [MFC], IsActiveTabBoldFont
- CMFCTabCtrl [MFC], IsActiveTabCloseButton
- CMFCTabCtrl [MFC], IsDrawFrame
- CMFCTabCtrl [MFC], IsFlatFrame
- CMFCTabCtrl [MFC], IsFlatTab
- CMFCTabCtrl [MFC], IsLeftRightRounded
- CMFCTabCtrl [MFC], IsMDITabGroup
- CMFCTabCtrl [MFC], IsOneNoteStyle
- CMFCTabCtrl [MFC], IsSharedScroll
- CMFCTabCtrl [MFC], IsTabDocumentsMenu
- CMFCTabCtrl [MFC], IsVS2005Style
- CMFCTabCtrl [MFC], ModifyTabStyle
- CMFCTabCtrl [MFC], OnDragEnter
- CMFCTabCtrl [MFC], OnDragOver
- CMFCTabCtrl [MFC], OnShowTabDocumentsMenu
- CMFCTabCtrl [MFC], SetActiveInMDITabGroup
- CMFCTabCtrl [MFC], SetActiveTab
- CMFCTabCtrl [MFC], SetActiveTabBoldFont
- CMFCTabCtrl [MFC], SetDrawFrame
- CMFCTabCtrl [MFC], SetFlatFrame
- CMFCTabCtrl [MFC], SetImageList
- CMFCTabCtrl [MFC], SetResizeMode
- CMFCTabCtrl [MFC], SetTabMaxWidth
- CMFCTabCtrl [MFC], StopResize
- CMFCTabCtrl [MFC], SynchronizeScrollBar
- CMFCTabCtrl [MFC], m_bEnableActivate
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad50deb1cb500abb532acac8c3c0d035c37b87ce
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726439"
---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
Die `CMFCTabCtrl` -Klasse enthält Funktionen für ein Registerkarten-Steuerelement. Das Registerkarten-Steuerelement zeigt ein andockbares Fenster an, mit flachen oder dreidimensionalen Registerkarten am oberen oder unteren Rand. Die Registerkarten können Text und ein Bild enthalten und bei Aktivierung die Farbe ändern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Standardkonstruktor|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|Zeigt die angegebene Registerkarte des aktuellen Registerkarten-Steuerelements, und legt den Fokus auf dieser Registerkarte fest.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|Gibt an, ob das Framework den Clientbereich aller Registerkarte Steuerelement-Fenster, wenn ein Element der Benutzeroberfläche des Steuerelements Registerkarte ändert die Größe ändern.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|Entleert die Größe des Bereichs für die angegebene Registerkarte an. (Überschreibt `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCTabCtrl::Create](#create)|Das Registerkarten-Steuerelement erstellt, und fügt es der `CMFCTabCtrl` Objekt.|  
|`CMFCTabCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|Anzeigen oder Ausblenden der Schaltfläche "Schließen" ( **X**) auf der aktiven Registerkarte.|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Aktiviert oder deaktiviert die registerkartenbezeichnungen bearbeitet werden. (Überschreibt [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|Ersetzt die zwei Schaltflächen, die die Registerkarten im Fenster mit einer Schaltfläche zu scrollen, die ein Menü von Fenstern im Registerkartenformat geöffnet wird.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|Stellt sicher, dass eine Registerkarte sichtbar ist.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|Ruft ab, das Symbol, das eine Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat zugeordnet ist.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|Ruft den Index der ersten Registerkarte, die im aktuellen Registerkarten-Steuerelement sichtbar ist.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|Ruft einen Wert, der angibt, wie die aktuellen Registerkarten-Steuerelement die Größe geändert werden kann.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|Ruft einen Zeiger auf das Scroll Bar-Objekt, das das Registerkarten-Steuerelement zugeordnet ist.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|Ruft das umschließende Rechteck des Registerkartenbereichs Bezeichnung oben oder unten auf der das Registerkarten-Steuerelement ab. (Überschreibt [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|Ruft ab, die Registerkarte, die einen angegebenen Punkt enthält. (Überschreibt [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|Ruft die maximale Breite einer Registerkarte ab.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|Ruft die Höhe des Registerkartenbereichs des aktuellen Registerkarten-Steuerelements ab.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|Ruft ein Rechteck, den Registerkartenbereich des aktuellen Registerkarten-Steuerelements umschließt, ab. (Überschreibt [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|Ruft die Begrenzung des Clientbereichs des aktuellen Registerkarten-Steuerelements ab.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|Blendet die horizontale Bildlaufleiste, ggf. des aktiven Fensters aus.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|Gibt an, ob das Framework Registerkarte "inaktiv"-Steuerelement anzuzeigen.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|Aktiviert oder deaktiviert den Registerkartenbereich zeichnen, wenn keine sichtbaren Registerkarten sind.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|Aktiviert oder deaktiviert eine Registerkarte zeichnen, wenn ein einziges im Registerkartenformat Fenster vorhanden ist. (Überschreibt [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|Gibt an, ob die aktuelle Registerkarte ein Registerkarten-Steuerelement die aktive Registerkarte in einer mehrere Registerkartengruppe der Dokument-Schnittstelle ist.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|Gibt an, ob der Text der aktiven Registerkarte mit fett formatierter Schrift angezeigt wird.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|Gibt an, ob die Schaltfläche "Schließen" ( **X**) auf einer aktiven Registerkarte oder in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|Gibt an, ob die Fenster im Registerkartenformat ein Frame-Rechteck um eingebettete Bereiche zeichnet.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|Gibt an, ob der Rahmen um den Registerkartenbereich flach oder in 3D ist.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|Gibt an, ob die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement flach oder nicht.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|Gibt an, ob die Darstellung der linken und rechten Rand eine Registerkarte im aktuellen Registerkarten-Steuerelement gerundet wird.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|Gibt an, ob die aktuellen Registerkarten-Steuerelement im Clientbereich eines Fensters Multiple Document Interface enthalten ist.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Gibt an, ob die aktuellen Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird.|  
|`CMFCTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt innerhalb der Registerkartenbereich ist. (Überschreibt [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|Gibt an, ob die aktuellen Registerkarten-Steuerelement ein Bildlauf durchgeführt wird, die als Gruppe Registerkarten gescrollt werden kann.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|Gibt an, ob das Registerkarten-Steuerelement angezeigt wird, scrollschaltflächen oder eine Schaltfläche, die ein Menü von Fenstern im Registerkartenformat angezeigt.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Gibt an, ob die Registerkarten im Stil von Visual Studio .NET 2005 angezeigt werden.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|Gibt die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement an.|  
|`CMFCTabCtrl::MoveTab`|Verschiebt eine Registerkarte in eine andere Registerkarte Position. (Überschreibt [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|Vom Framework aufgerufen, wenn der Cursor zuerst in das Fenster des Steuerelements Registerkarte gezogen wird.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|Wird von Framework während eines Ziehvorgangs aufgerufen, wenn die Maus über dem Drop-Ziel-Fenster verschoben wird. (Überschreibt [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|Ein Popupmenü von Fenstern im Registerkartenformat angezeigt wird, wartet, bis der Benutzer eine Registerkarte wählt, und stellt der ausgewählten Registerkarte auf die aktive Registerkarte.|  
|`CMFCTabCtrl::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. (Überschreibt [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|Berechnet das interne Layout des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|Legt die aktuelle Registerkarte ein Registerkarten-Steuerelement als aktive Registerkarte in einem mehrere Dokument Schnittstelle Registerkartengruppe fest.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|Aktiviert eine Registerkarte. (Überschreibt [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|Aktiviert oder deaktiviert die Verwendung der fett formatierter Schrift für aktive Registerkarten.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|Aktiviert oder deaktiviert die Drawinga-Frame-Rechteck um eine eingebettete Befehlsleiste.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|Gibt an, ob einem flachen oder einem 3D Frame um den Registerkartenbereich gezeichnet werden soll.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|Gibt eine Bildliste an. (Überschreibt [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|Gibt an, wie die aktuellen Registerkarten-Steuerelement die Größe geändert werden kann, und klicken Sie dann zeigt das Steuerelement.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|Gibt die maximale Registerkarte Breite in einem Fenster im Registerkartenformat.|  
|[CMFCTabCtrl::StopResize](#stopresize)|Beendet den aktuellen Resize-Vorgang für das Registerkarten-Steuerelement.|  
|`CMFCTabCtrl::SwapTabs`|Tauscht zwei Registerkarten an. (Überschreibt [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|Zeichnet eine horizontale Bildlaufleiste für ein Registerkarten-Steuerelement, das flache Registerkarten anzeigt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|Verhindert, dass die aktive Ansicht den Fokus, wenn eine neue Registerkarte eingefügt und aktiviert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCTabCtrl` -Klasse unterstützt:  
  
-   Registerkarte "Stile für Steuerelemente, die 3D mit einer gemeinsamen horizontalen Schiebeleiste flach und flach enthalten.  
  
-   Die Registerkarten am oberen oder unteren Rand des Fensters.  
  
-   Registerkarten, in denen Text, Bilder oder Text und Bilder angezeigt.  
  
-   Registerkarten, die Farbe ändern, wenn die Registerkarte aktiv ist.  
  
-   Änderungen des Rahmens für anpassbaren Registerkarten.  
  
-   Entfernbare Fenster im Registerformat.  
  
 Die `CMFCTabCtrl` Klasse kann verwendet werden, ein Dialogfeld, jedoch ist ausschließlich für Anwendungen, die Andocken Balken wie Microsoft Excel und Visual Studio zu steuern. Weitere Informationen finden Sie unter [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).  
  
 Führen Sie diese Schritte aus, um eine geändert werden kann, fügen ein Andocken von Registerkarten-Steuerelement in Ihrer Anwendung:  
  
1.  Erstellen Sie eine Instanz des [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Rufen Sie [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create).  
  
3.  Verwendung [cbasetabbedpane:: addTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) oder [cmfcbasetabctrl:: insertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) neue Registerkarten hinzufügen.  
  
4.  Rufen Sie [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) , damit das Andocken aktuellen Registerkarten-Steuerelement an das Hauptrahmenfenster Andocken kann.  
  
5.  Rufen Sie [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) das Fenster im Registerkartenformat an das Hauptrahmenfenster andocken.  
  
 Ein Beispiel für ein Fenster im Registerkartenformat als eine andockbare Steuerleiste erstellen, finden Sie unter [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md). Mit `CMFCTabCtrl` als nicht-docking-Steuerelement zu erstellen einen `CMFCTabCtrl` Objekt aus, und rufen dann [CMFCTabCtrl::Create](#create).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCTabCtrl` Klasse zum Konfigurieren einer `CMFCTabCtrl` Objekt. Im Beispiel wird erläutert, wie Hinzufügen einer Registerkarte, die Schaltfläche "Schließen" auf der aktiven Registerkarte angezeigt, bearbeitbaren registerkartenbezeichnungen aktivieren und ein Popup-Menü Fenster im Registerkartenformat Bezeichnungen angezeigt werden. In diesem Beispiel ist Teil der [Zustandsauflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#3](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>  CMFCTabCtrl::ActivateMDITab  
 Zeigt die angegebene Registerkarte des aktuellen Registerkarten-Steuerelements, und legt den Fokus auf dieser Registerkarte fest.  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>Parameter  
*nTab*<br/>
[in] Der nullbasierte Index, der eine Registerkarte, um die Anzeige oder -1, der derzeit aktiven Registerkarte an.  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="autosizewindow"></a>  CMFCTabCtrl::AutoSizeWindow  
 Gibt an, ob das Framework den Clientbereich aller Registerkarte Steuerelement-Fenster, wenn ein Element der Benutzeroberfläche des Steuerelements Registerkarte ändert die Größe ändern.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bAutoSize*<br/>
[in] True, um die Registerkarte steuerelementfenstern automatisch angepasst. andernfalls "false". Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>  CMFCTabCtrl::Create  
 Das Registerkarten-Steuerelement erstellt, und fügt es der `CMFCTabCtrl` Objekt.  
  
```  
BOOL Create(
    Style style,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    Location location=LOCATION_BOTTOM,  
    BOOL bCloseBtn=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
*Stil*<br/>
[in] Der Stil des Registerkarten-Steuerelements. Weitere Informationen finden Sie in den Hinweisen.  
  
*Rect*<br/>
[in] Ein Rechteck, das Registerkarten-Steuerelement umschließt.  
  
*pParentWnd*<br/>
[in] Ein Zeiger auf ein übergeordnetes Fenster. Nicht darf NULL sein.  
  
*nID*<br/>
[in] Die ID des Registerkarten-Steuerelements.  
  
*location*<br/>
[in] Der Speicherort der Registerkarten. Der Standardwert ist LOCATION_BOTTOM. Weitere Informationen finden Sie in den Hinweisen.  
  
*bCloseBtn*<br/>
[in] True, um eine Schaltfläche "Schließen" auf der Registerkarte angezeigt. andernfalls "false". Der Standardwert ist "false".  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn erfolgreich; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle beschreibt die Werte Sie, für angeben können die *Stil* Parameter.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|STYLE_3D|Erstellt ein Registerkarten-Steuerelement mit einem dreidimensionalen Erscheinungsbild.|  
|STYLE_FLAT|Erstellt ein Registerkarten-Steuerelement mit Flatfile-Registerkarten.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Erstellt ein Registerkarten-Steuerelement für flache Tabstopps und eine Bildlaufleiste angezeigt, die die Registerkarten gescrollt werden kann, wenn sie von einem übergeordneten Fenster zurechtgeschnitten werden.|  
|STYLE_3D_ONENOTE|Erstellt ein Registerkarten-Steuerelement im Stil von Microsoft OneNote.|  
|STYLE_3D_VS2005|Erstellt ein Registerkarten-Steuerelement im Stil von Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED|Erstellt ein Registerkarten-Steuerelement mit abgerundeten Registerkarten im Stil von Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED_SCROLL|Erstellt ein Registerkarten-Steuerelement mit abgerundeten Registerkarten und scrollschaltflächen im Stil von Microsoft Visual Studio 2005.|  
  
 Die folgende Tabelle enthält die Werte Sie, für angeben können die *Speicherort* Parameter.  
  
|Speicherort|Beschreibung|  
|--------------|-----------------|  
|LOCATION_BOTTOM|Registerkarten befinden sich am unteren Rand der Registerkarten-Steuerelement.|  
|LOCATION_TOP|Registerkarten sind im oberen Bereich des Registerkarten-Steuerelements.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in der die `CMFCTabCtrl` Klasse. In diesem Beispiel ist Teil der [Zustandsauflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#2](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>  CMFCTabCtrl::CalcRectEdit  
 Entleert die Größe des Bereichs für die angegebene Registerkarte an.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Parameter  
*rectEdit*<br/>
[in] Ein Rechteck, das den Bereich einer Registerkarte angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Bezeichnung einer Registerkarte ändern. Diese Methode der linken und rechten Seite des angegebenen Rechtecks von der Hälfte der aktuellen Registerkarte Höhe entleert und entleert oben und unten, um eine Einheit.  
  
##  <a name="enableactivetabclosebutton"></a>  CMFCTabCtrl::EnableActiveTabCloseButton  
 Anzeigen oder Ausblenden der Schaltfläche "Schließen" ( **X**) auf der aktiven Registerkarte.  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] True, um die Schaltfläche "Schließen" auf der aktiven Registerkarte angezeigt werden sollen. Zum Anzeigen der Schaltfläche "Schließen" in der oberen rechten Ecke des Registerkartenbereichs wird false ZURÜCKGEGEBEN. Der Standardwert ist "true".  
  
##  <a name="enableinplaceedit"></a>  CMFCTabCtrl::EnableInPlaceEdit  
 Aktiviert oder deaktiviert die registerkartenbezeichnungen bearbeitet werden.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] True, um bearbeitbare registerkartenbezeichnungen zu aktivieren. "False", um bearbeitbare registerkartenbezeichnungen zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletabdocumentsmenu"></a>  CMFCTabCtrl::EnableTabDocumentsMenu  
 Umschalten zwischen einer Benutzeroberfläche, die zwei Schaltflächen verwendet, um die Registerkarten im Fenster scrollen und eine Schnittstelle, die ein Popupmenü von Fenstern im Registerkartenformat angezeigt.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bAktivieren*<br/>
[in] TRUE, um ein Popupmenü Fenster im Registerkartenformat Bezeichnungen anzuzeigen; "False" Vorwärts und rückwärts-scrollschaltflächen angezeigt werden. Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
 Klickt der Benutzer eine registerkartenbezeichnung, zeigt das Framework die entsprechenden Registerkartenfenster an. Wenn die Bezeichnung der Registerkarte angezeigt wird, wird das Fenster im Registerkartenformat geöffnet, ohne Änderung der Position. Wenn der Benutzer ein Dokument aus dem Popupmenü wählt aus, und die entsprechenden Registerkartenfenster außerhalb des Bildschirms wird, wird das Fenster im Registerkartenformat der ersten Registerkarte an.  
  
##  <a name="ensurevisible"></a>  CMFCTabCtrl::EnsureVisible  
 Stellt sicher, dass eine Registerkarte sichtbar ist.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
*iTab*<br/>
[in] Der nullbasierte Index einer Registerkarte.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Vorgang erfolgreich ist. FALSE, wenn die *iTab* Parameterindex ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um sicherzustellen, dass die angegebene Registerkarte eingeblendet wird. Das Registerkarten-Steuerelement wird scrollen, wenn dies erforderlich ist.  
  
##  <a name="getdocumenticon"></a>  CMFCTabCtrl::GetDocumentIcon  
 Ruft das Bild, das eine Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat zugeordnet ist.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>Parameter  
*nCmdID*<br/>
[in] Die Befehls-ID einer Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle einer Bitmap.  
  
##  <a name="getfirstvisibletabnum"></a>  CMFCTabCtrl::GetFirstVisibleTabNum  
 Ruft den Index der ersten Registerkarte, die im aktuellen Registerkarten-Steuerelement sichtbar ist.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index einer Registerkarte im Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur, wenn das Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird. Verwenden der [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) Methode, um den Stil zu bestimmen.  
  
##  <a name="getresizemode"></a>  CMFCTabCtrl::GetResizeMode  
 Ruft einen Wert, der angibt, wie die aktuellen Registerkarten-Steuerelement die Größe geändert werden kann.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eines der `CMFCTabCtrl::ResizeMode` Enumerationswerte, der angibt, wie das Registerkarten-Steuerelement die Größe geändert werden kann. Eine Liste der möglichen Werte finden Sie im Abschnitt "Hinweise" der [CMFCTabCtrl::SetResizeMode](#setresizemode) Methode.  
  
##  <a name="getscrollbar"></a>  CMFCTabCtrl::GetScrollBar  
 Ruft einen Zeiger auf das Scroll Bar-Objekt, das das Registerkarten-Steuerelement zugeordnet ist.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Scrollbar-Objekt oder NULL, wenn das Registerkarten-Steuerelement nicht mithilfe des STYLE_FLAT_SHARED_HORZ_SCROLL-Stils erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eingebettete Bildlaufleiste das Registerkarten-Steuerelement zuzugreifen. Ein Scroll Bar-Objekt wird erstellt, nur, wenn das Registerkarten-Steuerelement das STYLE_FLAT_SHARED_HORZ_SCROLL Format hat.  
  
##  <a name="gettabarea"></a>  CMFCTabCtrl::GetTabArea  
 Ruft das umschließende Rechteck des Registerkartenbereichs Bezeichnung oben oder unten auf der das Registerkarten-Steuerelement ab.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
*rectTabAreaTop*<br/>
[out] Bei der Rückgabe dieser Methode enthält dieser Verweis ein Rechteck, das den obersten Bezeichnung Registerkartenbereich umschließt. Das Rechteck ist in Clientkoordinaten. Dieser Verweis ist leer, wenn keine Bezeichnung Registerkartenbereich am oberen Rand der Registerkarten-Steuerelement vorhanden ist.  
  
*rectTabAreaBottom*<br/>
[out] Bei der Rückgabe dieser Methode enthält dieser Verweis ein Rechteck, das die untere Bezeichnung Registerkartenbereich umschließt. Das Rechteck ist in Clientkoordinaten. Dieser Verweis ist leer, wenn keine Bezeichnung Registerkartenbereich am unteren Rand der Registerkarten-Steuerelement vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zu bestimmen.  
  
##  <a name="gettabmaxwidth"></a>  CMFCTabCtrl::GetTabMaxWidth  
 Ruft die maximale Breite einer Registerkarte ab.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Maximale Breite von einer Registerkarte in Pixel. Wenn der Rückgabewert 0 ist, ist die Registerkarte Breite unbegrenzt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) Methode, um maximale Tabulatorbreite festzulegen.  
  
##  <a name="gettabsheight"></a>  CMFCTabCtrl::GetTabsHeight  
 Ruft die Höhe des Registerkartenbereichs des aktuellen Registerkarten-Steuerelements ab.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Registerkartenbereichs, wenn eine beliebige Registerkarte sichtbar ist, oder NULL, wenn keine Registerkarte sichtbar ist.  
  
##  <a name="gettabsrect"></a>  CMFCTabCtrl::GetTabsRect  
 Ruft ein Rechteck, den Registerkartenbereich des aktuellen Registerkarten-Steuerelements umschließt, ab.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
*Rect*<br/>
[out] Bei der Rückgabe dieser Methode die *Rect* Parameter enthält ein Rechteck, das den Registerkartenbereich umschließt.  
  
##  <a name="getwndarea"></a>  CMFCTabCtrl::GetWndArea  
 Ruft die Begrenzung des Clientbereichs des aktuellen Registerkarten-Steuerelements ab.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
*Rect*<br/>
[in, out] Bei der Rückgabe dieser Methode enthält dieser Parameter ein Rechteck, das den aktuellen Registerkarten-Steuerelement umschließt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideactivewindowhorzscrollbar"></a>  CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 Blendet die horizontale Bildlaufleiste, ggf. in das aktive Fenster aus.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu verhindern, dass das Registerkarten-Steuerelement blinkt, wenn der Benutzer zwischen Registerkarten-Steuerelement wechselt.  
  
##  <a name="hideinactivewindow"></a>  CMFCTabCtrl::HideInactiveWindow  
 Gibt an, ob das Framework steuerelementfenstern Registerkarte "inaktiv" angezeigt.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bHide*<br/>
[in] True, nicht zum Anzeigen eines inaktiven Fensters. "False" zum Anzeigen eines inaktiven Fensters. Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hidenotabs"></a>  CMFCTabCtrl::HideNoTabs  
 Aktiviert oder deaktiviert des Registerkartenbereichs zeichnen, wenn keine sichtbaren Registerkarten sind.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bHide*<br/>
[in] True, um das Zeichnen der Registerkarte zu aktivieren. So deaktivieren Sie die Zeichnung wird false ZURÜCKGEGEBEN. Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hidesingletab"></a>  CMFCTabCtrl::HideSingleTab  
 Aktiviert oder deaktiviert Registerkarte zeichnen, wenn ein einziges im Registerkartenformat Fenster vorhanden ist.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bHide*<br/>
[in] True, um eine Registerkarte für eine einzelne Registerkartenfenster nicht gezeichnet werden soll. "False", um eine einzelne Registerkarte zu zeichnen. Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isactiveinmditabgroup"></a>  CMFCTabCtrl::IsActiveInMDITabGroup  
 Gibt an, ob die aktuelle Registerkarte ein Registerkarten-Steuerelement die aktive Registerkarte in einer mehrere Dokument-Schnittstelle ist.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die aktuelle Registerkarte ein Registerkarten-Steuerelement die aktive Registerkarte in einer Gruppe von MDI-Registerkarten. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Können Sie mehrere Dokumentfenstern in beide vertikalen oder horizontalen Registerkartengruppen organisieren und problemlos Dokumente zwischen in eine andere zu mischen.  
  
##  <a name="isactivetabboldfont"></a>  CMFCTabCtrl::IsActiveTabBoldFont  
 Gibt an, ob der Text der aktiven Registerkarte mit fett formatierter Schrift angezeigt wird.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die aktive Registerkarte angezeigt wird, verwenden die fettformatierung. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) Methode, um die aktive Registerkarte Schriftart zu ändern.  
  
##  <a name="isactivetabclosebutton"></a>  CMFCTabCtrl::IsActiveTabCloseButton  
 Gibt an, ob die Schaltfläche "Schließen" ( **X**) auf einer aktiven Registerkarte oder in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Schaltfläche "Schließen" auf der aktiven Registerkarte angezeigt wird. "False", wenn die Schaltfläche "Schließen" in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawframe"></a>  CMFCTabCtrl::IsDrawFrame  
 Gibt an, ob die Fenster im Registerkartenformat ein Frame-Rechteck um eingebettete Bereiche zeichnet.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein Frame Rechteck gezeichnet wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetDrawFrame](#setdrawframe) zu aktivieren oder deaktivieren Sie das Zeichnen eines Rechtecks Frame.  
  
##  <a name="isflatframe"></a>  CMFCTabCtrl::IsFlatFrame  
 Gibt an, ob der Rahmen um den Registerkartenbereich flach oder in 3D ist.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Sie der Rahmen um den Registerkartenbereich flach ist. FALSE, wenn der Frame dreidimensional ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetFlatFrame](#setflatframe) Methode ändern, wie der Rahmen gezeichnet wird.  
  
##  <a name="isflattab"></a>  CMFCTabCtrl::IsFlatTab  
 Gibt an, ob die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement flach oder nicht.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement flach ist. andernfalls "false".  
  
##  <a name="isleftrightrounded"></a>  CMFCTabCtrl::IsLeftRightRounded  
 Gibt an, ob die Darstellung der linken und rechten Rand eine Registerkarte im aktuellen Registerkarten-Steuerelement gerundet wird.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Seiten der einzelnen Registerkarten wird gerundet. andernfalls "false".  
  
##  <a name="ismditabgroup"></a>  CMFCTabCtrl::IsMDITabGroup  
 Gibt an, ob die aktuellen Registerkarten-Steuerelement im Clientbereich eines Fensters Multiple Document Interface enthalten ist.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die aktuellen Registerkarten-Steuerelement in ein MDI-Fenster des Clientbereichs. andernfalls "false".  
  
##  <a name="isonenotestyle"></a>  CMFCTabCtrl::IsOneNoteStyle  
 Gibt an, ob die aktuellen Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird. andernfalls "false".  
  
##  <a name="issharedscroll"></a>  CMFCTabCtrl::IsSharedScroll  
 Gibt an, ob die aktuellen Registerkarten-Steuerelement ein Bildlauf durchgeführt wird, die als Gruppe Registerkarten gescrollt werden kann.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das Registerkarten-Steuerelement eine freigegebene Bildlaufleiste hat. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt "true" zurück, wenn die *Stil* Parameter, der die [CMFCTabCtrl::Create](#create) Methode ist STYLE_FLAT_SHARED_HORZ_SCROLL.  
  
##  <a name="istabdocumentsmenu"></a>  CMFCTabCtrl::IsTabDocumentsMenu  
 Gibt an, ob das Registerkarten-Steuerelement angezeigt wird, scrollschaltflächen oder eine Schaltfläche, die ein Menü von Fenstern im Registerkartenformat angezeigt.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Fenster im Registerformat gescrollt werden über ein Popupmenü Fenster im Registerkartenformat Bezeichnungen. FALSE, wenn Fenster im Registerformat mit vorwärts und rückwärts scrollschaltflächen gescrollt werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) -Fenster Methode, um die Methode des Bildlaufs anzugeben.  
  
##  <a name="isvs2005style"></a>  CMFCTabCtrl::IsVS2005Style  
 Gibt an, ob Registerkarten mit dem Stil von Visual Studio 2005 gezeichnet werden.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Registerkarten mit dem Stil von Visual Studio 2005 gezeichnet werden. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der *Stil* Parameter, der die [CMFCTabCtrl::Create](#create) Methode, um anzugeben, wie Tabulatoren gezeichnet werden.  
  
##  <a name="m_benableactivate"></a>  CMFCTabCtrl::m_bEnableActivate  
 Verhindert, dass die aktive Ansicht den Fokus, wenn eine neue Registerkarte eingefügt und aktiviert ist.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Registerkarte eingefügt wird, und zum aktiven Server gemacht, wird der Fokus in der Regel von einem neuen Fenster mit Registerkarten weitergeleitet. Legen Sie die `CMFCTabCtrl::m_bEnableActivate` Membervariable auf "false", den ursprünglichen Fokus beibehalten werden sollen. Der Standardwert ist "true".  
  
##  <a name="modifytabstyle"></a>  CMFCTabCtrl::ModifyTabStyle  
 Gibt die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement an.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>Parameter  
*Stil*<br/>
[in] Einer der Enumerationswerte, der angibt, die Darstellung des Registerkarten-Steuerelements. Weitere Informationen finden Sie in der Tabelle unter "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Immer "true".  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des der *Stil* Parameter kann eine der folgenden `CMFCTabCtrl::Style` Enumerationen.  
  
|name|Beschreibung|  
|----------|-----------------|  
|STYLE_3D|Zeigt dreidimensionale, rechteckige Registerkarten an, die abgerundete Ecken aufweisen.|  
|STYLE_3D_ONENOTE|Die dreidimensionale Registerkarten, auf denen eine vertikale Seite und eine Schräge Seite und abgerundete Ecken haben, die, angezeigt.|  
|STYLE_3D_ROUNDED|Die dreidimensionale Registerkarten, die abgerundete Ecken und schräge Seiten angezeigt.|  
|STYLE_3D_ROUNDED_SCROLL|Die dreidimensionale Registerkarten, die abgerundete Ecken und schräge Seiten angezeigt. Wenn es weitere Registerkarten sind als gleichzeitig angezeigt werden können, zeigt das Framework eine Dropdown-Pfeil, und ein Menü mit Registerkarten zu aktivieren.|  
|STYLE_3D_SCROLLED|Dreidimensionale, rechteckige Registerkarten angezeigt. Wenn es weitere Registerkarten sind als gleichzeitig angezeigt werden können, zeigt das Framework eine Dropdown-Pfeil, und ein Menü mit Registerkarten zu aktivieren.|  
|STYLE_3D_VS2005|Zeigt dreidimensionalen, gerundet, Registerkarten, die eine Schräge Seite und einer vertikalen Seite verfügen.|  
|STYLE_FLAT|Zeigt die zweidimensionale Registerkarten an, die linken und rechten Seite schräg haben.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Die zweidimensionale Registerkarten angezeigt. Wenn es weitere Registerkarten sind als gleichzeitig angezeigt werden können, zeigt das Framework Bildlaufpfeile an den Enden des Registerkartenbereichs.|  
  
##  <a name="ondragenter"></a>  CMFCTabCtrl::OnDragEnter  
 Wird von Framework während eines Drag & Drop-Vorgangs aufgerufen, wenn der Cursor zuerst das Fenster des aktuellen Registerkarten-Steuerelements eintritt.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
*pDataObject*<br/>
[in] Verweist auf ein Objekt, das Daten enthält, die der Benutzer zieht.  
  
*dwKeyState*<br/>
[in] Enthält den Status der Modifizierertasten. Dieser Parameter ist eine bitweise Kombination (OR) die folgenden Werte: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON. Weitere Informationen finden Sie unter den **Meldungsparameter** Abschnitt [zu Mauseingabe](/windows/desktop/inputdev/about-mouse-input).  
  
*Zeigen Sie*<br/>
[in] Enthält die aktuelle Position des Cursors in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer DROPEFFECT_NONE, was bedeutet, dass das Ablageziel nicht die Daten akzeptieren kann.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen Drag & Drop-Vorgang zu unterstützen. Überschreiben Sie diese Methode, um Ihr eigenes benutzerdefiniertes Verhalten zu implementieren.  
  
 Standardmäßig ruft diese Methode nur `CMFCTabCtrl::OnDragOver`, DROPEFFECT_NONE immer zurück.  
  
##  <a name="ondragover"></a>  CMFCTabCtrl::OnDragOver  
 Wird von Framework während eines Ziehvorgangs aufgerufen, wenn die Maus über dem Drop-Ziel-Fenster verschoben wird.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
*pDataObject*<br/>
[in] Zeiger auf eine [COleDataObject](../../mfc/reference/coledataobject-class.md) -Objekt, das über das Ablageziel gezogen wird.  
  
*dwKeyState*<br/>
[in] Der Zustand der Zusatztasten, der eine bitweise Kombination (OR) von MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON und MK_RBUTTON ist. Weitere Informationen finden Sie unter "Meldungsparameter" in [zu Mauseingabe](/windows/desktop/inputdev/about-mouse-input).  
  
*Zeigen Sie*<br/>
[in] Die aktuelle Mausposition.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer DROPEFFECT_NONE.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode durch Ihre benutzerdefinierte Implementierung. Weitere Informationen finden Sie unter den [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) Methode.  
  
##  <a name="onshowtabdocumentsmenu"></a>  CMFCTabCtrl::OnShowTabDocumentsMenu  
 Ein Popup-Menü von Fenstern im Registerkartenformat angezeigt wird, wartet, bis der Benutzer eine Registerkarte wählt, und stellt der ausgewählten Registerkarte auf die aktive Registerkarte.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
*Zeigen Sie*<br/>
[in] Die Koordinaten, an dem das Popupmenü anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveinmditabgroup"></a>  CMFCTabCtrl::SetActiveInMDITabGroup  
 Legt die aktuelle Registerkarte ein Registerkarten-Steuerelement als aktive Registerkarte in einer mehrere Dokument-Schnittstelle fest.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
*bActive*<br/>
[in] True, um die aktive Registerkarte als aktuellen Registerkarte zu machen. "False", um die aktuelle Registerkarte inaktiv zu markieren.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie mehrere Dokumentfenstern in beide vertikalen oder horizontalen Registerkartengruppen organisieren und problemlos Dokumente zwischen in eine andere zu mischen.  
  
##  <a name="setactivetab"></a>  CMFCTabCtrl::SetActiveTab  
 Aktiviert eine Registerkarte.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
*iTab*<br/>
[in] Gibt an, der nullbasierte Index der Registerkarte zu aktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die angegebene Registerkarte aktiviert wurde. FALSE, wenn das angegebene *iTab* Parameterwert ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die Benachrichtigung AFX_WM_CHANGE_ACTIVE_TAB keine für das übergeordnete Fenster des Registerkarten-Steuerelements.  
  
 Die `SetActiveTab` Methode ruft automatisch die [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) Methode, um zu verhindern, dass den Bildschirm blinkt.  
  
##  <a name="setactivetabboldfont"></a>  CMFCTabCtrl::SetActiveTabBoldFont  
 Aktiviert oder deaktiviert die Verwendung der fett formatierter Schrift für aktive Registerkarten.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bIsBold*<br/>
[in] TRUE, fett formatierter Schrift zu verwenden, um die Beschriftung der aktiven Registerkarte angezeigt werden soll. "False" mit der Standardschriftart die Bezeichnung angezeigt werden. Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdrawframe"></a>  CMFCTabCtrl::SetDrawFrame  
 Gibt an, ob ein Frame Rechteck um eine eingebettete Leiste gezeichnet wird.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bDraw*<br/>
[in] TRUE, wenn ein Frame-Rechteck, um eine eingebettete Leiste angezeigt werden soll; andernfalls "false". Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setflatframe"></a>  CMFCTabCtrl::SetFlatFrame  
 Gibt an, ob einem flachen oder einem 3D Frame um den Registerkartenbereich gezeichnet werden soll.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
*bFlat*<br/>
[in] True, um einen flachen (2D) Frame um den Registerkartenbereich gezeichnet werden soll. FALSE, wenn einen dreidimensionalen (3D) Rahmen gezeichnet werden soll. Der Standardwert ist "true".  
  
*bRepaint*<br/>
[in] True, um das Fenster sofort neu zu zeichnen. andernfalls "false". Der Standardwert ist "true".  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimagelist"></a>  CMFCTabCtrl::SetImageList  
 Gibt eine Bildliste an.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
*uiID*<br/>
[in] Die ID einer Bitmap-Ressource, die Liste der Bilder enthält.  
  
*CX*<br/>
[in] Die Breite des jedes Bilds in Pixel. Der Standardwert ist 15.  
  
*clrTransp*<br/>
[in] Die Farbe, transparentes Bild. Die Teile des Bilds an, die diese Farbe werden transparent sein. Der Standardwert ist das Farbe Magenta, RGB(255,0,255).  
  
*hImageList*<br/>
[in] Ein Handle für einen vorab geladenen Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn diese Methode erfolgreich ist. FALSE, wenn das Registerkarten-Steuerelement mit einer Flatfile-Format erstellt wird, oder wenn die Bitmap nicht die erste methodenüberladung geladen werden kann, die angegeben wird die *UiID* Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Bildliste für das Registerkarten-Steuerelement festzulegen. Das Bild aus der Liste der Bilder werden neben der Beschriftung zur Registerkarte angezeigt. Diese Methode berechnet die Höhe der Registerkarte neu, damit, dass die Registerkarte angepasst wird, um sowohl das Bild und Text enthalten.  
  
 Verwenden der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) -Methode, die durch das Registerkarten-Steuerelement an den Index des anzuzeigenden Bilds geerbt wird.  
  
##  <a name="setresizemode"></a>  CMFCTabCtrl::SetResizeMode  
 Gibt an, wie die aktuellen Registerkarten-Steuerelement die Größe geändert werden kann, und klicken Sie dann zeigt das Steuerelement.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>Parameter  
*resizeMode*<br/>
[in] Eines der `CMFCTabCtrl::ResizeMode` Enumerationswerte, der angibt, wie das Registerkarten-Steuerelement die Größe geändert werden kann. Eine Liste der möglichen Werte finden Sie in der Tabelle unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die *ResizeMode* Parameter kann eine der folgenden `ResizeMode` -Enumerationswerte fest.  
  
|name|Beschreibung|  
|----------|-----------------|  
|RESIZE_NO|Das Registerkarten-Steuerelement kann nicht geändert werden.|  
|RESIZE_VERT|Das Registerkarten-Steuerelement kann vertikal, aber nicht horizontal geändert werden.|  
|RESIZE_HORIZ|Das Registerkarten-Steuerelement kann horizontal, aber nicht vertikal geändert werden.|  
  
##  <a name="settabmaxwidth"></a>  CMFCTabCtrl::SetTabMaxWidth  
 Gibt die maximale Registerkarte Breite in einem Fenster im Registerkartenformat.  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>Parameter  
*nTabMaxWidth*<br/>
[in] Die maximale Registerkarte Breite in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Breite der einzelnen Registerkarten in einem Fenster im Registerkartenformat zu beschränken. Diese Methode ist nützlich, wenn Registerkarten sehr lange Beschriftungen haben. Die [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) Klassenkonstruktor initialisiert die Registerkarte "maximale" Breite auf 0, was tatsächlich bedeutet, dass die Breite nicht begrenzt ist.  
  
##  <a name="stopresize"></a>  CMFCTabCtrl::StopResize  
 Beendet den aktuellen Resize-Vorgang für das Registerkarten-Steuerelement.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>Parameter  
*bAbbrechen*<br/>
[in] "True", den aktuellen Vorgang der Größenänderung abzubrechen; "False" zum Ausführen der aktuellen Anpassen der Größe ab. In beiden Fällen beendet das Framework an, das Ändern der Größe Rechteck zu zeichnen.  
  
##  <a name="synchronizescrollbar"></a>  CMFCTabCtrl::SynchronizeScrollBar  
 Zeichnet eine horizontale Bildlaufleiste für ein Registerkarten-Steuerelement, das flache Registerkarten anzeigt.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
*pScrollInfo*<br/>
[out] Zeiger auf eine [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo) Struktur oder NULL. Wenn diese Methode zurückgegeben wird und wenn dieser Parameter nicht NULL ist, enthält die Struktur alle Parameter der Bildlaufleiste an. Der Standardwert ist NULL.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn diese Methode erfolgreich ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wirkt sich nur ein Registerkarten-Steuerelement, das flache Registerkarten anzeigt. Die Bildlaufleiste beeinflusst alle Registerkarten zur gleichen Zeit.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md)
