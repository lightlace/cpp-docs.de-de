---
title: CMFCTabCtrl-Klasse | Microsoft Docs
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
ms.openlocfilehash: ad7a5331a2826df9dd6804e5c6a0f918bfeeb9d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
Die `CMFCTabCtrl` -Klasse bietet eine Funktionalität für ein Registerkarten-Steuerelement. Das Registerkarten-Steuerelement zeigt ein andockbares Fenster an, mit flachen oder dreidimensionalen Registerkarten am oberen oder unteren Rand. Die Registerkarten können Text und ein Bild enthalten und bei Aktivierung die Farbe ändern.  
  
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
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|Gibt an, ob das Framework ist, um die Größe der Clientbereich alle Registerkarte Steuerelement-Fenster, wenn ein Element der Benutzeroberfläche des Registerkarte Steuerelements ändert.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|Die Größe des angegebenen Registerkartenbereichs wird entfernt. (Überschreibt `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCTabCtrl::Create](#create)|Das Registerkarten-Steuerelement erstellt, und fügt es der `CMFCTabCtrl` Objekt.|  
|`CMFCTabCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|Blendet eine Schaltfläche "Schließen" ( **X**) auf der Registerkarte "active".|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Aktiviert oder deaktiviert die registerkartenbezeichnungen bearbeitet werden. (Überschreibt [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|Ersetzt die zwei Schaltflächen, die die Registerkarten im Fenster mit einer Schaltfläche zu blättern, die ein Menü mit Fenstern im Registerformat wird geöffnet.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|Stellt sicher, dass eine Registerkarte eingeblendet wird.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|Ruft das Symbol, das eine Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat zugeordnet ist.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|Ruft den Index der ersten Registerkarte, die im aktuellen Registerkarten-Steuerelement angezeigt wird.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|Ruft einen Wert, der angibt, wie das aktuelle Registerkarten-Steuerelement Größe geändert werden kann.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|Ruft einen Zeiger auf die Bildlaufleiste fest, die das Registerkarten-Steuerelement zugeordnet ist.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|Ruft das umschließende Rechteck des Registerkartenbereichs Bezeichnung nach oben oder unten des Registerkarten-Steuerelements ab. (Überschreibt [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|Ruft die Registerkarte, die einen angegebenen Punkt enthält. (Überschreibt [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|Ruft die maximale Breite einer Registerkarte ab.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|Ruft die Höhe des Registerkartenbereichs des aktuellen Registerkarten-Steuerelements ab.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|Ruft ein Rechteck, den Registerkartenbereich des aktuellen Registerkarten-Steuerelements umschließt, ab. (Überschreibt [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|Ruft die Grenzen des Clientbereichs des aktuellen Registerkarten-Steuerelements ab.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|Blendet die horizontale Bildlaufleiste aus, wenn keines des aktiven Fensters.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|Gibt an, ob das Framework Registerkarte "inaktiv" Steuerelement angezeigt.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|Aktiviert oder deaktiviert Registerkartenbereichs zeichnen, wenn keine Registerkarten sichtbar sind.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|Aktiviert oder deaktiviert eine Registerkarte zeichnen, wenn es ein einzelnes Fenster im Registerkartenformat ist. (Überschreibt [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|Gibt an, ob die aktuelle Registerkarte ein Registerkarten-Steuerelement der aktiven Registerkarte in mehreren Dokument Schnittstelle Registerkarte Gruppen ist.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|Gibt an, ob der Text der aktiven Registerkarte mit fett formatierter Schrift angezeigt wird.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|Gibt an, ob die Schaltfläche "Schließen" ( **X**) auf einer aktiven Registerkarte oder in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|Gibt an, ob es sich bei das Fenster im Registerkartenformat ein Frame-Rechteck, um eingebettete Bereiche zeichnet.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|Gibt an, ob Rahmen um den Registerkartenbereich flach oder 3D ist.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|Gibt an, ob die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement flach oder nicht.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|Gibt an, ob die Darstellung der linken und rechten Seite einer Registerkarte in der aktuellen Registerkarten-Steuerelement gerundet wird.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|Gibt an, ob das aktuelle Registerkarten-Steuerelement im Clientbereich eines Fensters Multiple Document Interface enthalten ist.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Gibt an, ob das aktuelle Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird.|  
|`CMFCTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt innerhalb der Registerkartenbereich befindet. (Überschreibt [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|Gibt an, ob das aktuelle Registerkarten-Steuerelement eine Bildlaufleiste besitzt, die über Registerkarten als Gruppe gescrollt werden kann.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|Gibt an, ob das Registerkarten-Steuerelement zeigt Bildlaufschaltflächen oder eine Schaltfläche, die ein Menü von Fenstern im Registerkartenformat angezeigt.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Gibt an, ob Registerkarten im Stil von Visual Studio .NET 2005 angezeigt werden.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|Gibt die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement an.|  
|`CMFCTabCtrl::MoveTab`|Verschiebt eine Registerkarte in eine andere Registerkarte Position. (Überschreibt [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|Vom Framework aufgerufen, wenn der Cursor in das Steuerelement "Verwaltung" zuerst gezogen wird.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger über die Drop-Zielfenster bewegt wird. (Überschreibt [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|Ein Popupmenü von Fenstern im Registerkartenformat angezeigt wird, wartet, bis der Benutzer eine Registerkarte wählt, und die ausgewählte Registerkarte die aktive Registerkarte definiert.|  
|`CMFCTabCtrl::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|Berechnet das interne Layout des Registerkarten-Steuerelements an. (Überschreibt [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|Legt die aktuelle Registerkarte ein Registerkarten-Steuerelement als aktive Registerkarte in einer mehrere Dokument Schnittstelle Registerkartengruppe fest.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|Aktiviert eine Registerkarte. (Überschreibt [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|Aktiviert oder deaktiviert die Verwendung der fett formatierter Schrift für aktive Registerkarten.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|Aktiviert oder deaktiviert Drawinga Frame Rechteck, um eine eingebettete Leiste.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|Gibt an, ob einem flachen oder einem 3D Rahmen um Registerkartenbereichs gezeichnet werden soll.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|Gibt an, mit einer Bildliste. (Überschreibt [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|Gibt an, wie das aktuelle Registerkarten-Steuerelement Größe geändert werden kann, und klicken Sie dann erneut an das Steuerelement.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|Gibt die maximale Registerkarte Breite in einem Fenster im Registerkartenformat.|  
|[CMFCTabCtrl::StopResize](#stopresize)|Beendet den aktuellen Vorgang der Größenänderung auf das Registerkarten-Steuerelement.|  
|`CMFCTabCtrl::SwapTabs`|Tauscht zwei Registerkarten an. (Überschreibt [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|Zeichnet eine horizontale Bildlaufleiste für ein Registerkarten-Steuerelement, in der Flatfile Registerkarten angezeigt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|Verhindert, dass die aktive Ansicht Fokus, wenn eine neue Registerkarte eingefügt und aktiviert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCTabCtrl` -Klasse unterstützt:  
  
-   Auf der Registerkarte Steuerelementtypen, die 3D, mit einer gemeinsamen horizontalen Schiebeleiste flach und flach enthalten.  
  
-   Die Registerkarten am oberen oder unteren Rand des Fensters.  
  
-   Registerkarten, in denen Text, Bilder oder Text und Bilder angezeigt.  
  
-   Registerkarten, die Farbe ändern, wenn die Registerkarte aktiv ist.  
  
-   Rahmen größenveränderung für veränderbare Registerkarten.  
  
-   Lösbare Fenstern im Registerformat.  
  
 Die `CMFCTabCtrl` Klasse mit einem Dialogfeld verwendet werden kann, aber ist ausschließlich für Anwendungen, die Andocken verwenden Balken wie steuern [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] und [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Weitere Informationen finden Sie unter [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).  
  
 Schritte zum Hinzufügen einer geändert werden kann, Andocken von Registerkarten-Steuerelement in der Anwendung:  
  
1.  Erstellen Sie eine Instanz des [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Rufen Sie [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create).  
  
3.  Verwendung [cbasetabbedpane:: addTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) oder [cmfcbasetabctrl:: insertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) neue Registerkarten hinzugefügt.  
  
4.  Rufen Sie [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) , damit das aktuelle andockbaren Registerkarten-Steuerelement an das Hauptrahmenfenster Andocken kann.  
  
5.  Rufen Sie [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) So docken Sie das Fenster im Registerkartenformat auf den Hauptframe an.  
  
 Ein Beispiel zum Erstellen von einem Fenster im Registerkartenformat als eine andockbare Symbolleiste finden Sie unter [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md). Mit `CMFCTabCtrl` als ein Steuerelement nicht Andocken erstellen eine `CMFCTabCtrl` Objekt, und rufen Sie anschließend [CMFCTabCtrl::Create](#create).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCTabCtrl` Klasse zum Konfigurieren einer `CMFCTabCtrl` Objekt. Das Beispiel erläutert das Hinzufügen einer Registerkarte, zeigen die Schaltfläche "Schließen" auf der Registerkarte "active", bearbeitbaren registerkartenbezeichnungen aktivieren und ein Popup-Menü Fenster im Registerkartenformat Bezeichnungen anzuzeigen. In diesem Beispiel ist Teil der [Auflistung Beispiel](../../visual-cpp-samples.md).  
  
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
 [in] `nTab`  
 Der nullbasierte Index von einem Tabulator, um die Anzeige oder 1, um die aktuelle aktive Registerkarte angeben.  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="autosizewindow"></a>  CMFCTabCtrl::AutoSizeWindow  
 Gibt an, ob das Framework ist, um die Größe der Clientbereich alle Registerkarte Steuerelement-Fenster, wenn ein Element der Benutzeroberfläche des Registerkarte Steuerelements ändert.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAutoSize`  
 `TRUE` Registerkarte "Steuerelement Windows automatisch angepasst; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
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
 [in] `style`  
 Die Art des Registerkarten-Steuerelements. Weitere Informationen finden Sie in den Hinweisen.  
  
 [in] `rect`  
 Ein Rechteck, das Registerkarten-Steuerelement umschließt.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf ein übergeordnetes Fenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `nID`  
 Die ID des Registerkarten-Steuerelements.  
  
 [in] `location`  
 Der Speicherort der Registerkarten. Der Standardwert ist `LOCATION_BOTTOM`. Weitere Informationen finden Sie in den Hinweisen.  
  
 [in] `bCloseBtn`  
 `TRUE` Um eine Schaltfläche "Schließen" auf der Registerkarte angezeigt. andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle beschreibt die Werte Sie, für angeben können die `style` Parameter.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|STYLE_3D|Erstellt ein Registerkarten-Steuerelement mit einem dreidimensionalen Erscheinungsbild.|  
|STYLE_FLAT|Erstellt ein Registerkarten-Steuerelement mit Flatfile-Registerkarten.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Erstellt ein Registerkarten-Steuerelement mit Flatfile Registerkarten und eine Bildlaufleiste angezeigt, die die Registerkarten gescrollt werden kann, wenn sie durch ein übergeordnetes Fenster zurechtgeschnitten werden.|  
|STYLE_3D_ONENOTE|Erstellt ein Registerkarten-Steuerelement im Stil von Microsoft OneNote.|  
|STYLE_3D_VS2005|Erstellt ein Registerkarten-Steuerelement im Stil von Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED|Erstellt ein Registerkarten-Steuerelement mit abgerundeten Registerkarten im Stile eines Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED_SCROLL|Erstellt ein Registerkarten-Steuerelement mit abgerundeten Registerkarten und Bildlaufschaltflächen im Stil von Microsoft Visual Studio 2005.|  
  
 Die folgende Tabelle enthält die Werte Sie, für angeben können die `location` Parameter.  
  
|Speicherort|Beschreibung|  
|--------------|-----------------|  
|LOCATION_BOTTOM|Registerkarten befinden sich am unteren Rand der Registerkarten-Steuerelement.|  
|LOCATION_TOP|Registerkarten befinden sich am oberen Rand der Registerkarten-Steuerelement.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode in der `CMFCTabCtrl` Klasse. In diesem Beispiel ist Teil der [Auflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection#1](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection#2](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>  CMFCTabCtrl::CalcRectEdit  
 Die Größe des angegebenen Registerkartenbereichs wird entfernt.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectEdit`  
 Ein Rechteck, das den Bereich einer Registerkarte angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Bezeichnung einer Registerkarte ändern. Diese Methode entfernt die linken und rechten Seite des angegebenen Rechtecks Hälfte der aktuellen Registerkarte Höhe und oben und unten, um eine Einheit entfernt.  
  
##  <a name="enableactivetabclosebutton"></a>  CMFCTabCtrl::EnableActiveTabCloseButton  
 Blendet eine Schaltfläche "Schließen" ( **X**) auf der Registerkarte "active".  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` auf die Schaltfläche "Schließen" auf der Registerkarte "aktiv" angezeigt. `FALSE` auf die Schaltfläche "Schließen" in der oberen rechten Ecke des Registerkartenbereichs anzuzeigen. Der Standardwert ist `TRUE`.  
  
##  <a name="enableinplaceedit"></a>  CMFCTabCtrl::EnableInPlaceEdit  
 Aktiviert oder deaktiviert die registerkartenbezeichnungen bearbeitet werden.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie bearbeitbar Registerkarte Bezeichnungen. `FALSE` bearbeitbaren registerkartenbezeichnungen deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletabdocumentsmenu"></a>  CMFCTabCtrl::EnableTabDocumentsMenu  
 Schaltet zwischen einer Benutzeroberfläche, die zwei Schaltflächen verwendet, um die Registerkarten im Fenster einen Bildlauf durchzuführen und eine Schnittstelle, die ein Popupmenü von Fenstern im Registerkartenformat angezeigt.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` Um ein Popup-Menü Fenster im Registerkartenformat Bezeichnungen anzuzeigen; `FALSE` vorwärts und rückwärts Bildlaufschaltflächen angezeigt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer eine registerkartenbezeichnung klickt, zeigt das Framework das entsprechende Fenster im Registerkartenformat. Wenn die Bezeichnung der Registerkarte angezeigt wird, wird das Fenster im Registerkartenformat geöffnet, ohne Änderung seiner Position. Wenn der Benutzer ein Dokument aus dem Popupmenü auswählt, und das entsprechende Fenster im Registerkartenformat außerhalb des Bildschirms ist, wird das Fenster im Registerkartenformat auf der ersten Registerkarte an.  
  
##  <a name="ensurevisible"></a>  CMFCTabCtrl::EnsureVisible  
 Stellt sicher, dass eine Registerkarte eingeblendet wird.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTab`  
 Der nullbasierte Index einer Registerkarte.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Bei Erfolg; `FALSE` Wenn die `iTab` Parameter-Index ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um sicherzustellen, dass die angegebene Registerkarte eingeblendet wird. Das Registerkarten-Steuerelement wird scrollen, wenn es erforderlich ist.  
  
##  <a name="getdocumenticon"></a>  CMFCTabCtrl::GetDocumentIcon  
 Ruft das Bild, das eine Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat zugeordnet ist.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCmdID`  
 Die Befehls-ID einer Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Bitmap-Bild.  
  
##  <a name="getfirstvisibletabnum"></a>  CMFCTabCtrl::GetFirstVisibleTabNum  
 Ruft den Index der ersten Registerkarte, die im aktuellen Registerkarten-Steuerelement angezeigt wird.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index einer Registerkarte im Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur, wenn das Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird. Verwenden der [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) Methode, um den Stil zu bestimmen.  
  
##  <a name="getresizemode"></a>  CMFCTabCtrl::GetResizeMode  
 Ruft einen Wert, der angibt, wie das aktuelle Registerkarten-Steuerelement Größe geändert werden kann.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eines der `CMFCTabCtrl::ResizeMode` Enumerationswerte, der angibt, wie das Registerkarten-Steuerelement Größe geändert werden kann. Eine Liste von möglichen Werten, finden Sie im Abschnitt "Hinweise" der [CMFCTabCtrl::SetResizeMode](#setresizemode) Methode.  
  
##  <a name="getscrollbar"></a>  CMFCTabCtrl::GetScrollBar  
 Ruft einen Zeiger auf die Bildlaufleiste fest, die das Registerkarten-Steuerelement zugeordnet ist.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Scrollbar-Objekt oder ein `NULL` Wenn das Registerkarten-Steuerelement mit nicht erstellt wurde die `STYLE_FLAT_SHARED_HORZ_SCROLL` Stil.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eingebettete Bildlaufleiste das Registerkarten-Steuerelement zuzugreifen. Ein Scroll Bar-Objekt wird erstellt, nur, wenn das Registerkarten-Steuerelement hat den `STYLE_FLAT_SHARED_HORZ_SCROLL` Stil.  
  
##  <a name="gettabarea"></a>  CMFCTabCtrl::GetTabArea  
 Ruft das umschließende Rechteck des Registerkartenbereichs Bezeichnung nach oben oder unten des Registerkarten-Steuerelements ab.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectTabAreaTop`  
 Bei der Rückgabe dieser Methode enthält dieser Verweis ein Rechteck, das oberste Registerkartenbereichs Bezeichnung umschließt. Das Rechteck wird in Clientkoordinaten. Dieser Verweis ist leer, wenn keine Beschriftung Registerkartenbereich am oberen Rand des Registersteuerelements vorhanden ist.  
  
 [out] `rectTabAreaBottom`  
 Bei der Rückgabe dieser Methode enthält dieser Verweis ein Rechteck, das die unteren Bezeichnung Registerkartenbereich umschließt. Das Rechteck wird in Clientkoordinaten. Dieser Verweis ist leer, wenn keine Beschriftung Registerkartenbereich am unteren Rand des Registersteuerelements vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zu bestimmen.  
  
##  <a name="gettabmaxwidth"></a>  CMFCTabCtrl::GetTabMaxWidth  
 Ruft die maximale Breite einer Registerkarte ab.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Maximale Breite einer Registerkarte, in Pixel. Wenn der Rückgabewert 0 ist, ist die Registerkarte Breite unbegrenzt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) Methode, um maximale Tabulatorbreite einzurichten.  
  
##  <a name="gettabsheight"></a>  CMFCTabCtrl::GetTabsHeight  
 Ruft die Höhe des Registerkartenbereichs des aktuellen Registerkarten-Steuerelements ab.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Registerkartenbereichs, wenn eine beliebige Registerkarte sichtbar ist, oder NULL, wenn keine Registerkarte angezeigt wird.  
  
##  <a name="gettabsrect"></a>  CMFCTabCtrl::GetTabsRect  
 Ruft ein Rechteck, den Registerkartenbereich des aktuellen Registerkarten-Steuerelements umschließt, ab.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Bei der Rückgabe dieser Methode die `rect` Parameter enthält ein Rechteck, das den Registerkartenbereich umschließt.  
  
##  <a name="getwndarea"></a>  CMFCTabCtrl::GetWndArea  
 Ruft die Grenzen des Clientbereichs des aktuellen Registerkarten-Steuerelements ab.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `rect`  
 Bei der Rückgabe dieser Methode enthält dieser Parameter ein Rechteck, das das aktuelle Registerkarten-Steuerelement umschließt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideactivewindowhorzscrollbar"></a>  CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 Blendet die horizontale Bildlaufleiste, ggf. in das aktive Fenster.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu verhindern, dass das Registerkarten-Steuerelement blinkt, wenn der Benutzer zwischen Registerkarten-Steuerelement wechselt.  
  
##  <a name="hideinactivewindow"></a>  CMFCTabCtrl::HideInactiveWindow  
 Gibt an, ob das Framework Registerkarte "inaktiv" Steuerelement Windows angezeigt.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHide`  
 `TRUE` keine anzuzeigenden ein inaktives Fensters; `FALSE` ein inaktives Fensters angezeigt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hidenotabs"></a>  CMFCTabCtrl::HideNoTabs  
 Aktiviert oder deaktiviert des Registerkartenbereichs zeichnen, wenn keine Registerkarten sichtbar sind.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHide`  
 `TRUE` So aktivieren Sie das Zeichnen des Registerkartenbereichs; `FALSE` Zeichnung zu deaktivieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hidesingletab"></a>  CMFCTabCtrl::HideSingleTab  
 Aktiviert oder deaktiviert Registerkarte zeichnen, wenn ein einzelnes Fenster im Registerkartenformat vorhanden ist.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHide`  
 `TRUE` eine Registerkarte für eine einzelnes Fenster im Registerkartenformat nicht gezeichnet werden soll; `FALSE` eine einzelne Registerkarte gezeichnet werden soll. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isactiveinmditabgroup"></a>  CMFCTabCtrl::IsActiveInMDITabGroup  
 Gibt an, ob die aktuelle Registerkarte ein Registerkarten-Steuerelement der aktiven Registerkarte in einer mehrere Dokument Schnittstelle Gruppe ist.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die aktuelle Registerkarte ein Registerkarten-Steuerelement der aktiven Registerkarte in einer MDI-Registerkartengruppe ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können mehrere Dokumentfenster in einer vertikalen oder horizontalen Registerkartengruppen organisieren und zufällige problemlos Dokumente aus einem Registerkartengruppe zu einem anderen.  
  
##  <a name="isactivetabboldfont"></a>  CMFCTabCtrl::IsActiveTabBoldFont  
 Gibt an, ob der Text der aktiven Registerkarte mit fett formatierter Schrift angezeigt wird.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die aktive Registerkarte angezeigt wird, verwenden die fette Schriftart; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) Methode, um die aktive Registerkarte Schriftart ändern.  
  
##  <a name="isactivetabclosebutton"></a>  CMFCTabCtrl::IsActiveTabCloseButton  
 Gibt an, ob die Schaltfläche "Schließen" ( **X**) auf einer aktiven Registerkarte oder in der oberen rechten Ecke des Registerkartenbereichs wird angezeigt.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Schaltfläche "Schließen" auf der aktiven Registerkarte angezeigt wird; `FALSE` , wenn die Schaltfläche "Schließen" in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawframe"></a>  CMFCTabCtrl::IsDrawFrame  
 Gibt an, ob es sich bei das Fenster im Registerkartenformat ein Frame-Rechteck, um eingebettete Bereiche zeichnet.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn ein Frame Rechteck gezeichnet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetDrawFrame](#setdrawframe) Methode zum Aktivieren oder deaktivieren einen Frame Rechteck gezeichnet.  
  
##  <a name="isflatframe"></a>  CMFCTabCtrl::IsFlatFrame  
 Gibt an, ob Rahmen um den Registerkartenbereich flach oder 3D ist.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie der Rahmen um den Registerkartenbereich flach ist; `FALSE` , wenn der Frame dreidimensional ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetFlatFrame](#setflatframe) Methode ändern, wie der Rahmen gezeichnet wird.  
  
##  <a name="isflattab"></a>  CMFCTabCtrl::IsFlatTab  
 Gibt an, ob die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement flach oder nicht.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement flach ist; andernfalls `FALSE`.  
  
##  <a name="isleftrightrounded"></a>  CMFCTabCtrl::IsLeftRightRounded  
 Gibt an, ob die Darstellung der linken und rechten Seite einer Registerkarte in der aktuellen Registerkarten-Steuerelement gerundet wird.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Seiten der einzelnen Registerkarten wird gerundet. andernfalls `FALSE`.  
  
##  <a name="ismditabgroup"></a>  CMFCTabCtrl::IsMDITabGroup  
 Gibt an, ob das aktuelle Registerkarten-Steuerelement im Clientbereich eines Fensters Multiple Document Interface enthalten ist.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das aktuelle Registerkarten-Steuerelement in ein MDI-Fenster des Clientbereichs ist. andernfalls `FALSE`.  
  
##  <a name="isonenotestyle"></a>  CMFCTabCtrl::IsOneNoteStyle  
 Gibt an, ob das aktuelle Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird; andernfalls `FALSE`.  
  
##  <a name="issharedscroll"></a>  CMFCTabCtrl::IsSharedScroll  
 Gibt an, ob das aktuelle Registerkarten-Steuerelement eine Bildlaufleiste besitzt, die über Registerkarten als Gruppe gescrollt werden kann.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Registerkarten-Steuerelement einer freigegebenen Bildlaufleiste; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `TRUE` Wenn die `style` Parameter von der [CMFCTabCtrl::Create](#create) Methode ist STYLE_FLAT_SHARED_HORZ_SCROLL.  
  
##  <a name="istabdocumentsmenu"></a>  CMFCTabCtrl::IsTabDocumentsMenu  
 Gibt an, ob das Registerkarten-Steuerelement zeigt Bildlaufschaltflächen oder eine Schaltfläche, die ein Menü von Fenstern im Registerkartenformat angezeigt.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn im Registerformat über ein Popup-Menü Fenster im Registerkartenformat Bezeichnungen gescrollt werden; `FALSE` Wenn Fenstern im Registerformat gescrollt werden mithilfe der Bildlaufschaltflächen führen Sie einen vorwärts und rückwärts.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) Methode an die Methode zum Durchführen eines Bildlaufs im Registerkartenformat zu Windows.  
  
##  <a name="isvs2005style"></a>  CMFCTabCtrl::IsVS2005Style  
 Gibt an, ob Registerkarten gezeichnet werden sollen, verwenden das Format von Visual Studio 2005.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Registerkarten im Stil von Visual Studio 2005 gezeichnet werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `style` Parameter von der [CMFCTabCtrl::Create](#create) Methode, um anzugeben, wie die Registerkarten gezeichnet werden.  
  
##  <a name="m_benableactivate"></a>  CMFCTabCtrl::m_bEnableActivate  
 Verhindert, dass die aktive Ansicht Fokus, wenn eine neue Registerkarte eingefügt und aktiviert ist.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Fokus wird in der Regel von einem neuen Fenster im Registerkartenformat ausgeführt, wenn die Registerkarte "eingefügt und aktiviert ist. Legen Sie die `CMFCTabCtrl::m_bEnableActivate` Membervariable `FALSE` den ursprünglichen Fokus beibehalten werden sollen. Der Standardwert ist `TRUE`.  
  
##  <a name="modifytabstyle"></a>  CMFCTabCtrl::ModifyTabStyle  
 Gibt die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement an.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `style`  
 Einer der Enumerationswerte, der die Darstellung des Registerkarten-Steuerelements angibt. Weitere Informationen finden Sie unter "Hinweise" der Tabelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert, der die `style` Parameter kann eine der folgenden `CMFCTabCtrl::Style` Enumerationen.  
  
|name|Beschreibung|  
|----------|-----------------|  
|STYLE_3D|Zeigt dreidimensionale, rechteckige Registerkarten, auf denen abgerundete Ecken haben.|  
|STYLE_3D_ONENOTE|Zeigt die dreidimensionalen Registerkarten, auf denen vertikale einseitige und schräge einseitige und abgerundete Ecken haben, die, an.|  
|STYLE_3D_ROUNDED|Zeigt die dreidimensionale Registerkarten, auf denen schräg Seiten und abgerundete Ecken.|  
|STYLE_3D_ROUNDED_SCROLL|Zeigt die dreidimensionale Registerkarten, auf denen schräg Seiten und abgerundete Ecken. Wenn es weitere Registerkarten sind als gleichzeitig angezeigt werden können, zeigt das Framework eine Dropdown-Pfeil, und ein Menü mit Registerkarten, damit aktiv ist.|  
|STYLE_3D_SCROLLED|Die dreidimensionale, rechteckige Registerkarten angezeigt. Wenn es weitere Registerkarten sind als gleichzeitig angezeigt werden können, zeigt das Framework eine Dropdown-Pfeil, und ein Menü mit Registerkarten, damit aktiv ist.|  
|STYLE_3D_VS2005|Zeigt dreidimensionalen, gerundet Registerkarten, auf denen Schrägen einseitige und einer vertikalen Seite verfügen.|  
|STYLE_FLAT|Zeigt die zweidimensionale Registerkarten, die linken und rechten Seite schräg haben.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Die zweidimensionale Registerkarten angezeigt. Wenn es weitere Registerkarten sind als gleichzeitig angezeigt werden können, zeigt das Framework Bildlaufpfeile an den Enden der Registerkartenbereich.|  
  
##  <a name="ondragenter"></a>  CMFCTabCtrl::OnDragEnter  
 Wird vom Framework während eines Drag & Drop-Vorgangs aufgerufen, wenn der Cursor zuerst das Fenster des aktuellen Registerkarten-Steuerelements wechselt.  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDataObject`  
 Verweist auf ein Objekt, das Daten enthält, die der Benutzer zieht.  
  
 [in] `dwKeyState`  
 Enthält den Status der Zusatztasten. Dieser Parameter ist eine bitweise Kombination (OR) der folgenden Werte: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`. Weitere Informationen finden Sie unter der **Nachrichtenparameter** Abschnitt [zu Mauseingabe](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 Enthält die aktuelle Position des Cursors in Clientkoordinaten.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `DROPEFFECT_NONE`, was bedeutet, dass die Drop-Ziel die Daten akzeptieren kann.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen Drag-and-Drop-Vorgang zu unterstützen. Überschreiben Sie diese Methode, um Ihr eigenes benutzerdefiniertes Verhalten zu implementieren.  
  
 Standardmäßig ruft diese Methode nur `CMFCTabCtrl::OnDragOver`, welche gibt immer `DROPEFFECT_NONE`.  
  
##  <a name="ondragover"></a>  CMFCTabCtrl::OnDragOver  
 Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger über die Drop-Zielfenster bewegt wird.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDataObject`  
 Zeiger auf eine [COleDataObject](../../mfc/reference/coledataobject-class.md) Objekt, das über das Ablageziel gezogen wird.  
  
 [in] `dwKeyState`  
 Der Status der Zusatztasten, also eine bitweise Kombination (oder) des `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`. Weitere Informationen finden Sie unter "Nachrichtenparameter" in [zu Mauseingabe](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 Die aktuelle Mausposition.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `DROPEFFECT_NONE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode mit Ihrer benutzerdefinierten Implementierung. Weitere Informationen finden Sie unter der [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) Methode.  
  
##  <a name="onshowtabdocumentsmenu"></a>  CMFCTabCtrl::OnShowTabDocumentsMenu  
 Ein Popupmenü von Fenstern im Registerkartenformat angezeigt wird, wartet, bis der Benutzer eine Registerkarte wählt, und die ausgewählte Registerkarte die aktive Registerkarte definiert.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die Koordinaten, an dem das Popupmenü anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveinmditabgroup"></a>  CMFCTabCtrl::SetActiveInMDITabGroup  
 Legt die aktuelle Registerkarte ein Registerkarten-Steuerelement als aktive Registerkarte in einer mehrere Dokument Schnittstelle Gruppe fest.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 `TRUE` um die aktive Registerkarte als aktuellen Registerkarte zu erstellen; `FALSE` um als aktuelle Registerkarte inaktiv festzulegen.  
  
### <a name="remarks"></a>Hinweise  
 Sie können mehrere Dokumentfenster in einer vertikalen oder horizontalen Registerkartengruppen organisieren und zufällige problemlos Dokumente aus einem Registerkartengruppe zu einem anderen.  
  
##  <a name="setactivetab"></a>  CMFCTabCtrl::SetActiveTab  
 Aktiviert eine Registerkarte.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTab`  
 Gibt den nullbasierten Index der Registerkarte zu aktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die angegebene Registerkarte aktiviert wurde; `FALSE` Wenn das angegebene `iTab` Parameterwert ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet keine der `AFX_WM_CHANGE_ACTIVE_TAB` -Benachrichtigung an das übergeordnete Fenster des Registerkarten-Steuerelements.  
  
 Die `SetActiveTab` Methodenaufrufe automatisch die [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) Methode, um zu verhindern, dass der Bildschirm blinkt.  
  
##  <a name="setactivetabboldfont"></a>  CMFCTabCtrl::SetActiveTabBoldFont  
 Aktiviert oder deaktiviert die Verwendung der fett formatierter Schrift für aktive Registerkarten.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsBold`  
 `TRUE` Um fett formatierter Schrift verwenden, um die Bezeichnung der aktiven Registerkarte angezeigt werden; `FALSE` Standardschriftart mit der Bezeichnung angezeigt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdrawframe"></a>  CMFCTabCtrl::SetDrawFrame  
 Gibt an, ob ein Frame Rechteck um ein eingebettetes Strich gezeichnet wird.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDraw`  
 `TRUE` ein Frame-Rechteck, um eine eingebettete Balken angezeigt; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setflatframe"></a>  CMFCTabCtrl::SetFlatFrame  
 Gibt an, ob einem flachen oder einem 3D Rahmen um Registerkartenbereichs gezeichnet werden soll.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 `TRUE` Um einen flachen (2D) Frame um Registerkartenbereichs zu zeichnen; `FALSE` einen dreidimensionalen (3D) Rahmen gezeichnet werden soll. Der Standardwert ist `TRUE`.  
  
 [in] `bRepaint`  
 `TRUE` Das Fenster sofort neu zeichnet; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimagelist"></a>  CMFCTabCtrl::SetImageList  
 Gibt an, mit einer Bildliste.  
  
```  
virtual BOOL SetImageList(
    UINT uiID,  
    int cx=15,  
    COLORREF clrTransp=RGB(255, 0, 255));  
  
virtual BOOL SetImageList(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die ID einer Bitmap-Ressource, die die Bildliste enthält.  
  
 [in] `cx`  
 Die Breite des jedes Bilds in Pixel. Der Standardwert ist 15.  
  
 [in] `clrTransp`  
 Die Farbe transparentes Bild. Die Teile des Bilds, die diese Farbe werden transparent sein. Der Standardwert ist das Farbe Magenta, RGB(255,0,255).  
  
 [in] `hImageList`  
 Ein Handle für einen vorab geladenen Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. `FALSE` Wenn das Registerkarten-Steuerelement mit einer Flatfile-Format erstellt wird oder wenn die erste methodenüberladung Bitmap nicht laden kann, die von angegeben wird die `uiID` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Bildliste des Registersteuerelements festzulegen. Die Bilder aus der Bildliste sind neben der Beschriftung Registerkarte angezeigt. Diese Methode berechnet die Höhe der Registerkarte ", damit die Registerkarte" festgelegt wird, um das Bild und Text enthalten.  
  
 Verwenden der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) -Methode, die durch das Registerkarten-Steuerelement an den Index des Bilds anzuzeigenden geerbt wird.  
  
##  <a name="setresizemode"></a>  CMFCTabCtrl::SetResizeMode  
 Gibt an, wie das aktuelle Registerkarten-Steuerelement Größe geändert werden kann, und klicken Sie dann erneut an das Steuerelement.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `resizeMode`  
 Eines der `CMFCTabCtrl::ResizeMode` Enumerationswerte, der angibt, wie das Registerkarten-Steuerelement Größe geändert werden kann. Eine Liste der möglichen Werte finden Sie unter "Hinweise" der Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 Die `resizeMode` Parameter kann eine der folgenden `ResizeMode` Enumerationswerte.  
  
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
 [in] `nTabMaxWidth`  
 Die maximale Registerkarte Breite in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Breite der einzelnen Registerkarten in einem Fenster im Registerkartenformat zu beschränken. Diese Methode ist nützlich, wenn die Registerkarten sehr lange Bezeichnungen sein. Die [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) Klassenkonstruktor initialisiert die Registerkarte maximale Breite 0, was bedeutet, dass die Breite nicht beschränkt ist.  
  
##  <a name="stopresize"></a>  CMFCTabCtrl::StopResize  
 Beendet den aktuellen Vorgang der Größenänderung auf das Registerkarten-Steuerelement.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCancel`  
 `TRUE` für das Abbrechen der aktuellen Größenänderung; `FALSE` zum Abschließen der aktuellen Größenänderungsvorgangs. In beiden Fällen beendet das Framework das Resize-Rechteck gezeichnet.  
  
##  <a name="synchronizescrollbar"></a>  CMFCTabCtrl::SynchronizeScrollBar  
 Zeichnet eine horizontale Bildlaufleiste für ein Registerkarten-Steuerelement, in der Flatfile Registerkarten angezeigt.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `pScrollInfo`  
 Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur oder `NULL`. Rückkehr dieser Methode, und wenn dieser Parameter nicht `NULL`, die Struktur enthält alle Parameter der Bildlaufleiste. Der Standardwert ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wirkt sich auf nur ein Registerkarten-Steuerelement, in der Flatfile Registerkarten angezeigt. Die Bildlaufleiste beeinflusst alle Registerkarten zur gleichen Zeit.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md)
