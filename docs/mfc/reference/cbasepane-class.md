---
title: CBasePane-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
dev_langs:
- C++
helpviewer_keywords:
- CBasePane [MFC], AccNotifyObjectFocusEvent
- CBasePane [MFC], AddPane
- CBasePane [MFC], AdjustDockingLayout
- CBasePane [MFC], AdjustLayout
- CBasePane [MFC], CalcFixedLayout
- CBasePane [MFC], CanAcceptPane
- CBasePane [MFC], CanAutoHide
- CBasePane [MFC], CanBeAttached
- CBasePane [MFC], CanBeClosed
- CBasePane [MFC], CanBeDocked
- CBasePane [MFC], CanBeResized
- CBasePane [MFC], CanBeTabbedDocument
- CBasePane [MFC], CanFloat
- CBasePane [MFC], CanFocus
- CBasePane [MFC], CopyState
- CBasePane [MFC], CreateDefaultMiniframe
- CBasePane [MFC], CreateEx
- CBasePane [MFC], DockPane
- CBasePane [MFC], DockPaneUsingRTTI
- CBasePane [MFC], DockToFrameWindow
- CBasePane [MFC], DoesAllowDynInsertBefore
- CBasePane [MFC], EnableDocking
- CBasePane [MFC], EnableGripper
- CBasePane [MFC], FloatPane
- CBasePane [MFC], get_accHelpTopic
- CBasePane [MFC], get_accSelection
- CBasePane [MFC], GetCaptionHeight
- CBasePane [MFC], GetControlBarStyle
- CBasePane [MFC], GetCurrentAlignment
- CBasePane [MFC], GetDockingMode
- CBasePane [MFC], GetDockSiteFrameWnd
- CBasePane [MFC], GetEnabledAlignment
- CBasePane [MFC], GetMFCStyle
- CBasePane [MFC], GetPaneIcon
- CBasePane [MFC], GetPaneRow
- CBasePane [MFC], GetPaneStyle
- CBasePane [MFC], GetParentDockSite
- CBasePane [MFC], GetParentMiniFrame
- CBasePane [MFC], GetParentTabbedPane
- CBasePane [MFC], GetParentTabWnd
- CBasePane [MFC], GetRecentVisibleState
- CBasePane [MFC], HideInPrintPreviewMode
- CBasePane [MFC], InsertPane
- CBasePane [MFC], IsAccessibilityCompatible
- CBasePane [MFC], IsAutoHideMode
- CBasePane [MFC], IsDialogControl
- CBasePane [MFC], IsDocked
- CBasePane [MFC], IsFloating
- CBasePane [MFC], IsHorizontal
- CBasePane [MFC], IsInFloatingMultiPaneFrameWnd
- CBasePane [MFC], IsMDITabbed
- CBasePane [MFC], IsPaneVisible
- CBasePane [MFC], IsPointNearDockSite
- CBasePane [MFC], IsResizable
- CBasePane [MFC], IsRestoredFromRegistry
- CBasePane [MFC], IsTabbed
- CBasePane [MFC], IsVisible
- CBasePane [MFC], LoadState
- CBasePane [MFC], MoveWindow
- CBasePane [MFC], OnAfterChangeParent
- CBasePane [MFC], OnBeforeChangeParent
- CBasePane [MFC], OnDrawCaption
- CBasePane [MFC], OnMovePaneDivider
- CBasePane [MFC], OnPaneContextMenu
- CBasePane [MFC], OnRemoveFromMiniFrame
- CBasePane [MFC], OnSetAccData
- CBasePane [MFC], PaneFromPoint
- CBasePane [MFC], RecalcLayout
- CBasePane [MFC], RemovePaneFromDockManager
- CBasePane [MFC], SaveState
- CBasePane [MFC], SelectDefaultFont
- CBasePane [MFC], SetControlBarStyle
- CBasePane [MFC], SetDockingMode
- CBasePane [MFC], SetPaneAlignment
- CBasePane [MFC], SetPaneStyle
- CBasePane [MFC], SetWindowPos
- CBasePane [MFC], ShowPane
- CBasePane [MFC], StretchPane
- CBasePane [MFC], UndockPane
- CBasePane [MFC], DoPaint
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 759ffd42b7de4d7f1922a95876a05ce4d3002dab
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337537"
---
# <a name="cbasepane-class"></a>CBasePane-Klasse
Basisklasse für alle Bereiche in MFC.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CBasePane::CBasePane`|Standardkonstruktor|  
|`CBasePane::~CBasePane`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CBasePane::accHitTest`|Wird durch das Framework aufgerufen, um das untergeordnete Element oder untergeordnete Objekt an einem bestimmten Punkt auf dem Bildschirm abzurufen. (Überschreibt [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CBasePane::accLocation`|Vom Framework aufgerufen, die die aktuelle Bildschirmposition des angegebenen Objekts abzurufen. (Überschreibt [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane` Diese Methode wird nicht verwendet werden.|  
|`CBasePane::accSelect`|Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben. (Überschreibt [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|Dock-Manager wird einen Bereich hinzugefügt.|  
|[Cbasepane:: Adjustdockinglayout](#adjustdockinglayout)|Leitet einen Aufruf Dock-Manager das docking-Layout anpassen.|  
|[Cbasepane:: Adjustlayout](#adjustlayout)|Vom Framework aufgerufen, wenn im Bereich des internen Layouts anpassen soll.|  
|[Cbasepane:: Calcfixedlayout](#calcfixedlayout)|Berechnet die horizontale Größe des eine Steuerleiste.|  
|[Cbasepane:: Canacceptpane](#canacceptpane)|Bestimmt, ob ein weiterer Bereich, in den Bereich angedockt werden kann.|  
|[CBasePane::CanAutoHide](#canautohide)|Bestimmt, ob der Bereich automatisch ausblendbaren-Modus unterstützt.|  
|[CBasePane::CanBeAttached](#canbeattached)|Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.|  
|[Cbasepane:: Canbeclosed](#canbeclosed)|Bestimmt, ob der Bereich geschlossen werden kann.|  
|[CBasePane::CanBeDocked](#canbedocked)|Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.|  
|[CBasePane::CanBeResized](#canberesized)|Bestimmt, ob der Bereich geändert werden kann.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|Gibt an, ob der Bereich in einer MDI-Dokumentfenster im Registerformat konvertiert werden kann.|  
|[CBasePane::CanFloat](#canfloat)|Bestimmt, ob der Bereich wechseln kann.|  
|[CBasePane::CanFocus](#canfocus)|Gibt an, ob der Bereich den Fokus erhalten kann.|  
|[CBasePane::CopyState](#copystate)|Kopiert den Status eines bestimmten Bereichs an.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Wenn der Bereich wechseln kann, erstellt ein Minirahmenfenster.|  
|[Cbasepane:: CreateEx](#createex)|Das Steuerelement wird erstellt.|  
|[Cbasepane:: Dockpane](#dockpane)|Dockt einen Bereich an, in einen anderen Bereich oder ein Rahmenfenster.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Dockt den Bereich mit der Laufzeit-Typeninformation an.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Dockt einen andockbaren Bereich in einen Datenrahmen an.|  
|[Cbasepane:: Doesallowdyninsertbefore](#doesallowdyninsertbefore)|Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem Bereich und den übergeordneten Frame eingefügt werden kann.|  
|[CBasePane::EnableDocking](#enabledocking)|Ermöglicht das Andocken des Bereichs zum Hauptframe auf.|  
|[CBasePane::EnableGripper](#enablegripper)|Aktiviert oder deaktiviert die ziehelements. Wenn ziehelements aktiviert ist, kann der Benutzer, um die Position im Bereichs ziehen.|  
|`CBasePane::FillWindowRect`|Wird intern verwendet.|  
|[CBasePane::FloatPane](#floatpane)|Wird im Bereich verschoben.|  
|`CBasePane::get_accChild`|Wird durch das Framework aufgerufen, um die Adresse einer `IDispatch`-Schnittstelle für das angegebene, untergeordnete Element abzurufen. (Überschreibt [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|Wird aufgerufen, durch das Framework, um die Anzahl der untergeordneten Elemente abzurufen, die zu diesem Objekt gehören. (Überschreibt [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|Wird aufgerufen, durch das Framework, um eine Zeichenfolge abzurufen, die die Standardaktion für das Objekt beschreibt. (Überschreibt [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt. (Überschreibt [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|Wird durch das Framework aufgerufen, um das Objekt abzurufen, das den Tastaturfokus hat. (Überschreibt [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|Wird aufgerufen, durch das Framework, um eine Zeichenfolge mit einer Hilfe für das Objekt abzurufen. (Überschreibt [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Wird aufgerufen, durch das Framework, um den vollständigen Pfad der WinHelp-Datei, die mit dem angegebenen Objekt zugeordnet ist und der Bezeichner des passenden Themas in der Datei abzurufen. (Überschreibt [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|Wird aufgerufen, durch das Framework die angegebene Tastenkombination für das Objekt abgerufen. (Überschreibt [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|Wird durch das Framework aufgerufen, um den Namen des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|Wird aufgerufen, durch das Framework zum Abrufen der `IDispatch` Schnittstelle für das übergeordnete Element des Objekts. (Überschreibt [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|Wird durch das Framework aufgerufen, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreiben. (Überschreibt [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|Wird durch das Framework aufgerufen, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen. (Überschreibt [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|Wird durch das Framework aufgerufen, um den aktuellen Status des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|Wird durch das Framework aufgerufen, um den Wert des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[Cbasepane:: Getcaptionheight](#getcaptionheight)|Gibt die Beschriftungshöhe zurück.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Gibt das Format des Steuerelements Leiste zurück.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Gibt die aktuelle Ausrichtung für den Bereich zurück.|  
|[Cbasepane:: Getdockingmode](#getdockingmode)|Gibt den aktuellen Andockmodus für den Bereich zurück.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Gibt einen Zeiger auf das Fenster, das für den Bereich der DockPosition ist.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Gibt zurück, die CBRS_ALIGN_-Stile, die in den Bereich angewendet werden.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|Gibt die Stile im Bereich der speziell mit MFC zurück.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|Gibt ein Handle auf das Symbol "Bereich" zurück.|  
|`CBasePane::GetPaneRect`|Wird intern verwendet.|  
|[CBasePane::GetPaneRow](#getpanerow)|Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem der Bereich angedockt ist.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|Gibt den Bereichsformat zurück.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|Gibt einen Zeiger an den übergeordneten Dock-Standort.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Gibt einen Zeiger auf das übergeordnete Minirahmenfenster.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Gibt einen Zeiger auf die übergeordnete Seite im Registerformat.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|Gibt einen Zeiger für das übergeordnete Fenster, das auf einer Registerkarte zurück.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Das Framework ruft diese Methode auf, wenn ein Bereich aus einem Archiv wiederhergestellt wird.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Gibt an, ob der Bereich, in der Seitenansicht angezeigt ausgeblendet ist.|  
|[CBasePane::InsertPane](#insertpane)|Registriert den angegebenen Bereich beim Dock-Manager.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Gibt an, ob im Bereich Active Accessibility unterstützt.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|Bestimmt, ob ein Bereich im Modus "automatisch ausblenden".|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|Gibt an, ob der Bereich ein dialogsteuerelement ist.|  
|[CBasePane::IsDocked](#isdocked)|Bestimmt, ob der Bereich angedockt ist.|  
|[CBasePane::IsFloating](#isfloating)|Bestimmt, ob der Bereich unverankert ist.|  
|[CBasePane::IsHorizontal](#ishorizontal)|Bestimmt, ob der Bereich horizontal angedockt ist.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|Bestimmt, ob der Bereich einen untergeordneten MDI-Fensters als ein Dokument im Registerkartenformat hinzugefügt wurde.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|Gibt an, ob für den Bereich der WS_VISIBLE-Flag festgelegt ist.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob ein angegebene Punkt befindet sich in der Nähe der DockPosition.|  
|[Cbasepane:: isResizable](#isresizable)|Bestimmt, ob der Bereich geändert werden kann.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Bestimmt, ob der Bereich aus der Registrierung wiederhergestellt wird.|  
|[CBasePane::IsTabbed](#istabbed)|Bestimmt, ob der Bereich im Registerkarten-Steuerelement von einem Fenster im Registerkartenformat eingefügt wurde.|  
|`CBasePane::IsTooltipTopmost`|Wird intern verwendet.|  
|[CBasePane::IsVisible](#isvisible)|Bestimmt, ob der Bereich angezeigt wird.|  
|[CBasePane::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung.|  
|[CBasePane::MoveWindow](#movewindow)|Verschiebt den Bereich an.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Vom Framework aufgerufen, wenn der Bereich der übergeordneten geändert wurde.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Wird vom Framework aufgerufen, kurz bevor der Bereich des übergeordneten Fensters ändert.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|Das Framework ruft diese Methode auf, wenn die Beschriftung gezeichnet wird.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|Diese Methode wird derzeit nicht verwendet werden.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Vom Framework aufgerufen, wenn es sich um ein Menü erstellt, die eine Liste von Bereichen.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Vom Framework aufgerufen, wenn ein Bereich von übergeordneten Mini-Frame-Fensters entfernt wird.|  
|[Cbasepane:: Onsetaccdata](#onsetaccdata)|`CBasePane` Diese Methode wird nicht verwendet werden.|  
|`CBasePane::OnUpdateCmdUI`|Wird intern verwendet.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|`CBasePane::PreTranslateMessage`|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane` Diese Methode wird nicht verwendet werden.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung für eines Bereichs, und entfernt sie aus der Liste im Dock-Manager.|  
|[CBasePane::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Wählt die Standardschriftart für einen angegebenen Gerätekontext.|  
|`CBasePane::Serialize`|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Legt das Format des Steuerelements Leiste fest.|  
|[CBasePane::SetDockingMode](#setdockingmode)|Legt den Andockmodus für den Bereich fest.|  
|`CBasePane::SetMDITabbed`|Wird intern verwendet.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|Legt die Ausrichtung für den Bereich fest.|  
|`CBasePane::SetPaneRect`|Wird intern verwendet.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|Legt den Stil des Bereichs.|  
|`CBasePane::SetRestoredFromRegistry`|Wird intern verwendet.|  
|[CBasePane::SetWindowPos](#setwindowpos)|Ändert die Größe, Position und Z-Reihenfolge eines Bereichs an.|  
|[CBasePane::ShowPane](#showpane)|Zeigt an, oder blendet den Bereich aus.|  
|[Cbasepane:: Stretchpane](#stretchpane)|Streckt einen Bereich vertikal oder horizontal.|  
|[CBasePane::UndockPane](#undockpane)|Entfernt den Bereich aus der DockPosition, Standard-Schieberegler oder ein Minirahmenfenster, in dem sie zurzeit angedockt wird.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|Füllt den Hintergrund des Bereichs an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine Klasse im Bereich zu erstellen, die den erweiterten in MFC verfügbare docking-Features unterstützt werden sollen, müssen Sie leiten Sie ihn von `CBasePane` oder [CPane-Klasse](../../mfc/reference/cpane-class.md).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgende Anpassungstipps beziehen sich auf die `CBasePane Class` und alle Klassen, die von dieser erben:  
  
-   Wenn Sie einen Bereich erstellen, können Sie mehrere neue Stile anwenden:  
  
    - AFX_CBRS_FLOAT wird der Bereich "float".  
  
    - AFX_CBRS_AUTOHIDE ermöglicht, automatisch ausgeblendet wird.  
  
    - AFX_CBRS_CLOSE können im Bereich (ausgeblendet) geschlossen werden.  
  
     Hierbei handelt es sich um Flags an, denen Sie mit einer bitweisen OR-Operation kombinieren können.  
  
 `CBasePane` implementiert die folgenden virtuellen booleschen Methoden entsprechend der folgenden Flags: [cbasepane:: Canbeclosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Sie können diese in abgeleiteten Klassen zum Anpassen ihres Verhaltens überschreiben.  
  
-   Sie können Andockverhalten anpassen, indem das Überschreiben [cbasepane:: Canacceptpane](#canacceptpane). Müssen Sie Ihrem Bereich "," false "von dieser Methode, um zu verhindern, dass ein weiterer Bereich, Andocken zurückgeben.  
  
-   Wenn Sie den Bereich "erstellen" einen statische, die darf nicht "float" und einen beliebigen anderen Bereich, der verhindert, dass vor dem Andocken (ähnlich wie die Outlook-Leiste in der OutlookDemo-Beispiel), erstellen Sie ihn als unverankerte und außer Kraft setzen möchten [cbasepane:: Doesallowdyninsertbefore](#doesallowdyninsertbefore) "false" zurückgegeben. Die Standardimplementierung gibt "false" zurück, wenn im Bereich ohne den Stil AFX_CBRS_FLOAT erstellt wird.  
  
-   Erstellen Sie alle Bereiche mit IDs ungleich-1.  
  
-   Verwenden Sie zum Bestimmen der Sichtbarkeit der Bereich [CBasePane::IsVisible](#isvisible). Er verarbeitet ordnungsgemäß den Sichtbarkeitszustand im Registerkartenformat und Automatisches Ausblenden von Modi.  
  
-   Wenn Sie einen unverankerte mit veränderbarer Größe Bereich erstellen möchten, erstellen Sie ihn ohne das AFX_CBRS_FLOAT-Stil, und rufen [CFrameWnd:: DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
-   Ein docking-Layout ein Bereichs ausschließen oder eine Symbolleiste in der Leiste Dock entfernen, rufen [CBasePane::UndockPane](#undockpane). Rufen Sie diese Methode nicht auf, für die Bereiche im Modus "automatisch ausblenden" oder für Bereiche, die sich auf die Registerkarten von Fenstern im Registerkartenformat befinden.  
  
-   Wenn Sie "float möchten" oder lösen einen Bereich, der im Modus "automatisch ausblenden" befindet, müssen Sie aufrufen [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) mit "false" als erstes Argument vor dem Aufruf [CBasePane::FloatPane](#floatpane) oder [ CBasePane::UndockPane](#undockpane).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CBasePane` Klasse. Das Beispiel veranschaulicht das Abrufen von einem Bereich von der `CFrameWndEx` -Klasse und zum Festlegen der Andockmodus, die im Bereich Ausrichtung und den Stil. Der Code stammt aus dem [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbasepane.h  
  
##  <a name="accnotifyobjectfocusevent"></a>  CBasePane::AccNotifyObjectFocusEvent  
 `CBasePane` Diese Methode wird nicht verwendet werden.  
  
```  
virtual void AccNotifyObjectFocusEvent(int);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Int*  
 Nicht verwendet.  
  
##  <a name="addpane"></a>  CBasePane::AddPane  
 Dock-Manager wird einen Bereich hinzugefügt.  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pBar*  
 Ein Zeiger auf einen Bereich hinzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine Hilfsmethode, die einen Bereich zu einem Dock-Manager hinzufügt. Mithilfe dieser Methode müssen Sie keinen Code schreiben, der den Typ des übergeordneten Rahmens analysiert.  
  
 Weitere Informationen finden Sie unter [CDockingManager-Klasse](../../mfc/reference/cdockingmanager-class.md) und [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).  
  
##  <a name="adjustdockinglayout"></a>  Cbasepane:: Adjustdockinglayout  
 Leitet einen Aufruf Dock-Manager das docking-Layout anpassen.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] *Hdwp*  
 Ein Handle für eine Struktur mit mehreren Fensterpositionen.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine bequeme Methode, die das docking-Layout angepasst wird. Mithilfe dieser Methode müssen Sie keinen Code schreiben, der den Typ des übergeordneten Rahmens analysiert.  
  
 Weitere Informationen finden Sie unter [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>  Cbasepane:: Adjustlayout  
 Wird aufgerufen, durch das Framework anpassen, das interne Layout eines Bereichs.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich hat das interne Layout anpassen. Die grundlegende Implementierung hat keine Auswirkung.  
  
##  <a name="calcfixedlayout"></a>  Cbasepane:: Calcfixedlayout  
 Berechnet die horizontale Größe des eine Steuerleiste.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bStretch*  
 Gibt an, ob die Leiste, auf die Größe des Rahmens gestreckt wird. Die *bStretch* Parameter ungleich NULL ist, wenn die Leiste keine andockleiste (nicht verfügbar für Andocken) und 0, ist wenn es angedockt oder unverankert ist (zum Andocken verfügbar).  
  
 [in] *bHorz*  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die *bHorz* Parameter ungleich NULL ist, wenn die Leiste horizontal ausgerichtet und 0, ist wenn es vertikal ausgerichtet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Steuerleiste Größe, in Pixel, der eine `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter die Hinweisen im Abschnitt [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>  Cbasepane:: Canacceptpane  
 Bestimmt, ob ein weiterer Bereich, in den Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pBar*  
 Ein Zeiger auf den Bereich anzudocken.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein weiterer Bereich akzeptiert werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor angedockt im Bereich gemäß wird *pBar* in den aktuellen Bereich.  
  
 Verwenden Sie diese Methode und die [CBasePane::CanBeDocked](#canbedocked) Methode zum Steuern, wie Andocken von Bereichen auf andere Bereiche in Ihrer Anwendung.  
  
 Die Standardimplementierung gibt "false" zurück.  
  
##  <a name="canautohide"></a>  CBasePane::CanAutoHide  
 Bestimmt, ob der Bereich automatisch ausblendbaren-Modus unterstützt.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn dieser Bereich automatisch ausblendbaren-Modus unterstützt. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um zu bestimmen, ob der Bereich automatisch ausblendbaren-Modus unterstützt.  
  
 Sie können diese Möglichkeit während der Erstellung festlegen, indem das AFX_CBRS_AUTOHIDE-Flag übergeben [cbasepane:: CreateEx](#createex).  
  
 Die standardmäßige Implementierung überprüft, ob das AFX_CBRS_AUTOHIDE-Flag. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um dieses Verhalten zu ändern.  
  
##  <a name="canbeattached"></a>  CBasePane::CanBeAttached  
 Bestimmt, ob der Bereich zu einem anderen Bereich oder der Zielframe, Fenster angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich zu einem anderen Bereich oder der Zielframe, Fenster angedockt werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt "false" zurück. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren die Möglichkeit, ohne Andocken [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="canbeclosed"></a>  Cbasepane:: Canbeclosed  
 Bestimmt, ob der Bereich geschlossen werden kann.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich geschlossen werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Bereich geschlossen werden kann. Wenn die Methode "true" zurückgibt. eine **schließen** Schaltfläche auf der Titelleiste des Bereichs hinzugefügt wird oder, wenn der Bereich auf der Titelleiste des Bereichs Minirahmenfenster unverankert ist.  
  
 Sie können diese Möglichkeit während der Erstellung festlegen, indem das AFX_CBRS_CLOSE-Flag übergeben [cbasepane:: CreateEx](#createex).  
  
 Die standardmäßige Implementierung überprüft, ob das AFX_CBRS_CLOSE-Flag.  
  
##  <a name="canbedocked"></a>  CBasePane::CanBeDocked  
 Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDockBar*  
 Ein Zeiger auf einen anderen Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn in diesem Bereich in einen anderen Bereich angedockt werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor angedockt im Bereich gemäß wird *pDockBar* in den aktuellen Bereich.  
  
 Verwenden Sie diese Methode und die [cbasepane:: Canacceptpane](#canacceptpane) Methode zum Steuern, wie Andocken von Bereichen auf andere Bereiche in Ihrer Anwendung.  
  
 Die Standardimplementierung gibt "false" zurück.  
  
##  <a name="canberesized"></a>  CBasePane::CanBeResized  
 Bestimmt, ob der Bereich geändert werden kann.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn im Bereich angepasst werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft, für das AFX_CBRS_RESIZE-Flag, das standardmäßig in angegeben wird `CBasePane::OnCreate`. Wenn dieses Flag nicht angegeben ist, kennzeichnet Dock-Manager im Bereich, der intern als angedockt. dann unbeweglicher an.  
  
##  <a name="canbetabbeddocument"></a>  CBasePane::CanBeTabbedDocument  
 Gibt an, ob der Bereich in einer MDI-Dokumentfenster im Registerformat konvertiert werden kann.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann. andernfalls "false". `CBasePane::CanBeTabbedDocument` Gibt immer "false" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Nur Objekte von bestimmten `CBasePane`-abgeleiteten Typen, z. B. die [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md), Dokumente im Registerformat konvertiert werden können.  
  
##  <a name="canfloat"></a>  CBasePane::CanFloat  
 Bestimmt, ob der Bereich wechseln kann.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich wechseln kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Bereich wechseln kann.  
  
 Sie können diese Möglichkeit während der Erstellung festlegen, indem das AFX_CBRS_FLOAT-Flag übergeben [cbasepane:: CreateEx](#createex).  
  
> [!NOTE]
>  Das Framework wird davon ausgegangen, dass unverankerte Bereiche statisch sind und ihre Andockstatus nicht ändern kann. Aus diesem Grund werden in das Framework den andockzustand unverankerte Bereiche nicht gespeichert.  
  
 Die standardmäßige Implementierung überprüft, ob der AFX_CBRS_FLOAT-Stil.  
  
##  <a name="canfocus"></a>  CBasePane::CanFocus  
 Gibt an, ob der Bereich den Fokus erhalten kann.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich den Fokus erhalten kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse den Fokus zu steuern. Z. B. weil Symbolleisten keinen Fokus erhalten können, diese Methode gibt FALSE zurück, wenn sie für Symbolleistenobjekte von aufgerufen wird.  
  
 Das Framework versucht, die den Eingabefokus festgelegt, wenn ein Bereich angedockt oder abgedockt wird.  
  
##  <a name="copystate"></a>  CBasePane::CopyState  
 Kopiert den Status eines bestimmten Bereichs an.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pOrgBar*  
 Ein Zeiger auf einen anderen Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Zustand von *pOrgBar* in diesen Bereich.  
  
##  <a name="createdefaultminiframe"></a>  CBasePane::CreateDefaultMiniframe  
 Wenn der Bereich wechseln kann, erstellt diese Methode ein Minirahmenfenster dafür an.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *RectInitial*  
 Gibt die Anfangskoordinaten des das Minirahmenfenster an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neue Minirahmenfenster oder NULL, wenn Fehler beim Erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich in einen unverankerten Zustand wechselt. Die Methode erstellt ein Minirahmenfenster und fügt den Bereich an dieses Fenster.  
  
 Die Standardimplementierung gibt NULL zurück.  
  
##  <a name="createex"></a>  Cbasepane:: CreateEx  
 Das Steuerelement wird erstellt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle=0,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwStyleEx*  
 Die erweiterten Stile (finden Sie unter [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) Informationen).  
  
 [in] *"lpszclassname"*  
 Der Klassenname des Fensters.  
  
 [in] *LpszWindowName*  
 Der Fenstername.  
  
 [in] *DwStyle*  
 Der Fensterstil (finden Sie unter [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).  
  
 [in] *Rect*  
 Das ursprüngliche Rechteck.  
  
 [in] *pParentWnd*  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] *nID*  
 Gibt den Bereich-ID an. Muss eindeutig sein.  
  
 [in] *DwControlBarStyle*  
 Formatflags für Bereiche.  
  
 [in] *"pContext"*  
 Ein Zeiger auf `CcreateContext`  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich wurde erfolgreich erstellt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Fenster der Klasse `lpszClassName`. Wenn Sie WS_CAPTION angeben, wird diese Methode löscht styl WS_CAPTION-bit- und legt diese fest `CBasePane::m_bHasCaption` auf "true", da die Bibliothek Bereiche mit Untertiteln nicht unterstützt.  
  
 Sie können eine beliebige Kombination von untergeordneten Window-Stile und MFC-Steuerleiste (CBRS_) Formatvorlagen verwenden.  
  
 Die Bibliothek fügt mehrere neue Stile für Bereiche hinzu. Die folgende Tabelle beschreibt die neuen Formate:  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|AFX_CBRS_FLOAT|Es kann im Bereich "float".|  
|AFX_CBRS_AUTOHIDE|Im Bereich unterstützt den Modus "automatisch ausblenden"|  
|AFX_CBRS_RESIZE|Der Bereich kann geändert werden. **Wichtig:** dieses Format ist nicht implementiert.|  
|AFX_CBRS_CLOSE|Der Bereich kann geschlossen werden.|  
|AFX_CBRS_AUTO_ROLLUP|Der Bereich kann gemacht werden, wenn es gleitet.|  
|AFX_CBRS_REGULAR_TABS|Wenn Sie einen Bereich in einen anderen Bereich angedockt, das dieser Stil verfügt, wird ein Fenster für den reguläres im Registerkartenformat erstellt. (Weitere Informationen finden Sie unter [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md).)|  
|AFX_CBRS_OUTLOOK_TABS|Wenn Sie einen Bereich in einen anderen Bereich angedockt, das dieser Stil verfügt, wird eine Outlook-Stil-Fenster im Registerkartenformat erstellt. (Weitere Informationen finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 Um die neue Stile zu verwenden, geben Sie sie in *DwControlBarStyle*.  
  
##  <a name="dockpane"></a>  Cbasepane:: Dockpane  
 Dockt einen Bereich an, in einen anderen Bereich oder ein Rahmenfenster.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDockBar*  
 Ein Zeiger auf einen anderen Bereich.  
  
 [in] *LpRect*  
 Gibt an, das Zielrechteck.  
  
 [in] *DockMethod*  
 Gibt die docking-Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Steuerleiste erfolgreich angedockt ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Bereich an einen anderen Bereich oder einer Leiste Dock andocken ( [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)) angegebenen *pDockBar*, oder um einen Hauptframe Wenn *pDockBar* ist NULL.  
  
 *DockMethod* gibt an, wie der Bereich angedockt ist. Finden Sie unter [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) eine Liste von möglichen Werten.  
  
##  <a name="dockpaneusingrtti"></a>  CBasePane::DockPaneUsingRTTI  
 Dockt den Bereich mit der Laufzeit-Typeninformation an.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bUseDockSite*  
 True gibt an, docken Sie an den Standort andocken. False gibt an, docken Sie an den übergeordneten Rahmen.  
  
##  <a name="docktoframewindow"></a>  CBasePane::DockToFrameWindow  
 Dockt einen andockbaren Bereich in einen Datenrahmen an.  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwAlignment*  
 Die Seite des übergeordneten Rahmens, die Sie im Bereich, um andocken möchten.  
  
 [in] *LpRect*  
 Die gewünschte Größe.  
  
 [in] *DwDockFlags*  
 Ignoriert.  
  
 [in] *pRelativeBar*  
 Ignoriert.  
  
 [in] *nRelativeIndex*  
 Ignoriert.  
  
 [in] *bOuterEdge*  
 Wenn "true", und es andere andockbare Bereiche auf der Seite, die anhand des sind *DwAlignment*, der Bereich angedockt ist, außerhalb von den anderen Bereichen, näher an den Rand des übergeordneten Rahmens. Wenn "FALSE" ist der Bereich in der Mitte des Clientbereichs näher angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Methode erfolgreich war. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn auf einen bereichsteiler ( [CPaneDivider-Klasse](../../mfc/reference/cpanedivider-class.md)) kann nicht erstellt werden. Andernfalls gibt immer "true" zurück.  
  
##  <a name="doesallowdyninsertbefore"></a>  Cbasepane:: Doesallowdyninsertbefore  
 Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem Bereich und den übergeordneten Frame eingefügt werden kann.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn ein Benutzer einen anderen Bereich einfügen kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob ein Benutzer dynamisch einen Bereich aus, bevor Sie in diesem Bereich einfügen kann.  
  
 Nehmen wir beispielsweise an, dass Ihre Anwendung einen Bereich angedockt, die auf der linken Seite des Rahmens (z. B. der Outlook-Leiste) erstellt. Um zu verhindern, dass den Benutzer einen anderen Bereich auf der linken Seite des Bereichs erste andocken, überschreiben diese Methode, und gibt "false".  
  
 Es wird empfohlen, dass Sie diese Methode überschreiben, und geben Sie "false" zurück, für unverankerte Bereiche abgeleitet [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).  
  
 Die Standardimplementierung gibt "true" zurück.  
  
##  <a name="dopaint"></a>  CBasePane::DoPaint  
 Füllt den Hintergrund des Bereichs an.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Ruft den aktuellen visual-Manager, um den Hintergrund aufzufüllen ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="enabledocking"></a>  CBasePane::EnableDocking  
 Ermöglicht das Andocken des Bereichs zum Hauptframe auf.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwAlignment*  
 Gibt die andockbare Ausrichtung zu aktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Andocken Ausrichtung zum Hauptframe zu ermöglichen. Sie können eine Kombination von Flags für CBRS_ALIGN_ übergeben (Weitere Informationen finden Sie unter [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking` das interne Flag `CBasePane::m_dwEnabledAlignment` und das Framework prüft dieses Flag an, wenn Sie ein Bereich angedockt ist.  
  
 Rufen Sie [CBasePane::GetEnabledAlignment](#getenabledalignment) um die Ausrichtung des andockbaren für einen Bereich zu ermitteln.  
  
##  <a name="enablegripper"></a>  CBasePane::EnableGripper  
 Aktiviert oder deaktiviert die ziehelements. Wenn ziehelements aktiviert ist, kann der Benutzer, um die Position im Bereichs ziehen.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 TRUE ziehelements aktiviert. "False", um ihn zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode zum Aktivieren eines ziehelements statt mit dem WS_CAPTION-Stil.  
  
##  <a name="floatpane"></a>  CBasePane::FloatPane  
 Wird im Bereich verschoben.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *RectFloat*  
 Gibt die Bildschirmkoordinaten der unverankerten Bereichs klicken, wobei angezeigt wird.  
  
 [in] *DockMethod*  
 Gibt die Dock-Methode zu verwenden, um den Bereich "float".  
  
 [in] *bShow*  
 Gibt an, ob der unverankerten Bereichs klicken sichtbar (TRUE) oder ausgeblendet (FALSE).  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich erfolgreich abgedockt wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich an der Bildschirmposition, angegeben durch "float" *RectFloat*.  
  
##  <a name="get_acchelptopic"></a>  CBasePane::get_accHelpTopic  
 Das Framework ruft diese Methode, um den vollständigen Pfad der Abrufen der **WinHelp** -Datei, die das angegebene Objekt und den Bezeichner des passenden Themas in der Datei zugeordnet ist.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PszHelpFile*  
 Adresse des BSTR, das den vollständigen Pfad der empfängt die **WinHelp** -Datei, die das angegebene Objekt zugeordnet ist, sofern vorhanden.  
  
 [in] *VarChild*  
 Gibt an, ob das Hilfethema abgerufen werden sollen, die das Objekt oder eine der untergeordneten Elemente des Objekts ist. Dieser Parameter kann entweder CHILDID_SELF (um ein Hilfethema für das Objekt zu erhalten) oder eine ID des untergeordneten Elements (um ein Hilfethema für eines der untergeordneten Elemente des Objekts zu erhalten) sein.  
  
 [in] *PidTopic*  
 Identifiziert die **Hilfe** Thema, das mit dem angegebenen Objekt verknüpft ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `CBasePane` Diese Methode implementiert nicht. Aus diesem Grund `CBasePane::get_accHelpTopic` immer gibt S_FALSE zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der Active Accessibility-Unterstützung in MFC. Überschreiben Sie diese Funktion in einer abgeleiteten Klasse, um Hilfeinformationen zu Ihr Objekt bereitzustellen.  
  
##  <a name="get_accselection"></a>  CBasePane::get_accSelection  
 Das Framework ruft diese Methode, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PvarChildren*  
 Empfängt, die den ausgewählten, untergeordneten Elemente identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 `CBasePane` Diese Methode implementiert nicht. Wenn *PvarChildren* NULL ist, diese Methode wird E_INVALIDARG zurückgegeben. Andernfalls gibt diese Methode DISP_E_MEMBERNOTFOUND zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der Active Accessibility-Unterstützung in MFC. Überschreiben Sie diese Funktion in einer abgeleiteten Klasse, wenn Sie nicht im Fenstermodus Elemente der Benutzeroberfläche als fensterlose ActiveX-Steuerelemente haben.  
  
##  <a name="getcaptionheight"></a>  Cbasepane:: Getcaptionheight  
 Gibt die Beschriftungshöhe zurück.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Überschriftenhöhe.  
  
##  <a name="getcontrolbarstyle"></a>  CBasePane::GetControlBarStyle  
 Gibt das Format des Steuerelements Leiste zurück.  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise OR-Kombination AFX_CBRS_-Flags.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert ist eine Kombination aus den folgenden möglichen Werten.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|AFX_CBRS_FLOAT|Stellt die Steuerelement-Leiste "float".|  
|AFX_CBRS_AUTOHIDE|Ermöglicht das automatische Ausblenden Modus.|  
|AFX_CBRS_RESIZE|Ermöglicht das Ändern der Größe der Steuerleiste. Wenn dieses Flag festgelegt ist, kann die Steuerleiste in einen andockbaren Bereich platziert werden.|  
|AFX_CBRS_CLOSE|Ermöglicht das Ausblenden der Steuerleiste.|  
  
##  <a name="getcurrentalignment"></a>  CBasePane::GetCurrentAlignment  
 Gibt die aktuelle Ausrichtung für den Bereich zurück.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Ausrichtung der Steuerleiste. Die folgende Tabelle zeigt die möglichen Werte:  
  
|Wert|Ausrichtung|  
|-----------|---------------|  
|CBRS_ALIGN_LEFT|Linksbündige Ausrichtung.|  
|CBRS_ALIGN_RIGHT|Rechtsbündige Ausrichtung.|  
|CBRS_ALIGN_TOP|Ausrichtung oben.|  
|CBRS_ALIGN_BOTTOM|Unten ausrichten.|  
  
##  <a name="getdockingmode"></a>  Cbasepane:: Getdockingmode  
 Gibt den aktuellen Andockmodus für den Bereich zurück.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 DT_STANDARD, wenn den Bereich ziehen, wird auf dem Bildschirm durch einem Rechteck angezeigt. DT_IMMEDIATE, wenn der Inhalt des Bereichs gezogen werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den aktuellen Andockmodus des Bereichs zu bestimmen.  
  
 Wenn `CBasePane::m_dockMode` ist nicht definiert (DT_UNDEFINED,), und klicken Sie dann der Andockmodus aus der globalen Andockmodus entnommen wird, (`AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 Durch Festlegen von *M_dockMode* oder überschreiben `GetDockingMode` können Sie steuern, den Andockmodus für jeden Bereich.  
  
##  <a name="getdocksiteframewnd"></a>  CBasePane::GetDockSiteFrameWnd  
 Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem der Bereich angedockt ist.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die DockPosition des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Zeiger auf die DockPosition des Bereichs abzurufen. Der DockPosition kann entweder ein Hauptrahmenfenster, wenn der Bereich zum Hauptframe angedockt ist, oder ein Minirahmenfenster sein, wenn der Bereich unverankert ist.  
  
##  <a name="getenabledalignment"></a>  CBasePane::GetEnabledAlignment  
 Gibt zurück, die CBRS_ALIGN_-Stile, die in den Bereich angewendet werden.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von CBRS_ALIGN_ Stile. Die folgende Tabelle zeigt die möglichen Formate:  
  
|Flag|Aktivierte Ausrichtung|  
|----------|-----------------------|  
|CBRS_ALIGN_LEFT|"Left".|  
|CBRS_ALIGN_RIGHT|Richting.|  
|CBRS_ALIGN_TOP|Nach oben.|  
|CBRS_ALIGN_BOTTOM|Nach unten.|  
|CBRS_ALIGN_ANY|Die Kombination aller Flags.|  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Ausrichtung aktiviert, für den Bereich zu ermitteln. Aktivierte Ausrichtung bedeutet, dass die Seiten des Hauptrahmenfenster, dem an ein Bereich angedockt werden kann.  
  
 Aktivieren Sie docking-Ausrichtung mit [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="getmfcstyle"></a>  CBasePane::GetMFCStyle  
 Gibt zurück, die im Bereich Formate, die mit MFC spezifisch sind.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination der Bibliothek spezifischen (AFX_CBRS_) im Bereich Formate.  
  
##  <a name="getpaneicon"></a>  CBasePane::GetPaneIcon  
 Gibt ein Handle auf das Symbol "Bereich" zurück.  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bBigIcon*  
 Gibt ein 32 Pixel von Symbol "32 Pixel" bei "true" an. Gibt eine 16-Pixel 16 Pixel großes Symbol, wenn "false".  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Symbol "Bereich". Wenn Fehler auftreten, gibt NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).  
  
##  <a name="getpanerow"></a>  CBasePane::GetPaneRow  
 Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem der Bereich angedockt ist.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf `CDockingPanesRow` ist der Bereich angedockt oder NULL, wenn sie unverankert ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für den Zugriff auf die Zeile, in dem ein Bereich angedockt ist. Zum Beispiel aufrufen, um die Bereiche in einer bestimmten Zeile anzuordnen, `GetPaneRow` und rufen dann [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).  
  
##  <a name="getpanestyle"></a>  CBasePane::GetPaneStyle  
 Gibt den Bereichsformat zurück.  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Leiste Steuerelementstile (einschließlich CBRS_ Stile), die festgelegt wurde, indem die [CBasePane::SetPaneStyle](#setpanestyle) Methode zum Zeitpunkt der Erstellung.  
  
##  <a name="getparentdocksite"></a>  CBasePane::GetParentDockSite  
 Gibt einen Zeiger an den übergeordneten Dock-Standort.  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der übergeordnete DockPosition.  
  
##  <a name="getparentminiframe"></a>  CBasePane::GetParentMiniFrame  
 Gibt einen Zeiger auf das übergeordnete Minirahmenfenster.  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bNoAssert*  
 Bei "true", überprüft diese Methode nicht für ungültigen Zeiger. Wenn Sie diese Methode aufrufen, wenn die Anwendung beendet wird, legen Sie diesen Parameter auf "true" fest.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf das übergeordnete Minirahmenfenster, wenn der Bereich unverankert ist; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf das übergeordnete Minirahmenfenster abzurufen. Diese Methode durchläuft alle übergeordneten Elemente und Überprüfungen für ein Objekt von [CPaneFrameWnd-Klasse](../../mfc/reference/cpaneframewnd-class.md).  
  
 Verwendung `GetParentMiniFrame` zu bestimmen, ob der Bereich unverankert ist.  
  
##  <a name="getparenttabbedpane"></a>  CBasePane::GetParentTabbedPane  
 Gibt einen Zeiger auf die übergeordnete Seite im Registerformat.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Seite im Registerformat falls vorhanden; andernfalls NULL.  
  
##  <a name="getparenttabwnd"></a>  CBasePane::GetParentTabWnd  
 Gibt einen Zeiger für das übergeordnete Fenster, das auf einer Registerkarte zurück.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] *hWndTab*  
 Wenn der zurückgegebene Wert nicht NULL ist, enthält dieser Parameter das Handle für das übergeordnete Fenster im Registerkartenformat.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf den übergeordneten-Fenster im Registerkartenformat oder NULL.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Zeiger auf das übergeordnete Fenster im Registerkartenformat abzurufen. Manchmal ist es nicht genügend aufzurufende `GetParent`, weil ein Bereich in einen andockbaren Wrapper sein kann ( [CDockablePaneAdapter-Klasse](../../mfc/reference/cdockablepaneadapter-class.md)) oder innerhalb eines Adapters im Bereich ( [CDockablePaneAdapter-Klasse](../../mfc/reference/cdockablepaneadapter-class.md)). Mithilfe von `GetParentTabWnd` einen gültigen Zeiger in diesen Fällen (vorausgesetzt, dass das übergeordnete Element ein Fenster im Registerkartenformat ist) abrufen können.  
  
##  <a name="getrecentvisiblestate"></a>  CBasePane::GetRecentVisibleState  
 Das Framework ruft diese Methode auf, wenn ein Bereich aus einem Archiv wiederhergestellt wird.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der den aktuelle sichtbaren Zustand angibt. Bei "true", wurde der Bereich sichtbar, wenn serialisiert und angezeigt, wenn wiederhergestellt werden. False gibt an, wurde der Bereich ausgeblendet, wenn es sich bei serialisiert und ausgeblendet werden soll, wenn wiederhergestellt.  
  
##  <a name="hideinprintpreviewmode"></a>  CBasePane::HideInPrintPreviewMode  
 Gibt an, ob der Bereich, in der Seitenansicht angezeigt ausgeblendet ist.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich nicht in der Seitenansicht angezeigt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Grundlegende Bereiche werden nicht in der Seitenansicht angezeigt. Aus diesem Grund gibt diese Methode immer "true" zurück.  
  
##  <a name="insertpane"></a>  CBasePane::InsertPane  
 Registriert den angegebenen Bereich beim Dock-Manager.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pControlBar*  
 Ein Zeiger auf den Bereich eingefügt.  
  
 [in] *pTarget*  
 Ein Zeiger auf angrenzenden Bereich.  
  
 [in] *bNach*  
 True gibt an, *pControlBar* eingefügt wird, nach dem *pTarget*. False gibt an, *pControlBar* eingefügt wird, bevor Sie *pTarget*.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Methode erfolgreich ist; FALSE andernfalls.  
  
##  <a name="isaccessibilitycompatible"></a>  CBasePane::IsAccessibilityCompatible  
 Gibt an, ob im Bereich Active Accessibility unterstützt.  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn im Bereich Active Accessibility unterstützt. andernfalls "false".  
  
##  <a name="isautohidemode"></a>  CBasePane::IsAutoHideMode  
 Bestimmt, ob ein Bereich im Modus "automatisch ausblenden".  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich in den Modus "automatisch ausblenden" ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Grundlegende Bereiche können nicht automatisch im Hintergrund. Diese Methode gibt immer "false" zurück.  
  
##  <a name="isdialogcontrol"></a>  CBasePane::IsDialogControl  
 Gibt an, ob der Bereich ein Dialogfeld-Steuerelement ist.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich ein Dialogfeld-Steuerelement. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode zur Gewährleistung der Konsistenz von Layout für alle Bereiche.  
  
##  <a name="isdocked"></a>  CBasePane::IsDocked  
 Bestimmt, ob der Bereich angedockt ist.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn das übergeordnete Element des Bereichs keiner Minirahmenfensters ist, oder wenn der Bereich in einem kleinen Frame mit einem anderen Bereich unverankert ist. andernfalls "false".  
  
##  <a name="isfloating"></a>  CBasePane::IsFloating  
 Bestimmt, ob der Bereich unverankert ist.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich unverankert ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt den entgegengesetzten Wert von [CBasePane::IsDocked](#isdocked).  
  
##  <a name="ishorizontal"></a>  CBasePane::IsHorizontal  
 Bestimmt, ob der Bereich horizontal angedockt ist.  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich horizontal angedockt ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung überprüft die aktuelle Ausrichtung CBRS_ORIENT_HORZ andocken.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CBasePane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist ( [CMultiPaneFrameWnd-Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich in einem Fenster mit mehreren Rahmen. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können in einem Multipane-Rahmenfenster "float". Aus diesem Grund `CBasePane::IsInFloatingMultiPaneFrameWnd` gibt immer "false" zurück.  
  
##  <a name="ismditabbed"></a>  CBasePane::IsMDITabbed  
 Bestimmt, ob der Bereich einen untergeordneten MDI-Fensters als ein Dokument im Registerkartenformat hinzugefügt wurde.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich einen untergeordneten MDI-Fensters als ein Dokument im Registerkartenformat hinzugefügt wurde. andernfalls "false".  
  
##  <a name="ispanevisible"></a>  CBasePane::IsPaneVisible  
 Gibt an, ob für den Bereich der WS_VISIBLE-Flag festgelegt ist.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn Sie WS_VISIBLE festgelegt ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBasePane::IsVisible](#isvisible) Bereich Sichtbarkeit zu bestimmen.  
  
##  <a name="ispointneardocksite"></a>  CBasePane::IsPointNearDockSite  
 Bestimmt, ob ein angegebene Punkt befindet sich in der Nähe der DockPosition.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *zeigen*  
 Der angegebene Punkt.  
  
 [out] *DwBarAlignment*  
 Gibt an, welchen Rand, in der Nähe der Punkt ist. Mögliche Werte sind CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP und CBRS_ALIGN_BOTTOM  
  
 [out] *bOuterEdge*  
 True, wenn der Punkt in der Nähe von der äußere Rahmen der DockPosition ist. "False" andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Punkt in der Nähe der DockPosition ist. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt ist in der Nähe der DockPosition, wenn es innerhalb der Vertraulichkeit, die im Dock-Manager festgelegt ist. Die Vertraulichkeit der Standardwert ist 15 Pixel.  
  
##  <a name="isresizable"></a>  Cbasepane:: isResizable  
 Bestimmt, ob der Bereich geändert werden kann.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich vom Benutzer angepasst werden kann. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Bereiche des [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) geändert werden kann.  
  
 Die Statusleiste ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) und die Dock-Leiste ( [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)) kann nicht geändert werden.  
  
##  <a name="isrestoredfromregistry"></a>  CBasePane::IsRestoredFromRegistry  
 Bestimmt, ob der Bereich aus der Registrierung wiederhergestellt wird.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich aus der Registrierung wiederhergestellt wird. andernfalls "false".  
  
##  <a name="istabbed"></a>  CBasePane::IsTabbed  
 Bestimmt, ob der Bereich im Registerkarten-Steuerelement von einem Fenster im Registerkartenformat eingefügt wurde.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Steuerleiste auf einer Registerkarte der ein Fenster im Registerkartenformat eingefügt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft einen Zeiger auf das unmittelbar übergeordnete Element und bestimmt, ob Runtime-Klasse des übergeordneten Elements ist [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
##  <a name="isvisible"></a>  CBasePane::IsVisible  
 Bestimmt, ob der Bereich angezeigt wird.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Bereich angezeigt wird. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Bestimmen der Sichtbarkeit eines Bereichs an. Verwenden Sie nicht `::IsWindowVisible`.  
  
 Wenn der Bereich nicht im Registerkartenformat ist (finden Sie unter [CBasePane::IsTabbed](#istabbed)), diese Methode überprüft, für das WS_VISIBLE-Format. Wenn der Bereich im Registerkartenformat ist, überprüft diese Methode die Sichtbarkeit des übergeordneten Fensters im Registerkartenformat. Wenn das übergeordnete Fenster sichtbar ist, wird die Funktion überprüft die Sichtbarkeit der Registerkarte für den Bereich über [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).  
  
##  <a name="loadstate"></a>  CBasePane::LoadState  
 Lädt den Zustand des Bereichs aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszProfileName*  
 Profilname.  
  
 [in] *nIndex*  
 Profil-Index.  
  
 [in] *UiID*  
 Im Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Zustand des Bereichs erfolgreich geladen wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Zustand des Bereichs in der Registrierung geladen werden. Überschreiben Sie diese in einer abgeleiteten Klasse zum Laden der zusätzliche Informationen, die von gespeicherten [CBasePane::SaveState](#savestate).  
  
##  <a name="movewindow"></a>  CBasePane::MoveWindow  
 Verschiebt den Bereich an.  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Rect*  
 Ein Rechteck, das Festlegen der neuen Position und die Größe des Bereichs.  
  
 [in] *bRepaint*  
 Bei "true", wird der Bereich neu gezeichnet werden. Wenn "FALSE" ist der Bereich nicht neu gezeichnet.  
  
 [in] *Hdwp*  
 Handle für eine verzögerte Fenster Position-Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine verzögerte Fenster Position-Struktur, oder NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie NULL als übergeben die *Hdwp* Parameter, die diese Methode verschiebt das Fenster Normal. Wenn Sie ein Handle übergeben, führt diese Methode eine verzögerte Fenster verschieben. Sie erhalten ein Handle durch Aufrufen von [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) oder durch Speichern den Rückgabewert von einem vorherigen Aufruf dieser Methode.  
  
##  <a name="onafterchangeparent"></a>  CBasePane::OnAfterChangeParent  
 Wird vom Framework aufgerufen, nach im Bereich der übergeordneten Änderungen.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndOldParent*  
 Ein Zeiger auf das vorherige übergeordnete Element.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode nach im Bereich der übergeordneten, in der Regel aufgrund eines andockbaren "oder" Gleitkomma-Vorgangs ändert.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="onbeforechangeparent"></a>  CBasePane::OnBeforeChangeParent  
 Wird vom Framework aufgerufen, kurz bevor der Bereich des übergeordneten Fensters ändert.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndNewParent*  
 Ein Zeiger auf eine neue übergeordnete Fenster.  
  
 [in] *bDelay*  
 Gibt an, ob es sich bei Layout-Anpassungen, die verzögert werden müssen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode direkt vor den Bereich der übergeordneten Änderungen in der Regel aufgrund einer andocken, Gleitkomma- oder automatisch im Hintergrund-Vorgang.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="ondrawcaption"></a>  CBasePane::OnDrawCaption  
 Das Framework ruft diese Methode auf, wenn die Beschriftung gezeichnet wird.  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode hat keine Funktion für die `CBasePane` Klasse.  
  
##  <a name="onmovepanedivider"></a>  CBasePane::OnMovePaneDivider  
 Diese Methode wird derzeit nicht verwendet werden.  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CPaneDivider\**  
 Nicht verwendet.  
  
##  <a name="onpanecontextmenu"></a>  CBasePane::OnPaneContextMenu  
 Vom Framework aufgerufen, wenn es sich um ein Menü erstellt, die eine Liste von Bereichen.  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pParentFrame*  
 Ein Zeiger auf den übergeordneten Rahmen.  
  
 [in] *zeigen*  
 Gibt den Speicherort des Kontextmenüs.  
  
### <a name="remarks"></a>Hinweise  
 `OnPaneContextMenu` Ruft die Dock-Manager, der die Liste der Bereiche verwaltet werden, die an das aktuelle Rahmenfenster gehören. Diese Methode fügt die Namen der Bereiche in einem Kontextmenü Menüelemente hinzu, und es wird angezeigt. Die Befehle im Menü anzeigen oder Ausblenden von einzelnen Bereiche.  
  
 Überschreiben Sie diese Methode, um dieses Verhalten anpassen.  
  
##  <a name="onremovefromminiframe"></a>  CBasePane::OnRemoveFromMiniFrame  
 Vom Framework aufgerufen, wenn ein Bereich von übergeordneten Mini-Frame-Fensters entfernt wird.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pMiniFrame*  
 Ein Zeiger auf ein Minirahmenfenster, das aus dem Bereich entfernt wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich aus der übergeordneten Minirahmenfenster (aufgrund der Dockingstation, z. B.) entfernt wird.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="onsetaccdata"></a>  Cbasepane:: Onsetaccdata  
 `CBasePane` Diese Methode wird nicht verwendet werden.  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *lVal*  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt immer "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="panefrompoint"></a>  CBasePane::PaneFromPoint  
 Gibt den Bereich, der den angegebenen Punkt enthält.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *zeigen*  
 Gibt den Punkt in Bildschirmkoordinaten, um zu überprüfen.  
  
 [in] *nSensitivity*  
 Erhöhen Sie den Suchbereich, um diesen Betrag. Ein Bereich ist die Suchkriterien erfüllt, fällt die der angegebene Punkt in der höheren Bereich.  
  
 [in] *bExactBar*  
 "True", ignoriert der *nSensitivity* Parameter ist, andernfalls FALSE.  
  
 [in] *pRTCBarType*  
 Wenn nicht NULL ist, sucht die Methode nur Bereiche des angegebenen Typs.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CBasePane`-abgeleitete Objekt, das die angegebenen Punkt enthält, oder NULL, wenn kein Bereich gefunden wurde.  
  
##  <a name="recalclayout"></a>  CBasePane::RecalcLayout  
 `CBasePane` Diese Methode wird nicht verwendet werden.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>  CBasePane::RemovePaneFromDockManager  
 Hebt die Registrierung für eines Bereichs, und entfernt sie aus der Liste im Dock-Manager.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pBar*  
 Ein Zeiger auf einen Bereich entfernt werden soll.  
  
 [in] *bDestroy*  
 Wenn "true", Bereich entfernte zerstört wird.  
  
 [in] *bAdjustLayout*  
 True gibt an, passen Sie sofort das docking-Layout.  
  
 [in] *bAutoHide*  
 Bei "true", bezieht sich das docking-Layout der Liste der automatisch im Hintergrund Balken. False gibt an, bezieht sich das docking-Layout auf die Liste der regulären Bereiche.  
  
 [in] *pBarReplacement*  
 Ein Zeiger auf einen Bereich, der Bereich entfernten ersetzt.  
  
##  <a name="savestate"></a>  CBasePane::SaveState  
 Speichert den Zustand des Bereichs in der Registrierung.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszProfileName*  
 Profilname.  
  
 [in] *nIndex*  
 Profil-Index.  
  
 [in] *UiID*  
 Im Bereich-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn der Zustand erfolgreich gespeichert wurde. andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode beim Speichern den Zustand des Bereichs in der Registrierung. Außer Kraft setzen `SaveState` in einer abgeleiteten Klasse, um weitere Informationen zu speichern.  
  
##  <a name="selectdefaultfont"></a>  CBasePane::SelectDefaultFont  
 Wählt die Standardschriftart für einen angegebenen Gerätekontext.  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Einen Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Standardwert [CFont-Klasse](../../mfc/reference/cfont-class.md) Objekt.  
  
##  <a name="setcontrolbarstyle"></a>  CBasePane::SetControlBarStyle  
 Legt das Format des Steuerelements Leiste fest.  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwNewStyle*  
 Eine bitweise OR-Kombination folgende Werte möglich.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|AFX_CBRS_FLOAT|Stellt die Steuerelement-Leiste "float".|  
|AFX_CBRS_AUTOHIDE|Ermöglicht das automatische Ausblenden Modus.|  
|AFX_CBRS_RESIZE|Ermöglicht das Ändern der Größe der Steuerleiste. Wenn dieses Flag festgelegt ist, kann die Steuerleiste in einen andockbaren Bereich platziert werden.|  
|AFX_CBRS_CLOSE|Ermöglicht das Ausblenden der Steuerleiste.|  
  
##  <a name="setdockingmode"></a>  CBasePane::SetDockingMode  
 Legt den Andockmodus für den Bereich fest.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DockModeNew*  
 Gibt den neuen Andockmodus für den Bereich an.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework unterstützt zwei andockbare Modi: standard und sofort.  
  
 In den Modus "standard andocken" werden Bereiche und Minirahmenfenster verschoben mit einem Rechteck. In der unmittelbaren Andockmodus werden Schiebeleisten-Steuerelemente und Minirahmenfenster sofort mit ihrem Kontext verschoben.  
  
 Der Andockmodus ist anfangs Global von definiert [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Sie können festlegen, dass den Andockmodus für jeden Bereich einzeln mithilfe der `SetDockingMode` Methode.  
  
##  <a name="setpanealignment"></a>  CBasePane::SetPaneAlignment  
 Legt die Ausrichtung für den Bereich fest.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwAlignment*  
 Gibt die neue Ausrichtung.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel ruft das Framework diese Methode, wenn ein Bereich von einer Seite des Hauptframe auf einen anderen angedockt ist.  
  
 Die folgende Tabelle zeigt die möglichen Werte für *DwAlignment*:  
  
|Wert|Ausrichtung|  
|-----------|---------------|  
|CBRS_ALIGN_LEFT|Linksbündige Ausrichtung.|  
|CBRS_ALIGN_RIGHT|Rechtsbündige Ausrichtung.|  
|CBRS_ALIGN_TOP|Ausrichtung oben.|  
|CBRS_ALIGN_BOTTOM|Unten ausrichten.|  
  
##  <a name="setpanestyle"></a>  CBasePane::SetPaneStyle  
 Legt den Stil des Bereichs.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwNewStyle*  
 Gibt das neue Format festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, die CBRS_-Formatvorlagen festlegen, die in afxres.h definiert sind. Da der Stil und der Bereich Ausrichtung zusammen gespeichert werden, legen Sie die neue Formatvorlage durch die Kombination mit der aktuellen Ausrichtung wie folgt.  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="setwindowpos"></a>  CBasePane::SetWindowPos  
 Ändert die Größe, Position und Z-Reihenfolge eines Bereichs an.  
  
```  
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndInsertAfter*  
 Identifiziert die `CWnd` -Objekt, das vor dieser `CWnd` Objekt in der Z-Reihenfolge. Weitere Informationen finden Sie unter [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] *x*  
 Gibt die Position der linken Seite des Fensters.  
  
 [in] *y*  
 Gibt die Position des oberen Rand des Fensters.  
  
 [in] *Cx*  
 Gibt die Breite des Fensters.  
  
 [in] *cy*  
 Gibt die Höhe des Fensters.  
  
 [in] *nFlags*  
 Gibt Optionen für Größe und Position. Weitere Informationen finden Sie unter [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] *Hdwp*  
 Handle für eine Struktur, die Größe und Position für ein oder mehrere Fenster enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine aktualisierte verzögerte Fenster Position-Struktur, oder NULL.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *pWndInsertAfter* NULL ist, ruft diese Methode [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Wenn *pWndInsertAfter* ist nicht NULL ist, ruft diese Methode `DeferWindowPos`.  
  
##  <a name="showpane"></a>  CBasePane::ShowPane  
 Zeigt an, oder blendet den Bereich aus.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bShow*  
 Gibt an, ob anzeigen (TRUE) oder ausblenden (FALSE), einen Bereich.  
  
 [in] *bDelay*  
 Bei "true", wird das Layout des Docks Neuberechnen verzögert.  
  
 [in] *bActivate*  
 Bei "true", ist der Bereich aktiv, wenn Sie angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode blendet oder aus einem Bereich. Verwenden Sie diese Methode anstelle von `ShowWindow` , da diese Methode die relevanten docking-Manager zu Änderungen in den Bereich, Sichtbarkeit benachrichtigt.  
  
 Verwendung [CBasePane::IsVisible](#isvisible) zum Bestimmen der aktuellen Sichtbarkeit eines Bereichs.  
  
##  <a name="stretchpane"></a>  Cbasepane:: Stretchpane  
 Streckt einen Bereich vertikal oder horizontal.  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nLength*  
 Die Länge, um stretch-Bereich.  
  
 [in] *bHoriz*  
 True gibt an, der den Bereich vertikal gestreckt. False gibt an, stretch-Bereich horizontal.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Bereichs gestreckt werden soll.  
  
##  <a name="undockpane"></a>  CBasePane::UndockPane  
 Entfernt den Bereich aus der DockPosition, Standard-Schieberegler oder ein Minirahmenfenster, in dem sie zurzeit angedockt wird.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bDelay*  
 Bei "true", wird das docking-Layout nicht sofort neu berechnet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Zustand des Bereichs zu ändern oder Layout des Docks Bereich ausgeschlossen.  
  
 Wenn Sie weiterhin diesen Bereich verwenden möchten, rufen Sie entweder [cbasepane:: Dockpane](#dockpane) oder [CBasePane::FloatPane](#floatpane) vor dem Aufrufen dieser Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)
