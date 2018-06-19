---
title: CDockablePane-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDockablePane [MFC], CDockablePane
- CDockablePane [MFC], AttachToTabWnd
- CDockablePane [MFC], CalcFixedLayout
- CDockablePane [MFC], CanAcceptMiniFrame
- CDockablePane [MFC], CanAcceptPane
- CDockablePane [MFC], CanAutoHide
- CDockablePane [MFC], CanBeAttached
- CDockablePane [MFC], ConvertToTabbedDocument
- CDockablePane [MFC], CopyState
- CDockablePane [MFC], Create
- CDockablePane [MFC], CreateDefaultPaneDivider
- CDockablePane [MFC], CreateEx
- CDockablePane [MFC], CreateTabbedPane
- CDockablePane [MFC], DockPaneContainer
- CDockablePane [MFC], DockPaneStandard
- CDockablePane [MFC], DockToRecentPos
- CDockablePane [MFC], DockToWindow
- CDockablePane [MFC], EnableAutohideAll
- CDockablePane [MFC], EnableGripper
- CDockablePane [MFC], GetAHRestoredRect
- CDockablePane [MFC], GetAHSlideMode
- CDockablePane [MFC], GetCaptionHeight
- CDockablePane [MFC], GetDefaultPaneDivider
- CDockablePane [MFC], GetDockingStatus
- CDockablePane [MFC], GetDragSensitivity
- CDockablePane [MFC], GetLastPercentInPaneContainer
- CDockablePane [MFC], GetTabArea
- CDockablePane [MFC], GetTabbedPaneRTC
- CDockablePane [MFC], HasAutoHideMode
- CDockablePane [MFC], HitTest
- CDockablePane [MFC], IsAutohideAllEnabled
- CDockablePane [MFC], IsAutoHideMode
- CDockablePane [MFC], IsDocked
- CDockablePane [MFC], IsHideInAutoHideMode
- CDockablePane [MFC], IsInFloatingMultiPaneFrameWnd
- CDockablePane [MFC], IsResizable
- CDockablePane [MFC], IsTabLocationBottom
- CDockablePane [MFC], IsTracked
- CDockablePane [MFC], IsVisible
- CDockablePane [MFC], OnAfterChangeParent
- CDockablePane [MFC], OnAfterDockFromMiniFrame
- CDockablePane [MFC], OnBeforeChangeParent
- CDockablePane [MFC], OnBeforeFloat
- CDockablePane [MFC], RemoveFromDefaultPaneDividier
- CDockablePane [MFC], ReplacePane
- CDockablePane [MFC], RestoreDefaultPaneDivider
- CDockablePane [MFC], SetAutoHideMode
- CDockablePane [MFC], SetAutoHideParents
- CDockablePane [MFC], SetLastPercentInPaneContainer
- CDockablePane [MFC], SetRestoredDefaultPaneDivider
- CDockablePane [MFC], SetTabbedPaneRTC
- CDockablePane [MFC], ShowPane
- CDockablePane [MFC], Slide
- CDockablePane [MFC], ToggleAutoHide
- CDockablePane [MFC], UndockPane
- CDockablePane [MFC], CheckAutoHideCondition
- CDockablePane [MFC], CheckStopSlideCondition
- CDockablePane [MFC], DrawCaption
- CDockablePane [MFC], OnPressButtons
- CDockablePane [MFC], OnSlide
- CDockablePane [MFC], m_bDisableAnimation
- CDockablePane [MFC], m_bHideInAutoHideMode
- CDockablePane [MFC], m_nSlideSteps
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0b00c40ded45d1d71b42c126e2461c404eb5223
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378799"
---
# <a name="cdockablepane-class"></a>CDockablePane Class
Implementiert einen Bereich, der entweder in eine Docksite angedockt oder in einer Seite im Registerformat enthalten sein kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDockablePane : public CPane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](#cdockablepane)|Erstellt und initialisiert ein `CDockablePane`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane:: Attachtotabwnd](#attachtotabwnd)|Fügt einen Bereich in einen anderen Bereich an. Dadurch wird ein Fenster mit Registerkarten erstellt.|  
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|Gibt die Größe des Rechtecks Bereich zurück.|  
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|Bestimmt, ob in den Bereich der angegebenen Mini-Rahmens angedockt werden kann.|  
|[CDockablePane::CanAcceptPane](#canacceptpane)|Bestimmt, ob es sich bei einem anderen Bereich in den aktuellen Bereich angedockt werden kann.|  
|[CDockablePane::CanAutoHide](#canautohide)|Bestimmt, ob der Bereich automatisch im Hintergrund-Modus unterstützt. (Überschreibt [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|  
|[CDockablePane::CanBeAttached](#canbeattached)|Bestimmt, ob der aktuelle Bereich in einen anderen Bereich angedockt werden kann.|  
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten an.|  
|[CDockablePane::CopyState](#copystate)|Kopiert den Status des ein andockbares Fenster an.|  
|[CDockablePane::Create](#create)|Erstellt die Windows-Steuerelement, und fügt es der `CDockablePane` Objekt.|  
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|Um ein Framefenster angedockt wird, ist erstellt einen Standard-Unterteiler für den Bereich.|  
|[CDockablePane:: CreateEx](#createex)|Erstellt die Windows-Steuerelement, und fügt es der `CDockablePane` Objekt.|  
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|Erstellt einen Bereich im Registerkartenformat im aktuellen Bereich.|  
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|Dockt einen Container in den Bereich an.|  
|[CDockablePane::DockPaneStandard](#dockpanestandard)|Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.|  
|`CDockablePane::DockToFrameWindow`|Wird intern verwendet. Verwenden, um einen Bereich anzudocken, [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) oder [CDockablePane::DockToWindow](#docktowindow).|  
|[CDockablePane::DockToRecentPos](#docktorecentpos)|Dockt einen Bereich auf seine gespeicherte aktuelle verankerten Position an.|  
|[CDockablePane::DockToWindow](#docktowindow)|Dockt einen andockbaren Bereich auf einen anderen andockbaren Bereich an.|  
|[CDockablePane::EnableAutohideAll](#enableautohideall)|Aktiviert oder deaktiviert die automatischen Ausblendemodus für diesen Bereich zusammen mit anderen Bereichen im Container.|  
|[CDockablePane::EnableGripper](#enablegripper)|Anzeigen oder ausblenden die Beschriftung (Ziehpunkt).|  
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|Gibt die Position des Bereichs, wenn im automatischen Ausblendemodus sichtbar.|  
|[CDockablePane::GetAHSlideMode](#getahslidemode)|Ruft das automatische Ausblenden Folienmodus für den Bereich ab.|  
|`CDockablePane::GetAutoHideButton`|Wird intern verwendet.|  
|`CDockablePane::GetAutoHideToolBar`|Wird intern verwendet.|  
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe des die aktuelle Beschriftung zurück.|  
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|Gibt standardmäßige bereichsteiler für den Bereich Container zurück.|  
|[CDockablePane::GetDockingStatus](#getdockingstatus)|Bestimmt die Möglichkeit eines Bereichs angedockt werden auf dem bereitgestellten Zeiger Speicherort basierend.|  
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|Gibt die Vertraulichkeit ziehen Sie einen andockbaren Bereich zurück.|  
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|Ruft den Prozentsatz des Speicherplatzes, der belegt ein Bereich innerhalb des Containers ab.|  
|[CDockablePane::GetTabArea](#gettabarea)|Ruft den Registerkartenbereich für den Bereich ab.|  
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|Gibt die laufzeitklasseninformationen über einem Fenster im Registerkartenformat, die erstellt wird, wenn Sie einen anderen Bereich in den aktuellen Bereich angedockt.|  
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|Gibt an, ob ein andockbarer Bereich zum automatischen Ausblenden Modus umgeschaltet werden kann.|  
|[CDockablePane::HitTest](#hittest)|Gibt die spezifische Stelle in einem Bereich, in dem der Benutzer die Maus klickt.|  
|`CDockablePane::IsAccessibilityCompatible`|Wird intern verwendet.|  
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|Gibt an, ob in den automatischen Ausblendemodus andockbaren Bereich und allen anderen Bereichen im Container platziert werden können.|  
|[CDockablePane::IsAutoHideMode](#isautohidemode)|Bestimmt, ob ein Bereich in den automatischen Ausblendemodus.|  
|`CDockablePane::IsChangeState`|Wird intern verwendet.|  
|[CDockablePane::IsDocked](#isdocked)|Bestimmt, ob der aktuelle Bereich angedockt ist.|  
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|Bestimmt das Verhalten eines Bereichs, der in den automatischen Ausblendemodus ist, wenn sie (durch Aufrufen oder ausgeblendet ist) `ShowPane`.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist.|  
|[CDockablePane::IsResizable](#isresizable)|Gibt an, ob der Bereich geändert wird.|  
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|Gibt an, ob die Registerkarten oben oder unten im Bereich befinden.|  
|[CDockablePane::IsTracked](#istracked)|Gibt an, ob ein Bereich vom Benutzer gezogen wird.|  
|[CDockablePane::IsVisible](#isvisible)|Bestimmt, ob der aktuelle Bereich angezeigt wird.|  
|[CDockablePane:: LoadState](http://msdn.microsoft.com/en-us/96110136-4f46-4764-8a76-3b4abaf77917)|Wird intern verwendet.|  
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|Vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert wurde. (Überschreibt [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|  
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|Vom Framework aufgerufen, wenn eine Gleitkommazahl andockleiste an ein Framefenster angedockt.|  
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|Vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird. (Überschreibt [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|  
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Vom Framework aufgerufen, wenn ein Bereich zu "float" befindet. (Überschreibt [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](#removefromdefaultpanedividier)|Das Framework ruft diese Methode auf, wenn ein Bereichs abgedockten wird ist.|  
|[CDockablePane::ReplacePane](#replacepane)|Ersetzt den Bereich mit einem angegebenen Bereich.|  
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|Das Framework ruft diese Methode an, wie ein Bereich deserialisiert wird, um die Standard-bereichsteiler wiederherzustellen.|  
|`CDockablePane::SaveState`|Wird intern verwendet.|  
|`CDockablePane::Serialize`|Serialisiert den Bereich an. (Überschreibt `CBasePane::Serialize`.)|  
|[CDockablePane::SetAutoHideMode](#setautohidemode)|Schaltet die andockbaren Bereich zwischen sichtbar und automatischen Ausblendemodus.|  
|[CDockablePane::SetAutoHideParents](#setautohideparents)|Die Schaltfläche zum automatischen Ausblenden und automatisch im Hintergrund-Symbolleiste für den Bereich festgelegt.|  
|`CDockablePane::SetDefaultPaneDivider`|Wird intern verwendet.|  
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|Bestimmt den Prozentsatz des Speicherplatzes, der ein Bereich innerhalb des Containers belegt.|  
|`CDockablePane::SetResizeMode`|Wird intern verwendet.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|Legt die wiederhergestellten bereichsteiler fest.|  
|[CDockablePane:: Settabbedpanertc](#settabbedpanertc)|Legt die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, die erstellt wird, wenn zwei Bereiche zusammen docken fest.|  
|[CDockablePane::ShowPane](#showpane)|Anzeigen oder ausblenden ein Bereichs.|  
|[CDockablePane::Slide](#slide)|Zeigt an, oder blendet Sie aus einem Bereich mit einem gleitenden Animation angezeigt wird, nur, wenn der Bereich in den automatischen Ausblendemodus ist.|  
|[CDockablePane::ToggleAutoHide](#toggleautohide)|Schaltet automatischen Ausblendemodus. (Überschreibt [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|  
|[CDockablePane::UndockPane](#undockpane)|Dockt einen Bereich von Hauptrahmenfenster oder Miniframe Fenster Container an.|  
|`CDockablePane::UnSetAutoHideMode`|Wird intern verwendet. Verwenden Sie zum Festlegen der automatischen Ausblendemodus [CDockablePane::SetAutoHideMode](#setautohidemode)|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|Bestimmt, ob die andockbare Bereich (im automatischen Ausblendemodus) ausgeblendet ist.|  
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|Bestimmt, wenn ein automatisch ausblendbaren andockbaren Bereich kann an verschiebbaren beendet werden soll.|  
|[CDockablePane::DrawCaption](#drawcaption)|Zeichnet die andockbaren Bereich Beschriftung (Ziehpunkt).|  
|[CDockablePane::OnPressButtons](#onpressbuttons)|Wird aufgerufen, wenn der Benutzer eine Beschriftung außer drückt die `AFX_HTCLOSE` und `AFX_HTMAXBUTTON` Schaltflächen.|  
|[CDockablePane::OnSlide](#onslide)|Vom Framework aufgerufen, die automatisch ausblendbare Abrolleffekt gerendert werden soll, wenn der Bereich entweder angezeigt oder ausgeblendet wird.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|Gibt an, ob automatisch ausblendbaren Animation andockbaren Bereich deaktiviert ist.|  
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|Bestimmt das Verhalten des Bereichs an, wenn der Bereich in den automatischen Ausblendemodus ist.|  
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|Gibt die Geschwindigkeit der Animation des Bereichs an, wenn es gerade angezeigt oder ausgeblendet werden, wenn in den automatischen Ausblendemodus.|  
  
## <a name="remarks"></a>Hinweise  
 `CDockablePane` implementiert die folgende Funktionen:  
  
-   Einen Bereich andocken eine Hauptrahmenfenster.  
  
-   Wechseln zum automatischen Ausblendemodus einen Bereich.  
  
-   Einen Bereich wird an ein Fenster im Registerkartenformat angefügt.  
  
-   Gleitkomma-einen Bereich in einem Minirahmenfenster.  
  
-   Andocken von einem Bereich in einen anderen Bereich, die in einem Minirahmenfenster unverankert ist.  
  
-   Ändern der Größe eines Bereichs.  
  
-   Laden und Speichern des Zustands für einen andockbaren Bereich.  
  
    > [!NOTE]
    >  Zustandsinformationen wird in der Windows-Registrierung gespeichert.  
  
-   Erstellen einen Bereich mit oder ohne Beschriftung. Die Beschriftung kann eine Beschriftung aufweisen, und es mit einem Farbverlauf ausgefüllt werden kann.  
  
-   Ziehen einen Bereich beim Anzeigen des Inhalts des Bereichs  
  
-   Ziehen beim Anzeigen eines Rechtecks ziehen Sie einen Bereich.  
  
 Um einen andockbaren Bereich in der Anwendung zu verwenden, leiten Sie eine Klasse im Bereich von der `CDockablePane` Klasse. Betten Sie das abgeleitete Objekt in die Hauptframe-Fensterobjekt oder in einem Fensterobjekt, das die Instanz von Ihrem Bereich "" steuert. Rufen Sie anschließend die [CDockablePane::Create](#create) Methode oder die [CDockablePane:: CreateEx](#createex) Methode, die beim Verarbeiten der `WM_CREATE` Nachricht im Hauptrahmenfenster. Richten Pane-Objekt durch Aufrufen von [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [cbasepane:: Dockpane](../../mfc/reference/cbasepane-class.md#dockpane), oder [CDockablePane:: Attachtotabwnd](#attachtotabwnd).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgenden Tipps gelten für `CDockablePane` Objekte:  
  
-   Beim Aufrufen [CDockablePane:: Attachtotabwnd](#attachtotabwnd) für zwei nicht im Registerkartenformat, andockbare Bereiche, ein Zeiger auf ein Fenster im Registerkartenformat im zurückgegeben der `ppTabbedControlBar` Parameter. Sie können weiterhin das Fenster im Registerkartenformat durch Verwendung dieses Parameters Registerkarten hinzu.  
  
-   Die Art der Bereich im Registerkartenformat durch die erstellte [CDockablePane:: Attachtotabwnd](#attachtotabwnd) richtet sich nach der `CDockablePane` Objekt in der `pTabControlBarAttachTo` Parameter. Sie erreichen [CDockablePane:: Settabbedpanertc](#settabbedpanertc) auf der Art der Bereich im Registerkartenformat festlegen, die die `CDockablePane` wird erstellt. Der Standardtyp richtet sich nach der `dwTabbedStyle` von [CDockablePane::Create](#create) beim Erstellen der `CDockablePane`. Wenn `dwTabbedStyle` ist der Standardtyp ist AFX_CBRS_OUTLOOK_TABS [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md); Wenn `dwTabbedStyle` ist der Standardtyp ist AFX_CBRS_REGULAR_TABS [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md).  
  
-   Wenn Sie einen andockbaren Bereich in einen anderen andocken möchten, rufen Sie die [CDockablePane::DockToWindow](#docktowindow) Methode. Der ursprüngliche Bereich muss an einer Stelle angedockt werden, bevor Sie diese Methode aufrufen.  
  
-   Die Membervariable [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) Steuerelemente andockbare Bereiche im Autocommit Verhalten ausblenden Modus beim Aufrufen von [CDockablePane::ShowPane](#showpane). Wenn diese Membervariable, um festgelegt ist `TRUE`, andockbare Bereiche und deren automatische Ausblenden-Schaltflächen werden ausgeblendet. Andernfalls werden sie ein-und schieben.  
  
-   Sie können automatisch ausblendbaren Animation deaktivieren, indem die [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) Membervariable `TRUE`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Konfigurieren einer `CDockablePane` -Objekt mithilfe verschiedener Methoden in der `CDockablePane` Klasse. Im Beispiel veranschaulicht die automatisch ausblendbare alle Funktion für die andockbaren Bereich aktivieren, aktivieren die Beschriftung oder die Ziehpunkte, aktivieren den automatischen Ausblendemodus, Anzeigen des Bereichs und animieren einen Bereich, der in den automatischen Ausblendemodus ist. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#27](../../mfc/codesnippet/cpp/cdockablepane-class_1.cpp)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#28](../../mfc/codesnippet/cpp/cdockablepane-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockablePane.h  
  
##  <a name="attachtotabwnd"></a>  CDockablePane:: Attachtotabwnd  
 Fügt den aktuellen Bereich zu einem Zielbereich, und erstellen einen Bereich im Registerkartenformat.  
  
```  
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bSetActive= TRUE,  
    CDockablePane** ppTabbedControlBar = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pTabControlBarAttachTo`  
 Gibt an, die Zielbereich, dem der aktuellen Bereich zugeordnet wird. Der Zielbereich muss es sich um einen andockbaren Bereich sein.  
  
 [in] `dockMethod`  
 Gibt die Andock-Methode.  
  
 [in] `bSetActive`  
 `TRUE` So aktivieren Sie die Seite im Registerformat nach dem Anfügevorgang; andernfalls `FALSE`.  
  
 [out] `ppTabbedControlBar`  
 Enthält der Bereich im Registerkartenformat, die durch den Anfügevorgang entsteht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den aktuellen Bereich, wenn es sich nicht um einen Bereich im Registerkartenformat handelt; andernfalls ein Zeiger auf den Bereich im Registerkartenformat, die durch den Anfügevorgang entsteht. Der Rückgabewert ist `NULL` Wenn im aktuellen Bereich kann nicht angefügt werden, oder wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn zu einem anderen Bereich, die mit dieser Methode einen andockbaren Bereich anfügt, geschieht Folgendes:  
  
1.  Das Framework überprüft, ob Zielbereich `pTabControlBarAttachTo` ist eine reguläre andocken, Bereich oder wenn es von abgeleitet ist [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md).  
  
2.  Ist das Zielbereich einen Bereich im Registerkartenformat, fügt das Framework im aktuellen Bereich darauf als Registerkarte an.  
  
3.  Wenn die Zielbereich einen regulären andockbaren Bereich ist, erstellt das Framework einen Bereich im Registerkartenformat.  
  
    -   Das Framework ruft `pTabControlBarAttachTo->CreateTabbedPane`. Das Format der der neue Bereich im Registerkartenformat richtet sich nach der `m_pTabbedControlBarRTC` Member. Wird standardmäßig bei diesem Member festgelegt ist, auf die Laufzeitklasse der [CTabbedPane](../../mfc/reference/ctabbedpane-class.md). Wenn Sie übergeben die `AFX_CBRS_OUTLOOK_TABS` als Formatieren der `dwTabbedStyle` Parameter an die [CDockablePane::Create](#create) -Methode, die Common Language Runtime-Klassenobjekt in der Common Language Runtime-Klasse des festgelegt ist [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md). Sie können dieses Elements zu einem beliebigen Zeitpunkt so ändern Sie das Format des neuen Bereichs ändern.  
  
    -   Wenn diese Methode einen Bereich im Registerkartenformat erstellt wird, ersetzt das Framework den Zeiger auf `pTabControlBarAttachTo` (wenn der Bereich angedockt oder unverankert in einer Multi-Minirahmenfenster ist) mit einem Zeiger auf den neuen Bereich im Registerkartenformat.  
  
    -   Fügt das Framework der `pTabControlBarAttachTo` Bereich, um den Bereich im Registerkartenformat als erste Registerkarte. Das Framework fügt dann der aktuelle Bereich als zweiten Registerkarte.  
  
4.  Wenn der aktuelle Bereich von abgeleitet ist `CBaseTabbedPane`, alle Registerkarten verschoben `pTabControlBarAttachTo` und der aktuelle Bereich zerstört wird. Daher vorsichtig sein, wenn Sie diese Methode aufrufen, da ein Zeiger auf den aktuellen Bereich möglicherweise ungültig, wenn die Methode zurückkehrt.  
  
 Wenn Sie einen Bereich in einen anderen anfügen, wenn eine andocklayout erstellen, legen Sie `dockMethod` auf `DM_SHOW`.  
  
 Sie sollten den ersten Bereich andocken, bevor Sie einen anderen Bereich anfügen.  
  
##  <a name="calcfixedlayout"></a>  CDockablePane::CalcFixedLayout  
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
 Ein `CSize` Objekt, das die Größe des Rechtecks Bereich enthält.  
  
##  <a name="canacceptminiframe"></a>  CDockablePane::CanAcceptMiniFrame  
 Bestimmt, ob die angegebenen Minirahmenfensters in den Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMiniFrame`  
 Zeiger auf eine `CPaneFrameWnd` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn `pMiniFrame` können in den Bereich angedockt ist, andernfalls werden `FALSE`.  
  
##  <a name="canacceptpane"></a>  CDockablePane::CanAcceptPane  
 Bestimmt, ob es sich bei einem anderen Bereich in den aktuellen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Gibt den Bereich, um den aktuellen Bereich angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn im angegebene Bereich in diesen Bereich; angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor Sie ein Bereich in den aktuellen Bereich angedockt ist.  
  
 Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren Sie auf einen bestimmten Bereich andocken.  
  
 Standardmäßig gibt diese Methode `TRUE` Wenn `pBar` oder das übergeordnete Element ist vom Typ `CDockablePane`.  
  
##  <a name="canautohide"></a>  CDockablePane::CanAutoHide  
 Bestimmt, ob der Bereich automatisch im Hintergrund kann.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich automatisch im Hintergrund kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 `CDockablePane::CanAutoHide` Gibt `FALSE` in den folgenden Situationen:  
  
-   Der Bereich verfügt über kein übergeordnetes Element.  
  
-   Dock-Manager lässt keine Bereiche zum automatischen ausblenden.  
  
-   Der Bereich wird nicht angedockt.  
  
##  <a name="canbeattached"></a>  CDockablePane::CanBeAttached  
 Bestimmt, ob der aktuelle Bereich in einen anderen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich in einen anderen Bereich oder an das Hauptrahmenfenster; angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig gibt diese Methode immer `TRUE`. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren, ohne Aufruf Andocken [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).  
  
##  <a name="cdockablepane"></a>  CDockablePane::CDockablePane  
 Erstellt und initialisiert ein [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
```  
CDockablePane();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen andockbaren Bereich-Objekt erstellt haben, rufen [CDockablePane::Create](#create) oder [CDockablePane:: CreateEx](#createex) , ihn zu erstellen.  
  
##  <a name="converttotabbeddocument"></a>  CDockablePane::ConvertToTabbedDocument  
 Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten an.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActiveTabOnly`  
 Bei der Konvertierung einer `CTabbedPane`, geben Sie `TRUE` nur die aktive Registerkarte zu konvertieren. Geben Sie `FALSE` aller Registerkarten im Bereich zu konvertieren.  
  
##  <a name="checkautohidecondition"></a>  CDockablePane::CheckAutoHideCondition  
 Bestimmt, ob die andockbare Bereich ausgeblendet ist (auch als in den Hintergrundmodus bezeichnet).  
  
```  
virtual BOOL CheckAutoHideCondition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die ausblenden erfüllt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet einen Timer, um regelmäßig zu prüfen, ob einen Automatisches Ausblenden andockbaren Bereich auszublenden. Die Methode gibt `TRUE` beim Bereich nicht aktiv ist, der Bereich nicht geändert wird und der Mauszeiger die Form nicht über den Bereich ist.  
  
 Wenn alle genannten Bedingungen erfüllt sind, das Framework ruft [CDockablePane::Slide](#slide) So blenden Sie den Bereich aus.  
  
##  <a name="checkstopslidecondition"></a>  CDockablePane::CheckStopSlideCondition  
 Bestimmt, wann ein Automatisches Ausblenden andockbaren Bereich kann an verschiebbaren beendet werden soll.  
  
```  
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDirection`  
 `TRUE` Wenn der Bereich sichtbar ist; `FALSE` , wenn der Bereich ausgeblendet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die beenden-Bedingung erfüllt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein andockbares Fenster in den Hintergrundmodus festgelegt ist, verwendet das Framework gleitende Effekte ein-oder Ausblenden des Bereichs an. Das Framework ruft diese Funktion auf, wenn der Bereich kann an verschiebbaren ist. `CheckStopSlideCondition` Gibt `TRUE` Wenn Bereich vollständig sichtbar ist, oder wenn es vollständig ausgeblendet ist.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Taskleisten Auswirkungen.  
  
##  <a name="copystate"></a>  CDockablePane::CopyState  
 Kopiert den Status des ein andockbares Fenster an.  
  
```  
virtual void CopyState(CDockablePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOrgBar`  
 Ein Zeiger auf einen andockbaren Bereich.  
  
### <a name="remarks"></a>Hinweise  
 `CDockablePane::CopyState` kopiert den Status des `pOrgBar` in den aktuellen Bereich durch Aufrufen der folgenden Methoden:  
  
- [CPane::CopyState](../../mfc/reference/cpane-class.md#copystate)  
  
- [CDockablePane::GetAHRestoredRect](#getahrestoredrect)  
  
- [CDockablePane::GetAHSlideMode](#getahslidemode)  
  
- [CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)  
  
- [CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)  
  
##  <a name="create"></a>  CDockablePane::Create  
 Erstellt die Windows-Steuerelement, und fügt es der [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
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
  
 [in] [out] `pParentWnd`  
 Gibt das übergeordnete Fenster.  
  
 [in] `rect`  
 Gibt die Größe und Position des Fensters, in Clientkoordinaten der `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE` So erstellen Sie im Bereich mit einem Titel; andernfalls `FALSE`.  
  
 [in] `nID`  
 Gibt die ID des untergeordneten Fensters. Dieser Wert muss eindeutig sein, wenn für diese andockbaren Bereich andockzustand gespeichert werden soll.  
  
 [in] `dwStyle`  
 Gibt an, die Fenster-Stilattribute.  
  
 [in] `dwTabbedStyle`  
 Gibt die im Registerkartenformat Art von einem Fenster im Registerkartenformat, die erstellt wird, wenn der Benutzer einen Bereich auf die Beschriftung des in diesem Bereich zieht.  
  
 [in] `dwControlBarStyle`  
 Gibt zusätzliche Formatattribute an.  
  
 [in] [out] `pContext`  
 Gibt den Kontext Erstellen des Fensters.  
  
 [in] `lpszWindowName`  
 Gibt den Fensternamen.  
  
 [in] `sizeDefault`  
 Gibt die Größe des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich erfolgreich erstellt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Windows-Bereich und fügt es der `CDockablePane` Objekt.  
  
 Wenn die `dwStyle` Fensterstil hat die `CBRS_FLOAT_MULTI` Flag, das Minirahmenfenster kann mit anderen Bereichen in der Minirahmenfenster float. Standardmäßig kann andockbare Bereiche nur einzeln verschieben.  
  
 Wenn die `dwTabbedStyle` Parameter hat die `AFX_CBRS_OUTLOOK_TABS` Flag angegeben, die der Bereich erstellt Outlook-Stil im Registerkartenformat Bereiche aus, wenn auf diesen Bereich mit einem anderen Bereich angefügt ist die [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode. Standardmäßig erstellen andockbare Bereiche reguläre Bereiche im Registerkartenformat Typ [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createdefaultpanedivider"></a>  CDockablePane::CreateDefaultPaneDivider  
 Um ein Framefenster angedockt wird, ist erstellt einen Standard-Unterteiler für den Bereich.  
  
```  
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,  
    CWnd* pParent,  
    CRuntimeClass* pSliderRTC = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Gibt das Ende der Hauptframe, zu dem der Bereich angedockt wird, ist. Wenn `dwAlignment` enthält die `CBRS_ALIGN_LEFT` oder `CBRS_ALIGN_RIGHT` Flag, diese Methode erstellt eine vertikale ( `CPaneDivider::SS_VERT`) Unterteiler; andernfalls erstellt diese Methode eine horizontale ( `CPaneDivider::SS_HORZ`) Unterteiler.  
  
 [in] `pParent`  
 Ein Zeiger auf den übergeordneten Frame.  
  
 [in] `pSliderRTC`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt einen Zeiger auf den Unterteiler neu erstellt oder `NULL` Wenn Unterteiler Erstellung ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 `dwAlignment` eine der folgenden Werte kann sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Der Bereich wird am oberen Rand der Clientbereich eines Rahmenfensters angedockt wird.|  
|`CBRS_ALIGN_BOTTOM`|Der Bereich wird am Ende der Clientbereich eines Rahmenfensters angedockt wird.|  
|`CBRS_ALIGN_LEFT`|Der Bereich wird auf der linken Seite des Clientbereichs eines Frame-Fensters angedockt wird.|  
|`CBRS_ALIGN_RIGHT`|Der Bereich wird auf die rechte Seite des Clientbereichs eines Frame-Fensters angedockt wird.|  
  
##  <a name="createex"></a>  CDockablePane:: CreateEx  
 Erstellt die Windows-Steuerelement, und fügt es der [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.  
  
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
 Gibt den erweiterten Stilattribute für das neue Fenster an.  
  
 [in] `lpszCaption`  
 Gibt den Fensternamen.  
  
 [in] [out] `pParentWnd`  
 Gibt das übergeordnete Fenster.  
  
 [in] `rect`  
 Gibt die Größe und Position des Fensters, in Clientkoordinaten der `pParentWnd`.  
  
 [in] `bHasGripper`  
 `TRUE` So erstellen Sie im Bereich mit einem Titel; andernfalls `FALSE`.  
  
 [in] `nID`  
 Gibt die ID des untergeordneten Fensters. Dieser Wert muss eindeutig sein, wenn Sie den andockzustand für diese andockbaren Bereich speichern möchten.  
  
 [in] `dwStyle`  
 Gibt an, die Fenster-Stilattribute.  
  
 [in] `dwTabbedStyle`  
 Gibt die im Registerkartenformat Art von einem Fenster im Registerkartenformat, die erstellt wird, wenn der Benutzer einen Bereich auf die Beschriftung des in diesem Bereich zieht.  
  
 [in] `dwControlBarStyle`  
 Gibt an, die zusätzliche Stilattribute.  
  
 [in] [out] `pContext`  
 Gibt den Kontext Erstellen des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich erfolgreich erstellt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Windows-Bereich und fügt es der `CDockablePane` Objekt.  
  
 Wenn die `dwStyle` Fensterstil hat die `CBRS_FLOAT_MULTI` Flag, das Minirahmenfenster kann mit anderen Bereichen in der Minirahmenfenster float. Standardmäßig kann andockbare Bereiche nur einzeln verschieben.  
  
 Wenn die `dwTabbedStyle` Parameter hat die `AFX_CBRS_OUTLOOK_TABS` Flag angegeben, die der Bereich erstellt Outlook-Stil im Registerkartenformat Bereiche aus, wenn auf diesen Bereich mit einem anderen Bereich angefügt ist die [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode. Standardmäßig erstellen andockbare Bereiche reguläre Bereiche im Registerkartenformat Typ [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).  
  
##  <a name="createtabbedpane"></a>  CDockablePane::CreateTabbedPane  
 Erstellt einen Bereich im Registerkartenformat im aktuellen Bereich.  
  
```  
virtual CTabbedPane* CreateTabbedPane();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neue Bereich im Registerkartenformat, oder `NULL` bei fehlgeschlagenem Erstellungsvorgang.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es sich um einen Bereich im Registerkartenformat, ersetzen Sie in diesem Bereich erstellt. Weitere Informationen finden Sie unter [CDockablePane:: Attachtotabwnd](#attachtotabwnd).  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Bereiche wie im Registerkartenformat erstellt und initialisiert werden.  
  
 Bereich im Registerkartenformat wird gemäß der Laufzeit-Klasseninformationen in gespeicherten erstellt die `m_pTabbedControlBarRTC` Member, der Initialisierung von der [CDockablePane:: CreateEx](#createex) Methode.  
  
##  <a name="dockpanecontainer"></a>  CDockablePane::DockPaneContainer  
 Dockt einen Container in den Bereich an.  
  
```  
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `barContainerManager`  
 Ein Verweis auf den Manager des Containers, die gerade angedockt ist.  
  
 [in] `dwAlignment`  
 `DWORD` die gibt es sich um die Seite des Bereichs ist, an dem der Container angedockt wird.  
  
 [in] `dockMethod`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Container wurde erfolgreich in den Bereich; angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 `dwAlignment` eine der folgenden Werte kann sein:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`CBRS_ALIGN_TOP`|Der Container wird an den Anfang der Bereich angedockt wird.|  
|`CBRS_ALIGN_BOTTOM`|Der Container wird an das Ende der Bereich angedockt wird.|  
|`CBRS_ALIGN_LEFT`|Der Container wird auf der linken Seite des Bereichs angedockt wird.|  
|`CBRS_ALIGN_RIGHT`|Der Container wird rechts neben dem Bereich angedockt wird.|  
  
##  <a name="dockpanestandard"></a>  CDockablePane::DockPaneStandard  
 Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.  
  
```  
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bWasDocked`  
 Wenn die Methode zurückkehrt, enthält dieser Wert `TRUE` war Bereich erfolgreich angedockt, andernfalls enthält er `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Bereich in einem Fenster im Registerkartenformat angedockt wurde, oder wenn ein Fenster im Registerkartenformat aufgrund Andocken erstellt wurde, gibt diese Methode einen Zeiger auf Fenster im Registerkartenformat. Wenn der Bereich andernfalls erfolgreich angedockt war, gibt diese Methode die `this` Zeiger. Wenn das Andocken fehlgeschlagen ist, gibt diese Methode `NULL`.  
  
##  <a name="docktorecentpos"></a>  CDockablePane::DockToRecentPos  
 Dockt einen Bereich auf die gespeicherten verankerten Position an.  
  
```  
BOOL CDockablePane::DockToRecentPos();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich angedockt ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Andockbare Bereiche speichern neuesten andockbaren Informationen in einem [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) Objekt.  
  
##  <a name="docktowindow"></a>  CDockablePane::DockToWindow  
 Dockt einen andockbaren Bereich auf einen anderen andockbaren Bereich an.  
  
```  
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pTargetWindow`  
 Gibt an, andockbaren Bereich um diesem Bereich anzudocken.  
  
 [in] `dwAlignment`  
 Gibt die Ausrichtung des andockbaren Bereich an. Dabei kann es sich um eine CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM oder CBRS_ALIGN_ANY sein. (Definiert in afxres.h).  
  
 [in] `lpRect`  
 Gibt das Andocken Rechteck für den Bereich an.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich in einen anderen Bereich mit der Ausrichtung, angegeben durch Andocken `dwAlignment`.  
  
##  <a name="drawcaption"></a>  CDockablePane::DrawCaption  
 Zeichnet die Beschriftung (auch als ziehelements bezeichnet), der einen andockbaren Bereich an.  
  
```  
virtual void DrawCaption(
    CDC* pDC,  
    CRect rectCaption);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Stellt den Gerätekontext, der zum Zeichnen verwendeten dar.  
  
 [in] `rectCaption`  
 Gibt das umschließende Rechteck der Beschriftung des Bereichs an.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um die Beschriftung des einen andockbaren Bereich zu zeichnen.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Beschriftung.  
  
##  <a name="enableautohideall"></a>  CDockablePane::EnableAutohideAll  
 Aktiviert oder deaktiviert die in den Hintergrundmodus für diesen Bereich und anderen Bereichen im Container.  
  
```  
void EnableAutohideAll(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` die zum automatischen Ausblenden aller Funktion für die andockbaren Bereich aktiviert; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer hält die `Ctrl` Schlüssel und klickt auf die Pin-Schaltfläche, um einen Bereich in den Hintergrundmodus, alle anderen Bereiche im gleichen Container zu wechseln, werden auch in den Hintergrundmodus gewechselt.  
  
 Rufen Sie diese Methode mit `bEnable` festgelegt `FALSE` So deaktivieren Sie dieses Feature für einen bestimmten Bereich.  
  
##  <a name="enablegripper"></a>  CDockablePane::EnableGripper  
 Anzeigen oder ausblenden die Beschriftung (auch als ziehelements bezeichnet).  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` So aktivieren Sie die Beschriftung; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Framework andockbare Bereiche erstellt, sie verfügen nicht über die **WS_STYLE** Fensterstil, selbst wenn angegeben. Dies bedeutet, dass der Bereich Beschriftung ist ein nicht-Clientbereichs, der durch das Framework gesteuert wird, aber dieser Bereich unterscheidet sich von der standardmäßigen fensterbeschriftung.  
  
 Sie können ein- oder ausblenden die Beschriftung zu einem beliebigen Zeitpunkt. Das Framework Blendet die Beschriftung, wenn ein Fenster als Registerkarte hinzugefügt wird, ein Fenster im Registerkartenformat hinzu, oder wenn ein Bereich in einem Minirahmenfenster umfließt ist.  
  
##  <a name="getahrestoredrect"></a>  CDockablePane::GetAHRestoredRect  
 Gibt die Position des Bereichs im automatischen Ausblendemodus.  
  
```  
CRect GetAHRestoredRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` Objekt, das die Position des Bereichs enthält, wenn er im automatischen Ausblendemodus ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getahslidemode"></a>  CDockablePane::GetAHSlideMode  
 Ruft die automatisch ausblendbare Folienmodus für den Bereich ab.  
  
```  
virtual UINT GetAHSlideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `UINT` , die automatisch ausblendbare Folie den für den Bereich angibt. Der Rückgabewert kann entweder `AFX_AHSM_MOVE` oder `AFX_AHSM_STRETCH`, aber die Implementierung verwendet nur `AFX_AHSM_MOVE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcaptionheight"></a>  CDockablePane::GetCaptionHeight  
 Gibt die Höhe des die aktuelle Beschriftung in Pixel zurück.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe der Beschriftung in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Die Überschriftenhöhe ist 0, wenn die Beschriftung von ausgeblendet war die [CDockablePane::EnableGripper](#enablegripper) -Methode, oder wenn der Bereich keine Beschriftung.  
  
##  <a name="getdefaultpanedivider"></a>  CDockablePane::GetDefaultPaneDivider  
 Gibt standardmäßige bereichsteiler für den Bereich Container zurück.  
  
```  
CPaneDivider* GetDefaultPaneDivider() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger [CPaneDivider](../../mfc/reference/cpanedivider-class.md) Objekt ist an das Hauptrahmenfenster andockbare Bereich angedockt oder `NULL` Wenn andockbare Bereich nicht angedockt ist oder wenn es unverankert ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum bereichsteiler, finden Sie unter [CPaneDivider Klasse](../../mfc/reference/cpanedivider-class.md).  
  
##  <a name="getdockingstatus"></a>  CDockablePane::GetDockingStatus  
 Bestimmt die Möglichkeit eines Bereichs angedockt werden auf dem bereitgestellten Zeiger Speicherort basierend.  
  
```  
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,  
    int nSensitivity);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Die Position des Mauszeigers in Bildschirmkoordinaten.  
  
 [in] `nSensitivity`  
 Den Abstand in Pixel Weg von den Rand eines Rechtecks, das muss die Zeiger Andocken aktivieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Statuswerte:  
  
|`AFX_CS_STATUS`-Wert|Bedeutung|  
|---------------------------|-------------|  
|`CS_NOTHING`|Der Zeiger ist nicht über eine docksite. Das Framework ist nicht auf den Bereich anzudocken.|  
|`CS_DOCK_IMMEDIATELY`|Der Zeiger befindet sich über der DockPosition in unmittelbarer Modus (der Bereich wird die `DT_IMMEDIATE` Andockmodus). Das Framework Dockt den Bereich sofort an.|  
|`CS_DELAY_DOCK`|Der Zeiger wird über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe. Das Framework Dockt den Bereich an, nach einer Verzögerung. Finden Sie im Abschnitt "Hinweise" Weitere Informationen über diese Verzögerung.|  
|`CS_DELAY_DOCK_TO_TAB`|Der Zeiger befindet sich über eine docksite, die bewirkt, dass der Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Mauszeiger über die Beschriftung des anderen andockbaren Bereich oder der Registerkartenbereich, der einen Bereich im Registerkartenformat befindet.|  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode zum Behandeln Andocken eines unverankerten angezeigt.  
  
 Unverankerte Symbolleisten oder andockbare Bereiche, mit denen die `DT_IMMEDIATE` Andocken Modus, verzögert das Framework die Dock-Befehl aus, um dem Benutzer ermöglichen, das den Clientbereich des übergeordneten Frames vor dem Andocken tritt auf, das Fenster verschieben. Die Länge der Verzögerung in Millisekunden gemessen und wird gesteuert, indem die [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) -Datenmember... Der Standardwert von [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) liegt bei 200. Dieses Verhalten emuliert das Andockverhalten des [!INCLUDE[ofprword](../../mfc/reference/includes/ofprword_md.md)] 2007.  
  
 Andocken Zustände verzögert ( `CS_DELAY_DOCK` und `CS_DELAY_DOCK_TO_TAB`), das Framework führt keine andocken, bis der Benutzer die Maustaste loslässt. Wenn ein Bereich verwendet die `DT_STANDARD` Andocken Modus vom Framework ein Rechteck an projizierten Andockposition angezeigt. Wenn ein Bereich verwendet die `DT_SMART` Andocken Modus an, das Framework zeigt intelligenten andockmarkern und halbtransparente Rechtecke an projizierten Andockposition. Rufen Sie zum Angeben des Andockmodus für Ihre Bereich der [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) Methode. Weitere Informationen zu intelligentes Andocken, finden Sie unter [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams).  
  
##  <a name="getdragsensitivity"></a>  CDockablePane::GetDragSensitivity  
 Gibt die Vertraulichkeit ziehen Sie einen andockbaren Bereich zurück.  
  
```  
static const CSize& GetDragSensitivity();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die Breite und Höhe in Pixel, eines Rechtecks, dessen Mitte sich an einem Ziehpunkt befindet, enthält. Der Ziehvorgang beginnt nicht bis außerhalb dieses Rechteck der Mauszeiger bewegt wird.  
  
##  <a name="getlastpercentinpanecontainer"></a>  CDockablePane::GetLastPercentInPaneContainer  
 Ruft den Prozentsatz des Speicherplatzes, der ein Bereich in dessen Container belegt ( [CPaneContainer Klasse](../../mfc/reference/cpanecontainer-class.md)).  
  
```  
int GetLastPercentInPaneContainer() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `int` , der den Prozentsatz des Speicherplatzes, der der Bereich in den Container belegt angibt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird verwendet, wenn der Container passt das Layout an.  
  
##  <a name="gettabarea"></a>  CDockablePane::GetTabArea  
 Ruft den Registerkartenbereich für den Bereich ab.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectTabAreaTop`  
 `GetTabArea` füllt diese Variable mit der Registerkartenbereich auf, wenn Registerkarten am oberen Rand des Bereichs befinden. Wenn Registerkarten am unteren Rand des Bereichs befinden, wird diese Variable mit einem leeren Rechteck ausgefüllt.  
  
 [in] `rectTabAreaBottom`  
 `GetTabArea` füllt diese Variable mit der Registerkartenbereich auf, wenn Registerkarten am unteren Rand des Bereichs befinden. Wenn Registerkarten am oberen Rand des Bereichs befinden, wird diese Variable mit einem leeren Rechteck ausgefüllt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird nur in die von der abgeleiteten Klassen verwendet `CDockablePane` und Registerkarten haben. Weitere Informationen finden Sie unter [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) und [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea).  
  
##  <a name="gettabbedpanertc"></a>  CDockablePane::GetTabbedPaneRTC  
 Gibt die laufzeitklasseninformationen über einem Fenster im Registerkartenformat, die erstellt wird, wenn Sie einen anderen Bereich in den aktuellen Bereich angedockt.  
  
```  
CRuntimeClass* GetTabbedPaneRTC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die laufzeitklasseninformationen für den andockbaren Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die laufzeitklasseninformationen für Bereiche im Registerkartenformat abzurufen, die dynamisch erstellt werden. Dies kann auftreten, wenn ein Benutzer einen Bereich auf die Beschriftung eines anderen Bereichs zieht, oder rufen Sie die [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode, um einen Bereich im Registerkartenformat programmgesteuert aus zwei andockbare Bereiche zu erstellen.  
  
 Sie können die Laufzeit-Klasseninformationen festlegen, durch Aufrufen der [CDockablePane:: Settabbedpanertc](#settabbedpanertc) Methode.  
  
##  <a name="hasautohidemode"></a>  CDockablePane::HasAutoHideMode  
 Gibt an, ob ein andockbarer Bereich in den Hintergrundmodus gewechselt werden kann.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich in den Hintergrundmodus gewechselt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse den Hintergrundmodus für einen bestimmten andockbaren Bereich deaktivieren.  
  
##  <a name="hittest"></a>  CDockablePane::HitTest  
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
 `TRUE` Wenn `HTCAPTION` zurückgegeben werden soll, wenn der Punkt auf den Bereich Beschriftung; ist, andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte:  
  
- `HTNOWHERE` Wenn `point` befindet sich nicht im Bereich angedockt.  
  
- `HTCLIENT` Wenn `point` im Clientbereich des andockbaren Bereich ist.  
  
- `HTCAPTION` Wenn `point` andockbaren Bereich im Bereich "Caption" ist.  
  
- `AFX_HTCLOSE` Wenn `point` befindet sich auf die Schaltfläche "Schließen".  
  
- `HTMAXBUTTON` Wenn `point` befindet sich auf die Schaltfläche "Pin".  
  
##  <a name="isautohideallenabled"></a>  CDockablePane::IsAutohideAllEnabled  
 Gibt an, ob die andockbaren Bereich und allen anderen Bereichen im Container in den Hintergrundmodus gewechselt werden können.  
  
```  
virtual BOOL IsAutohideAllEnabled() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbaren Bereich, und alle anderen Bereiche in den Container, in den Hintergrundmodus gewechselt werden können; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Benutzer kann in den Hintergrundmodus andockbaren Pin Klicken bei gedrückter der **STRG** Schlüssel  
  
 Rufen Sie zum Aktivieren oder Deaktivieren dieses Verhalten, die [CDockablePane::EnableAutohideAll](#enableautohideall) Methode.  
  
##  <a name="isautohidemode"></a>  CDockablePane::IsAutoHideMode  
 Bestimmt, ob ein Bereich in den Hintergrundmodus.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich in den Hintergrundmodus ist. andernfalls `FALSE`.  
  
##  <a name="isdocked"></a>  CDockablePane::IsDocked  
 Bestimmt, ob der aktuelle Bereich angedockt ist.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich nicht zu einem Minirahmenfenster gehört oder wenn es in einem Minirahmenfenster mit einem anderen Bereich unverankert ist. `FALSE` Wenn der Bereich ein untergeordnetes Element des ein Minirahmenfenster ist, und es sind keine anderen Bereichen, die zu dem Minirahmenfenster gehören.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen, um zu bestimmen, ob der Bereich, an das Hauptrahmenfenster angedockt ist, [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider). Wenn die Methode einen nicht-NULL-Zeiger zurückgibt, wird der Bereich an das Hauptrahmenfenster angedockt.  
  
##  <a name="ishideinautohidemode"></a>  CDockablePane::IsHideInAutoHideMode  
 Bestimmt das Verhalten eines Bereichs, der in den Hintergrundmodus ist, wenn sie (durch Aufrufen oder ausgeblendet ist) [CDockablePane::ShowPane](#showpane).  
  
```  
virtual BOOL IsHideInAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn andockbare Bereich ausgeblendet werden soll, wenn in den Hintergrundmodus; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein andockbares Fenster in den Hintergrundmodus ist, es verhält sich anders beim Aufruf `ShowPane` ausblenden oder Anzeigen des Bereichs. Dieses Verhalten wird gesteuert, indem Sie den statischen Member [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode). Wenn bei diesem Member handelt `TRUE`, andockbaren Bereich sowie verwandte zum automatischen ausblenden Symbolleiste oder AutoAusblenden-Schaltfläche ausgeblendet oder angezeigt, wenn Sie aufrufen `ShowPane`. Andernfalls andockbare Bereich aktiviert bzw. deaktiviert wird, und der zugehörigen zum automatischen ausblenden Symbolleiste oder AutoAusblenden-Schaltfläche ist immer sichtbar.  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Ändern des Standardverhaltens für einzelne Bereiche.  
  
 Der Standardwert für `m_bHideInAutoHideMode` lautet `FALSE`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CDockablePane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist ( [CMultiPaneFrameWnd Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in einem Multipane-Rahmenfenster ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isresizable"></a>  CDockablePane::IsResizable  
 Gibt an, ob der Bereich geändert wird.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich geändert wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig sind andockbare Bereiche in der Größe veränderbar. Um zu verhindern, Größenänderung, überschreiben Sie diese Methode in einer abgeleiteten Klasse und zurückgeben `FALSE`. Beachten Sie, dass eine `FALSE` Wert führt zu einer fehlerhaften `ASSERT` in [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane). Verwendung [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) stattdessen auf einen Bereich innerhalb eines übergeordneten Frames anzudocken.  
  
 Bereiche, dessen Größe angepasst werden können nicht, können weder float noch automatischen Ausblendemodus eingeben und befinden sich immer am äußeren Rand des übergeordneten Frames.  
  
##  <a name="istablocationbottom"></a>  CDockablePane::IsTabLocationBottom  
 Gibt an, ob die Registerkarten oben oder unten im Bereich befinden.  
  
```  
virtual BOOL IsTabLocationBottom() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Registerkarten am unteren Rand der Bereich befinden; `FALSE` Wenn Registerkarten am oberen Rand des Bereichs befinden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom).  
  
##  <a name="istracked"></a>  CDockablePane::IsTracked  
 Gibt an, ob ein Bereich vom Benutzer verschoben wird.  
  
```  
BOOL IsTracked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich verschoben wird; andernfalls `FALSE`.  
  
##  <a name="isvisible"></a>  CDockablePane::IsVisible  
 Bestimmt, ob der aktuelle Bereich angezeigt wird.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die andockbare Bereich sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zu bestimmen, ob ein andockbares Fenster sichtbar ist. Sie können diese Methode verwenden, statt [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) oder Tests für die `WS_VISIBLE` Stil. Der zurückgegebene Sichtbarkeitszustand hängt von, ob in den Hintergrundmodus aktiviert oder deaktiviert ist und der Wert des der [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) Eigenschaft.  
  
 Wenn der andockbare Bereich in den Hintergrundmodus ist und `IsHideInAutoHideMode` gibt `FALSE` der Sichtbarkeitszustand ist immer `FALSE`.  
  
 Wenn der andockbare Bereich in den Hintergrundmodus ist und `IsHideInAutoHideMode` gibt `TRUE` der Sichtbarkeitszustand hängt von den Sichtbarkeitszustand der zugehörigen zum automatischen ausblenden Symbolleiste.  
  
 Wenn andockbare Bereich nicht in den Hintergrundmodus ist, wird durch der Sichtbarkeitszustand bestimmt die [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) Methode.  
  
##  <a name="m_bdisableanimation"></a>  CDockablePane::m_bDisableAnimation  
 Gibt an, ob die Animation zum automatischen Ausblenden andockbaren Bereich deaktiviert ist.  
  
```  
AFX_IMPORT_DATA static BOOL m_bDisableAnimation;  
```  
  
##  <a name="m_bhideinautohidemode"></a>  CDockablePane::m_bHideInAutoHideMode  
 Bestimmt das Verhalten des Bereichs an, wenn der Bereich in den Hintergrundmodus ist.  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideInAutoHideMode;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert wirkt sich auf alle andockbare Bereiche in der Anwendung.  
  
 Wenn Sie dieses Element, um festlegen `TRUE`, andockbare Bereiche mit ihren zugehörigen Taskleisten Symbolleisten und Schaltflächen angezeigt werden, wenn Sie aufrufen oder ausgeblendet werden [CDockablePane::ShowPane](#showpane).  
  
 Wenn Sie dieses Element, um festlegen `FALSE`, andockbare Bereiche sind aktiviert oder deaktiviert werden, wenn Sie aufrufen [CDockablePane::ShowPane](#showpane).  
  
##  <a name="m_nslidesteps"></a>  CDockablePane::m_nSlideSteps  
 Gibt die animationsgeschwindigkeit des Bereichs an, wenn es in den Hintergrundmodus ist.  
  
```  
AFX_IMPORT_DATA static int m_nSlideSteps;  
```  
  
### <a name="remarks"></a>Hinweise  
 Für eine schnellere Animationseffekt verringern dieses Werts. Erhöhen Sie diesen Wert für eine langsamere Animationseffekt.  
  
##  <a name="onafterchangeparent"></a>  CDockablePane::OnAfterChangeParent  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndOldParent`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onafterdockfromminiframe"></a>  CDockablePane::OnAfterDockFromMiniFrame  
 Vom Framework aufgerufen, wenn eine Gleitkommazahl andockleiste an ein Framefenster angedockt.  
  
```  
virtual void OnAfterDockFromMiniFrame();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Methode keine Aktion ausgeführt.  
  
##  <a name="onbeforechangeparent"></a>  CDockablePane::OnBeforeChangeParent  
 Das Framework ruft diese Methode auf, bevor das übergeordnete Element des Bereichs geändert.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndNewParent`  
 Ein Zeiger auf das neue übergeordnete Fenster.  
  
 [in] `bDelay`  
 `BOOL` die angibt, ob eine neuberechnung der am Layout Docks zu verzögern, wenn der Bereich nicht in der Dockingstation ist. Weitere Informationen finden Sie unter [CDockablePane::UndockPane](#undockpane).  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich angedockt ist und das neue übergeordnete Element lässt keine andocken, wird diese Methode im Bereich abgedockt.  
  
 Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert wird, speichert diese Methode die aktuelle verankerten Position an. Das Framework verwendet die letzte verankerten Position, um die Position des Bereichs wiederherstellen, wenn es wieder in einem angedockten Zustand konvertiert wird.  
  
##  <a name="onbeforefloat"></a>  CDockablePane::OnBeforeFloat  
 Das Framework ruft diese Methode vor einem Bereich Übergänge in einen unverankerten Zustand.  
  
```  
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt die Position und Größe des Bereichs an, wenn es in einen unverankerten Zustand ist.  
  
 [in] `dockMethod`  
 Gibt die Andock-Methode. Finden Sie unter [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) eine Liste der möglichen Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich umfließt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn ein Bereich zu "float" ist. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn Verarbeitungsschritte auszuführen, bevor Bereich wird verschoben werden sollen.  
  
##  <a name="onpressbuttons"></a>  CDockablePane::OnPressButtons  
 Wird aufgerufen, wenn der Benutzer eine Beschriftung außer drückt die `AFX_HTCLOSE` und `AFX_HTMAXBUTTON` Schaltflächen.  
  
```  
virtual void OnPressButtons(UINT nHit);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nHit`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie eine benutzerdefinierte Schaltfläche, die Beschriftung des einen andockbaren Bereich hinzufügen, überschreiben Sie diese Methode, um Benachrichtigungen zu erhalten, wenn ein Benutzer die Schaltfläche drückt.  
  
##  <a name="onslide"></a>  CDockablePane::OnSlide  
 Vom Framework aufgerufen, die im Bereich dem animiert werden soll, wenn es in den Hintergrundmodus ist.  
  
```  
virtual void OnSlide(BOOL bSlideOut);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSlideOut`  
 `TRUE` um den Bereich anzuzeigen; `FALSE` So blenden Sie den Bereich aus.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten Taskleisten Auswirkungen.  
  
##  <a name="removefromdefaultpanedividier"></a>  CDockablePane::RemoveFromDefaultPaneDividier  
 Das Framework ruft diese Methode auf, wenn ein Bereichs abgedockten wird ist.  
  
```  
void RemoveFromDefaultPaneDividier();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die Standard-bereichsteiler auf `NULL` und den Bereich aus dem zugehörigen Container entfernt.  
  
##  <a name="replacepane"></a>  CDockablePane::ReplacePane  
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
 Wenn `TRUE`, der neue Bereich wird beim Dock-Manager des übergeordneten Elements des alten Bereichs registriert. Der neue Bereich wird am Index aus der alten Bereich in der Liste der Bereiche eingefügt, die mit Dock-Manager verwaltet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Austausch erfolgreich war; andernfalls `FALSE`.  
  
##  <a name="restoredefaultpanedivider"></a>  CDockablePane::RestoreDefaultPaneDivider  
 Wenn ein Bereich deserialisiert wird, ruft das Framework diese Methode, um die Standard-bereichsteiler wiederherstellen.  
  
```  
void RestoreDefaultPaneDivider();
```  
  
### <a name="remarks"></a>Hinweise  
 Bereichsteiler wiederhergestellten ersetzt der aktuellen Standardeinstellung bereichsteiler, falls vorhanden.  
  
##  <a name="setautohidemode"></a>  CDockablePane::SetAutoHideMode  
 Schaltet die andockbaren Bereich zwischen sichtbar und in den Hintergrundmodus.  
  
```  
virtual CMFCAutoHideBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMode`  
 `TRUE` So aktivieren Sie in den Hintergrundmodus; `FALSE` reguläre Andockmodus zu aktivieren.  
  
 [in] `dwAlignment`  
 Gibt die Ausrichtung des Bereichs "automatisch ausblenden" zu erstellen.  
  
 [in] [out] `pCurrAutoHideBar`  
 Ein Zeiger auf der Symbolleiste des aktuellen zum automatischen ausblenden. Kann `NULL`.  
  
 [in] `bUseTimer`  
 Gibt an, ob den Effekt zum automatischen Ausblenden verwenden, wenn der Benutzer im Bereich in den Hintergrundmodus gewechselt wird oder sofort Ausblenden des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Automatisches Ausblenden Symbolleiste, die aufgrund der Wechsel in den Hintergrundmodus, erstellt wurde oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode klickt ein Benutzer die Pin-Schaltfläche, um die andockbaren Bereich in den Hintergrundmodus bzw. zu regulären Andockmodus gewechselt werden.  
  
 Rufen Sie diese Methode, um ein andockbares Fenster in den Hintergrundmodus programmgesteuert zu wechseln. Der Bereich angedockt werden muss, an das Hauptrahmenfenster ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) muss einen gültigen Zeiger auf Zurückgeben der [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
##  <a name="setautohideparents"></a>  CDockablePane::SetAutoHideParents  
 Die Schaltfläche zum automatischen Ausblenden und automatisch im Hintergrund-Symbolleiste für den Bereich festgelegt.  
  
```  
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,  
    CMFCAutoHideButton* pBtn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pToolBar`  
 Ein Zeiger auf eine Symbolleiste automatisch im Hintergrund.  
  
 [in] `pBtn`  
 Ein Zeiger auf eine Schaltfläche zum automatischen ausblenden.  
  
##  <a name="setlastpercentinpanecontainer"></a>  CDockablePane::SetLastPercentInPaneContainer  
 Bestimmt den Prozentsatz des Speicherplatzes, der ein Bereich im Container einnimmt.  
  
```  
void SetLastPercentInPaneContainer(int n);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `n`  
 Ein `int` , der den Prozentsatz des Speicherplatzes, der der Bereich in den Container belegt angibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework passt den Bereich, um den neuen Wert übernehmen, wenn das Layout neu berechnet wird.  
  
##  <a name="setrestoreddefaultpanedivider"></a>  CDockablePane::SetRestoredDefaultPaneDivider  
 Legt die wiederhergestellten bereichsteiler fest.  
  
```  
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hRestoredSlider`  
 Ein Handle für einen bereichsteiler (Schieberegler).  
  
### <a name="remarks"></a>Hinweise  
 Ein bereichsteiler wiederhergestellten abgerufen wird, wenn ein Bereich deserialisiert wird. Weitere Informationen finden Sie unter [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider).  
  
##  <a name="settabbedpanertc"></a>  CDockablePane:: Settabbedpanertc  
 Legt die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, die erstellt wird, wenn zwei Bereiche zusammen docken fest.  
  
```  
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRTC`  
 Die laufzeitklasseninformationen für den Bereich im Registerkartenformat.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die laufzeitklasseninformationen für Bereiche im Registerkartenformat festlegen, die dynamisch erstellt werden. Dies kann auftreten, wenn ein Benutzer einen Bereich auf die Beschriftung eines anderen Bereichs zieht, oder rufen Sie die [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode, um einen Bereich im Registerkartenformat programmgesteuert aus zwei andockbare Bereiche zu erstellen.  
  
 Die Standardklasse für die Common Language Runtime festgelegt ist, entsprechend der `dwTabbedStyle` Parameter [CDockablePane::Create](#create) und [CDockablePane:: CreateEx](#createex). Um die neuen Bereiche im Registerkartenformat anzupassen, leiten Sie eine Klasse von einer der folgenden Klassen:  
  
- [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)  
  
- [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md)  
  
- [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Rufen Sie dann diese Methode mit dem Zeiger auf die laufzeitklasseninformationen.  
  
##  <a name="showpane"></a>  CDockablePane::ShowPane  
 Anzeigen oder ausblenden ein Bereichs.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 `TRUE` um den Bereich anzuzeigen; `FALSE` So blenden Sie den Bereich aus.  
  
 [in] `bDelay`  
 `TRUE` verzögern Sie am Layout des Docks anpassen; `FALSE` am Layout des Docks unmittelbar anpassen.  
  
 [in] `bActivate`  
 `TRUE` So aktivieren Sie den Bereich, wenn Sie angezeigt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode anstelle der [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) beim ein- bzw. ausblenden andockbare Bereiche.  
  
##  <a name="slide"></a>  CDockablePane::Slide  
 Erstellt eine Animation einen Bereich, der in den Hintergrundmodus ist.  
  
```  
virtual void Slide(
    BOOL bSlideOut,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSlideOut`  
 `TRUE` um den Bereich anzuzeigen; `FALSE` So blenden Sie den Bereich aus.  
  
 [in] `bUseTimer`  
 `TRUE` ein-oder Ausblenden des Bereichs mit dem Taskleisten Effekt; `FALSE` ein-oder Ausblenden des Bereichs sofort.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um einen Bereich zu animieren, der in den Hintergrundmodus ist.  
  
 Diese Methode verwendet die `CDockablePane::m_nSlideDefaultTimeOut` um das Timeout für die Abrolleffekt zu bestimmen. Der Standardwert für das Timeout ist 1. Wenn Sie den Algorithmus zum automatischen Ausblenden anpassen, ändern Sie dieses Element aus, um das Timeout zu ändern.  
  
##  <a name="toggleautohide"></a>  CDockablePane::ToggleAutoHide  
 Schaltet den Bereich zwischen immer sichtbar und den automatischen Ausblendemodus.  
  
```  
virtual void ToggleAutoHide();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schaltet automatischen Ausblendemodus für den Bereich durch Aufrufen von [CDockablePane::SetAutoHideMode](#setautohidemode).  
  
##  <a name="undockpane"></a>  CDockablePane::UndockPane  
 Dockt einen Bereich von Hauptrahmenfenster oder Miniframe Fenster Container an.  
  
```  
virtual void UndockPane(BOOL bDelay = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bDelay`  
 `TRUE` verzögert die Berechnung am Layouts des Docks; `FALSE` am Layout des Docks sofort neu zu berechnen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich von Hauptrahmenfenster oder einen Container für Multi-Miniframe-Fenster (ein Bereich, der in einer einzelnen Minirahmenfenster mit anderen Bereichen unverankert ist) die Verankerung aufheben.  
  
 Sie müssen einen Bereich abdocken, vor dem Ausführen von eines externen Vorgangs, die nicht von ausgeführt werden die [CDockingManager](../../mfc/reference/cdockingmanager-class.md). Beispielsweise müssen Sie einen Bereich zu verschieben programmgesteuert von einem Speicherort zu einem anderen Verankerung aufheben.  
  
 Das Framework wird abgedockt automatisch auf die Bereiche aus, bevor sie zerstört werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane-Klasse](../../mfc/reference/cpane-class.md)
