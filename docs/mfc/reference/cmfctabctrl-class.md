---
title: CMFCTabCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CMFCTabCtrl::SwapTabs method
- CMFCTabCtrl constructor
- CMFCTabCtrl::MoveTab method
- CMFCTabCtrl::GetTabFromPoint method
- CMFCTabCtrl::PreTranslateMessage method
- CMFCTabCtrl::RecalcLayout method
- CMFCTabCtrl class
- CMFCTabCtrl::IsPtInTabArea method
ms.assetid: d441385d-2c72-4203-96fa-deae2273da35
caps.latest.revision: 33
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
ms.openlocfilehash: 595ff7fbcd55f3b756ce650e02b6247b898d7629
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabctrl-class"></a>CMFCTabCtrl Class
Die `CMFCTabCtrl` Klasse bietet Funktionen für ein Registerkarten-Steuerelement. Das Registerkarten-Steuerelement zeigt ein andockbares Fenster an, mit flachen oder dreidimensionalen Registerkarten am oberen oder unteren Rand. Die Registerkarten können Text und ein Bild enthalten und bei Aktivierung die Farbe ändern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCTabCtrl::CMFCTabCtrl`|Standardkonstruktor|  
|`CMFCTabCtrl::~CMFCTabCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTabCtrl::ActivateMDITab](#activatemditab)|Zeigt die angegebene Registerkarte des aktuellen Registerkarten-Steuerelements, und setzt den Fokus auf die Registerkarte.|  
|[CMFCTabCtrl::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)||  
|[CMFCTabCtrl::AutoSizeWindow](#autosizewindow)|Gibt an, ob das Framework Größe des Clientbereichs aller Registerkarte Steuerelement-Fenster, wenn ein Element der Benutzeroberfläche der Registerkarte Steuerelement.|  
|[CMFCTabCtrl::CalcRectEdit](#calcrectedit)|Verkleinert die Größe des angegebenen Bereichs. (Überschreibt `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCTabCtrl::Create](#create)|Das Registerkarten-Steuerelement erstellt, und fügt es der `CMFCTabCtrl` Objekt.|  
|`CMFCTabCtrl::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCTabCtrl::EnableActiveTabCloseButton](#enableactivetabclosebutton)|Blendet eine Schaltfläche zum Schließen ( **X**) auf der aktiven Registerkarte.|  
|[CMFCTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Aktiviert oder deaktiviert die registerkartenbezeichnungen bearbeitet werden. (Überschreibt [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu)|Ersetzt die zwei Schaltflächen, die die Registerkarten mit einer Schaltfläche ausgeführt wird, die im Registerformat ein Menü geöffnet wird.|  
|[CMFCTabCtrl::EnsureVisible](#ensurevisible)|Stellt sicher, dass eine Registerkarte angezeigt wird.|  
|[CMFCTabCtrl::GetDocumentIcon](#getdocumenticon)|Ruft das Symbol, das eine Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat zugeordnet ist.|  
|[CMFCTabCtrl::GetFirstVisibleTabNum](#getfirstvisibletabnum)|Ruft den Index der ersten Registerkarte, die im aktuellen Registerkarten-Steuerelement angezeigt wird.|  
|[CMFCTabCtrl::GetResizeMode](#getresizemode)|Ruft einen Wert, der angibt, wie das aktuelle Registerkarten-Steuerelement geändert werden kann.|  
|[CMFCTabCtrl::GetScrollBar](#getscrollbar)|Ruft einen Zeiger auf die Bildlaufleiste fest, die das Registerkarten-Steuerelement zugeordnet ist.|  
|[CMFCTabCtrl::GetTabArea](#gettabarea)|Ruft das umschließende Rechteck des Registerkartenbereichs Bezeichnung der oberen oder unteren des Registerkarten-Steuerelements ab. (Überschreibt [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCTabCtrl::GetTabFromPoint`|Ruft die Registerkarte, die einen angegebenen Punkt enthält. (Überschreibt [CMFCBaseTabCtrl::GetTabFromPoint](../../mfc/reference/cmfcbasetabctrl-class.md#gettabfrompoint).)|  
|[CMFCTabCtrl::GetTabMaxWidth](#gettabmaxwidth)|Ruft die maximale Breite einer Registerkarte ab.|  
|[CMFCTabCtrl::GetTabsHeight](#gettabsheight)|Ruft die Höhe des Registerkartenbereichs des aktuellen Registerkarten-Steuerelements ab.|  
|[CMFCTabCtrl::GetTabsRect](#gettabsrect)|Ruft ein Rechteck, den Registerkartenbereich des aktuellen Registerkarten-Steuerelements umschließt, ab. (Überschreibt [CMFCBaseTabCtrl::GetTabsRect](../../mfc/reference/cmfcbasetabctrl-class.md#gettabsrect).)|  
|`CMFCTabCtrl::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCTabCtrl::GetWndArea](#getwndarea)|Ruft die Grenzen des Clientbereichs des aktuellen Registerkarten-Steuerelements ab.|  
|[CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar)|Blendet die horizontale Bildlaufleiste, ggf. das aktive Fenster.|  
|[CMFCTabCtrl::HideInactiveWindow](#hideinactivewindow)|Gibt an, ob das Framework um inaktive Registerkarte Steuerelement anzuzeigen.|  
|[CMFCTabCtrl::HideNoTabs](#hidenotabs)|Aktiviert oder deaktiviert den Registerkartenbereich zeichnen, wenn keine Registerkarten sichtbar sind.|  
|[CMFCTabCtrl::HideSingleTab](#hidesingletab)|Aktiviert oder deaktiviert eine Registerkarte zeichnen, bei ein einzelnes Fenster im Registerkartenformat. (Überschreibt [CMFCBaseTabCtrl::HideSingleTab](../../mfc/reference/cmfcbasetabctrl-class.md#hidesingletab).)|  
|[CMFCTabCtrl::IsActiveInMDITabGroup](#isactiveinmditabgroup)|Gibt an, ob die aktuelle Registerkarte eines Registersteuerelements der aktiven Registerkarte in einer mehrere Registerkartengruppe der Dokument-Schnittstelle ist.|  
|[CMFCTabCtrl::IsActiveTabBoldFont](#isactivetabboldfont)|Gibt an, ob der Text der aktiven Registerkarte mit fett angezeigt wird.|  
|[CMFCTabCtrl::IsActiveTabCloseButton](#isactivetabclosebutton)|Gibt an, ob die Schaltfläche "Schließen" ( **X**) auf eine aktive Registerkarte oder in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.|  
|[CMFCTabCtrl::IsDrawFrame](#isdrawframe)|Gibt an, ob es sich bei das Fenster im Registerkartenformat ein Frame Rechteck um eingebettete Bereiche zeichnet.|  
|[CMFCTabCtrl::IsFlatFrame](#isflatframe)|Gibt an, ob der Rahmen um den Registerkartenbereich flach oder in 3D ist.|  
|[CMFCTabCtrl::IsFlatTab](#isflattab)|Gibt an, ob die Darstellung der Registerkarten im aktuellen Registersteuerelement flach oder nicht.|  
|[CMFCTabCtrl::IsLeftRightRounded](#isleftrightrounded)|Gibt an, ob die Darstellung der linken und rechten Seite einer Registerkarte im aktuellen Registersteuerelement gerundet wird.|  
|[CMFCTabCtrl::IsMDITabGroup](#ismditabgroup)|Gibt an, ob das aktuelle Registerkarten-Steuerelement im Clientbereich eines Fensters Multiple Document Interface enthalten ist.|  
|[CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle)|Gibt an, ob das aktuelle Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird.|  
|`CMFCTabCtrl::IsPtInTabArea`|Bestimmt, ob ein Punkt in der Registerkartenbereich ist. (Überschreibt [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|[CMFCTabCtrl::IsSharedScroll](#issharedscroll)|Gibt an, ob das aktuelle Registerkarten-Steuerelement ein Bildlauf durchgeführt wird, die über Registerkarten als Gruppe einen Bildlauf durchführen kann.|  
|[CMFCTabCtrl::IsTabDocumentsMenu](#istabdocumentsmenu)|Gibt an, ob das Registerkarten-Steuerelement zeigt Bildlaufschaltflächen oder eine Schaltfläche, die ein Menü Fenster im Registerkartenformat angezeigt.|  
|[CMFCTabCtrl::IsVS2005Style](#isvs2005style)|Gibt an, ob Registerkarten im Stil von Visual Studio .NET 2005 angezeigt werden.|  
|[CMFCTabCtrl::ModifyTabStyle](#modifytabstyle)|Gibt die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement.|  
|`CMFCTabCtrl::MoveTab`|Verschiebt eine Registerkarte auf eine andere Registerkarte Position. (Überschreibt [CMFCBaseTabCtrl::MoveTab](../../mfc/reference/cmfcbasetabctrl-class.md#movetab).)|  
|[CMFCTabCtrl::OnDragEnter](#ondragenter)|Wird vom Framework aufgerufen, wenn der Cursor zuerst in der Registerkarte Steuerelementfensters gezogen wird.|  
|[CMFCTabCtrl::OnDragOver](#ondragover)|Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger über das Zielfenster bewegt wird. (Überschreibt [CMFCBaseTabCtrl::OnDragOver](../../mfc/reference/cmfcbasetabctrl-class.md#ondragover).)|  
|[CMFCTabCtrl::OnShowTabDocumentsMenu](#onshowtabdocumentsmenu)|Ein Popup-Menü im Registerformat angezeigt wird, wartet, bis der Benutzer wählt eine Registerkarte aus, und die ausgewählten der aktive Registerkarte definiert.|  
|`CMFCTabCtrl::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CMFCBaseTabCtrl::PreTranslateMessage](../../mfc/reference/cmfcbasetabctrl-class.md#pretranslatemessage).)|  
|`CMFCTabCtrl::RecalcLayout`|Berechnet das interne Layout des Registerkarten-Steuerelements. (Überschreibt [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCTabCtrl::SetActiveInMDITabGroup](#setactiveinmditabgroup)|Die aktuelle Registerkarte ein Registerkarten-Steuerelement festgelegt als die aktive Registerkarte in einer mehrere Dokument Schnittstelle Registerkartengruppe.|  
|[CMFCTabCtrl::SetActiveTab](#setactivetab)|Aktiviert eine Registerkarte. (Überschreibt [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont)|Aktiviert oder deaktiviert die Verwendung der fett auf aktive Registerkarten.|  
|[CMFCTabCtrl::SetDrawFrame](#setdrawframe)|Aktiviert oder deaktiviert Drawinga Frame Rechteck um eine eingebettete Statusleiste.|  
|[CMFCTabCtrl::SetFlatFrame](#setflatframe)|Gibt an, ob einem flachen oder einem 3D Rahmen um den Registerkartenbereich zu zeichnen.|  
|[CMFCTabCtrl::SetImageList](#setimagelist)|Gibt eine Liste der Images. (Überschreibt [CMFCBaseTabCtrl::SetImageList](../../mfc/reference/cmfcbasetabctrl-class.md#setimagelist).)|  
|[CMFCTabCtrl::SetResizeMode](#setresizemode)|Gibt an, wie das aktuelle Registerkarten-Steuerelement geändert werden kann, und zeigt dann das Steuerelement erneut an.|  
|[CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth)|Gibt die maximale Tabulatorbreite in einem Fenster im Registerkartenformat.|  
|[CMFCTabCtrl::StopResize](#stopresize)|Beendet den aktuellen Vorgang auf die Registerkarte.|  
|`CMFCTabCtrl::SwapTabs`|Tauscht zwei Registerkarten. (Überschreibt [CMFCBaseTabCtrl::SwapTabs](../../mfc/reference/cmfcbasetabctrl-class.md#swaptabs).)|  
|[CMFCTabCtrl::SynchronizeScrollBar](#synchronizescrollbar)|Zeichnet eine horizontale Bildlaufleiste ein Registerkarten-Steuerelement, das flache Registerkarten anzeigt.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCTabCtrl::m_bEnableActivate](#m_benableactivate)|Verhindert, dass die aktive Ansicht den Fokus verlieren, wenn eine neue Registerkarte eingefügt und aktiviert ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCTabCtrl` -Klasse unterstützt:  
  
-   Registerkarte Steuerelement Formaten mit 3D flach und Flatfile mit einer gemeinsamen horizontalen Bildlaufleiste.  
  
-   Die Registerkarten am oberen oder unteren Rand des Fensters.  
  
-   Registerkarten, die Text, Bilder oder Text und Bilder anzeigen.  
  
-   Registerkarten, die Farbe zu ändern, wenn die Registerkarte aktiv ist.  
  
-   Rahmen Sie für anpassbaren Registerkarten ändert sich.  
  
-   Abnehmbare im Registerformat.  
  
 Die `CMFCTabCtrl` -Klasse kann verwendet werden, mit einem Dialogfeld, eignet sich jedoch für Applikationen, mit dem Andocken Balken wie steuern [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] und [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Weitere Informationen finden Sie unter [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).  
  
 Gehen Sie folgendermaßen vor um eine geändert werden kann, fügen Andocken von Registerkarten-Steuerelement in Ihrer Anwendung:  
  
1.  Erstellen Sie eine Instanz des [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md).  
  
2.  Rufen Sie [CDockablePane::Create](../../mfc/reference/cdockablepane-class.md#create).  
  
3.  Verwendung [CBaseTabbedPane::AddTab](../../mfc/reference/cbasetabbedpane-class.md#addtab) oder [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) neue Registerkarten hinzufügen.  
  
4.  Rufen Sie [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking) , damit das aktuelle andockbaren Registerkarten-Steuerelement an das Hauptrahmenfenster Andocken kann.  
  
5.  Rufen Sie [CFrameWndEx::DockPane](../../mfc/reference/cframewndex-class.md#dockpane) das Fenster im Registerkartenformat an das Hauptrahmenfenster andocken.  
  
 Ein Beispiel zum Erstellen ein Fenster im Registerkartenformat als eine andockbare Symbolleiste finden Sie unter [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md). Verwenden `CMFCTabCtrl` als Steuerelement nicht angedockt, erstellen Sie eine `CMFCTabCtrl` Objekt, und rufen Sie dann [CMFCTabCtrl::Create](#create).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCTabCtrl` Klasse zum Konfigurieren einer `CMFCTabCtrl` Objekt. Das Beispiel erläutert das Hinzufügen einer Registerkarte, zeigen die Schaltfläche "Schließen" auf der aktiven Registerkarte, bearbeitbaren registerkartenbezeichnungen aktivieren und ein Popup-Menü Fenster im Registerkartenformat Bezeichnungen anzuzeigen. Dieses Beispiel ist Teil der [Auflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection&#1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection&3;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtabctrl.h  
  
##  <a name="activatemditab"></a>CMFCTabCtrl::ActivateMDITab  
 Zeigt die angegebene Registerkarte des aktuellen Registerkarten-Steuerelements, und setzt den Fokus auf die Registerkarte.  
  
```  
void ActivateMDITab(int nTab = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTab`  
 Der nullbasierte Index von einer Registerkarte zur Anzeige oder -1, der derzeit aktiven Registerkarte an.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CMFCTabCtrl::AllowDestroyEmptyTabbedPane  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="autosizewindow"></a>CMFCTabCtrl::AutoSizeWindow  
 Gibt an, ob das Framework Größe des Clientbereichs aller Registerkarte Steuerelement-Fenster, wenn ein Element der Benutzeroberfläche der Registerkarte Steuerelement.  
  
```  
void AutoSizeWindow(BOOL bAutoSize = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAutoSize`  
 `TRUE`Registerkarte Steuerelement Windows automatisch angepasst; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="create"></a>CMFCTabCtrl::Create  
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
 Der Stil des Registerkarten-Steuerelements. Weitere Informationen finden Sie in den Hinweisen.  
  
 [in] `rect`  
 Ein Rechteck, das Registerkarten-Steuerelement umschließt.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf ein übergeordnetes Fenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `nID`  
 Die ID des Registerkarten-Steuerelements.  
  
 [in] `location`  
 Der Speicherort der Registerkarten. Der Standardwert ist `LOCATION_BOTTOM`. Weitere Informationen finden Sie in den Hinweisen.  
  
 [in] `bCloseBtn`  
 `TRUE`Um eine Schaltfläche "Schließen" auf der Registerkarte angezeigt werden. andernfalls `FALSE`. Der Standardwert ist `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`, wenn erfolgreich, andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle beschreibt die Werte Sie, für angeben können die `style` Parameter.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|STYLE_3D|Erstellt ein Registerkarten-Steuerelement mit einem dreidimensionalen Erscheinungsbild.|  
|STYLE_FLAT|Erstellt ein Registerkarten-Steuerelement mit Flatfile-Registerkarten.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Erstellt ein Registerkarten-Steuerelement mit Flatfile-Registerkarten und eine Bildlaufleiste angezeigt, die die Registerkarten einen Bildlauf durchführen kann, wenn sie von einem übergeordneten Fenster abgeschnitten werden.|  
|STYLE_3D_ONENOTE|Erstellt ein Registerkarten-Steuerelement im Stil von Microsoft OneNote.|  
|STYLE_3D_VS2005|Erstellt ein Registerkarten-Steuerelement im Stil von Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED|Erstellt ein Registerkarten-Steuerelement mit abgerundeten Registerkarten im Stil von Microsoft Visual Studio 2005.|  
|STYLE_3D_ROUNDED_SCROLL|Erstellt ein Registerkarten-Steuerelement mit abgerundeten Registerkarten und Bildlaufschaltflächen im Stil von Microsoft Visual Studio 2005.|  
  
 Die folgende Tabelle enthält die Werte Sie, für angeben können die `location` Parameter.  
  
|Speicherort|Beschreibung|  
|--------------|-----------------|  
|LOCATION_BOTTOM|Registerkarten befinden sich am unteren Rand des Registersteuerelements.|  
|LOCATION_TOP|Registerkarten befinden sich am oberen Rand der Registerkarten-Steuerelement.|  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in der `CMFCTabCtrl` Klasse. Dieses Beispiel ist Teil der [Auflistung Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_StateCollection&#1;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_1.h)]  
[!code-cpp[NVC_MFC_StateCollection&#2;](../../mfc/reference/codesnippet/cpp/cmfctabctrl-class_3.cpp)]  
  
##  <a name="calcrectedit"></a>CMFCTabCtrl::CalcRectEdit  
 Verkleinert die Größe des angegebenen Bereichs.  
  
```  
virtual void CalcRectEdit(CRect& rectEdit);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectEdit`  
 Ein Rechteck, das den Bereich einer Registerkarte angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn Sie die Beschriftung einer Registerkarte ändern. Diese Methode entfernt die Links und rechts des angegebenen Rechtecks von einem halben der aktuellen Registerkarte Höhe und oben und unten, um eine Einheit entfernt.  
  
##  <a name="enableactivetabclosebutton"></a>CMFCTabCtrl::EnableActiveTabCloseButton  
 Blendet eine Schaltfläche zum Schließen ( **X**) auf der aktiven Registerkarte.  
  
```  
void EnableActiveTabCloseButton(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`auf die Schaltfläche "Schließen" auf der aktiven Registerkarte angezeigt werden. `FALSE` auf die Schaltfläche "Schließen" in der oberen rechten Ecke des Registerkartenbereichs anzuzeigen. Der Standardwert ist `TRUE`.  
  
##  <a name="enableinplaceedit"></a>CMFCTabCtrl::EnableInPlaceEdit  
 Aktiviert oder deaktiviert die registerkartenbezeichnungen bearbeitet werden.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Registerkarte bearbeitet werden Bezeichnungen. `FALSE` bearbeitbaren registerkartenbezeichnungen zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enabletabdocumentsmenu"></a>CMFCTabCtrl::EnableTabDocumentsMenu  
 Schaltet zwischen einer Benutzeroberfläche, die zwei Schaltflächen wird verwendet, um die Registerkarten zu blättern und eine Schnittstelle, die ein Popupmenü von Fenstern im Registerkartenformat angezeigt.  
  
```  
void EnableTabDocumentsMenu(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Um ein Popupmenü der Fenster im Registerkartenformat Bezeichnungen angezeigt werden. `FALSE` vorwärts und rückwärts Bildlaufschaltflächen angezeigt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer eine registerkartenbezeichnung klickt, zeigt das Framework das entsprechende Fenster im Registerkartenformat. Wenn die Bezeichnung der Registerkarte angezeigt wird, wird das Fenster im Registerkartenformat geöffnet, ohne Änderung seiner Position. Wenn der Benutzer ein Dokument aus dem Popupmenü wählt aus, und das entsprechende Fenster im Registerkartenformat außerhalb des Bildschirms ist, wird das Fenster im Registerkartenformat der ersten Registerkarte.  
  
##  <a name="ensurevisible"></a>CMFCTabCtrl::EnsureVisible  
 Stellt sicher, dass eine Registerkarte angezeigt wird.  
  
```  
virtual BOOL EnsureVisible(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTab`  
 Der nullbasierte Index der Registerkarte.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn sie erfolgreich ist; `FALSE` Wenn das `iTab` Parameterindex ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um sicherzustellen, dass die angegebene Registerkarte sichtbar ist. Das Registerkarten-Steuerelement wird scrollen, wenn dies erforderlich ist.  
  
##  <a name="getdocumenticon"></a>CMFCTabCtrl::GetDocumentIcon  
 Ruft das Bild, das mit einer Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat verknüpft ist.  
  
```  
static HICON __stdcall GetDocumentIcon(UINT nCmdID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nCmdID`  
 Die Befehls-ID einer Registerkarte in einem Popupmenü von Fenstern im Registerkartenformat.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des ein Bitmap-Bild.  
  
##  <a name="getfirstvisibletabnum"></a>CMFCTabCtrl::GetFirstVisibleTabNum  
 Ruft den Index der ersten Registerkarte, die im aktuellen Registerkarten-Steuerelement angezeigt wird.  
  
```  
virtual int GetFirstVisibleTabNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index einer Registerkarte im Registerkarten-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode nur, wenn das Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird. Verwenden der [CMFCTabCtrl::IsOneNoteStyle](#isonenotestyle) Methode, um den Stil zu bestimmen.  
  
##  <a name="getresizemode"></a>CMFCTabCtrl::GetResizeMode  
 Ruft einen Wert, der angibt, wie das aktuelle Registerkarten-Steuerelement geändert werden kann.  
  
```  
ResizeMode GetResizeMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eines der `CMFCTabCtrl::ResizeMode` -Enumerationswerte, der angibt, wie das Registerkarten-Steuerelement geändert werden kann. Eine Liste der möglichen Werte finden Sie im Abschnitt Hinweise der [CMFCTabCtrl::SetResizeMode](#setresizemode) Methode.  
  
##  <a name="getscrollbar"></a>CMFCTabCtrl::GetScrollBar  
 Ruft einen Zeiger auf die Bildlaufleiste fest, die das Registerkarten-Steuerelement zugeordnet ist.  
  
```  
CScrollBar* GetScrollBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Scrollbar-Objekt oder ein `NULL` das Registerkarten-Steuerelement wurde keine mithilfe von erstellt die `STYLE_FLAT_SHARED_HORZ_SCROLL` Stil.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eingebettete Schiebeleiste des Steuerelements zuzugreifen. Eine Bildlaufleiste fest wird nur erstellt, wenn das Registerkarten-Steuerelement verfügt über die `STYLE_FLAT_SHARED_HORZ_SCROLL` Stil.  
  
##  <a name="gettabarea"></a>CMFCTabCtrl::GetTabArea  
 Ruft das umschließende Rechteck des Registerkartenbereichs Bezeichnung der oberen oder unteren des Registerkarten-Steuerelements ab.  
  
```  
void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectTabAreaTop`  
 Bei der Rückgabe dieser Methode enthält dieser Verweis ein Rechteck, das die oberste Bezeichnung Registerkartenbereich umschließt. Das Rechteck ist in Clientkoordinaten. Dieser Verweis ist leer, wenn keine Bezeichnung Registerkartenbereich am oberen Rand des Registersteuerelements vorhanden ist.  
  
 [out] `rectTabAreaBottom`  
 Bei der Rückgabe dieser Methode enthält dieser Verweis ein Rechteck, das den unteren Bezeichnung Registerkartenbereich umschließt. Das Rechteck ist in Clientkoordinaten. Dieser Verweis ist leer, wenn keine Registerkarte Bezeichnung Bereich am unteren Rand des Registersteuerelements vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Größe und Position des Registerkartenbereichs im Fenster im Registerkartenformat zu bestimmen.  
  
##  <a name="gettabmaxwidth"></a>CMFCTabCtrl::GetTabMaxWidth  
 Ruft die maximale Breite einer Registerkarte ab.  
  
```  
int GetTabMaxWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Maximale Breite von einer Registerkarte in Pixel. Wenn der Rückgabewert 0 ist, ist die Registerkarte Breite unbegrenzt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetTabMaxWidth](#settabmaxwidth) maximale Tabulatorbreite festgelegt.  
  
##  <a name="gettabsheight"></a>CMFCTabCtrl::GetTabsHeight  
 Ruft die Höhe des Registerkartenbereichs des aktuellen Registerkarten-Steuerelements ab.  
  
```  
virtual int GetTabsHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Registerkartenbereichs, wenn eine beliebige Registerkarte sichtbar ist, oder NULL, wenn keine Registerkarte angezeigt wird.  
  
##  <a name="gettabsrect"></a>CMFCTabCtrl::GetTabsRect  
 Ruft ein Rechteck, den Registerkartenbereich des aktuellen Registerkarten-Steuerelements umschließt, ab.  
  
```  
virtual void GetTabsRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rect`  
 Bei dieser Methode wird der `rect` Parameter enthält ein Rechteck, das den Registerkartenbereich umschließt.  
  
##  <a name="getwndarea"></a>CMFCTabCtrl::GetWndArea  
 Ruft die Grenzen des Clientbereichs des aktuellen Registerkarten-Steuerelements ab.  
  
```  
void GetWndArea(CRect& rect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `rect`  
 Bei der Rückgabe dieser Methode enthält dieser Parameter ein Rechteck, das aktuelle Registerkarten-Steuerelement umschließt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hideactivewindowhorzscrollbar"></a>CMFCTabCtrl::HideActiveWindowHorzScrollBar  
 Blendet die horizontale Bildlaufleiste, ggf. in das aktive Fenster.  
  
```  
void HideActiveWindowHorzScrollBar();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um zu verhindern, dass das Registerkarten-Steuerelement blinkt, wenn der Benutzer zwischen Registerkarten-Steuerelement wechselt.  
  
##  <a name="hideinactivewindow"></a>CMFCTabCtrl::HideInactiveWindow  
 Gibt an, ob das Framework inaktiv Registerkarte Steuerelement Windows.  
  
```  
void HideInactiveWindow(BOOL bHide = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHide`  
 `TRUE`nicht zu einer inaktiven Fensters angezeigt werden. `FALSE` ein inaktives Fensters angezeigt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hidenotabs"></a>CMFCTabCtrl::HideNoTabs  
 Aktivieren oder Deaktivieren des Registerkartenbereichs zeichnen, wenn keine Registerkarten sichtbar sind.  
  
```  
void HideNoTabs(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHide`  
 `TRUE`So aktivieren Sie das Zeichnen der Registerkarte; `FALSE` Zeichnung zu deaktivieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="hidesingletab"></a>CMFCTabCtrl::HideSingleTab  
 Aktiviert oder deaktiviert Registerkarte zeichnen, wird ein einzelnes Fenster im Registerkartenformat.  
  
```  
virtual void HideSingleTab(BOOL bHide=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bHide`  
 `TRUE`Um eine Registerkarte für ein einzelnes Fenster im Registerkartenformat nicht zu zeichnen. `FALSE` zum Zeichnen einer einzelnen Registerkarte. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isactiveinmditabgroup"></a>CMFCTabCtrl::IsActiveInMDITabGroup  
 Gibt an, ob die aktuelle Registerkarte eines Registersteuerelements der aktiven Registerkarte in einer Registerkartengruppe der mehrere Dokument-Schnittstelle ist.  
  
```  
BOOL IsActiveInMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn als aktuelle Registerkarte eines Registersteuerelements der aktiven Registerkarte in einer MDI-Registerkarte-Gruppe ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie mehrere Dokumentfenster in entweder vertikal oder horizontal Registerkartengruppen organisieren und problemlos Dokumente von einer Registerkartengruppe in eine andere mischen.  
  
##  <a name="isactivetabboldfont"></a>CMFCTabCtrl::IsActiveTabBoldFont  
 Gibt an, ob der Text der aktiven Registerkarte mit fett angezeigt wird.  
  
```  
BOOL IsActiveTabBoldFont() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die aktive Registerkarte angezeigt wird, verwenden die fette Schriftart; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetActiveTabBoldFont](#setactivetabboldfont) Methode, um die aktive Registerkarte Schriftart zu ändern.  
  
##  <a name="isactivetabclosebutton"></a>CMFCTabCtrl::IsActiveTabCloseButton  
 Gibt an, ob die Schaltfläche "Schließen" ( **X**) auf einem aktiven Registerkarte oder in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.  
  
```  
virtual BOOL IsActiveTabCloseButton() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche "Schließen" auf der aktiven Registerkarte angezeigt wird. `FALSE` Wenn die Schaltfläche "Schließen" in der oberen rechten Ecke des Registerkartenbereichs angezeigt wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawframe"></a>CMFCTabCtrl::IsDrawFrame  
 Gibt an, ob es sich bei das Fenster im Registerkartenformat ein Frame Rechteck um eingebettete Bereiche zeichnet.  
  
```  
BOOL IsDrawFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Frame Rechteck gezeichnet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetDrawFrame](#setdrawframe) Methode zum Aktivieren oder deaktivieren das Zeichnen eines Rechtecks Frame.  
  
##  <a name="isflatframe"></a>CMFCTabCtrl::IsFlatFrame  
 Gibt an, ob der Rahmen um den Registerkartenbereich flach oder in 3D ist.  
  
```  
BOOL IsFlatFrame() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie der Rahmen um den Registerkartenbereich flach ist; `FALSE` , wenn der Frame dreidimensional ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::SetFlatFrame](#setflatframe) -Methode ändern, wie der Rahmen gezeichnet wird.  
  
##  <a name="isflattab"></a>CMFCTabCtrl::IsFlatTab  
 Gibt an, ob die Darstellung der Registerkarten im aktuellen Registersteuerelement flach oder nicht.  
  
```  
virtual BOOL IsFlatTab() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Darstellung der Registerkarten im aktuellen Registersteuerelement flach ist; andernfalls `FALSE`.  
  
##  <a name="isleftrightrounded"></a>CMFCTabCtrl::IsLeftRightRounded  
 Gibt an, ob die Darstellung der linken und rechten Seite einer Registerkarte im aktuellen Registersteuerelement gerundet wird.  
  
```  
virtual BOOL IsLeftRightRounded() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Seiten der einzelnen Registerkarten wird gerundet. andernfalls `FALSE`.  
  
##  <a name="ismditabgroup"></a>CMFCTabCtrl::IsMDITabGroup  
 Gibt an, ob das aktuelle Registerkarten-Steuerelement im Clientbereich eines Fensters Multiple Document Interface enthalten ist.  
  
```  
virtual BOOL IsMDITabGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das aktuelle Registerkarten-Steuerelement in ein MDI-Fenster des Clientbereichs ist. andernfalls `FALSE`.  
  
##  <a name="isonenotestyle"></a>CMFCTabCtrl::IsOneNoteStyle  
 Gibt an, ob das aktuelle Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird.  
  
```  
virtual BOOL IsOneNoteStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Registerkarten-Steuerelement im Stil von Microsoft OneNote angezeigt wird; andernfalls `FALSE`.  
  
##  <a name="issharedscroll"></a>CMFCTabCtrl::IsSharedScroll  
 Gibt an, ob das aktuelle Registerkarten-Steuerelement ein Bildlauf durchgeführt wird, die über Registerkarten als Gruppe einen Bildlauf durchführen kann.  
  
```  
BOOL IsSharedScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Registerkarten-Steuerelement eine Bildlaufleiste freigegebenen hat. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `TRUE` Wenn die `style` Parameter von der [CMFCTabCtrl::Create](#create) Methode STYLE_FLAT_SHARED_HORZ_SCROLL ist.  
  
##  <a name="istabdocumentsmenu"></a>CMFCTabCtrl::IsTabDocumentsMenu  
 Gibt an, ob das Registerkarten-Steuerelement zeigt Bildlaufschaltflächen oder eine Schaltfläche, die ein Menü Fenster im Registerkartenformat angezeigt.  
  
```  
BOOL IsTabDocumentsMenu() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Popup-Menü Fenster im Registerkartenformat Etiketten mit Fenstern im Registerformat durchgeführt; `FALSE` wenn Fenster im Registerkartenformat mit vorwärts und rückwärts Bildlaufschaltflächen durchgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCTabCtrl::EnableTabDocumentsMenu](#enabletabdocumentsmenu) -Methode an die Methode des Bildlaufs im Registerkartenformat Windows.  
  
##  <a name="isvs2005style"></a>CMFCTabCtrl::IsVS2005Style  
 Gibt an, ob Registerkarten im Stil von Visual Studio 2005 gezeichnet werden.  
  
```  
virtual BOOL IsVS2005Style() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Registerkarten im Stil von Visual Studio 2005 gezogen werden. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `style` Parameter von der [CMFCTabCtrl::Create](#create) Methode, um anzugeben, wie die Registerkarten gezeichnet werden.  
  
##  <a name="m_benableactivate"></a>CMFCTabCtrl::m_bEnableActivate  
 Verhindert, dass die aktive Ansicht den Fokus verlieren, wenn eine neue Registerkarte eingefügt und aktiviert ist.  
  
```  
static BOOL m_bEnableActivate;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Fokus wird in der Regel von einem neuen Fenster im Registerkartenformat ausgeführt, wenn die Registerkarte eingefügt und aktiviert ist. Legen Sie die `CMFCTabCtrl::m_bEnableActivate` Membervariable `FALSE` behält die ursprünglichen den Fokus. Der Standardwert ist `TRUE`.  
  
##  <a name="modifytabstyle"></a>CMFCTabCtrl::ModifyTabStyle  
 Gibt die Darstellung der Registerkarten im aktuellen Registerkarten-Steuerelement.  
  
```  
BOOL ModifyTabStyle(Style style);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `style`  
 Einer der Enumerationswerte, der die Darstellung des Registerkarten-Steuerelements angibt. Weitere Informationen finden Sie in der Tabelle unter "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der `style` Parameter kann eine der folgenden `CMFCTabCtrl::Style` Enumerationen.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|STYLE_3D|Dreidimensionale, rechteckige Registerkarten, die abgerundeten Ecken angezeigt.|  
|STYLE_3D_ONENOTE|Die dreidimensionale Registerkarten, die eine vertikale und eine Schräge Seite besitzen und abgerundete Ecken haben, die, angezeigt.|  
|STYLE_3D_ROUNDED|Zeigt die dreidimensionale Registerkarten, die schräg Seiten und abgerundete Ecken.|  
|STYLE_3D_ROUNDED_SCROLL|Zeigt die dreidimensionale Registerkarten, die schräg Seiten und abgerundete Ecken. Gibt es zeigt weitere Registerkarten als gleichzeitig angezeigt werden können, das Framework ein Dropdown Pfeil und ein Menü mit Registerkarten zu aktivieren.|  
|STYLE_3D_SCROLLED|Dreidimensionale, rechteckige Registerkarten angezeigt. Gibt es zeigt weitere Registerkarten als gleichzeitig angezeigt werden können, das Framework ein Dropdown Pfeil und ein Menü mit Registerkarten zu aktivieren.|  
|STYLE_3D_VS2005|Zeigt dreidimensionale, gerundet Registerkarten, die eine Schräge und einem vertikalen Seite verfügen.|  
|STYLE_FLAT|Zweidimensionale Registerkarten, die Links und rechts schräg haben angezeigt.|  
|STYLE_FLAT_SHARED_HORZ_SCROLL|Zweidimensionale Registerkarten angezeigt. Gibt es zeigt weitere Registerkarten als gleichzeitig angezeigt werden können, das Framework Bildlaufpfeile an den Enden des Registerkartenbereichs.|  
  
##  <a name="ondragenter"></a>CMFCTabCtrl::OnDragEnter  
 Wird vom Framework während eines Drag & Drop-Vorgangs aufgerufen, wenn der Cursor zuerst das Fenster des aktuellen Registerkarten-Steuerelements betritt.  
  
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
 Immer `DROPEFFECT_NONE`, was bedeutet, dass das Ablageziel die Daten akzeptieren kann.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einen Drag & Drop-Vorgang zu unterstützen. Überschreiben Sie diese Methode, um eigene benutzerdefinierte Verhalten zu implementieren.  
  
 Standardmäßig ruft diese Methode nur `CMFCTabCtrl::OnDragOver`, welche gibt immer `DROPEFFECT_NONE`.  
  
##  <a name="ondragover"></a>CMFCTabCtrl::OnDragOver  
 Wird vom Framework während eines Ziehvorgangs aufgerufen, wenn der Mauszeiger über das Zielfenster bewegt wird.  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDataObject`  
 Zeiger auf eine [COleDataObject](../../mfc/reference/coledataobject-class.md) -Objekt, das über das Ablageziel gezogen wird.  
  
 [in] `dwKeyState`  
 Der Status der Zusatztasten, die eine bitweise Kombination ist (oder) der `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, und `MK_RBUTTON`. Weitere Informationen finden Sie unter "Message-Parameter" in [zu Mauseingabe](http://msdn.microsoft.com/library/windows/desktop/ms645601).  
  
 [in] `point`  
 Die aktuelle Mausposition.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `DROPEFFECT_NONE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode durch eine benutzerdefinierte Implementierung. Weitere Informationen finden Sie unter der [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover) Methode.  
  
##  <a name="onshowtabdocumentsmenu"></a>CMFCTabCtrl::OnShowTabDocumentsMenu  
 Zeigt ein Popupmenü mit Fenstern im Registerformat, wartet, bis der Benutzer wählt eine Registerkarte aus, und die ausgewählten Registerkarte auf die aktive Registerkarte definiert an.  
  
```  
virtual void OnShowTabDocumentsMenu(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Die Koordinaten an, wo das Popup-Menü anzuzeigen.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveinmditabgroup"></a>CMFCTabCtrl::SetActiveInMDITabGroup  
 Die aktuelle Registerkarte ein Registerkarten-Steuerelement festgelegt als die aktive Registerkarte in einer mehrere Dokument Schnittstelle Registerkartengruppe.  
  
```  
void SetActiveInMDITabGroup(BOOL bActive);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActive`  
 `TRUE`Um der aktiven Registerkarte als aktuellen Registerkarte zu machen; `FALSE` auf die aktuelle Registerkarte als inaktiv zu markieren.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie mehrere Dokumentfenster in entweder vertikal oder horizontal Registerkartengruppen organisieren und problemlos Dokumente von einer Registerkartengruppe in eine andere mischen.  
  
##  <a name="setactivetab"></a>CMFCTabCtrl::SetActiveTab  
 Aktiviert eine Registerkarte.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTab`  
 Gibt den nullbasierten Index der Registerkarte zu aktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die angegebene Registerkarte aktiviert wurde; `FALSE` Wenn das angegebene `iTab` Parameterwert ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet keine der `AFX_WM_CHANGE_ACTIVE_TAB` Benachrichtigung an das übergeordnete Fenster des Registerkarten-Steuerelements.  
  
 Die `SetActiveTab` -Methode ruft automatisch die [CMFCTabCtrl::HideActiveWindowHorzScrollBar](#hideactivewindowhorzscrollbar) Methode, um zu verhindern, dass den Bildschirm blinkt.  
  
##  <a name="setactivetabboldfont"></a>CMFCTabCtrl::SetActiveTabBoldFont  
 Aktiviert oder deaktiviert die Verwendung der fett auf aktive Registerkarten.  
  
```  
void SetActiveTabBoldFont(BOOL bIsBold=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bIsBold`  
 `TRUE`Um fett nicht mit der Bezeichnung der aktiven Registerkarte angezeigt. `FALSE` mit der Standardschriftart die Bezeichnung angezeigt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdrawframe"></a>CMFCTabCtrl::SetDrawFrame  
 Gibt an, ob ein Rechteck des Rahmens um eine eingebettete Leiste gezeichnet wird.  
  
```  
void SetDrawFrame(BOOL bDraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDraw`  
 `TRUE`ein Frame Rechteck um eine eingebettete Leiste angezeigt; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setflatframe"></a>CMFCTabCtrl::SetFlatFrame  
 Gibt an, ob einem flachen oder einem 3D Rahmen um den Registerkartenbereich zu zeichnen.  
  
```  
void SetFlatFrame(
    BOOL bFlat=TRUE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 `TRUE`Um einen flachen (2D) Rahmen um den Registerkartenbereich zu zeichnen. `FALSE` einen dreidimensionalen (3D) Rahmen gezeichnet. Der Standardwert ist `TRUE`.  
  
 [in] `bRepaint`  
 `TRUE`Das Fenster sofort neu gezeichnet; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setimagelist"></a>CMFCTabCtrl::SetImageList  
 Gibt eine Liste der Images.  
  
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
 Die Breite der einzelnen Bilds in Pixel. Der Standardwert ist 15.  
  
 [in] `clrTransp`  
 Die Farbe, transparentes Bild. Die Teile des Bilds, die diese Farbe werden transparent sein. Der Standardwert ist das Farbe Magenta, RGB(255,0,255).  
  
 [in] `hImageList`  
 Ein Handle für einen vorab geladenen Bildliste.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist. `FALSE`Wenn das Registerkarten-Steuerelement mit flach erstellt wird oder wenn die erste methodenüberladung die Bitmap geladen werden kann, der durch angegeben ist die `uiID` Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um einer Bildliste des Registersteuerelements festzulegen. Die Bilder aus der Bildliste neben die Bezeichnung der Registerkarte angezeigt. Diese Methode berechnet die Höhe der Registerkarte so, dass die Registerkarte angepasst wird, um das Bild und Text enthalten.  
  
 Verwenden der [:: addTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) -Methode, die durch das Registerkarten-Steuerelement an den Index des anzuzeigenden Bildes geerbt wird.  
  
##  <a name="setresizemode"></a>CMFCTabCtrl::SetResizeMode  
 Gibt an, wie das aktuelle Registerkarten-Steuerelement geändert werden kann, und zeigt dann das Steuerelement erneut an.  
  
```  
void SetResizeMode(ResizeMode resizeMode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `resizeMode`  
 Eines der `CMFCTabCtrl::ResizeMode` -Enumerationswerte, der angibt, wie das Registerkarten-Steuerelement geändert werden kann. Eine Liste der möglichen Werte finden Sie unter der Tabelle unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die `resizeMode` Parameter kann eine der folgenden `ResizeMode` -Enumerationswerte.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|RESIZE_NO|Das Registerkarten-Steuerelement kann nicht geändert werden.|  
|RESIZE_VERT|Das Registerkarten-Steuerelement kann vertikal, aber nicht horizontal geändert werden.|  
|RESIZE_HORIZ|Das Registerkarten-Steuerelement kann horizontal, aber nicht vertikal geändert werden.|  
  
##  <a name="settabmaxwidth"></a>CMFCTabCtrl::SetTabMaxWidth  
 Gibt die maximale Tabulatorbreite in einem Fenster im Registerkartenformat.  
  
```  
void SetTabMaxWidth(int nTabMaxWidth);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTabMaxWidth`  
 Die maximale Registerkarte Breite in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Breite der einzelnen Registerkarten in einem Fenster im Registerkartenformat zu beschränken. Diese Methode ist nützlich, wenn Registerkarten sehr lange Bezeichnungen haben. Die [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) Klassenkonstruktor initialisiert die Registerkarte maximale Breite auf 0, was eigentlich bedeutet, dass die Breite nicht beschränkt ist.  
  
##  <a name="stopresize"></a>CMFCTabCtrl::StopResize  
 Beendet den aktuellen Vorgang auf die Registerkarte.  
  
```  
void StopResize(BOOL bCancel);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bCancel`  
 `TRUE`um den aktuellen Vorgang abzubrechen; `FALSE` zum Abschließen der aktuellen ändern. In beiden Fällen beendet das Framework das Resize-Rechteck gezeichnet.  
  
##  <a name="synchronizescrollbar"></a>CMFCTabCtrl::SynchronizeScrollBar  
 Zeichnet eine horizontale Bildlaufleiste ein Registerkarten-Steuerelement, das flache Registerkarten anzeigt.  
  
```  
BOOL SynchronizeScrollBar(SCROLLINFO* pScrollInfo = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `pScrollInfo`  
 Zeiger auf eine [SCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb787537) Struktur oder `NULL`. Diese Methode gibt, und wenn dieser Parameter ist nicht `NULL`, die Struktur enthält alle Parameter der Bildlaufleiste. Der Standardwert ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wirkt sich nur ein Registerkarten-Steuerelement, das flache Registerkarten anzeigt. Die Bildlaufleiste beeinflusst alle Registerkarten zur gleichen Zeit.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md)

