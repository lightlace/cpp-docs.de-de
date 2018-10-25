---
title: CDockablePane-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
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
ms.openlocfilehash: 91058da47a97098826939be2248d81ba657f3cbb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078309"
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
|[CDockablePane:: Attachtotabwnd](#attachtotabwnd)|Fügt einen Bereich in einen anderen Bereich. Dadurch wird ein Fenster mit Registerkarten erstellt.|
|[CDockablePane::CalcFixedLayout](#calcfixedlayout)|Gibt die Größe des Rechtecks im Bereich zurück.|
|[CDockablePane::CanAcceptMiniFrame](#canacceptminiframe)|Bestimmt, ob der angegebene Mini-Frame in den Bereich angedockt werden kann.|
|[CDockablePane::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein weiterer Bereich, in den aktuellen Bereich angedockt werden kann.|
|[CDockablePane::CanAutoHide](#canautohide)|Bestimmt, ob der Bereich automatisch ausblendbaren-Modus unterstützt. (Überschreibt [CBasePane::CanAutoHide](../../mfc/reference/cbasepane-class.md#canautohide).)|
|[CDockablePane::CanBeAttached](#canbeattached)|Bestimmt, ob der aktuelle Bereich in einen anderen Bereich angedockt werden kann.|
|[CDockablePane::ConvertToTabbedDocument](#converttotabbeddocument)|Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten.|
|[CDockablePane::CopyState](#copystate)|Kopiert den Zustand des einen andockbaren Bereich an.|
|[CDockablePane::Create](#create)|Erstellt die Windows-Steuerelement, und fügt es der `CDockablePane` Objekt.|
|[CDockablePane::CreateDefaultPaneDivider](#createdefaultpanedivider)|Erstellt einen Unterteiler Standardwert für den Bereich an, wie es um ein Framefenster angedockt wird.|
|[CDockablePane:: CreateEx](#createex)|Erstellt die Windows-Steuerelement, und fügt es der `CDockablePane` Objekt.|
|[CDockablePane::CreateTabbedPane](#createtabbedpane)|Erstellt einen Bereich im Registerkartenformat im aktuellen Bereich.|
|[CDockablePane::DockPaneContainer](#dockpanecontainer)|Dockt einen Container in den Bereich an.|
|[CDockablePane::DockPaneStandard](#dockpanestandard)|Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.|
|`CDockablePane::DockToFrameWindow`|Wird intern verwendet. Verwenden Sie einen Bereich für das Andocken [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) oder [CDockablePane::DockToWindow](#docktowindow).|
|[CDockablePane::DockToRecentPos](#docktorecentpos)|Dockt einen Bereich auf die aktuelle gespeicherte dockingposition an.|
|[CDockablePane::DockToWindow](#docktowindow)|Dockt einen andockbaren Bereich auf einen anderen andockbaren Bereich an.|
|[CDockablePane::EnableAutohideAll](#enableautohideall)|Aktiviert oder deaktiviert die automatischen Ausblendemodus für diesen Bereich zusammen mit anderen Bereichen im Container.|
|[CDockablePane::EnableGripper](#enablegripper)|Anzeigen oder ausblenden die Beschriftung (Ziehpunkt).|
|[CDockablePane::GetAHRestoredRect](#getahrestoredrect)|Gibt die Position des Bereichs, wenn im Modus "automatisch ausblenden" angezeigt.|
|[CDockablePane::GetAHSlideMode](#getahslidemode)|Ruft die Auto-Modus zum Folie ausblenden für den Bereich ab.|
|`CDockablePane::GetAutoHideButton`|Wird intern verwendet.|
|`CDockablePane::GetAutoHideToolBar`|Wird intern verwendet.|
|[CDockablePane::GetCaptionHeight](#getcaptionheight)|Gibt die Höhe des die aktuelle Beschriftung zurück.|
|[CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider)|Gibt standardmäßige bereichsteiler für den Bereich des Containers zurück.|
|[CDockablePane::GetDockingStatus](#getdockingstatus)|Bestimmt, ob die Möglichkeit, einen Bereich angedockt werden abhängig von der angegebenen Position.|
|[CDockablePane::GetDragSensitivity](#getdragsensitivity)|Gibt die Vertraulichkeit ziehen Sie einen andockbaren Bereich zurück.|
|[CDockablePane::GetLastPercentInPaneContainer](#getlastpercentinpanecontainer)|Ruft den Prozentsatz des Speicherplatzes, die ein Bereich, in dessen Container belegt ab.|
|[CDockablePane::GetTabArea](#gettabarea)|Ruft den Registerkartenbereich für den Bereich.|
|[CDockablePane::GetTabbedPaneRTC](#gettabbedpanertc)|Gibt zurück, die laufzeitklasseninformationen zu einem Fenster im Registerkartenformat, die erstellt wird, wenn ein weiterer Bereich in den aktuellen Bereich angedockt.|
|[CDockablePane::HasAutoHideMode](#hasautohidemode)|Gibt an, ob ein andockbarer Bereich, den Modus "automatisch ausblenden" umgeschaltet werden kann.|
|[CDockablePane::HitTest](#hittest)|Gibt die bestimmte Position in einem Bereich, in denen der Benutzer die Maus klickt.|
|`CDockablePane::IsAccessibilityCompatible`|Wird intern verwendet.|
|[CDockablePane::IsAutohideAllEnabled](#isautohideallenabled)|Gibt an, ob die andockbaren Bereich, und alle anderen Bereiche in den Container im Modus "automatisch ausblenden" platziert werden können.|
|[CDockablePane::IsAutoHideMode](#isautohidemode)|Bestimmt, ob ein Bereich im Modus "automatisch ausblenden".|
|`CDockablePane::IsChangeState`|Wird intern verwendet.|
|[CDockablePane::IsDocked](#isdocked)|Bestimmt, ob der aktuelle Bereich angedockt ist.|
|[CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode)|Bestimmt das Verhalten eines Bereichs, der im Modus "automatisch ausblenden" ist, wenn sie (durch Aufrufen von ein- oder ausgeblendet ist) `ShowPane`.|
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist.|
|[CDockablePane::IsResizable](#isresizable)|Gibt an, ob der Bereich geändert werden kann.|
|[CDockablePane::IsTabLocationBottom](#istablocationbottom)|Gibt an, ob die Registerkarten oben oder unteren Rand des Bereichs befinden.|
|[CDockablePane::IsTracked](#istracked)|Gibt an, ob ein Bereich vom Benutzer gezogen wird.|
|[CDockablePane::IsVisible](#isvisible)|Bestimmt, ob der aktuelle Bereich angezeigt wird.|
|[CDockablePane:: LoadState](#loadstate)|Wird intern verwendet.|
|[CDockablePane::OnAfterChangeParent](#onafterchangeparent)|Wird vom Framework aufgerufen, wenn das übergeordnete Element eines Bereichs geändert wurde. (Überschreibt [CPane::OnAfterChangeParent](../../mfc/reference/cpane-class.md#onafterchangeparent).)|
|[CDockablePane::OnAfterDockFromMiniFrame](#onafterdockfromminiframe)|Vom Framework aufgerufen, wenn eine unverankerte andockleiste an ein Framefenster angedockt.|
|[CDockablePane::OnBeforeChangeParent](#onbeforechangeparent)|Vom Framework aufgerufen, wenn das übergeordnete Element des Bereichs geändert wird. (Überschreibt [CPane::OnBeforeChangeParent](../../mfc/reference/cpane-class.md#onbeforechangeparent).)|
|[CDockablePane::OnBeforeFloat](#onbeforefloat)|Vom Framework aufgerufen, wenn ein Bereich, der auf "float" geht. (Überschreibt [CPane::OnBeforeFloat](../../mfc/reference/cpane-class.md#onbeforefloat).)|
|[CDockablePane:: removefromdefaultpanedividier wurde](#removefromdefaultpanedividier)|Das Framework ruft diese Methode auf, wenn ein Bereich wird abgedockt wird.|
|[CDockablePane::ReplacePane](#replacepane)|Ersetzt den Bereich mit einem angegebenen Bereich.|
|[CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider)|Das Framework ruft diese Methode auf, wenn ein Bereich zum Wiederherstellen der Standard-bereichsteiler deserialisiert wird.|
|`CDockablePane::SaveState`|Wird intern verwendet.|
|`CDockablePane::Serialize`|Serialisiert den Bereich an. (Überschreibt `CBasePane::Serialize`.)|
|[CDockablePane::SetAutoHideMode](#setautohidemode)|Schaltet die andockbaren Bereich zwischen sichtbar und automatischen Ausblendemodus.|
|[CDockablePane::SetAutoHideParents](#setautohideparents)|Legt fest, der automatisch ausblendbaren Schaltfläche und der automatisch ausblendbaren-Symbolleiste für den Bereich.|
|`CDockablePane::SetDefaultPaneDivider`|Wird intern verwendet.|
|[CDockablePane::SetLastPercentInPaneContainer](#setlastpercentinpanecontainer)|Bestimmt den Prozentsatz des Speicherplatzes, der ein Bereich in dessen Container einnimmt.|
|`CDockablePane::SetResizeMode`|Wird intern verwendet.|
|[CDockablePane::SetRestoredDefaultPaneDivider](#setrestoreddefaultpanedivider)|Wird die wiederhergestellte Standard Trennlinie.|
|[CDockablePane:: Settabbedpanertc](#settabbedpanertc)|Legt die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, die erstellt wird, wenn zwei Bereiche zusammen docken fest.|
|[CDockablePane::ShowPane](#showpane)|Anzeigen oder ausblenden ein Bereichs.|
|[CDockablePane::Slide](#slide)|Anzeigen oder ausblenden ein Bereichs mit einem gleitenden Animation aus, die angezeigt wird, nur, wenn der Bereich in den Modus "automatisch ausblenden" ist.|
|[CDockablePane::ToggleAutoHide](#toggleautohide)|Schaltet automatischen Ausblendemodus. (Überschreibt [CPane::ToggleAutoHide](../../mfc/reference/cpane-class.md#toggleautohide) .)|
|[CDockablePane::UndockPane](#undockpane)|Dockt einen Bereich von Hauptrahmenfenster oder einen Benutzer im Fenster-Container.|
|`CDockablePane::UnSetAutoHideMode`|Wird intern verwendet. Verwenden Sie zum Festlegen der automatischen Ausblendemodus [CDockablePane::SetAutoHideMode](#setautohidemode)|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDockablePane::CheckAutoHideCondition](#checkautohidecondition)|Bestimmt, ob die andockbare Bereich (im Modus "automatisch ausblenden") ausgeblendet ist.|
|[CDockablePane::CheckStopSlideCondition](#checkstopslidecondition)|Bestimmt, wann ein andockbarer Bereich der automatisch ausblendbaren gleitendes beendet werden soll.|
|[CDockablePane::DrawCaption](#drawcaption)|Zeichnet die andockbaren Bereich Beschriftung (Ziehpunkt) an.|
|[CDockablePane::OnPressButtons](#onpressbuttons)|Wird aufgerufen, wenn der Benutzer mit Ausnahme der Schaltflächen AFX_HTCLOSE und AFX_HTMAXBUTTON eine Titelleisten-Schaltfläche drückt.|
|[CDockablePane::OnSlide](#onslide)|Vom Framework aufgerufen, der automatisch ausblendbaren Abrolleffekt gerendert werden soll, wenn der Bereich entweder ein- oder ausgeblendet ist.|

### <a name="data-members"></a>Datenmember

|name|Beschreibung|
|----------|-----------------|
|[CDockablePane::m_bDisableAnimation](#m_bdisableanimation)|Gibt an, ob der automatisch ausblendbaren Animation andockbaren Bereich deaktiviert ist.|
|[CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode)|Bestimmt das Verhalten des Bereichs an, wenn der Bereich in den Modus "automatisch ausblenden" ist.|
|[CDockablePane::m_nSlideSteps](#m_nslidesteps)|Gibt die Geschwindigkeit der Animation des Bereichs an, wenn es gerade angezeigt oder ausgeblendet wird, im Modus "automatisch ausblenden".|

## <a name="remarks"></a>Hinweise

`CDockablePane` implementiert die folgende Funktionen:

- Einen Bereich andocken ein Hauptrahmenfenster.

- Wechseln zum automatischen Ausblendemodus einen Bereich.

- Anfügen eines Bereichs einem Fenster im Registerkartenformat.

- Gleitkommatyp in einem Minirahmenfenster in einen Bereich.

- Andocken eines Bereichs in einen anderen Bereich, der in einem Minirahmenfenster unverankert ist.

- Ändern der Größe eines Bereichs.

- Laden und Speichern des Zustands für einen andockbaren Bereich.

    > [!NOTE]
    >  Zustandsinformationen wird in der Windows-Registrierung gespeichert.

- Erstellen einen Bereich mit oder ohne eine Beschriftung. Die Beschriftung kann eine textbezeichnung und sie können mit einem Farbverlauf gefüllt werden.

- Ziehen einen Bereich beim Anzeigen des Inhalts des Bereichs

- Ziehen einen Bereich beim Anzeigen eines Rechtecks ziehen Sie aus.

Um einen andockbaren Bereich in Ihrer Anwendung zu verwenden, leiten Sie eine Klasse im Bereich von der `CDockablePane` Klasse. Betten Sie entweder das abgeleitete Objekt, in die Hauptframe-Window-Objekt oder ein Window-Objekt, das die Instanz von Ihr Bereich steuert. Rufen Sie dann die [CDockablePane::Create](#create) Methode oder der [CDockablePane:: CreateEx](#createex) Methode, wenn Sie die WM_CREATE-Meldung in das Hauptrahmenfenster verarbeiten. Richten Sie das Objekt im Bereich durch den Aufruf [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking), [cbasepane:: Dockpane](../../mfc/reference/cbasepane-class.md#dockpane), oder [CDockablePane:: Attachtotabwnd](#attachtotabwnd).

## <a name="customization-tips"></a>Anpassungstipps

Die folgenden Tipps beziehen sich auf `CDockablePane` Objekte:

- Wenn Sie aufrufen [CDockablePane:: Attachtotabwnd](#attachtotabwnd) für zwei nicht im Registerkartenformat, andockbare Bereiche, wird ein Zeiger auf ein Fenster im Registerkartenformat zurückgegeben werden die *PpTabbedControlBar* Parameter. Sie können weiterhin auf Registerkarten Fenster im Registerkartenformat hinzufügen, indem Sie mithilfe dieses Parameters.

- Die Art der Bereich im Registerkartenformat von erstellt wird [CDockablePane:: Attachtotabwnd](#attachtotabwnd) richtet sich nach der `CDockablePane` -Objekt in der *pTabControlBarAttachTo* Parameter. Rufen Sie [CDockablePane:: Settabbedpanertc](#settabbedpanertc) auf der Art der Bereich im Registerkartenformat festlegen, die die `CDockablePane` erstellt. Der Standardtyp richtet sich nach der `dwTabbedStyle` von [CDockablePane::Create](#create) beim ersten Erstellen der `CDockablePane`. Wenn *DwTabbedStyle* ist der Standardtyp ist AFX_CBRS_OUTLOOK_TABS [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md); Wenn *DwTabbedStyle* AFX_CBRS_REGULAR_TABS der Standardtyp ist [ CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md).

- Wenn Sie einen andockbaren Bereich in eine andere andocken möchten, rufen Sie die [CDockablePane::DockToWindow](#docktowindow) Methode. An einer Stelle muss im ursprüngliche Bereich angedockt sein, bevor Sie diese Methode aufrufen.

- Die Membervariable [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode) Verhalten von andockbare Bereiche in Automatisches Ausblenden von Steuerelementen Modus beim Aufrufen [CDockablePane::ShowPane](#showpane). Wenn diese Membervariable auf "true" festgelegt ist, werden andockbare Bereiche sowie die Auto-ausblenden-Schaltflächen ausgeblendet. Andernfalls werden sie ein-und schieben.

- Sie können automatisch ausblendbaren Animation deaktivieren, indem die [CDockablePane::m_bDisableAnimation](#m_bdisableanimation) Membervariable auf "true".

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie konfigurieren eine `CDockablePane` -Objekt unter Verwendung verschiedener Methoden in der `CDockablePane` Klasse. Das Beispiel veranschaulicht, wie Sie der automatisch ausblendbaren alle Feature für den andockbaren Bereich aktivieren, aktivieren Sie die Beschriftung oder die Ziehpunkte, aktivieren den automatischen Ausblendemodus, des Bereichs und animieren einen Bereich, der im Modus "automatisch ausblenden" befindet. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).

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

Fügt den aktuellen Bereich an ein Zielbereich, und erstellen einen Bereich im Registerkartenformat an.

```
virtual CDockablePane* AttachToTabWnd(
    CDockablePane* pTabControlBarAttachTo,
    AFX_DOCK_METHOD dockMethod,
    BOOL bSetActive= TRUE,
    CDockablePane** ppTabbedControlBar = NULL);
```

### <a name="parameters"></a>Parameter

*pTabControlBarAttachTo*<br/>
[in, out] Gibt den Bereich "Ziel", dem im aktuelle Bereich an anfügt. Der Bereich "Ziel" muss es sich um einen andockbaren Bereich sein.

*dockMethod*<br/>
[in] Gibt die docking-Methode.

*bSetActive*<br/>
[in] True, um den Bereich im Registerkartenformat zu aktivieren, nachdem der Anfügevorgang. andernfalls "false".

*ppTabbedControlBar*<br/>
[out] Enthält der Bereich im Registerkartenformat, die durch den Anfügevorgang entsteht.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den aktuellen Bereich, wenn es sich nicht um einen Bereich im Registerkartenformat ist; andernfalls ein Zeiger auf den Bereich im Registerkartenformat, die durch den Anfügevorgang entsteht. Der Rückgabewert ist NULL, wenn im aktuelle Bereich kann nicht angefügt werden, oder wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Wenn zu einem anderen Bereich, die mit dieser Methode einen andockbaren Bereich angefügt wird, geschieht Folgendes:

1. Die Framework-sicherheitsüberprüfungen, ob der Bereich "Ziel" *pTabControlBarAttachTo* ist eine reguläre andocken, Bereich, oder wenn es von abgeleitet ist [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md).

1. Wenn der Bereich "Ziel" einen Bereich im Registerkartenformat ist, fügt das Framework im aktuellen Bereich darauf als Registerkarte an.

1. Wenn der Bereich "Ziel" einen regulären andockbaren Bereich ist, erstellt das Framework einen Bereich im Registerkartenformat.

   - Das Framework ruft `pTabControlBarAttachTo->CreateTabbedPane`. Hängt von die Darstellung der neue Bereich im Registerkartenformat der `m_pTabbedControlBarRTC` Member. Standardmäßig ist dieser Member in der Common Language Runtime-Klasse des festgelegt [CTabbedPane](../../mfc/reference/ctabbedpane-class.md). Wenn Sie den Stil AFX_CBRS_OUTLOOK_TABS als übergeben die *DwTabbedStyle* Parameter, um die [CDockablePane::Create](#create) -Methode, das Laufzeitobjekt für die Klasse wird festgelegt, auf die Common Language Runtime-Klasse des [ CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md). Sie können diesen Member zu einem beliebigen Zeitpunkt so ändern Sie das Format des neuen Bereichs ändern.

   - Wenn diese Methode einen Bereich im Registerkartenformat erstellt, ersetzt das Framework den Zeiger auf *pTabControlBarAttachTo* (wenn der Bereich in einem Multi-Benutzer-Fenster angedockt oder unverankert ist) mit einem Zeiger auf den neuen Bereich im Registerkartenformat.

   - Das Framework fügt der *pTabControlBarAttachTo* Bereich, um den Bereich im Registerkartenformat als erste Registerkarte. Das Framework fügt dann im aktuellen Bereich als eine zweite Registerkarte hinzu.

1. Wenn im aktuelle Bereich von abgeleitet ist `CBaseTabbedPane`, werden alle Registerkarten in verschoben *pTabControlBarAttachTo* und im aktuelle Bereich zerstört wird. Aus diesem Grund vorsichtig sein, wenn Sie diese Methode aufrufen, da ein Zeiger auf den aktuellen Bereich ungültig sein kann, wenn die Methode zurückgegeben.

Wenn Sie einen Bereich in einen anderen anfügen, wenn ein docking-Layout erstellen, legen Sie `dockMethod` zu DM_SHOW.

Sie sollten den ersten Bereich andocken, bevor Sie einen anderen Bereich anfügen.

##  <a name="calcfixedlayout"></a>  CDockablePane::CalcFixedLayout

Gibt die Größe des Rechtecks im Bereich zurück.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*bStretch*<br/>
[in] Nicht verwendet.

*bHorz*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Ein `CSize` Objekt, das die Größe des Rechtecks im Bereich enthält.

##  <a name="canacceptminiframe"></a>  CDockablePane::CanAcceptMiniFrame

Bestimmt, ob der angegebene Minirahmenfensters in den Bereich angedockt werden kann.

```
virtual BOOL CanAcceptMiniFrame(CPaneFrameWnd* pMiniFrame) const;
```

### <a name="parameters"></a>Parameter

*pMiniFrame*<br/>
[in] Zeiger auf eine `CPaneFrameWnd` Objekt.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn *pMiniFrame* möglich in den Bereich angedockt ist, andernfalls "false".

##  <a name="canacceptpane"></a>  CDockablePane::CanAcceptPane

Bestimmt, ob ein weiterer Bereich, in den aktuellen Bereich angedockt werden kann.

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
[in] Gibt den Bereich, um den aktuellen Bereich angedockt.

### <a name="return-value"></a>Rückgabewert

True, wenn der angegebene Bereich in diesen Bereich angedockt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, bevor Sie ein Bereich in den aktuellen Bereich angedockt ist.

Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren auf einen bestimmten Bereich andocken.

Standardmäßig diese Methode gibt TRUE zurück, wenn entweder *pBar* oder das übergeordnete Element ist vom Typ `CDockablePane`.

##  <a name="canautohide"></a>  CDockablePane::CanAutoHide

Bestimmt, ob der Bereich automatisch ausblenden kann.

```
virtual BOOL CanAutoHide() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Bereich automatisch im Hintergrund kann; andernfalls "false".

### <a name="remarks"></a>Hinweise

`CDockablePane::CanAutoHide` "false" werden in den folgenden Situationen zurückgegeben:

- Im Bereich besitzt kein übergeordnetes Element.

- Dock-Manager lässt sich nicht auf Bereiche, zum automatischen Ausblenden aus.

- Der Bereich wird nicht angedockt.

##  <a name="canbeattached"></a>  CDockablePane::CanBeAttached

Bestimmt, ob der aktuelle Bereich in einen anderen Bereich angedockt werden kann.

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich in einen anderen Bereich oder an das Hauptrahmenfenster angedockt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Standardmäßig gibt diese Methode immer "true" zurück. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren, ohne Andocken [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).

##  <a name="cdockablepane"></a>  CDockablePane::CDockablePane

Erstellt und initialisiert ein [CDockablePane](../../mfc/reference/cdockablepane-class.md) Objekt.

```
CDockablePane();
```

### <a name="remarks"></a>Hinweise

Nachdem Sie einen andockbaren Bereich-Objekt erstellen, rufen [CDockablePane::Create](#create) oder [CDockablePane:: CreateEx](#createex) , ihn zu erstellen.

##  <a name="converttotabbeddocument"></a>  CDockablePane::ConvertToTabbedDocument

Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Parameter

*bActiveTabOnly*<br/>
[in] Bei der Konvertierung einer `CTabbedPane`, geben Sie "true", um nur die aktive Registerkarte zu konvertieren. Geben Sie "false", um alle Registerkarten in den Bereich zu konvertieren.

##  <a name="checkautohidecondition"></a>  CDockablePane::CheckAutoHideCondition

Bestimmt, ob die andockbare Bereich ausgeblendet ist (auch als in den Hintergrundmodus bezeichnet).

```
virtual BOOL CheckAutoHideCondition();
```

### <a name="return-value"></a>Rückgabewert

True, wenn die ausblenden Bedingung erfüllt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Framework verwendet einen Timer, um in regelmäßigen Abständen überprüfen, ob einen Automatisches Ausblenden andockbaren Bereich ausgeblendet. Die Methode gibt TRUE zurück, wenn der Bereich nicht aktiv ist, im Bereich nicht geändert werden und der Mauszeiger befindet sich nicht über den Bereich.

Wenn alle Bedingungen erfüllt sind, um das Framework ruft [CDockablePane::Slide](#slide) Bereich ausgeblendet.

##  <a name="checkstopslidecondition"></a>  CDockablePane::CheckStopSlideCondition

Bestimmt, wenn ein Automatisches Ausblenden andockbaren Bereich gleitend beendet werden soll.

```
virtual BOOL CheckStopSlideCondition(BOOL bDirection);
```

### <a name="parameters"></a>Parameter

*bDirection*<br/>
[in] True, wenn der Bereich angezeigt wird. "False", wenn der Bereich ausgeblendet ist.

### <a name="return-value"></a>Rückgabewert

True, wenn die beenden-Bedingung erfüllt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn in den Hintergrundmodus ein andockbaren Bereich festgelegt ist, verwendet das Framework gleitende Effekte anzeigen oder Ausblenden des Bereichs. Das Framework ruft diese Funktion an, wenn im Bereich gleitend ist. `CheckStopSlideCondition` Gibt TRUE zurück, wenn der Bereich vollständig sichtbar ist oder wenn es vollständig ausgeblendet ist.

Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten automatisch im Hintergrund Auswirkungen.

##  <a name="copystate"></a>  CDockablePane::CopyState

Kopiert den Zustand des einen andockbaren Bereich an.

```
virtual void CopyState(CDockablePane* pOrgBar);
```

### <a name="parameters"></a>Parameter

*pOrgBar*<br/>
[in] Ein Zeiger auf einen andockbaren Bereich.

### <a name="remarks"></a>Hinweise

`CDockablePane::CopyState` kopiert den Status der *pOrgBar* in den aktuellen Bereich durch Aufrufen der folgenden Methoden:

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

*lpszCaption*<br/>
[in] Gibt den Fensternamen.

*pParentWnd*<br/>
[in, out] Gibt das übergeordnete Fenster an.

*Rect*<br/>
[in] Gibt die Größe und Position des Fensters, in Clientkoordinaten des *pParentWnd*.

*bHasGripper*<br/>
[in] "True", um den Bereich mit einer Beschriftung zu erstellen; andernfalls "false".

*nID*<br/>
[in] Gibt die ID des untergeordneten Fensters. Dieser Wert muss eindeutig sein, wenn für diesen andockbaren Bereich Andockstatus gespeichert werden soll.

*dwStyle*<br/>
[in] Gibt an, der die Stilattribute für Fenster.

*dwTabbedStyle*<br/>
[in] Gibt das Format im Registerkartenformat, der ein Fenster im Registerkartenformat, die erstellt wird, wenn der Benutzer einen Bereich in der Titelleiste dieses Bereichs zieht.

*dwControlBarStyle*<br/>
[in] Gibt zusätzliche Stilattribute.

*pContext*<br/>
[in, out] Gibt den Kontext Erstellen des Fensters.

*lpszWindowName*<br/>
[in] Gibt den Fensternamen.

*sizeDefault*<br/>
[in] Gibt die Größe des Fensters.

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich wurde erfolgreich erstellt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Erstellt einen Windows-Bereich und fügt es der `CDockablePane` Objekt.

Wenn die *DwStyle* Fensterstil ist das CBRS_FLOAT_MULTI-Flag, das Minirahmenfenster kann mit anderen Bereichen im Fenster "Benutzer" "float". Standardmäßig kann andockbare Bereiche nur einzeln "float".

Wenn die *DwTabbedStyle* Parameter hat das AFX_CBRS_OUTLOOK_TABS-Flag angegeben, im Bereich erstellt im Outlook-Stil im Registerkartenformat Bereiche aus, wenn ein weiterer Bereich angefügt wird, um diesen Bereich mit der [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode. Standardmäßig erstellen andockbare Bereiche im Registerkartenformat mit Typ regulären [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).

##  <a name="createdefaultpanedivider"></a>  CDockablePane::CreateDefaultPaneDivider

Erstellt einen Unterteiler Standardwert für den Bereich an, wie es um ein Framefenster angedockt wird.

```
static CPaneDivider* __stdcall CreateDefaultPaneDivider(
    DWORD dwAlignment,
    CWnd* pParent,
    CRuntimeClass* pSliderRTC = NULL);
```

### <a name="parameters"></a>Parameter

*dwAlignment*<br/>
[in] Gibt die Seite den Hauptframe, zu dem der Bereich angedockt wird. Wenn *DwAlignment* enthält das Flag CBRS_ALIGN_LEFT oder CBRS_ALIGN_RIGHT diese Methode erstellt eine vertikale (`CPaneDivider::SS_VERT`) Unterteiler; andernfalls wird diese Methode erstellt eine horizontale (`CPaneDivider::SS_HORZ`) Unterteiler.

*pParent*<br/>
[in] Zeiger auf den übergeordneten Frame.

*pSliderRTC*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt einen Zeiger auf den neu erstellten Unterteiler, oder NULL, wenn Unterteiler Datenbankerstellung fehlgeschlagen ist.

### <a name="remarks"></a>Hinweise

*DwAlignment* kann eines der folgenden Werte sein:

|Wert|Beschreibung|
|-----------|-----------------|
|CBRS_ALIGN_TOP|Der Bereich wird am oberen Rand der Clientbereich eines Rahmenfensters angedockt wird.|
|CBRS_ALIGN_BOTTOM|Der Bereich wird am unteren Rand der Clientbereich eines Rahmenfensters angedockt wird.|
|CBRS_ALIGN_LEFT|Der Bereich ist auf die linke Seite des Clientbereichs Rand eines Rahmenfensters angedockt wird.|
|CBRS_ALIGN_RIGHT|Der Bereich ist auf die rechte Seite des Clientbereichs Rand eines Rahmenfensters angedockt wird.|

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

*dwStyleEx*<br/>
[in] Gibt die erweiterten Stilattribute für das neue Fenster.

*lpszCaption*<br/>
[in] Gibt den Fensternamen.

*pParentWnd*<br/>
[in, out] Gibt das übergeordnete Fenster an.

*Rect*<br/>
[in] Gibt die Größe und Position des Fensters, in Clientkoordinaten des *pParentWnd*.

*bHasGripper*<br/>
[in] "True", um den Bereich mit einer Beschriftung zu erstellen; andernfalls "false".

*nID*<br/>
[in] Gibt die ID des untergeordneten Fensters. Dieser Wert muss eindeutig sein, wenn Sie den andockzustand für diesen andockbaren Bereich speichern möchten.

*dwStyle*<br/>
[in] Gibt an, der die Stilattribute für Fenster.

*dwTabbedStyle*<br/>
[in] Gibt das Format im Registerkartenformat, der ein Fenster im Registerkartenformat, die erstellt wird, wenn der Benutzer einen Bereich in der Titelleiste dieses Bereichs zieht.

*dwControlBarStyle*<br/>
[in] Gibt an, die zusätzliche Stilattribute.

*pContext*<br/>
[in, out] Gibt den Kontext Erstellen des Fensters.

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich wurde erfolgreich erstellt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Erstellt einen Windows-Bereich und fügt es der `CDockablePane` Objekt.

Wenn die *DwStyle* Fensterstil ist das CBRS_FLOAT_MULTI-Flag, das Minirahmenfenster kann mit anderen Bereichen im Fenster "Benutzer" "float". Standardmäßig kann andockbare Bereiche nur einzeln "float".

Wenn die *DwTabbedStyle* Parameter hat das AFX_CBRS_OUTLOOK_TABS-Flag angegeben, im Bereich erstellt im Outlook-Stil im Registerkartenformat Bereiche aus, wenn ein weiterer Bereich angefügt wird, um diesen Bereich mit der [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode. Standardmäßig erstellen andockbare Bereiche im Registerkartenformat mit Typ regulären [CTabbedPane](../../mfc/reference/ctabbedpane-class.md).

##  <a name="createtabbedpane"></a>  CDockablePane::CreateTabbedPane

Erstellt einen Bereich im Registerkartenformat im aktuellen Bereich.

```
virtual CTabbedPane* CreateTabbedPane();
```

### <a name="return-value"></a>Rückgabewert

Die neue Seite im Registerformat oder NULL, wenn der Erstellungsvorgang ist fehlgeschlagen.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn es sich um einen Bereich im Registerkartenformat, ersetzen in diesem Bereich erstellt. Weitere Informationen finden Sie unter [CDockablePane:: Attachtotabwnd](#attachtotabwnd).

Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen, wie Seiten im Registerformat erstellt und initialisiert werden.

Bereich im Registerkartenformat ist gemäß den Laufzeit-Klasseninformationen in gespeicherten erstellt die `m_pTabbedControlBarRTC` Member, der durch initialisiert wird und die [CDockablePane:: CreateEx](#createex) Methode.

##  <a name="dockpanecontainer"></a>  CDockablePane::DockPaneContainer

Dockt einen Container in den Bereich an.

```
virtual BOOL DockPaneContainer(
    CPaneContainerManager& barContainerManager,
    DWORD dwAlignment,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

*barContainerManager*<br/>
[in] Ein Verweis auf den Manager des Containers, der angedockt wird.

*dwAlignment*<br/>
[in] DWORD, das den Rand des Bereichs angibt, der der Container angedockt wird.

*dockMethod*<br/>
[in] Nicht verwendet.

### <a name="return-value"></a>Rückgabewert

True, wenn der Container wurde erfolgreich in den Bereich angedockt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

*DwAlignment* kann eines der folgenden Werte sein:

|Wert|Beschreibung|
|-----------|-----------------|
|CBRS_ALIGN_TOP|Der Container wird am oberen Rand der Bereich angedockt wird.|
|CBRS_ALIGN_BOTTOM|Der Container wird am unteren Rand der Bereich angedockt wird.|
|CBRS_ALIGN_LEFT|Der Container wird auf der linken Seite im Bereich angedockt wird.|
|CBRS_ALIGN_RIGHT|Der Container wird rechts neben dem Bereich angedockt wird.|

##  <a name="dockpanestandard"></a>  CDockablePane::DockPaneStandard

Dockt einen Bereich mithilfe der Gliederung (standard) Andocken an.

```
virtual CPane* DockPaneStandard(BOOL& bWasDocked);
```

### <a name="parameters"></a>Parameter

*bWasDocked*<br/>
[in] Bei der Rückgabe der Methode enthält dieser Wert "true" auf, wenn der Bereich erfolgreich angedockt wurde; Andernfalls enthält er "false".

### <a name="return-value"></a>Rückgabewert

Wenn der Bereich einem Fenster im Registerkartenformat angedockt wurde oder wenn ein Fenster im Registerkartenformat aufgrund der Dockingstation erstellt wurde, gibt diese Methode einen Zeiger auf Fenster im Registerkartenformat. Wenn der Bereich, andernfalls erfolgreich angedockt wurde, gibt diese Methode die **dies** Zeiger. Wenn Andocken fehlgeschlagen ist, gibt diese Methode NULL zurück.

##  <a name="docktorecentpos"></a>  CDockablePane::DockToRecentPos

Dockt einen Bereich auf die gespeicherten verankerten Position an.

```
BOOL CDockablePane::DockToRecentPos();
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich erfolgreich angedockt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Andockbare Bereiche speichern aktuelle docking-Informationen in einem [CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md) Objekt.

##  <a name="docktowindow"></a>  CDockablePane::DockToWindow

Dockt einen andockbaren Bereich auf einen anderen andockbaren Bereich an.

```
virtual BOOL DockToWindow(
    CDockablePane* pTargetWindow,
    DWORD dwAlignment,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Parameter

*pTargetWindow*<br/>
[in, out] Gibt an, andockbaren Bereich um diesem Bereich anzudocken.

*dwAlignment*<br/>
[in] Gibt die Ausrichtung des andockbaren Bereich an. Dabei kann es sich um CBRS_ALIGN_LEFT, CBRS_ALIGN_TOP, CBRS_ALIGN_RIGHT, CBRS_ALIGN_BOTTOM oder CBRS_ALIGN_ANY sein. (Die in afxres.h definiert.)

*lpRect*<br/>
[in] Gibt das Andocken Rechteck für den Bereich.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich erfolgreich angedockt wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um einen Bereich in einen anderen Bereich mit die Ausrichtung anhand des Andocken *DwAlignment*.

##  <a name="drawcaption"></a>  CDockablePane::DrawCaption

Zeichnet die Beschriftung, die (auch als ziehelements bezeichnet), der einen andockbaren Bereich an.

```
virtual void DrawCaption(
    CDC* pDC,
    CRect rectCaption);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
[in] Stellt den Gerätekontext zum Zeichnen verwendet.

*rectCaption*<br/>
[in] Gibt das umschließende Rechteck der Beschriftung für den Bereich an.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode, um die Beschriftung des einen andockbaren Bereich gezeichnet werden soll.

Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung der Beschriftung.

##  <a name="enableautohideall"></a>  CDockablePane::EnableAutohideAll

Aktiviert oder deaktiviert den Hintergrundmodus, für diesen Bereich, und für andere Bereiche im Container.

```
void EnableAutohideAll(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] "True", die automatisch im Hintergrund alle Feature für den andockbaren Bereich zu aktivieren; andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn ein Benutzer hält die **STRG** Schlüssel und klickt auf die Schaltfläche "anheften", um einen Bereich in den Hintergrundmodus, alle anderen Bereiche im selben Container zu wechseln, werden auch in den Hintergrundmodus gewechselt.

Beim Aufrufen dieser Methode *bAktivieren* auf "false" festgelegt, um dieses Feature für einen bestimmten Bereich deaktivieren.

##  <a name="enablegripper"></a>  CDockablePane::EnableGripper

Anzeigen oder ausblenden die Beschriftung (auch als ziehelements bezeichnet).

```
virtual void EnableGripper(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] True, um die Beschriftung zu aktivieren. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn das Framework andockbare Bereiche erstellt wird, verfügen sie nicht den Fensterstil WS_STYLE, über selbst wenn angegeben. Dies bedeutet, dass im Bereich der Beschriftung einer nicht-Clientbereich, die vom Framework gesteuert wird, aber in diesem Bereich unterscheidet sich die standardmäßige fensterbeschriftung.

Sie können ein- oder ausblenden die Beschriftung zu einem beliebigen Zeitpunkt. Das Framework die Beschriftung wird ausgeblendet, wenn ein Bereich als Registerkarte hinzugefügt wird, ein Fenster im Registerkartenformat oder ein Bereich in einem Minirahmenfenster abgedockt wird.

##  <a name="getahrestoredrect"></a>  CDockablePane::GetAHRestoredRect

Gibt die Position des Bereichs im Modus "automatisch ausblenden".

```
CRect GetAHRestoredRect() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CRect` Objekt, das die Position des Bereichs enthält, wenn er im Modus "automatisch ausblenden" ist.

### <a name="remarks"></a>Hinweise

##  <a name="getahslidemode"></a>  CDockablePane::GetAHSlideMode

Ruft ab, der automatisch ausblendbaren Folienmodus für den Bereich.

```
virtual UINT GetAHSlideMode() const;
```

### <a name="return-value"></a>Rückgabewert

UINT, der angibt, der automatisch ausblendbaren Folienmodus für den Bereich. Der Rückgabewert kann entweder AFX_AHSM_MOVE oder AFX_AHSM_STRETCH sein, aber die Implementierung nur AFX_AHSM_MOVE verwendet.

### <a name="remarks"></a>Hinweise

##  <a name="getcaptionheight"></a>  CDockablePane::GetCaptionHeight

Gibt die Höhe des die aktuelle Beschriftung in Pixel zurück.

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>Rückgabewert

Die Höhe der Beschriftung in Pixel.

### <a name="remarks"></a>Hinweise

Die Überschriftenhöhe ist 0, wenn die Beschriftung von ausgeblendet wurde die [CDockablePane::EnableGripper](#enablegripper) -Methode, oder wenn der Bereich nicht über eine Beschriftung verfügt.

##  <a name="getdefaultpanedivider"></a>  CDockablePane::GetDefaultPaneDivider

Gibt standardmäßige bereichsteiler für den Bereich des Containers zurück.

```
CPaneDivider* GetDefaultPaneDivider() const;
```

### <a name="return-value"></a>Rückgabewert

Ein gültiger [CPaneDivider](../../mfc/reference/cpanedivider-class.md) -Objekt, wenn das Hauptrahmenfenster andockbare Bereich angedockt ist oder `NULL` Wenn andockbare Bereich nicht angedockt ist, oder wenn es sich bei schwimmen.

### <a name="remarks"></a>Hinweise

Weitere Informationen zum bereichsteiler, finden Sie unter [CPaneDivider-Klasse](../../mfc/reference/cpanedivider-class.md).

##  <a name="getdockingstatus"></a>  CDockablePane::GetDockingStatus

Bestimmt, ob die Möglichkeit, einen Bereich angedockt werden abhängig von der angegebenen Position.

```
virtual AFX_CS_STATUS GetDockingStatus(
    CPoint pt,
    int nSensitivity);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
[in] Die Position des Mauszeigers in Bildschirmkoordinaten.

*nSensitivity*<br/>
[in] Die Entfernung in Pixel von der Kante eines Rechtecks muss der Zeiger so aktivieren Sie das Andocken.

### <a name="return-value"></a>Rückgabewert

Eine der folgenden Statuswerte:

|AFX_CS_STATUS Wert|Bedeutung|
|---------------------------|-------------|
|CS_NOTHING|Der Zeiger ist nicht über eine docksite. Das Framework ist nicht auf den Bereich anzudocken.|
|CS_DOCK_IMMEDIATELY|Der Zeiger befindet sich über der DockPosition in unmittelbarer Modus (der Bereich verwendet den Andockmodus DT_IMMEDIATE). Das Framework Dockt den Bereich sofort an.|
|CS_DELAY_DOCK|Der Zeiger ist, über eine docksite, die eine andere andockbaren Bereich oder eine Kante der Hauptframe ist. Das Framework Dockt den Bereich an, nach einer Verzögerung. Finden Sie im Abschnitt "Hinweise" Weitere Informationen zu dieser Verzögerung.|
|CS_DELAY_DOCK_TO_TAB|Der Zeiger befindet sich über eine docksite, die bewirkt, dass den Bereich in einem Fenster im Registerkartenformat angedockt werden. Dies tritt auf, wenn der Mauszeiger über die Beschriftung von einem anderen andockbaren Bereich oder der Registerkartenbereich von einem Bereich im Registerkartenformat gefunden wird.|

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode zum Behandeln von Andocken eines unverankerten Bereichs.

Für unverankerte Symbolleisten sowie andockbare Bereiche, die den Andockmodus DT_IMMEDIATE verwenden verzögert das Framework die Dock-Befehl aus, um dem Benutzer ermöglichen, bevor Andocken auftritt, verschieben Sie das Fenster aus den Clientbereich des übergeordneten Rahmens. Die Länge der Verzögerung in Millisekunden gemessen wird und wird gesteuert, indem die [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) Datenmember... Der Standardwert von [CDockingManager::m_nTimeOutBeforeToolBarDock](../../mfc/reference/cdockingmanager-class.md#m_ntimeoutbeforetoolbardock) ist 200. Dieses Verhalten emuliert das Andockverhalten des Microsoft Word 2007.

Für verzögerte Andocken Staaten (CS_DELAY_DOCK und CS_DELAY_DOCK_TO_TAB) führt das Framework keine andocken, bis der Benutzer die Maustaste loslässt. Wenn ein Bereich den Andockmodus DT_STANDARD verwendet wird, zeigt das Framework ein Rechteck auf die voraussichtliche Andockposition aus. Wenn ein Bereich den Andockmodus DT_SMART verwendet wird, zeigt das Framework intelligente andockmarker und halb transparent Rechtecke an die voraussichtliche Andockposition an. Rufen Sie zum Angeben des Andockmodus für die im Eigenschaftenbereich die [CBasePane::SetDockingMode](../../mfc/reference/cbasepane-class.md#setdockingmode) Methode. Weitere Informationen zu intelligentes Andocken, finden Sie unter [CDockingManager::GetSmartDockingParams](../../mfc/reference/cdockingmanager-class.md#getsmartdockingparams).

##  <a name="getdragsensitivity"></a>  CDockablePane::GetDragSensitivity

Gibt die Vertraulichkeit ziehen Sie einen andockbaren Bereich zurück.

```
static const CSize& GetDragSensitivity();
```

### <a name="return-value"></a>Rückgabewert

Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die Breite und Höhe in Pixel eines Rechtecks, dessen Mitte sich an einem Ziehpunkt befindet, enthält. Der Ziehvorgang beginnt nicht, bis der Mauszeiger bewegt, außerhalb dieses Rechteck wird.

##  <a name="getlastpercentinpanecontainer"></a>  CDockablePane::GetLastPercentInPaneContainer

Ruft den Prozentsatz des Speicherplatzes, der ein Bereich in einem Container belegt ( [CPaneContainer-Klasse](../../mfc/reference/cpanecontainer-class.md)).

```
int GetLastPercentInPaneContainer() const;
```

### <a name="return-value"></a>Rückgabewert

Ein *Int* , der den Prozentsatz des Speicherplatzes, der der Bereich in einem Container belegt angibt.

### <a name="remarks"></a>Hinweise

Diese Methode wird verwendet, wenn der Container das Layout angepasst wird.

##  <a name="gettabarea"></a>  CDockablePane::GetTabArea

Ruft den Registerkartenbereich für den Bereich.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const;
```

### <a name="parameters"></a>Parameter

*rectTabAreaTop*<br/>
[in] `GetTabArea` füllt Sie diese Variable mit der Registerkartenbereich, wenn die Registerkarten am oberen Rand des Bereichs befinden. Wenn die Registerkarten am unteren Rand des Bereichs befinden, wird diese Variable mit einem leeren Rechteck gefüllt.

*rectTabAreaBottom*<br/>
[in] `GetTabArea` füllt Sie diese Variable mit der Registerkartenbereich, wenn die Registerkarten am unteren Rand des Bereichs befinden. Wenn die Registerkarten am oberen Rand des Bereichs befinden, wird diese Variable mit einem leeren Rechteck gefüllt.

### <a name="remarks"></a>Hinweise

Diese Methode wird nur in von abgeleiteten Klassen verwendet `CDockablePane` und Registerkarten angezeigt. Weitere Informationen finden Sie unter [CTabbedPane::GetTabArea](../../mfc/reference/ctabbedpane-class.md#gettabarea) und [CMFCOutlookBar::GetTabArea](../../mfc/reference/cmfcoutlookbar-class.md#gettabarea).

##  <a name="gettabbedpanertc"></a>  CDockablePane::GetTabbedPaneRTC

Gibt zurück, die laufzeitklasseninformationen zu einem Fenster im Registerkartenformat, die erstellt wird, wenn ein weiterer Bereich in den aktuellen Bereich angedockt.

```
CRuntimeClass* GetTabbedPaneRTC() const;
```

### <a name="return-value"></a>Rückgabewert

Die Laufzeit-Klasseninformationen für den andockbaren Bereich.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die laufzeitklasseninformationen für Seiten im Registerformat abzurufen, die dynamisch erstellt werden. Dies kann auftreten, wenn ein Benutzer einen Bereich auf die Beschriftung des anderen Bereichs zieht, oder rufen Sie die [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode, um einen Bereich im Registerkartenformat aus zwei andockbare Bereiche programmgesteuert zu erstellen.

Sie können die laufzeitklasseninformationen festlegen, durch den Aufruf der [CDockablePane:: Settabbedpanertc](#settabbedpanertc) Methode.

##  <a name="hasautohidemode"></a>  CDockablePane::HasAutoHideMode

Gibt an, ob ein andockbarer Bereich in den Hintergrundmodus gewechselt werden kann.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich, in den Hintergrundmodus gewechselt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse den Hintergrundmodus für ein bestimmtes andockbare Fenster zu deaktivieren.

##  <a name="hittest"></a>  CDockablePane::HitTest

Gibt den Speicherort in einem Bereich, in denen der Benutzer die Maus klickt.

```
virtual int HitTest(
    CPoint point,
    BOOL bDetectCaption = FALSE);
```

### <a name="parameters"></a>Parameter

*Zeigen Sie*<br/>
[in] Legt den Punkt zu testen.

*bDetectCaption*<br/>
[in] True, wenn der HTCAPTION zurückgegeben werden soll, wenn der Punkt, auf den Bereich der Beschriftung ist. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Einer der folgenden Werte:

- HTNOWHERE Wenn *zeigen* befindet sich nicht in der andockbaren Bereich.

- HTCLIENT Wenn *zeigen* befindet sich in den Clientbereich des andockbaren Bereich.

- HTCAPTION Wenn *zeigen* befindet sich im Headerbereich des andockbaren Bereich.

- AFX_HTCLOSE Wenn *zeigen* befindet sich auf die Schaltfläche "Schließen".

- HTMAXBUTTON Wenn *zeigen* befindet sich auf die Schaltfläche "anheften".

##  <a name="isautohideallenabled"></a>  CDockablePane::IsAutohideAllEnabled

Gibt an, ob die andockbaren Bereich, und alle anderen Bereiche im Container in den Hintergrundmodus gewechselt werden können.

```
virtual BOOL IsAutohideAllEnabled() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbaren Bereich, und alle anderen Bereiche in den Container, in den Hintergrundmodus gewechselt werden können. andernfalls "false".

### <a name="remarks"></a>Hinweise

Ein Benutzer kann den Hintergrundmodus, indem Sie auf das Andocken Schaltfläche "anheften" bei gedrückter der **STRG** Schlüssel

Rufen Sie zum Aktivieren oder Deaktivieren dieses Verhalten, das [CDockablePane::EnableAutohideAll](#enableautohideall) Methode.

##  <a name="isautohidemode"></a>  CDockablePane::IsAutoHideMode

Bestimmt, ob ein Bereich in den Hintergrundmodus.

```
virtual BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich in den Hintergrundmodus ist. andernfalls "false".

##  <a name="isdocked"></a>  CDockablePane::IsDocked

Bestimmt, ob der aktuelle Bereich angedockt ist.

```
virtual BOOL IsDocked() const;
```

### <a name="return-value"></a>Rückgabewert

"True", wenn der andockbare Bereich nicht zu einem Minirahmenfenster gehört oder in einem Minirahmenfenster mit einem anderen Bereich schwimmen. "False", wenn der Bereich ein untergeordnetes Element des ein Minirahmenfenster ist und es keine andere Bereiche gibt, die das Minirahmenfenster angehören.

### <a name="remarks"></a>Hinweise

Aufrufen, um zu bestimmen, ob der Bereich, an das Hauptrahmenfenster angedockt ist, [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider). Wenn die Methode einen nicht-NULL-Zeiger zurückgibt, wird der Bereich an das Hauptrahmenfenster angedockt.

##  <a name="ishideinautohidemode"></a>  CDockablePane::IsHideInAutoHideMode

Bestimmt das Verhalten eines Bereichs, der in den Hintergrundmodus ist, wenn sie (durch Aufrufen von ein- oder ausgeblendet ist) [CDockablePane::ShowPane](#showpane).

```
virtual BOOL IsHideInAutoHideMode() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich, in den Hintergrundmodus ausgeblendet werden soll. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn in den Hintergrundmodus ein andockbaren Bereich ist, es verhält sich anders beim Aufruf `ShowPane` ein-und Ausblenden des Bereichs. Dieses Verhalten wird gesteuert, indem Sie den statischen Member [CDockablePane::m_bHideInAutoHideMode](#m_bhideinautohidemode). Wenn dieser Member "true", andockbaren Bereich und seiner zugehörigen automatisch im Hintergrund-Symbolleiste ist oder AutoAusblenden-Schaltfläche angezeigt oder ausgeblendet wird beim Aufruf `ShowPane`. Andernfalls andockbare Bereich aktiviert oder deaktiviert, und der zugehörigen automatisch im Hintergrund-Symbolleiste oder die AutoAusblenden-Schaltfläche ist immer sichtbar.

Überschreiben Sie diese Methode in einer abgeleiteten Klasse das Standardverhalten für die einzelnen Bereiche zu ändern.

Der Standardwert für `m_bHideInAutoHideMode` ist "false".

##  <a name="isinfloatingmultipaneframewnd"></a>  CDockablePane::IsInFloatingMultiPaneFrameWnd

Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist ( [CMultiPaneFrameWnd-Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich in einem Fenster mit mehreren Rahmen. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="isresizable"></a>  CDockablePane::IsResizable

Gibt an, ob der Bereich geändert werden kann.

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich geändert werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Standardmäßig sind andockbare Bereiche mit veränderbarer Größe. Um zu verhindern, Größenänderung, überschreiben Sie diese Methode in einer abgeleiteten Klasse, und gibt "false". Beachten Sie, die ein FALSE-Wert zu einem Fehler führt **ASSERT** in [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane). Verwendung [CDockingManager::AddPane](../../mfc/reference/cdockingmanager-class.md#addpane) stattdessen einen Bereich innerhalb eines übergeordneten Rahmens angedockt.

Bereiche, die nicht verändert werden können können weder "float" und geben Sie die automatischen Ausblendemodus und befinden sich immer am äußeren Rand des übergeordneten Rahmens.

##  <a name="istablocationbottom"></a>  CDockablePane::IsTabLocationBottom

Gibt an, ob die Registerkarten oben oder unteren Rand des Bereichs befinden.

```
virtual BOOL IsTabLocationBottom() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn die Registerkarten am unteren Rand des Bereichs befinden. FALSE, wenn die Registerkarten am oberen Rand des Bereichs befinden.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [CTabbedPane::IsTabLocationBottom](../../mfc/reference/ctabbedpane-class.md#istablocationbottom).

##  <a name="istracked"></a>  CDockablePane::IsTracked

Gibt an, ob ein Bereich vom Benutzer verschoben wird.

```
BOOL IsTracked() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich verschoben wird. andernfalls "false".

##  <a name="isvisible"></a>  CDockablePane::IsVisible

Bestimmt, ob der aktuelle Bereich angezeigt wird.

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der andockbare Bereich angezeigt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um zu bestimmen, ob ein andockbares Fenster sichtbar ist. Sie können diese Methode verwenden, statt [CWnd::IsWindowVisible](../../mfc/reference/cwnd-class.md#iswindowvisible) oder für das Format WS_VISIBLE testen. Der zurückgegebene Sichtbarkeitszustand hängt davon ab, ob in den Hintergrundmodus aktiviert oder deaktiviert ist und auf dem Wert der [CDockablePane::IsHideInAutoHideMode](#ishideinautohidemode) Eigenschaft.

Wenn der andockbare Bereich in den Hintergrundmodus ist und `IsHideInAutoHideMode` gibt "false" den Sichtbarkeitszustand ist immer "false".

Wenn der andockbare Bereich in den Hintergrundmodus ist und `IsHideInAutoHideMode` gibt TRUE zurück, der Sichtbarkeitszustand hängt von den Sichtbarkeitsstatus der zugehörigen automatisch im Hintergrund-Symbolleiste.

Ist der andockbare Bereich nicht in den Hintergrundmodus, wird durch der Sichtbarkeitszustand bestimmt die [CBasePane::IsVisible](../../mfc/reference/cbasepane-class.md#isvisible) Methode.

## ##  <a name="loadstate"></a>  CDockablePane:: LoadState

Nur für interne Verwendung. Ausführliche Informationen finden Sie im Quellcode des Ordners VC\atlmfc\src\mfc der Visual Studio-Installation.

```
virtual BOOL LoadState(
   LPCTSTR lpszProfileName = NULL,
   int nIndex = -1,
   UINT uiID = (UINT) -1
);
```

##  <a name="m_bdisableanimation"></a>  CDockablePane::m_bDisableAnimation

Gibt an, ob die Animation andockbaren Bereich automatisch im Hintergrund deaktiviert ist.

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

Wenn Sie dieses Element auf "true" werden andockbare Bereiche festgelegt sind, ausgeblendet oder mit ihren entsprechenden automatisch im Hintergrund Symbolleisten und Schaltflächen angezeigt wird, beim Aufrufen [CDockablePane::ShowPane](#showpane).

Wenn Sie dieses Element auf "false", andockbare Bereiche festlegen aktiviert oder deaktiviert werden, wenn Sie aufrufen [CDockablePane::ShowPane](#showpane).

##  <a name="m_nslidesteps"></a>  CDockablePane::m_nSlideSteps

Gibt die Geschwindigkeit der Animation des Bereichs an, wenn er sich in den Hintergrundmodus.

```
AFX_IMPORT_DATA static int m_nSlideSteps;
```

### <a name="remarks"></a>Hinweise

Reduzieren Sie für eine schnellere Animationseffekt diesen Wert. Erhöhen Sie für den Animationseffekt langsamer diesen Wert.

##  <a name="onafterchangeparent"></a>  CDockablePane::OnAfterChangeParent

Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>Parameter

[in] *pWndOldParent*<br/>

### <a name="remarks"></a>Hinweise

##  <a name="onafterdockfromminiframe"></a>  CDockablePane::OnAfterDockFromMiniFrame

Vom Framework aufgerufen, wenn eine unverankerte andockleiste an ein Framefenster angedockt.

```
virtual void OnAfterDockFromMiniFrame();
```

### <a name="remarks"></a>Hinweise

Standardmäßig führt diese Methode keine Aktion.

##  <a name="onbeforechangeparent"></a>  CDockablePane::OnBeforeChangeParent

Das Framework ruft diese Methode auf, bevor das übergeordnete Element des Bereichs geändert.

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Parameter

*pWndNewParent*<br/>
[in] Ein Zeiger auf das neue übergeordnete Fenster.

*bDelay*<br/>
[in] Boolescher Wert, der angibt, ob eine neuberechnung der Layout des Docks zu verzögern, wenn der Bereich nicht in der Dockingstation ist. Weitere Informationen finden Sie unter [CDockablePane::UndockPane](#undockpane).

### <a name="remarks"></a>Hinweise

Wenn der Bereich angedockt ist, und das neue übergeordnete Element lässt nicht zu andocken, wird diese Methode im Bereich abgedockt.

Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert wird, speichert diese Methode die aktuelle verankerten Position. Das Framework verwendet die aktuelle dockingposition der Position des Bereichs wiederherstellen, wenn es wieder in einem angedockten Zustand konvertiert wird.

##  <a name="onbeforefloat"></a>  CDockablePane::OnBeforeFloat

Das Framework ruft diese Methode vor einen Bereich geht in einen unverankerten Zustand.

```
virtual BOOL OnBeforeFloat(
    CRect& rectFloat,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>Parameter

*rectFloat*<br/>
[in] Gibt die Position und Größe des Bereichs an, wenn es in einen unverankerten Zustand befindet.

*dockMethod*<br/>
[in] Gibt die docking-Methode. Finden Sie unter [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) eine Liste von möglichen Werten.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich abgedockt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn ein Bereich, der auf "float" geht. Sie können diese Methode in einer abgeleiteten Klasse überschreiben, wenn die Verarbeitung auszuführen, bevor der Bereich wird verschoben werden sollen.

##  <a name="onpressbuttons"></a>  CDockablePane::OnPressButtons

Wird aufgerufen, wenn der Benutzer mit Ausnahme der Schaltflächen AFX_HTCLOSE und AFX_HTMAXBUTTON eine Titelleisten-Schaltfläche drückt.

```
virtual void OnPressButtons(UINT nHit);
```

### <a name="parameters"></a>Parameter

*nHit*<br/>
[in] Dieser Parameter wird nicht verwendet.

### <a name="remarks"></a>Hinweise

Wenn Sie eine benutzerdefinierte Schaltfläche auf die Beschriftung des einen andockbaren Bereich hinzufügen, überschreiben Sie diese Methode, um Benachrichtigungen zu erhalten, wenn ein Benutzer die Schaltfläche klickt.

##  <a name="onslide"></a>  CDockablePane::OnSlide

Wird aufgerufen, durch das Framework den Bereich zu animieren, wenn er sich in den Hintergrundmodus.

```
virtual void OnSlide(BOOL bSlideOut);
```

### <a name="parameters"></a>Parameter

*bSlideOut*<br/>
[in] True, um im Bereich angezeigt. "False" zum Ausblenden des Fensters.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren von benutzerdefinierten automatisch im Hintergrund Auswirkungen.

##  <a name="removefromdefaultpanedividier"></a>  CDockablePane:: removefromdefaultpanedividier wurde

Das Framework ruft diese Methode auf, wenn ein Bereich wird abgedockt wird.

```
void RemoveFromDefaultPaneDividier();
```

### <a name="remarks"></a>Hinweise

Diese Methode legt bereichsteiler standardmäßig auf NULL fest und entfernt im Bereich von seinem Container.

##  <a name="replacepane"></a>  CDockablePane::ReplacePane

Ersetzt den Bereich mit einem angegebenen Bereich.

```
BOOL ReplacePane(
    CDockablePane* pBarToReplaceWith,
    AFX_DOCK_METHOD dockMethod,
    BOOL bRegisterWithFrame = FALSE);
```

### <a name="parameters"></a>Parameter

*pBarToReplaceWith*<br/>
[in] Ein Zeiger auf einen andockbaren Bereich.

*dockMethod*<br/>
[in] Nicht verwendet.

*bRegisterWithFrame*<br/>
[in] Wenn "true" ist im neuen beim Dock-Manager des übergeordneten Elements des alten Bereichs registriert. Der neue Bereich wird am Index aus der alten Bereich in der Liste der Bereiche eingefügt, die von Dock-Manager verwaltet wird.

### <a name="return-value"></a>Rückgabewert

True, wenn die Ersetzung erfolgreich ist. andernfalls "false".

##  <a name="restoredefaultpanedivider"></a>  CDockablePane::RestoreDefaultPaneDivider

Wenn ein Bereich deserialisiert wird, ruft das Framework diese Methode, um die standardmäßige bereichsteiler wiederherstellen.

```
void RestoreDefaultPaneDivider();
```

### <a name="remarks"></a>Hinweise

Bereichsteiler wiederhergestellten standardmäßig ersetzt der aktuelle Standard-bereichsteiler, falls vorhanden.

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

*bMode*<br/>
[in] True, um den Hintergrundmodus zu aktivieren. "False", um reguläre Andockmodus zu aktivieren.

*dwAlignment*<br/>
[in] Gibt die Ausrichtung des Bereichs automatisch im Hintergrund zu erstellen.

*pCurrAutoHideBar*<br/>
[in, out] Ein Zeiger auf der Symbolleiste des aktuellen automatisch im Hintergrund. NULL kann sein.

*bUseTimer*<br/>
[in] Gibt an, ob Sie den Effekt automatisch im Hintergrund verwenden, wenn der Benutzer den Bereich in den Hintergrundmodus wechselt oder Sie den Bereich unmittelbar ausblenden.

### <a name="return-value"></a>Rückgabewert

Die automatisch im Hintergrund-Symbolleiste, die als Ergebnis der Wechsel zu den Hintergrundmodus oder NULL erstellt wurde.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode aus, klickt ein Benutzer die Schaltfläche "anheften" andockbaren Bereich in den Hintergrundmodus oder regulären Andockmodus wechseln.

Rufen Sie diese Methode, um einen andockbaren Bereich in den Hintergrundmodus programmgesteuert zu wechseln. Der Bereich angedockt werden muss, an das Hauptrahmenfenster ( [CDockablePane::GetDefaultPaneDivider](#getdefaultpanedivider) muss einen gültigen Zeiger auf Zurückgeben der [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).

##  <a name="setautohideparents"></a>  CDockablePane::SetAutoHideParents

Legt fest, der automatisch ausblendbaren Schaltfläche und der automatisch ausblendbaren-Symbolleiste für den Bereich.

```
void SetAutoHideParents(
    CMFCAutoHideBar* pToolBar,
    CMFCAutoHideButton* pBtn);
```

### <a name="parameters"></a>Parameter

*pToolBar*<br/>
[in] Zeiger auf ein solches.

*pBtn*<br/>
[in] Zeiger auf eine Schaltfläche zum automatischen ausblenden.

##  <a name="setlastpercentinpanecontainer"></a>  CDockablePane::SetLastPercentInPaneContainer

Bestimmt den Prozentsatz des Speicherplatzes, der ein Bereich in einem Container einnimmt.

```
void SetLastPercentInPaneContainer(int n);
```

### <a name="parameters"></a>Parameter

*n*<br/>
[in] Ein **Int** , der den Prozentsatz des Speicherplatzes, der der Bereich in einem Container belegt angibt.

### <a name="remarks"></a>Hinweise

Das Framework passt den Bereich, um den neuen Wert zu verwenden, wenn das Layout neu berechnet wird.

##  <a name="setrestoreddefaultpanedivider"></a>  CDockablePane::SetRestoredDefaultPaneDivider

Wird die wiederhergestellte Standard Trennlinie.

```
void SetRestoredDefaultPaneDivider(HWND hRestoredSlider);
```

### <a name="parameters"></a>Parameter

*hRestoredSlider*<br/>
[in] Ein Handle für einen bereichsteiler (Schieberegler).

### <a name="remarks"></a>Hinweise

Ein bereichsteiler wiederhergestellten Standard wird abgerufen, wenn ein Bereich deserialisiert wird. Weitere Informationen finden Sie unter [CDockablePane::RestoreDefaultPaneDivider](#restoredefaultpanedivider).

##  <a name="settabbedpanertc"></a>  CDockablePane:: Settabbedpanertc

Legt die laufzeitklasseninformationen für ein Fenster im Registerkartenformat, die erstellt wird, wenn zwei Bereiche zusammen docken fest.

```
void SetTabbedPaneRTC(CRuntimeClass* pRTC);
```

### <a name="parameters"></a>Parameter

*pRTC*<br/>
[in] Die Laufzeit-Klasseninformationen für die Seite im Registerformat.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die laufzeitklasseninformationen für Bereiche im Registerkartenformat festlegen, die dynamisch erstellt werden. Dies kann auftreten, wenn ein Benutzer einen Bereich auf die Beschriftung des anderen Bereichs zieht, oder rufen Sie die [CDockablePane:: Attachtotabwnd](#attachtotabwnd) Methode, um einen Bereich im Registerkartenformat aus zwei andockbare Bereiche programmgesteuert zu erstellen.

Die Standardklasse für die Common Language Runtime wird festgelegt, gemäß der *DwTabbedStyle* Parameter [CDockablePane::Create](#create) und [CDockablePane:: CreateEx](#createex). Um die neue Registerkartenformat anzupassen, leiten Sie die Klasse von einer der folgenden Klassen:

- [CBaseTabbedPane-Klasse](../../mfc/reference/cbasetabbedpane-class.md)

- [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md)

- [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).

Anschließend rufen Sie diese Methode mit dem Zeiger auf die Laufzeit-Klasseninformationen an.

##  <a name="showpane"></a>  CDockablePane::ShowPane

Anzeigen oder ausblenden ein Bereichs.

```
virtual void ShowPane(
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Parameter

*bShow*<br/>
[in] True, um im Bereich angezeigt. "False" zum Ausblenden des Fensters.

*bDelay*<br/>
[in] Anpassen von "true" Verzögerung Layout des Docks; FALSE, um das Layout des Docks sofort anpassen.

*bActivate*<br/>
[in] TRUE, aktivieren Sie im Bereich, wenn Sie angezeigt werden soll andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode statt der [ShowWindow](../../mfc/reference/cwnd-class.md#showwindow) beim ein- bzw. ausblenden andockbare Bereiche.

##  <a name="slide"></a>  CDockablePane::Slide

Führt eine Animation einen Bereich, der in den Hintergrundmodus ist.

```
virtual void Slide(
    BOOL bSlideOut,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Parameter

*bSlideOut*<br/>
[in] True, um im Bereich angezeigt. "False" zum Ausblenden des Fensters.

*bUseTimer*<br/>
[in] True, um ein- oder Ausblenden des Bereichs mit dem Effekt automatisch im Hintergrund. "False" zum Anzeigen oder Ausblenden des Bereichs sofort.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode, um einen Bereich zu animieren, der in den Hintergrundmodus ist.

Diese Methode verwendet die `CDockablePane::m_nSlideDefaultTimeOut` um das Timeout für die Abrolleffekt zu bestimmen. Der Standardwert für das Timeout ist 1. Wenn Sie den Algorithmus automatisch im Hintergrund anpassen, ändern Sie dieses Element aus, um das Timeout zu ändern.

##  <a name="toggleautohide"></a>  CDockablePane::ToggleAutoHide

Schaltet den Bereich zwischen immer sichtbar und den automatischen Ausblendemodus.

```
virtual void ToggleAutoHide();
```

### <a name="remarks"></a>Hinweise

Diese Methode schaltet den automatischen Ausblendemodus für den Bereich durch den Aufruf [CDockablePane::SetAutoHideMode](#setautohidemode).

##  <a name="undockpane"></a>  CDockablePane::UndockPane

Dockt einen Bereich von Hauptrahmenfenster oder einen Benutzer im Fenster-Container.

```
virtual void UndockPane(BOOL bDelay = FALSE);
```

### <a name="parameters"></a>Parameter

*bDelay*<br/>
[in] Berechnen von "true" Verzögerung Layout des Docks; "False", um das Layout des Docks neuberechnung sofort auszuführen.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um einen Bereich von Hauptrahmenfenster oder aus einem Container für Multi-Benutzer-Fenster (ein Bereich, der in einem einzelnen Benutzer-Fenster mit anderen Bereichen unverankert ist) zu lösen.

Sie müssen einen Bereich abdocken, bevor Sie alle externen Vorgänge ausführen, die nicht von ausgeführt wird die [CDockingManager](../../mfc/reference/cdockingmanager-class.md). Beispielsweise müssen Sie einen Bereich zu verschieben programmgesteuert von einem Speicherort in einen anderen lösen.

Das Framework wird abgedockt automatisch auf die Bereiche aus, bevor sie zerstört werden.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CPane-Klasse](../../mfc/reference/cpane-class.md)
