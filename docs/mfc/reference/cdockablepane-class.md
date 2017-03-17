---
title: CDockablePane-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDockablePane
- AFXDOCKABLEPANE/CDockablePane
- AFXDOCKABLEPANE/CDockablePane::CDockablePane
- AFXDOCKABLEPANE/CDockablePane::AttachToTabWnd
- AFXDOCKABLEPANE/CDockablePane::CalcFixedLayout
- AFXDOCKABLEPANE/CDockablePane::CanAcceptMiniFrame
- AFXDOCKABLEPANE/CDockablePane::CanAcceptPane
- AFXDOCKABLEPANE/CDockablePane::CanAutoHide
- AFXDOCKABLEPANE/CDockablePane::CanBeAttached
- AFXDOCKABLEPANE/CDockablePane::ConvertToTabbedDocument
- AFXDOCKABLEPANE/CDockablePane::CopyState
- AFXDOCKABLEPANE/CDockablePane::Create
- AFXDOCKABLEPANE/CDockablePane::CreateDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::CreateEx
- AFXDOCKABLEPANE/CDockablePane::CreateTabbedPane
- AFXDOCKABLEPANE/CDockablePane::DockPaneContainer
- AFXDOCKABLEPANE/CDockablePane::DockPaneStandard
- AFXDOCKABLEPANE/CDockablePane::DockToRecentPos
- AFXDOCKABLEPANE/CDockablePane::DockToWindow
- AFXDOCKABLEPANE/CDockablePane::EnableAutohideAll
- AFXDOCKABLEPANE/CDockablePane::EnableGripper
- AFXDOCKABLEPANE/CDockablePane::GetAHRestoredRect
- AFXDOCKABLEPANE/CDockablePane::GetAHSlideMode
- AFXDOCKABLEPANE/CDockablePane::GetCaptionHeight
- AFXDOCKABLEPANE/CDockablePane::GetDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::GetDockingStatus
- AFXDOCKABLEPANE/CDockablePane::GetDragSensitivity
- AFXDOCKABLEPANE/CDockablePane::GetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::GetTabArea
- AFXDOCKABLEPANE/CDockablePane::GetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::HasAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::HitTest
- AFXDOCKABLEPANE/CDockablePane::IsAutohideAllEnabled
- AFXDOCKABLEPANE/CDockablePane::IsAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsDocked
- AFXDOCKABLEPANE/CDockablePane::IsHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::IsInFloatingMultiPaneFrameWnd
- AFXDOCKABLEPANE/CDockablePane::IsResizable
- AFXDOCKABLEPANE/CDockablePane::IsTabLocationBottom
- AFXDOCKABLEPANE/CDockablePane::IsTracked
- AFXDOCKABLEPANE/CDockablePane::IsVisible
- AFXDOCKABLEPANE/CDockablePane::OnAfterChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnAfterDockFromMiniFrame
- AFXDOCKABLEPANE/CDockablePane::OnBeforeChangeParent
- AFXDOCKABLEPANE/CDockablePane::OnBeforeFloat
- AFXDOCKABLEPANE/CDockablePane::RemoveFromDefaultPaneDividier
- AFXDOCKABLEPANE/CDockablePane::ReplacePane
- AFXDOCKABLEPANE/CDockablePane::RestoreDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::SetAutoHideParents
- AFXDOCKABLEPANE/CDockablePane::SetLastPercentInPaneContainer
- AFXDOCKABLEPANE/CDockablePane::SetRestoredDefaultPaneDivider
- AFXDOCKABLEPANE/CDockablePane::SetTabbedPaneRTC
- AFXDOCKABLEPANE/CDockablePane::ShowPane
- AFXDOCKABLEPANE/CDockablePane::Slide
- AFXDOCKABLEPANE/CDockablePane::ToggleAutoHide
- AFXDOCKABLEPANE/CDockablePane::UndockPane
- AFXDOCKABLEPANE/CDockablePane::CheckAutoHideCondition
- AFXDOCKABLEPANE/CDockablePane::CheckStopSlideCondition
- AFXDOCKABLEPANE/CDockablePane::DrawCaption
- AFXDOCKABLEPANE/CDockablePane::OnPressButtons
- AFXDOCKABLEPANE/CDockablePane::OnSlide
- AFXDOCKABLEPANE/CDockablePane::m_bDisableAnimation
- AFXDOCKABLEPANE/CDockablePane::m_bHideInAutoHideMode
- AFXDOCKABLEPANE/CDockablePane::m_nSlideSteps
dev_langs:
- C++
helpviewer_keywords:
- CDockablePane class
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 34
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
ms.openlocfilehash: dea1f1ce66c0e9bedbe83109ab62055a4af2ebce
ms.lasthandoff: 02/24/2017

---
# <a name="cdockablepane-class"></a>CDockablePane Class
Implementiert einen Bereich, der entweder in eine Docksite angedockt oder in einer Seite im Registerformat enthalten sein kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|Erstellt und initialisiert ein `CDockablePane`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](#attachtotabwnd)|Fügt einen Bereich in einen anderen Bereich. Dadurch wird ein Fenster mit Registerkarten erstellt.|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|Gibt die Größe des Rechtecks Bereich zurück.|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|Bestimmt, ob die angegebenen Mini-Frames in den Bereich angedockt werden kann.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein weiterer Bereich, in den aktuellen Bereich angedockt werden kann.|  
|[CDockablePane::CanAutoHide](#canautohide)|Bestimmt, ob der Bereich automatisch ausgeblendet unterstützt. (Überschreibt [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|Bestimmt, ob der aktuelle Bereich in einen anderen Bereich angedockt werden kann.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert eine oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumente.|  
|[CDockablePane::CopyState](#copystate)|Kopiert den Zustand des einen andockbaren Bereich.|  
|[CDockablePane::Create](#create)|Das Windows-Steuerelement erstellt, und fügt es der `CDockablePane` Objekt.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|Einem Rahmenfenster angedockt wird, wird erstellt einen Standard-Unterteiler für den Bereich.|  
|[CDockablePane::CreateEx](#createex)|Das Windows-Steuerelement erstellt, und fügt es der `CDockablePane` Objekt.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|Erstellt ein Fenster mit Registerkarten aus dem aktuellen Bereich.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|Der Bereich ein Containers angedockt.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|Dockt einen Bereich mithilfe der Gliederung (standard) andocken.|  
|`CDockablePane::DockToFrameWindow`|Wird intern verwendet. Verwenden Sie einen Bereich für das Andocken, [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) oder [CDockablePane::DockToWindow](#docktowindow).|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|Die gespeicherte aktuelle andockbaren Position einen Bereich angedockt.|  
|[CDockablePane::DockToWindow](#docktowindow)|Ein weiterer andockbaren Bereich einen andockbaren Bereich angedockt.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|Aktiviert oder deaktiviert automatisch im Hintergrund-Modus für diesen Bereich zusammen mit anderen Bereichen im Container.|  
|[CDockablePane::EnableGripper](#enablegripper)|Anzeigen oder ausblenden die Beschriftung (Ziehpunkt).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|Gibt die Position im Bereich automatisch ausgeblendet angezeigt.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|Ruft das automatische Ausblenden Folienmodus für den Bereich ab.|  
|`CDockablePane::GetAutoHideButton`|Wird intern verwendet.|  
|`CDockablePane::GetAutoHideToolBar`|Wird intern verwendet.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe der aktuellen Beschriftung.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|Gibt die Standard-Trennlinie für den Bereich Container zurück.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|Bestimmt, ob die Möglichkeit eines Bereichs angedockt werden abhängig von der angegebenen Position.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|Gibt die Empfindlichkeit ziehen Sie von einem Andockbereich zurück.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|Ruft den Prozentsatz des Speicherplatzes, der belegt ein Bereich innerhalb des Containers ab.|  
|[CDockablePane::GetTabArea](#gettabarea)|Ruft den Registerkartenbereich für den Bereich.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|Die Common Language Runtime-Klasseninformationen über ein Fenster im Registerkartenformat, das erstellt wird, wenn Sie einen anderen Bereich in den aktuellen Bereich angedockt zurückgegeben.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|Gibt an, ob es sich bei einem Andockbereich automatisch im Hintergrund-Modus gewechselt werden kann.|  
|[CDockablePane::HitTest](#hittest)|Gibt die Position in einem Bereich, in dem der Benutzer die Maus klickt.|  
|`CDockablePane::IsAccessibilityCompatible`|Wird intern verwendet.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|Gibt an, ob die andockbaren und alle anderen Bereiche im Container automatisch ausgeblendet platziert werden können.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|Bestimmt, ob ein Fenster automatisch ausgeblendet wird.|  
|`CDockablePane::IsChangeState`|Wird intern verwendet.|  
|[CDockablePane::IsDocked](#isdocked)|Bestimmt, ob der aktuelle Bereich angedockt ist.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|Bestimmt das Verhalten eines Bereichs, die automatisch ausgeblendet wird, wenn sie (durch Aufrufen von ein- oder ausgeblendet ist) `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen.|  
|[CDockablePane::IsResizable](#isresizable)|Gibt an, ob der Bereich geändert werden.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|Gibt an, ob die Registerkarten oben oder unten im Bereich befinden.|  
|[CDockablePane::IsTracked](#istracked)|Gibt an, ob ein Bereich vom Benutzer gezogen wird.|  
|[CDockablePane::IsVisible](#isvisible)|Bestimmt, ob der aktuelle Bereich angezeigt wird.|  
|[CDockablePane:: LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|Wird intern verwendet.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|Wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert hat. (Überschreibt [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|Wird vom Framework aufgerufen, wenn eine Gleitkommazahl andockleiste an einem Rahmenfenster angedockt.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|Wird vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird. (Überschreibt [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Wird vom Framework aufgerufen, wenn ein Bereich in einen Gleitkommawert ist. (Überschreibt [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|Das Framework ruft diese Methode auf, wenn ein Bereich ist abgedockt wird.|  
|[CDockablePane::ReplacePane](#replacepane)|Ersetzt den Bereich mit einem angegebenen Bereich.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|Das Framework ruft diese Methode auf, wenn ein Bereich deserialisiert wird, um die Trennlinie Standard wiederherstellen.|  
|`CDockablePane::SaveState`|Wird intern verwendet.|  
|`CDockablePane::Serialize`|Serialisiert den Bereich. (Überschreibt `CBasePane::Serialize`.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|Schaltet die andockbaren zwischen angezeigt und automatisch ausgeblendet.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|Die Schaltfläche automatisch im Hintergrund und automatisch im Hintergrund-Symbolleiste für den Bereich festgelegt.|  
|`CDockablePane::SetDefaultPaneDivider`|Wird intern verwendet.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|Stellt den Prozentsatz des Speicherplatzes, der ein Bereich innerhalb des Containers belegt.|  
|`CDockablePane::SetResizeMode`|Wird intern verwendet.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|Wird der wiederhergestellten Trennlinie.|  
|[CDockablePane::SetTabbedPaneRTC](#settabbedpanertc)|Legt die Laufzeit-Klasseninformationen für ein Fenster im Registerkartenformat, das erstellt wird, wenn zwei Bereichen zusammen andocken.|  
|[CDockablePane::ShowPane](#showpane)|Anzeigen oder ausblenden ein Bereichs.|  
|[CDockablePane::Slide](#slide)|Anzeigen oder ausblenden ein Bereichs mit einem gleitenden Animation nur zeigt, wenn der Bereich automatisch ausgeblendet wird.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|Schaltet das automatische Ausblenden Modus. (Überschreibt [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|Wird einen Bereich im Hauptrahmenfenster oder Miniframe Fenster Container abgedockt.|  
|`CDockablePane::UnSetAutoHideMode`|Wird intern verwendet. Verwenden Sie zum Festlegen des Modus automatisch im Hintergrund [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|Bestimmt, ob die andockbaren (im Modus automatisch im Hintergrund) ausgeblendet ist.|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|Legt fest, wenn ein Automatisches Ausblenden andockbaren gleitende beendet werden soll.|  
|[CDockablePane::DrawCaption](#drawcaption)|Zeichnet die andockbaren Bereich Beschriftung (Ziehpunkt).|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|Wird aufgerufen, wenn der Benutzer eine Beschriftung als drückt die `AFX_HTCLOSE` und `AFX_HTMAXBUTTON` Schaltflächen.|  
|[CDockablePane::OnSlide](#onslide)|Vom Framework aufgerufen, der Abrolleffekt automatisch im Hintergrund gerendert werden soll, wenn der Bereich entweder ein- oder ausgeblendet wird.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|Gibt an, ob die Animation andockbaren Bereich automatisch im Hintergrund deaktiviert ist.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|Bestimmt das Verhalten des Bereichs an, wenn der Bereich automatisch ausgeblendet ist.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|Gibt die Geschwindigkeit der Animation des Bereichs an, wenn es gerade angezeigt oder ausgeblendet werden, im Modus "automatisch ausblenden".|  
  
## <a name="remarks"></a>Hinweise  
 `CDockablePane`implementiert die folgende Funktionen:  
  
-   Einen Bereich andocken ein Hauptrahmenfenster.  
  
-   Wechseln einen Bereich zu automatisch ausgeblendet.  
  
-   Ein Fenster im Registerkartenformat zuordnen einen Bereich.  
  
-   Gleitkomma-einen Bereich in einem Minirahmenfenster.  
  
-   Andocken eines Bereichs zu einem anderen Bereich, der in einem Minirahmenfenster verankert ist.  
  
-   Ändern der Größe eines Bereichs.  
  
-   Laden und Speichern des Zustands für einen andockbaren Bereich.  
  
    > [!NOTE]
    >  Die Zustandsinformationen wird in der Windows-Registrierung gespeichert.  
  
-   Erstellen einen Bereich, mit oder ohne Beschriftung. Die Beschriftung kann eine Beschriftung und es kann mit einem Farbverlauf gefüllt werden.  
  
-   Ziehen einen Bereich beim Anzeigen des Inhalts des Bereichs  
  
-   Ziehen beim Anzeigen eines Rechtecks ziehen Sie einen Bereich.  
  
 Um einen andockbaren Bereich in der Anwendung zu verwenden, leiten Sie eine Klasse im Bereich von der `CDockablePane` Klasse. Betten Sie das abgeleitete Objekt in das Hauptrahmenfenster-Objekt oder ein Window-Objekt, das die Instanz im Fenster steuert. Rufen Sie dann die [CDockablePane::Create](#create) -Methode oder die [CDockablePane::CreateEx](#createex) Methode beim Verarbeiten der `WM_CREATE` Nachricht im Hauptrahmenfenster. Legen Sie schließlich das Objekt im Bereich durch Aufrufen von [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane), oder [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgenden Tipps gelten für `CDockablePane` Objekte:  
  
-   Wenn Sie aufrufen [CDockablePane::AttachToTabWnd](#attachtotabwnd) für zwei nicht im Registerkartenformat, andockbare Bereiche ein Zeiger auf ein Fenster im Registerkartenformat zurückgegeben werden die `ppTabbedControlBar` Parameter. Sie können weiterhin dem Fenster im Registerkartenformat mit diesem Parameter Registerkarten hinzufügen.  
  
-   Die Art der im Registerformat durch die erstellte [CDockablePane::AttachToTabWnd](#attachtotabwnd) richtet sich nach der `CDockablePane` -Objekt in die `pTabControlBarAttachTo` Parameter. Rufen Sie [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) zum Festlegen der Art der Registerkarten, die die `CDockablePane` erstellt. Der Standardtyp richtet sich nach der `dwTabbedStyle` von [CDockablePane::Create](#create) beim Erstellen der `CDockablePane`. Wenn `dwTabbedStyle` ist der Standardtyp ist AFX_CBRS_OUTLOOK_TABS [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md); Wenn `dwTabbedStyle` ist der Standardtyp ist AFX_CBRS_REGULAR_TABS [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md).  
  
-   Wenn Sie einen andockbaren Bereich in einen anderen andocken möchten, rufen Sie die [CDockablePane::DockToWindow](#docktowindow) Methode. Der ursprüngliche Bereich muss an einer Stelle angedockt werden, bevor Sie diese Methode aufrufen.  
  
-   Membervariable [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) Verhalten von andockbare Bereiche in automatisch ausblenden von Steuerelementen Modus beim Aufruf von [CDockablePane::ShowPane](#showpane). Wenn diese Membervariable, um festgelegt ist `TRUE`, andockbare Bereiche sowie die automatische Ausblenden-Schaltflächen ausgeblendet werden. Andernfalls werden sie ein-und schieben.  
  
-   Sie können Animation Automatisches Ausblenden deaktivieren, indem die [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) Membervariable `TRUE`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine `CDockablePane` Objekt mit verschiedenen Methoden in der `CDockablePane` Klasse. Das Beispiel veranschaulicht, wie automatisch ausblenden aller-Funktion für die andockbaren Bereich aktivieren, aktivieren die Beschriftung oder die Ziehpunkte, aktivieren Sie den Modus automatisch ausblenden, Einblenden des Fensterbereichs und Animieren eines Bereichs, das automatisch ausgeblendet wird. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#27;](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo&#28;](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>CDockablePane::AttachToTabWnd  
 Fügt den aktuellen Bereich zu einem Zielbereich, und erstellen ein Fenster mit Registerkarten.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pTabControlBarAttachTo`  
 Gibt die Zielbereich, dem im aktuelle Bereich zugeordnet wird. Der Zielbereich muss einen andockbaren Bereich sein.  
  
 [in] `dockMethod`  
 Gibt die Methode andocken.  
  
 [in] `bSetActive`  
 `TRUE`um die Seite im Registerformat nach dem Anfügevorgang zu aktivieren; andernfalls `FALSE`.  
  
 [out] `ppTabbedControlBar`  
 Enthält die Seite im Registerformat, die durch den Anfügevorgang entsteht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Bereich, wenn es sich nicht um ein Fenster mit Registerkarten ist; andernfalls ein Zeiger auf die Seite im Registerformat, die durch den Anfügevorgang entsteht. Der Rückgabewert ist `NULL` , wenn der aktuelle Bereich kann nicht angefügt werden, oder wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein weiterer Bereich, der mit dieser Methode einen andockbaren Bereich zugeordnet wird, geschieht Folgendes:  
  
1.  Das Framework überprüft, ob Zielbereich `pTabControlBarAttachTo` ist eine reguläre andocken, Bereich oder wenn es abgeleitet wird [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md).  
  
2.  Wenn der Zielbereich ein Fenster mit Registerkarten ist hinzugefügt das Framework im aktuellen Bereich als Registerkarte.  
  
3.  Wenn Zielbereich einen regulären andockbaren Bereich ist, erstellt das Framework ein Fenster mit Registerkarten.  
  
    -   Das Framework ruft `pTabControlBarAttachTo->CreateTabbedPane`. Das Format des der neuen Seite im Registerformat hängt die `m_pTabbedControlBarRTC` Member. Standardmäßig ist dieser Member auf die Common Language Runtime-Klasse der festgelegt [CTabbedPane](../../mfc/reference/ctabbedpane-class.md). Übergeben der `AFX_CBRS_OUTLOOK_TABS` als Formatieren der `dwTabbedStyle` Parameter, um die [CDockablePane::Create](#create) -Methode, die Common Language Runtime-Klassenobjekt wird festgelegt, auf die Common Language Runtime-Klasse der [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md). Sie können dieses Elements zu einem beliebigen Zeitpunkt so ändern Sie das Format des neuen Bereichs ändern.  
  
    -   Wenn diese Methode ein Fenster mit Registerkarten erstellt, ersetzt das Framework den Zeiger auf `pTabControlBarAttachTo` (wenn der Bereich gedockt oder nicht in einen Multi-Minirahmenfenster ist) mit einem Zeiger auf die neue Seite im Registerformat.  
  
    -   Das Framework fügt der `pTabControlBarAttachTo` Bereich, um die Seite im Registerformat als erste Registerkarte. Das Framework fügt dann den aktuellen Bereich als zweiten Registerkarte.  
  
4.  Wenn der aktuelle Bereich von abgeleitet ist `CBaseTabbedPane`, werden alle Registerkarten verschoben, um `pTabControlBarAttachTo` und der aktuelle Bereich ist beschädigt. Daher vorsichtig, wenn Sie diese Methode aufrufen, da ein Zeiger auf den aktuellen Bereich möglicherweise ungültig, wenn die Methode zurückkehrt.  
  
 Wenn Sie einen Bereich in einen anderen anfügen, beim Erstellen einer andocklayout, `dockMethod` auf `DM_SHOW`.  
  
 Sie sollte den ersten Bereich andocken, bevor Sie einen anderen Bereich anfügen.  
  
##  <a name="calcfixedlayout"></a>CDockablePane::CalcFixedLayout  
 Gibt die Größe des Rechtecks Bereich zurück.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStretch`  
 Nicht verwendet.  
  
 [in] `bHorz`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CSize` -Objekt, das die Größe des Rechtecks Bereich enthält.  
  
##  <a name="canacceptminiframe"></a>CDockablePane::CanAcceptMiniFrame  
 Bestimmt, ob die angegebenen Minirahmenfensters in den Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMiniFrame`  
 Zeiger auf ein `CPaneFrameWnd` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `pMiniFrame` können in den Bereich angedockt ist, andernfalls werden `FALSE`.  
  
##  <a name="canacceptpane"></a>CDockablePane::CanAcceptPane  
 Bestimmt, ob ein weiterer Bereich, in den aktuellen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Gibt den Bereich der aktuelle Bereich angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der angegebene Bereich kann, in diesen Bereich angedockt werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor Sie ein Bereich in den aktuellen Bereich angedockt ist.  
  
 Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren die Zuordnung zu einem bestimmten Bereich.  
  
 Standardmäßig gibt diese Methode `TRUE` Wenn `pBar` oder das übergeordnete Element ist vom Typ `CDockablePane`.  
  
##  <a name="canautohide"></a>CDockablePane::CanAutoHide  
 Bestimmt, ob der Bereich automatisch ausblenden kann.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich automatisch im Hintergrund kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 `CDockablePane::CanAutoHide`Gibt `FALSE` in den folgenden Situationen:  
  
-   Der Bereich ist kein übergeordnetes Element.  
  
-   Der Andocken Manager lässt sich nicht auf Bereiche automatisch im Hintergrund aus.  
  
-   Der Bereich wird nicht angedockt.  
  
##  <a name="canbeattached"></a>CDockablePane::CanBeAttached  
 Bestimmt, ob der aktuelle Bereich in einen anderen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die andockbare Bereich in einen anderen Bereich oder an das Hauptrahmenfenster; angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `TRUE`. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren, ohne Aufruf Andocken [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="cdockablepane"></a>CDockablePane::CDockablePane  
 Erstellt und initialisiert ein [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>Hinweise  
 Nachdem Sie einen andockbaren Bereich-Objekt zu erstellen, rufen Sie [CDockablePane::Create](#create) oder [CDockablePane::CreateEx](#createex) zu erstellen.  
  
##  <a name="converttotabbeddocument"></a>CDockablePane::ConvertToTabbedDocument  
 Konvertiert eine oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumente.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActiveTabOnly`  
 Beim Konvertieren einer `CTabbedPane`, geben Sie `TRUE` nur die aktive Registerkarte zu konvertieren. Geben Sie `FALSE` alle Registerkarten im Bereich zu konvertieren.  
  
##  <a name="checkautohidecondition"></a>CDockablePane::CheckAutoHideCondition  
 Bestimmt, ob die andockbare Bereich ausgeblendet ist (auch als automatisches Ausblendmodus bezeichnet).  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die ausblenden-Bedingung erfüllt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet einen Zeitgeber, um in regelmäßigen Abständen zu prüfen, ob einen Automatisches Ausblenden andockbaren Bereich ausgeblendet. Gibt die Methode `TRUE` beim Bereich nicht aktiv ist, der Bereich nicht geändert wird und der Mauszeiger befindet sich nicht über den Bereich.  
  
 Wenn alle vorherigen Bedingungen erfüllt sind, ruft das Framework [CDockablePane::Slide](#slide) zum Ausblenden des Fensters.  
  
##  <a name="checkstopslidecondition"></a>CDockablePane::CheckStopSlideCondition  
 Legt fest, wenn ein Automatisches Ausblenden andockbaren gleitende beendet werden soll.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDirection`  
 `TRUE`Wenn das Fenster sichtbar ist; `FALSE` , wenn der Bereich ausgeblendet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die beenden-Bedingung erfüllt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein andockbares Fenster automatisch im Hintergrund-Modus festgelegt ist, verwendet das Framework gleitende Effekte ein-oder Ausblenden des Bereichs. Das Framework ruft diese Funktion auf, wenn im Bereich verschieben, ist. `CheckStopSlideCondition`Gibt `TRUE` Wenn Bereich vollständig sichtbar ist, oder wenn es vollständig ausgeblendet ist.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten AutoAusblenden Effekte.  
  
##  <a name="copystate"></a>CDockablePane::CopyState  
 Kopiert den Zustand des einen andockbaren Bereich.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOrgBar`  
 Ein Zeiger auf einen andockbaren Bereich.  
  
### <a name="remarks"></a>Hinweise  
 `CDockablePane::CopyState`kopiert den Zustand des `pOrgBar` in den aktuellen Bereich durch Aufrufen der folgenden Methoden:  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>CDockablePane::Create  
 Das Windows-Steuerelement erstellt, und fügt es der [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);

 
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    CSize sizeDefault,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle = WS_CHILD|WS_VISIBLE|CBRS_TOP|CBRS_HIDE_INPLACE,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszCaption`  
 Gibt den Fensternamen.  
  
 [in] [out]`pParentWnd`  
 Gibt das übergeordnete Fenster.  
  
 [in] `rect`  
 Gibt die Größe und Position des Fensters, in Clientkoordinaten des `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE`So erstellen Sie den Bereich mit einer Beschriftung; andernfalls `FALSE`.  
  
 [in] `nID`  
 Gibt die ID des untergeordneten Fensters. Dieser Wert muss eindeutig sein, wenn Sie Andockstatus für diese andockbaren speichern möchten.  
  
 [in] `dwStyle`  
 Gibt die Stilattribute Fenster an.  
  
 [in] `dwTabbedStyle`  
 Gibt das Format im Registerkartenformat von einem Fenster im Registerkartenformat, das erstellt wird, wenn der Benutzer einen Bereich in der Titelleiste des in diesem Bereich zieht.  
  
 [in] `dwControlBarStyle`  
 Gibt zusätzliche Formatattribute.  
  
 [in] [out]`pContext`  
 Gibt den Kontext Erstellen des Fensters.  
  
 [in] `lpszWindowName`  
 Gibt den Fensternamen.  
  
 [in] `sizeDefault`  
 Gibt die Größe des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn andockbare Bereich erfolgreich erstellt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Windows-Bereich und fügt es der `CDockablePane` Objekt.  
  
 Wenn die `dwStyle` Fensterstil hat das `CBRS_FLOAT_MULTI` -Flag, das Minirahmenfenster kann mit anderen Bereichen in der Minirahmenfenster float. Standardmäßig kann andockbare Bereiche nur einzeln verschoben.  
  
 Wenn die `dwTabbedStyle` Parameter hat die `AFX_CBRS_OUTLOOK_TABS` -Flag angegeben, die im Bereich erstellt im Outlook-Stil im Registerkartenformat Bereiche aus, wenn auf diesen Bereich mit einem anderen Bereich zugeordnet ist die [CDockablePane::AttachToTabWnd](#attachtotabwnd) Methode. Standardmäßig erstellen andockbare Bereiche im Registerkartenformat mit Typ regulären [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createdefaultpanedivider"></a>CDockablePane::CreateDefaultPaneDivider  
 Einem Rahmenfenster angedockt wird, wird erstellt einen Standard-Unterteiler für den Bereich.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Gibt die Seite für den Hauptframe an den Bereich angedockt wird, ist. Wenn `dwAlignment` enthält die `CBRS_ALIGN_LEFT` oder `CBRS_ALIGN_RIGHT` -Flag erstellt diese Methode eine vertikale ( `CPaneDivider::SS_VERT`) Unterteiler; andernfalls wird diese Methode erstellt eine horizontale ( `CPaneDivider::SS_HORZ`) Unterteiler.  
  
 [in] `pParent`  
 Ein Zeiger auf den übergeordneten Frame.  
  
 [in] `pSliderRTC`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt einen Zeiger auf den Unterteiler neu erstellt oder `NULL` Wenn Unterteiler Erstellung fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 `dwAlignment`die folgenden Werte sind möglich:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Der Bereich ist am Anfang der Clientbereich eines Rahmenfensters angedockt wird.|  
|`CBRS_ALIGN_BOTTOM`|Der Bereich wird am unteren Rand der Clientbereich eines Rahmenfensters angedockt wird.|  
|`CBRS_ALIGN_LEFT`|Der Bereich wird auf der linken Seite des Clientbereichs eines Rahmenfensters angedockt wird.|  
|`CBRS_ALIGN_RIGHT`|Der Bereich wird auf der rechten Seite des Clientbereichs eines Rahmenfensters angedockt wird.|  
  
##  <a name="createex"></a>CDockablePane::CreateEx  
 Das Windows-Steuerelement erstellt, und fügt es der [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszCaption,  
    CWnd* pParentWnd,  
    const RECT& rect,  
    BOOL bHasGripper,  
    UINT nID,  
    DWORD dwStyle,  
    DWORD dwTabbedStyle = AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle = AFX_DEFAULT_DOCKING_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyleEx`  
 Gibt die erweiterten Stilattribute für das neue Fenster.  
  
 [in] `lpszCaption`  
 Gibt den Fensternamen.  
  
 [in] [out]`pParentWnd`  
 Gibt das übergeordnete Fenster.  
  
 [in] `rect`  
 Gibt die Größe und Position des Fensters, in Clientkoordinaten des `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE`So erstellen Sie den Bereich mit einer Beschriftung; andernfalls `FALSE`.  
  
 [in] `nID`  
 Gibt die ID des untergeordneten Fensters. Dieser Wert muss eindeutig sein, wenn der Andockstatus für diese andockbaren gespeichert werden soll.  
  
 [in] `dwStyle`  
 Gibt die Stilattribute Fenster an.  
  
 [in] `dwTabbedStyle`  
 Gibt das Format im Registerkartenformat von einem Fenster im Registerkartenformat, das erstellt wird, wenn der Benutzer einen Bereich in der Titelleiste des in diesem Bereich zieht.  
  
 [in] `dwControlBarStyle`  
 Gibt die zusätzliche Stilattribute.  
  
 [in] [out]`pContext`  
 Gibt den Kontext Erstellen des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn andockbare Bereich erfolgreich erstellt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Windows-Bereich und fügt es der `CDockablePane` Objekt.  
  
 Wenn die `dwStyle` Fensterstil hat das `CBRS_FLOAT_MULTI` -Flag, das Minirahmenfenster kann mit anderen Bereichen in der Minirahmenfenster float. Standardmäßig kann andockbare Bereiche nur einzeln verschoben.  
  
 Wenn die `dwTabbedStyle` Parameter hat die `AFX_CBRS_OUTLOOK_TABS` -Flag angegeben, die im Bereich erstellt im Outlook-Stil im Registerkartenformat Bereiche aus, wenn auf diesen Bereich mit einem anderen Bereich zugeordnet ist die [CDockablePane::AttachToTabWnd](#attachtotabwnd) Methode. Standardmäßig erstellen andockbare Bereiche im Registerkartenformat mit Typ regulären [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createtabbedpane"></a>CDockablePane::CreateTabbedPane  
 Erstellt ein Fenster mit Registerkarten aus dem aktuellen Bereich.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue Seite im Registerformat, oder `NULL` bei einem fehlgeschlagenen Erstellungsvorgang.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es sich um ein Fenster mit Registerkarten in diesem Bereich ersetzen erstellt. Weitere Informationen finden Sie unter [CDockablePane::AttachToTabWnd](#attachtotabwnd).  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen, wie Seiten im Registerformat erstellt und initialisiert werden.  
  
 Die Seite im Registerformat wird gemäß der Laufzeit-Klasseninformationen in gespeicherten erstellt die `m_pTabbedControlBarRTC` Member, der durch initialisiert wird die [CDockablePane::CreateEx](#createex) Methode.  
  
##  <a name="dockpanecontainer"></a>CDockablePane::DockPaneContainer  
 Der Bereich ein Containers angedockt.  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `barContainerManager`  
 Ein Verweis auf den Container, der angedockt wird, wird der Container-Manager.  
  
 [in] `dwAlignment`  
 `DWORD`die gibt den Rand des Bereichs ist, an dem der Container angedockt wird.  
  
 [in] `dockMethod`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Container wurde erfolgreich in den Bereich; angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 `dwAlignment`die folgenden Werte sind möglich:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Der Container wird an den oberen Rand des Bereichs angedockt wird.|  
|`CBRS_ALIGN_BOTTOM`|Der Container wird an den unteren Rand des Bereichs angedockt wird.|  
|`CBRS_ALIGN_LEFT`|Der Container wird links neben dem Bereich angedockt wird.|  
|`CBRS_ALIGN_RIGHT`|Der Container wird rechts neben dem Bereich angedockt wird.|  
  
##  <a name="dockpanestandard"></a>CDockablePane::DockPaneStandard  
 Dockt einen Bereich mithilfe der Gliederung (standard) andocken.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bWasDocked`  
 Wenn die Methode zurückkehrt, enthält dieser Wert `TRUE` , wenn der Bereich erfolgreich angedockten; andernfalls wurde, enthält es `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn ein Fenster im Registerkartenformat Bereich angedockt ist, oder wenn ein Fenster im Registerkartenformat durch Andocken erstellt wurde, gibt diese Methode einen Zeiger auf das Fenster im Registerkartenformat. Wenn der Bereich andernfalls erfolgreich angedockt wurde, gibt diese Methode die `this` Zeiger. Wenn das Andocken fehlgeschlagen ist, gibt diese Methode `NULL`.  
  
##  <a name="docktorecentpos"></a>CDockablePane::DockToRecentPos  
 Die gespeicherte andockbaren Position einen Bereich angedockt.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Andockbare Bereiche speichern aktuelle docking Informationen in einem [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) Objekt.  
  
##  <a name="docktowindow"></a>CDockablePane::DockToWindow  
 Ein weiterer andockbaren Bereich einen andockbaren Bereich angedockt.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pTargetWindow`  
 Gibt die andockbaren Bereich um diesem Bereich anzudocken.  
  
 [in] `dwAlignment`  
 Gibt die Dockingstation Ausrichtung für den Bereich. Dabei kann es sich um eine CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM oder CBRS_ALIGN_ANY sein. (Definiert in afxres.h).  
  
 [in] `lpRect`  
 Gibt das Andocken Rechteck für den Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich in einen anderen Bereich mit der angegebenen Ausrichtung Andocken `dwAlignment`.  
  
##  <a name="drawcaption"></a>CDockablePane::DrawCaption  
 Zeichnet die Beschriftung (auch als die Ziehpunkte) einen andockbaren Bereich.  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Stellt den Gerätekontext zum Zeichnen verwendeten dar.  
  
 [in] `rectCaption`  
 Gibt das umschließende Rechteck der Beschriftung des Bereichs an.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um die Beschriftung des einen andockbaren Bereich zu zeichnen.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Beschriftung.  
  
##  <a name="enableautohideall"></a>CDockablePane::EnableAutohideAll  
 Aktiviert oder deaktiviert automatisch im Hintergrund-Modus für diesen Bereich und für andere Bereiche im Container.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die automatisch im Hintergrund alle Feature für den andockbaren Bereich; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer hält die `Ctrl` Schlüssel und klickt auf die Pin-Schaltfläche, um einen Bereich alle anderen Bereiche im selben Container automatisch Ausblendmodus wechselt, werden auch in den Ausblendmodus zum automatischen umgeschaltet.  
  
 Beim Aufrufen dieser Methode `bEnable` festgelegt `FALSE` Sie dieses Feature für einen bestimmten Bereich deaktivieren.  
  
##  <a name="enablegripper"></a>CDockablePane::EnableGripper  
 Anzeigen oder ausblenden die Beschriftung (auch als ziehelements bezeichnet).  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um die Beschriftung zu aktivieren. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Framework andockbare Bereiche erstellt, sie verfügen nicht über die **WS_STYLE** Fensterstil, selbst wenn angegeben. Dies bedeutet, dass im Bereich Beschriftung ist ein nicht-Clientbereich, der vom Framework gesteuert wird, aber in diesem Bereich unterscheidet sich von der standardmäßigen Beschriftung.  
  
 Sie können ein- oder ausblenden die Beschriftung zu einem beliebigen Zeitpunkt. Das Framework Blendet die Beschriftung, wenn ein Bereich als Registerkarte hinzugefügt wird, um ein Fenster im Registerkartenformat oder ein Bereich in einem Minirahmenfenster abgedockt ist.  
  
##  <a name="getahrestoredrect"></a>CDockablePane::GetAHRestoredRect  
 Gibt die Position des Bereichs im Modus "automatisch ausblenden".  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das die Position des Bereichs enthält, wenn diese automatisch ausgeblendet wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getahslidemode"></a>CDockablePane::GetAHSlideMode  
 Ruft den Modus für den Bereich automatisch im Hintergrund ab.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `UINT` , die automatisch im Hintergrund Folienmodus für den Bereich angibt. Der Rückgabewert kann entweder `AFX_AHSM_MOVE` oder `AFX_AHSM_STRETCH`, aber die Implementierung nur `AFX_AHSM_MOVE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcaptionheight"></a>CDockablePane::GetCaptionHeight  
 Gibt die Höhe des die aktuelle Beschriftung in Pixel zurück.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der Beschriftung in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die Überschriftenhöhe ist 0, wenn die Beschriftung von ausgeblendet war die [CDockablePane::EnableGripper](#enablegripper) -Methode, oder wenn der Bereich keine Beschriftung.  
  
##  <a name="getdefaultpanedivider"></a>CDockablePane::GetDefaultPaneDivider  
 Gibt die Standard-Trennlinie für den Bereich Container zurück.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger [CPaneDivider](../../mfc/reference/cpanedivider-class.md) -Objekt, wenn das Hauptrahmenfenster andockbare Bereich angedockt ist oder `NULL` Wenn andockbare Bereich nicht angedockt ist oder wenn es verankert ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu bereichsteiler, finden Sie unter [CPaneDivider Klasse](../../mfc/reference/cpanedivider-class.md).  
  
##  <a name="getdockingstatus"></a>CDockablePane::GetDockingStatus  
 Bestimmt, ob die Möglichkeit eines Bereichs angedockt werden abhängig von der angegebenen Position.  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Die Position des Mauszeigers in Bildschirmkoordinaten.  
  
 [in] `nSensitivity`  
 Den Abstand in Pixel von der Kante eines Rechtecks muss der Zeiger so aktivieren Sie das Andocken.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Statuswerte:  
  
|`AFX_CS_STATUS`-Wert|Bedeutung|  
|---------------------------|-------------|  
|`CS_NOTHING`|Der Zeiger ist nicht über eine docksite. Das Framework ist nicht im Bereich andocken.|  
|`CS_DOCK_IMMEDIATELY`|Der Zeiger befindet sich über die Dock-Website in den Befehlsmodus (im Bereich wird die `DT_IMMEDIATE` Andockmodus). Das Framework Dockt den Bereich sofort an.|  
|`CS_DELAY_DOCK`|Der Zeiger wird über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe. Das Framework Dockt den Bereich nach einer Verzögerung an. Finden Sie im Abschnitt "Hinweise" für Weitere Informationen zu dieser Verzögerung.|  
|`CS_DELAY_DOCK_TO_TAB`|Der Zeiger befindet sich über eine docksite, bei dem der Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Mauszeiger über die Beschriftung des anderen andockbaren Bereich oder über den Registerkartenbereich des ein Fenster mit Registerkarten befindet.|  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode zum Behandeln von einem nicht verankerten Fenster andocken.  
  
 Unverankerte Symbolleisten oder andockbare Bereiche, mit denen die `DT_IMMEDIATE` Andocken Modus verzögert das Framework die Dock-Befehl aus, um dem Benutzer ermöglichen, den Clientbereich des übergeordneten Rahmens vor andockbare Fenster verschieben. Die Länge der Verzögerung wird in Millisekunden gemessen und wird gesteuert, indem die [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) -Datenmember... Der Standardwert von [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) ist 200. Dieses Verhalten emuliert das Andockverhalten des [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007.  
  
 Verzögert Andocken Zustände ( `CS_DELAY_DOCK` und `CS_DELAY_DOCK_TO_TAB`), das Framework führt keine andocken, bis der Benutzer die Maustaste loslässt. Wenn ein Bereich wird die `DT_STANDARD` Andocken Modus zeigt das Framework ein Rechteck am der voraussichtlichen Andockposition an. Wenn ein Bereich wird die `DT_SMART` Andocken Modus das Framework zeigt intelligenten andockmarkern und halb transparenten Rechtecke an die voraussichtliche Andockposition. Rufen Sie zum Angeben des Andockmodus für die im Bereich der [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) Methode. Weitere Informationen zu intelligentes Andocken, finden Sie unter [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams).  
  
##  <a name="getdragsensitivity"></a>CDockablePane::GetDragSensitivity  
 Gibt die Empfindlichkeit ziehen Sie von einem Andockbereich zurück.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) -Objekt, das die Breite und Höhe in Pixel eines Rechtecks, dessen Mitte sich an einem Ziehpunkt befindet, enthält. Der Ziehvorgang beginnt nicht bis außerhalb dieses Rechteck der Mauszeiger bewegt wird.  
  
##  <a name="getlastpercentinpanecontainer"></a>CDockablePane::GetLastPercentInPaneContainer  
 Ruft den Prozentsatz des Speicherplatzes, der ein Bereich in einem Container einnimmt ( [CPaneContainer Klasse](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `int` , die den Prozentsatz des Speicherplatzes, der der Bereich in einem Container befindet sich angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird verwendet, wenn der Container das Layout angepasst.  
  
##  <a name="gettabarea"></a>CDockablePane::GetTabArea  
 Ruft den Registerkartenbereich für den Bereich.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectTabAreaTop`  
 `GetTabArea`wird diese Variable den Registerkartenbereich Wenn Registerkarten am oberen Rand des Bereichs befinden. Wenn Registerkarten am unteren Rand des Bereichs befinden, wird diese Variable mit einem leeren Rechteck ausgefüllt.  
  
 [in] `rectTabAreaBottom`  
 `GetTabArea`wird diese Variable den Registerkartenbereich Wenn Registerkarten am unteren Rand des Bereichs befinden. Wenn Registerkarten am oberen Rand des Bereichs befinden, wird diese Variable mit einem leeren Rechteck ausgefüllt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird nur in von abgeleiteten Klassen verwendet `CDockablePane` und Registerkarten. Weitere Informationen finden Sie unter [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) und [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea).  
  
##  <a name="gettabbedpanertc"></a>CDockablePane::GetTabbedPaneRTC  
 Die Common Language Runtime-Klasseninformationen über ein Fenster im Registerkartenformat, das erstellt wird, wenn Sie einen anderen Bereich in den aktuellen Bereich angedockt zurückgegeben.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Laufzeit-Klasseninformationen für andockbaren Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Laufzeit-Klasseninformationen für Seiten im Registerformat abzurufen, die dynamisch erstellt werden. Dies kann auftreten, wenn ein Benutzer einen Bereich, der die Beschriftung von einem anderen Bereich zieht, oder rufen Sie die [CDockablePane::AttachToTabWnd](#attachtotabwnd) Methode, um ein Fenster mit Registerkarten aus zwei andockbare Bereiche programmgesteuert zu erstellen.  
  
 Sie können die Laufzeit-Klasseninformationen festlegen, durch Aufrufen der [CDockablePane::SetTabbedPaneRTC](#settabbedpanertc) Methode.  
  
##  <a name="hasautohidemode"></a>CDockablePane::HasAutoHideMode  
 Gibt an, ob es sich bei einem Andockbereich AutoAusblenden-Modus gewechselt werden kann.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn in den Ausblendmodus zum automatischen der andockbare Bereich gewechselt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse automatisch im Hintergrund-Modus für ein bestimmtes andockbare Fenster zu deaktivieren.  
  
##  <a name="hittest"></a>CDockablePane::HitTest  
 Gibt den Speicherort in einem Bereich, in dem der Benutzer die Maus klickt.  
  
```  
virtual int HitTest(
    CPoint point,  
    BOOL bDetectCaption = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt an, um zu testen.  
  
 [in] `bDetectCaption`  
 `TRUE`Wenn `HTCAPTION` zurückgegeben werden soll, wenn der wird auf den Bereich; anderenfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- `HTNOWHERE`Wenn `point` nicht im Bereich angedockt ist.  
  
- `HTCLIENT`Wenn `point` im Clientbereich des Bereichs angedockt ist.  
  
- `HTCAPTION`Wenn `point` im Headerbereich des Bereichs angedockt ist.  
  
- `AFX_HTCLOSE`Wenn `point` auf die Schaltfläche "Schließen" ist.  
  
- `HTMAXBUTTON`Wenn `point` auf die Schaltfläche "Pin" ist.  
  
##  <a name="isautohideallenabled"></a>CDockablePane::IsAutohideAllEnabled  
 Gibt an, ob die andockbaren Bereich und alle anderen Bereiche im Container automatisch im Hintergrund-Modus gewechselt werden können.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die andockbaren Bereich, und alle anderen Bereiche im Container automatisch im Hintergrund-Modus gewechselt werden können; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Benutzer kann automatisch im Hintergrund-Modus mit der Schaltfläche andockbaren Pin halten die **STRG** Schlüssel  
  
 Rufen Sie zum Aktivieren oder Deaktivieren dieses Verhalten, die [CDockablePane::EnableAutohideAll](#enableautohideall) Methode.  
  
##  <a name="isautohidemode"></a>CDockablePane::IsAutoHideMode  
 Bestimmt, ob ein Bereich im automatisch im Hintergrund ausgeführt wird.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der andockbare Bereich im Ausblendmodus zum automatischen wird; andernfalls `FALSE`.  
  
##  <a name="isdocked"></a>CDockablePane::IsDocked  
 Bestimmt, ob der aktuelle Bereich angedockt ist.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der andockbare Bereich nicht zu einem Minirahmenfenster gehört oder ein Minirahmenfenster mit einem anderen Bereich schwimmen. `FALSE`Wenn der Bereich ein untergeordnetes Element des ein Minirahmenfenster ist, und es keine anderen Bereiche gibt, die das Minirahmenfenster angehören.  
  
### <a name="remarks"></a>Hinweise  
 Bestimmt, ob das Hauptrahmenfenster Bereich angedockt ist, rufen Sie [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider). Wenn die Methode einen nicht-NULL-Zeiger zurückgegeben wird, ist das Hauptrahmenfenster Bereich angedockt.  
  
##  <a name="ishideinautohidemode"></a>CDockablePane::IsHideInAutoHideMode  
 Bestimmt das Verhalten eines Bereichs, die automatisch im Hintergrund-Modus ist, wenn sie (durch Aufrufen von ein- oder ausgeblendet ist) [CDockablePane::ShowPane](#showpane).  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn im Ausblendmodus zum automatischen der andockbare Bereich ausgeblendet werden soll andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wird ein andockbares Fenster im Ausblendmodus zum automatischen, es verhält sich anders beim Aufruf `ShowPane` ausblenden oder Einblenden des Fensterbereichs. Dieses Verhalten wird gesteuert, von den statischen Member [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode). Wenn dieser Member ist `TRUE`, andockbaren Bereich sowie verwandte zum automatischen ausblenden Symbolleiste oder AutoAusblenden-Schaltfläche ausgeblendet oder angezeigt wird, beim Aufruf von `ShowPane`. Anderenfalls andockbare Bereich aktiviert bzw. deaktiviert wird, und der zugehörigen zum automatischen ausblenden Symbolleiste oder AutoAusblenden-Schaltfläche ist immer sichtbar.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse das Standardverhalten für einzelne Bereiche zu ändern.  
  
 Der Standardwert für `m_bHideInAutoHideMode` lautet `FALSE`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>CDockablePane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen ist ( [CMultiPaneFrameWnd Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in einem Rahmenfenster mit mehreren Bereichen wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isresizable"></a>CDockablePane::IsResizable  
 Gibt an, ob der Bereich geändert werden.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich geändert wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig sind andockbare Bereiche mit veränderbarer Größe. Um zu verhindern, Ändern der Größe, diese Methode in einer abgeleiteten Klasse überschreiben und zurückgeben `FALSE`. Beachten Sie, dass ein `FALSE` Wert führt zu einer fehlgeschlagenen `ASSERT` in [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane). Verwendung [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) stattdessen einen Bereich innerhalb eines übergeordneten Frames andocken.  
  
 Bereiche, die nicht verändert werden können können weder float noch Geben Sie automatisch ausgeblendet und befinden sich immer am äußeren Rand des übergeordneten Rahmens.  
  
##  <a name="istablocationbottom"></a>CDockablePane::IsTabLocationBottom  
 Gibt an, ob die Registerkarten oben oder unten im Bereich befinden.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Registerkarten am unteren Rand des Bereichs befinden; `FALSE` Wenn Registerkarten am oberen Rand des Bereichs befinden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom).  
  
##  <a name="istracked"></a>CDockablePane::IsTracked  
 Gibt an, ob ein Bereich vom Benutzer verschoben wird.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich verschoben wird; andernfalls `FALSE`.  
  
##  <a name="isvisible"></a>CDockablePane::IsVisible  
 Bestimmt, ob der aktuelle Bereich angezeigt wird.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die andockbare Fenster sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob ein andockbares Fenster sichtbar ist. Sie können diese Methode verwenden, statt [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) oder Tests für die `WS_VISIBLE` Stil. Der zurückgegebenen Sichtbarkeitszustand hängt davon ab, ob der Ausblendmodus zum automatischen aktiviert oder deaktiviert ist und auf dem Wert der [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) Eigenschaft.  
  
 Wenn der andockbare Bereich im Ausblendmodus zum automatischen wird und `IsHideInAutoHideMode` gibt `FALSE` der Sichtbarkeitsstatus ist immer `FALSE`.  
  
 Wenn der andockbare Bereich im Ausblendmodus zum automatischen wird und `IsHideInAutoHideMode` gibt `TRUE` der Sichtbarkeitszustand hängt von den Sichtbarkeitsstatus der zugehörigen zum automatischen ausblenden Symbolleiste.  
  
 Ist der andockbare Bereich nicht im Ausblendmodus zum automatischen, der Sichtbarkeitsstatus wird anhand der [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) Methode.  
  
##  <a name="m_bdisableanimation"></a>CDockablePane::m_bDisableAnimation  
 Gibt an, ob die Animation zum automatischen Ausblenden andockbaren Bereich deaktiviert ist.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>CDockablePane::m_bHideInAutoHideMode  
 Bestimmt das Verhalten des Bereichs an, wenn der Bereich im automatisch im Hintergrund ausgeführt wird.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wirkt sich auf alle andockbare Bereiche in der Anwendung.  
  
 Wenn Sie dieses Element, um festlegen `TRUE`, andockbare Bereiche ausgeblendet oder mit ihren zugehörigen AutoAusblenden Symbolleisten und Schaltflächen angezeigt werden, wenn Sie aufrufen [CDockablePane::ShowPane](#showpane).  
  
 Wenn Sie dieses Element, um festlegen `FALSE`, andockbare Bereiche sind aktiviert oder deaktiviert werden, wenn Sie aufrufen [CDockablePane::ShowPane](#showpane).  
  
##  <a name="m_nslidesteps"></a>CDockablePane::m_nSlideSteps  
 Gibt die Geschwindigkeit der Animation im Bereich an, wenn im automatisch im Hintergrund ausgeführt wird.  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>Hinweise  
 Für eine schnellere Animationseffekt verringern dieses Werts. Erhöhen Sie diesen Wert für eine langsamere Animationseffekt.  
  
##  <a name="onafterchangeparent"></a>CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndOldParent`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onafterdockfromminiframe"></a>CDockablePane::OnAfterDockFromMiniFrame  
 Wird vom Framework aufgerufen, wenn eine Gleitkommazahl andockleiste an einem Rahmenfenster angedockt.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig bewirkt diese Methode nichts.  
  
##  <a name="onbeforechangeparent"></a>CDockablePane::OnBeforeChangeParent  
 Das Framework ruft diese Methode auf, bevor sie das übergeordnete Element des Bereichs ändert.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndNewParent`  
 Ein Zeiger auf den neuen übergeordneten Fenster.  
  
 [in] `bDelay`  
 `BOOL`die angibt, ob die Berechnung des andocklayouts zu verzögern, wenn der Bereich nicht in der Dockingstation ist. Weitere Informationen finden Sie unter [CDockablePane::UndockPane](#undockpane).  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich angedockt ist, und das neue übergeordnete Objekt lässt keine andocken, wird diese Methode im Bereich abgedockt.  
  
 Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert wird, speichert diese Methode die aktuelle andockbare Position. Das Framework verwendet die aktuelle dockingposition, um die Position des Bereichs wiederherstellen, wenn es wieder in einem angedockten Zustand konvertiert wird.  
  
##  <a name="onbeforefloat"></a>CDockablePane::OnBeforeFloat  
 Das Framework ruft diese Methode vor einen Bereich Übergänge in einen unverankerten Zustand.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt die Position und Größe des Bereichs an, wenn es in einen unverankerten Zustand ist.  
  
 [in] `dockMethod`  
 Gibt die Methode andocken. Finden Sie unter [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) eine Liste der möglichen Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich abgedockt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Bereich in einen Gleitkommawert ist. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Verarbeitungsschritte auszuführen, bevor Bereich wird verschoben werden soll.  
  
##  <a name="onpressbuttons"></a>CDockablePane::OnPressButtons  
 Wird aufgerufen, wenn der Benutzer eine Beschriftung als drückt die `AFX_HTCLOSE` und `AFX_HTMAXBUTTON` Schaltflächen.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHit`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine benutzerdefinierte Schaltfläche die Beschriftung des einen andockbaren Bereich hinzufügen, überschreiben Sie diese Methode zum Empfangen von Benachrichtigungen, wenn ein Benutzer die Taste drückt.  
  
##  <a name="onslide"></a>CDockablePane::OnSlide  
 Aufgerufen, um den Bereich zu animieren, wenn im automatisch im Hintergrund ausgeführt wird.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSlideOut`  
 `TRUE`um den Bereich anzuzeigen; `FALSE` zum Ausblenden des Fensters.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten AutoAusblenden Effekte.  
  
##  <a name="removefromdefaultpanedividier"></a>CDockablePane::RemoveFromDefaultPaneDividier  
 Das Framework ruft diese Methode auf, wenn ein Bereich ist abgedockt wird.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die Standard-Trennlinie auf `NULL` und entfernt den Bereich von seinem Container.  
  
##  <a name="replacepane"></a>CDockablePane::ReplacePane  
 Ersetzt den Bereich mit einem angegebenen Bereich.  
  
```  
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bRegisterWithFrame = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBarToReplaceWith`  
 Ein Zeiger auf einen andockbaren Bereich.  
  
 [in] `dockMethod`  
 Nicht verwendet.  
  
 [in] `bRegisterWithFrame`  
 Wenn `TRUE`, im neuen docking-Manager des übergeordneten Elements des alten Bereichs registriert ist. Der neue Bereich wird am Index aus der alten Bereich in der Liste der Bereiche eingefügt, die von der Dockingstation-Manager verwaltet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Austausch erfolgreich war; andernfalls `FALSE`.  
  
##  <a name="restoredefaultpanedivider"></a>CDockablePane::RestoreDefaultPaneDivider  
 Wenn ein Bereich deserialisiert wird, ruft das Framework diese Methode, um die Trennlinie Standard wiederherstellen.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>Hinweise  
 Die wiederhergestellten Trennlinie ersetzt die aktuelle Standard-Trennlinie, falls vorhanden.  
  
##  <a name="setautohidemode"></a>CDockablePane::SetAutoHideMode  
 Schaltet die andockbaren zwischen angezeigt und automatisch im Hintergrund-Modus.  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMode`  
 `TRUE`Aktivieren Sie zum automatischen Ausblendmodus; `FALSE` reguläre Andockmodus aktivieren.  
  
 [in] `dwAlignment`  
 Gibt die Ausrichtung des Bereichs automatisch im Hintergrund zu erstellen.  
  
 [in] [out]`pCurrAutoHideBar`  
 Ein Zeiger auf die aktuelle zum automatischen ausblenden Symbolleiste. Kann `NULL`.  
  
 [in] `bUseTimer`  
 Gibt an, ob den Effekt automatisch im Hintergrund zu verwenden, wenn der Benutzer den Bereich zum automatischen Ausblendmodus wechselt oder sofort Ausblenden des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Automatisches Ausblenden Symbolleiste, die erstellt wurde, durch das Wechseln in den Ausblendmodus zum automatischen oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode klickt ein Benutzer die Pin-Schaltfläche, um die andockbaren Bereich Ausblendmodus zum automatischen oder regulären Andockmodus wechseln.  
  
 Rufen Sie diese Methode, um ein andockbares Fenster programmgesteuert in AutoAusblenden-Modus zu wechseln. Der Bereich muss an das Hauptrahmenfenster angedockt werden ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) muss einen gültigen Zeiger auf Zurückgeben der [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="setautohideparents"></a>CDockablePane::SetAutoHideParents  
 Die Schaltfläche automatisch im Hintergrund und automatisch im Hintergrund-Symbolleiste für den Bereich festgelegt.  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pToolBar`  
 Ein Zeiger auf ein solches.  
  
 [in] `pBtn`  
 Ein Zeiger auf eine Schaltfläche automatisch im Hintergrund.  
  
##  <a name="setlastpercentinpanecontainer"></a>CDockablePane::SetLastPercentInPaneContainer  
 Stellt den Prozentsatz des Speicherplatzes, der ein Bereich in einem Container einnimmt.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Eine `int` , die den Prozentsatz des Speicherplatzes, der der Bereich in einem Container befindet sich angibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework passt den Bereich, um den neuen Wert zu verwenden, wenn das Layout neu berechnet wird.  
  
##  <a name="setrestoreddefaultpanedivider"></a>CDockablePane::SetRestoredDefaultPaneDivider  
 Wird der wiederhergestellten Trennlinie.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hRestoredSlider`  
 Ein Handle für eine Trennlinie (Schieberegler).  
  
### <a name="remarks"></a>Hinweise  
 Eine Trennlinie wiederhergestellten wird abgerufen, wenn ein Bereich deserialisiert wird. Weitere Informationen finden Sie unter [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider).  
  
##  <a name="settabbedpanertc"></a>CDockablePane::SetTabbedPaneRTC  
 Legt die Laufzeit-Klasseninformationen für ein Fenster im Registerkartenformat, das erstellt wird, wenn zwei Bereichen zusammen andocken.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRTC`  
 Die Laufzeit-Klasseninformationen für die Seite im Registerformat.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Laufzeit-Klasseninformationen für Seiten im Registerformat festgelegt, die dynamisch erstellt werden. Dies kann auftreten, wenn ein Benutzer einen Bereich, der die Beschriftung von einem anderen Bereich zieht, oder rufen Sie die [CDockablePane::AttachToTabWnd](#attachtotabwnd) Methode, um ein Fenster mit Registerkarten aus zwei andockbare Bereiche programmgesteuert zu erstellen.  
  
 Die Standardklasse für die Common Language Runtime festgelegt ist, entsprechend der `dwTabbedStyle` Parameter der [CDockablePane::Create](#create) und [CDockablePane::CreateEx](#createex). Um die neuen Bereiche im Registerkartenformat anzupassen, leiten Sie eine Klasse von einer der folgenden Klassen:  
  
- [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md)  
  
- [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Anschließend rufen Sie diese Methode mit dem Mauszeiger auf die Laufzeit-Klasseninformationen.  
  
##  <a name="showpane"></a>CDockablePane::ShowPane  
 Anzeigen oder ausblenden ein Bereichs.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE`um den Bereich anzuzeigen; `FALSE` zum Ausblenden des Fensters.  
  
 [in] `bDelay`  
 `TRUE`verzögern der andocklayout anpassen; `FALSE` sofort das Andocken Layout anpassen.  
  
 [in] `bActivate`  
 `TRUE`Aktivieren Sie im Bereich Wenn angezeigt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode statt der [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) beim ein- oder Ausblenden der andockbare Bereiche.  
  
##  <a name="slide"></a>CDockablePane::Slide  
 Verwendet einen Bereich, der im automatisch im Hintergrund ausgeführt wird.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSlideOut`  
 `TRUE`um den Bereich anzuzeigen; `FALSE` zum Ausblenden des Fensters.  
  
 [in] `bUseTimer`  
 `TRUE`ein-oder Ausblenden des Bereichs mit dem Effekt zum automatischen Ausblenden; `FALSE` ein-oder Ausblenden des Bereichs sofort.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um einen Bereich zu animieren, der im automatisch im Hintergrund ausgeführt wird.  
  
 Diese Methode verwendet die `CDockablePane::m_nSlideDefaultTimeOut` um das Timeout für die Abrolleffekt zu bestimmen. Der Standardwert für das Timeout ist 1. Beim Anpassen des Algorithmus automatisch im Hintergrund ändern Sie diesen Member, um das Zeitlimit ändern.  
  
##  <a name="toggleautohide"></a>CDockablePane::ToggleAutoHide  
 Schaltet den Bereich zwischen immer sichtbar und automatisch ausgeblendet.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schaltet automatisch im Hintergrund-Modus für den Bereich durch Aufrufen von [CDockablePane::SetAutoHideMode](#setautohidemode).  
  
##  <a name="undockpane"></a>CDockablePane::UndockPane  
 Wird einen Bereich im Hauptrahmenfenster oder Miniframe Fenster Container abgedockt.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDelay`  
 `TRUE`verzögern der andocklayout berechnen; `FALSE` , die andocklayout sofort neu zu berechnen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich von Hauptrahmenfenster oder aus einem Container für Multi-Miniframe-Fenster (ein Bereich, der in einer einzelnen Minirahmenfenster mit anderen Bereichen verankert ist) abdocken.  
  
 Sie müssen einen Bereich abdocken, bevor Sie alle externen Vorgänge ausführen, die nicht von ausgeführt werden die [CDockingManager](../../mfc/reference/cdockingmanager-class.md). Beispielsweise müssen Sie einen Bereich zu verschieben programmgesteuert von einem Speicherort zu einem anderen abdocken.  
  
 Das Framework werden Bereiche automatisch abgedockt, bevor sie zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)

