---
title: CBasePane Klasse | Microsoft Docs
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
ms.openlocfilehash: 74e8909a86a9382121dc2dc3375d12ed828c8c88
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957467"
---
# <a name="cbasepane-class"></a>CBasePane-Klasse
Die Basisklasse für alle Bereiche in MFC.  
  
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
|`CBasePane::accLocation`|Wird aufgerufen, durch das Framework, um die aktuelle Bildschirmposition des angegebenen Objekts abzurufen. (Überschreibt [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane` Diese Methode wird nicht verwendet werden.|  
|`CBasePane::accSelect`|Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben. (Überschreibt [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|Dock-Manager wird einen Bereich hinzugefügt.|  
|[Cbasepane:: Adjustdockinglayout](#adjustdockinglayout)|Leitet einen Aufruf Dock-Manager am Layout des Docks anpassen.|  
|[Cbasepane:: Adjustlayout](#adjustlayout)|Vom Framework aufgerufen, wenn der Bereich das interne Layout angepasst.|  
|[Cbasepane:: Calcfixedlayout](#calcfixedlayout)|Berechnet die horizontale Größe einer Steuerleiste.|  
|[Cbasepane:: Canacceptpane](#canacceptpane)|Bestimmt, ob es sich bei einem anderen Bereich in den Bereich angedockt werden kann.|  
|[CBasePane::CanAutoHide](#canautohide)|Bestimmt, ob der Bereich automatisch im Hintergrund-Modus unterstützt.|  
|[CBasePane::CanBeAttached](#canbeattached)|Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.|  
|[Cbasepane:: Canbeclosed](#canbeclosed)|Bestimmt, ob der Bereich geschlossen werden kann.|  
|[CBasePane::CanBeDocked](#canbedocked)|Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.|  
|[CBasePane::CanBeResized](#canberesized)|Bestimmt, ob der Bereich, dessen Größe angepasst werden kann.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|Gibt an, ob der Bereich in einer MDI-Dokumentfenster im Registerformat konvertiert werden kann.|  
|[CBasePane::CanFloat](#canfloat)|Bestimmt, ob im Bereich verschieben kann.|  
|[CBasePane::CanFocus](#canfocus)|Gibt an, ob der Bereich den Fokus erhalten kann.|  
|[CBasePane::CopyState](#copystate)|Kopiert den Status eines bestimmten Bereichs an.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Wenn der Bereich float kann, erstellt ein Minirahmenfenster.|  
|[Cbasepane:: CreateEx](#createex)|Erstellt das Bereichssteuerelement an.|  
|[Cbasepane:: Dockpane](#dockpane)|Dockt einen Bereich an, zu einem anderen Bereich oder einem Rahmenfenster.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Dockt den Bereich mit der Laufzeit-Typeninformation an.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Dockt einen andockbaren Bereich mit einem Frame an.|  
|[Cbasepane:: Doesallowdyninsertbefore](#doesallowdyninsertbefore)|Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem Bereich und den übergeordneten Frame eingefügt werden kann.|  
|[CBasePane::EnableDocking](#enabledocking)|Ermöglicht das Andocken des Bereichs zum Hauptframe.|  
|[CBasePane::EnableGripper](#enablegripper)|Aktiviert oder deaktiviert die Ziehpunkte. Wenn ziehelements aktiviert ist, kann der Benutzer es um die Position im Bereichs zu ziehen.|  
|`CBasePane::FillWindowRect`|Wird intern verwendet.|  
|[CBasePane::FloatPane](#floatpane)|Gleitkommazahlen im Bereich an.|  
|`CBasePane::get_accChild`|Wird durch das Framework aufgerufen, um die Adresse einer `IDispatch`-Schnittstelle für das angegebene, untergeordnete Element abzurufen. (Überschreibt [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|Wird aufgerufen, durch das Framework, um die Anzahl der untergeordneten Elemente abzurufen, die zu diesem Objekt gehören. (Überschreibt [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|Wird aufgerufen, durch das Framework um eine Zeichenfolge abzurufen, die die Standardaktion des Objekts beschreibt. (Überschreibt [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt. (Überschreibt [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|Wird durch das Framework aufgerufen, um das Objekt abzurufen, das den Tastaturfokus hat. (Überschreibt [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|Wird aufgerufen, durch das Framework eine Zeichenfolge mit einer Hilfe für das Objekt abgerufen. (Überschreibt [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Wird aufgerufen, durch das Framework, um den vollständigen Pfad der WinHelp-Datei, die das angegebene Objekt zugeordnet ist und der Bezeichner des passenden Themas in der Datei abzurufen. (Überschreibt [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|Wird aufgerufen, durch das Framework die angegebenen Tastenkombination für das Objekt abgerufen. (Überschreibt [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|Wird durch das Framework aufgerufen, um den Namen des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|Wird aufgerufen, durch das Framework zum Abrufen der `IDispatch` Schnittstelle für das übergeordnete Element des Objekts. (Überschreibt [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|Wird durch das Framework aufgerufen, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreiben. (Überschreibt [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|Wird durch das Framework aufgerufen, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen. (Überschreibt [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|Wird durch das Framework aufgerufen, um den aktuellen Status des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|Wird durch das Framework aufgerufen, um den Wert des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[Cbasepane:: Getcaptionheight](#getcaptionheight)|Gibt die Beschriftungshöhe zurück.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Gibt das Format des Steuerelements Leiste zurück.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Gibt den aktuellen Bereich Ausrichtung zurück.|  
|[Cbasepane:: Getdockingmode](#getdockingmode)|Gibt den aktuellen Andockmodus für den Bereich zurück.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Gibt einen Zeiger auf das Fenster, für den Bereich der DockPosition.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Gibt die CBRS_ALIGN_-Formate, die in den Bereich angewendet werden.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|Gibt die Stile Bereich bestimmte mit MFC zurück.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|Gibt ein Handle auf das Symbol "Bereich" zurück.|  
|`CBasePane::GetPaneRect`|Wird intern verwendet.|  
|[CBasePane::GetPaneRow](#getpanerow)|Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem der Bereich angedockt ist.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|Gibt den Schriftschnitt Bereich.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|Gibt einen Zeiger auf den übergeordneten Andocken Standort an.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Gibt einen Zeiger auf das übergeordnete Minirahmenfenster.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Gibt einen Zeiger auf die übergeordnete Seite im Registerformat.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|Gibt einen Zeiger auf das übergeordnete Fenster, das innerhalb einer Registerkarte liegt.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Das Framework ruft diese Methode ein Bereich aus einem Archiv wiederhergestellt wird.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Gibt an, ob der Bereich in der Seitenansicht ausgeblendet ist.|  
|[CBasePane::InsertPane](#insertpane)|Registriert den angegebenen Bereich beim Dock-Manager.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Gibt an, ob der Bereich Active Accessibility unterstützt.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|Bestimmt, ob ein Bereich in den automatischen Ausblendemodus.|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|Gibt an, ob der Bereich ein dialogsteuerelement ist.|  
|[CBasePane::IsDocked](#isdocked)|Bestimmt, ob der Bereich angedockt ist.|  
|[CBasePane::IsFloating](#isfloating)|Bestimmt, ob der Bereich unverankert ist.|  
|[CBasePane::IsHorizontal](#ishorizontal)|Bestimmt, ob der Bereich horizontal angedockt ist.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|Bestimmt, ob der Bereich ein untergeordnetes MDI-Fenster als ein Dokument im Registerkartenformat hinzugefügt wurde.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|Gibt an, ob die `WS_VISIBLE` -Flag wird festgelegt, für den Bereich.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob ein angegebener Punkt in der Nähe der DockPosition ist.|  
|[Cbasepane:: isResizable](#isresizable)|Bestimmt, ob der Bereich, dessen Größe angepasst werden kann.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Bestimmt, ob der Bereich aus der Registrierung wiederhergestellt wird.|  
|[CBasePane::IsTabbed](#istabbed)|Bestimmt, ob der Bereich im Registerkarten-Steuerelement ein Fenster im Registerkartenformat eingefügt wurde.|  
|`CBasePane::IsTooltipTopmost`|Wird intern verwendet.|  
|[CBasePane::IsVisible](#isvisible)|Bestimmt, ob der Bereich angezeigt wird.|  
|[CBasePane::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung.|  
|[CBasePane::MoveWindow](#movewindow)|Verschiebt den Bereich an.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Vom Framework aufgerufen, wenn der Bereich übergeordneten geändert wurde.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Wird vom Framework aufgerufen, kurz bevor die Änderungen des übergeordneten Fensters.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|Das Framework ruft diese Methode auf, wenn der Titel gezeichnet wird.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|Diese Methode wird derzeit nicht verwendet.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Vom Framework aufgerufen, wenn sie ein Menü erstellt, das eine Liste von Bereichen verfügt.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Vom Framework aufgerufen, wenn ein Bereich aus seiner übergeordneten Mini-Rahmenfensters entfernt wird.|  
|[Cbasepane:: Onsetaccdata](#onsetaccdata)|`CBasePane` Diese Methode wird nicht verwendet werden.|  
|`CBasePane::OnUpdateCmdUI`|Wird intern verwendet.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|`CBasePane::PreTranslateMessage`|Wird von der [CWinApp](../../mfc/reference/cwinapp-class.md) -Klasse verwendet, um Fenstermeldungen zu übersetzen, bevor diese an die Windows-Funktionen [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) gesendet werden. (Überschreibt [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane` Diese Methode wird nicht verwendet werden.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung auf einen Bereich, und entfernt es aus der Liste im Dock-Manager.|  
|[CBasePane::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Wählt die Standardschriftart für einen angegebenen Gerätekontext.|  
|`CBasePane::Serialize`|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Legt das Format des Steuerelements Balken an.|  
|[CBasePane::SetDockingMode](#setdockingmode)|Legt den Andockmodus für den Bereich an.|  
|`CBasePane::SetMDITabbed`|Wird intern verwendet.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|Legt die Ausrichtung für den Bereich an.|  
|`CBasePane::SetPaneRect`|Wird intern verwendet.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|Legt das Format des Bereichs.|  
|`CBasePane::SetRestoredFromRegistry`|Wird intern verwendet.|  
|[CBasePane::SetWindowPos](#setwindowpos)|Ändert die Größe, Position und Z-Reihenfolge eines Bereichs an.|  
|[CBasePane::ShowPane](#showpane)|Zeigt an, oder blendet den Bereich aus.|  
|[Cbasepane:: Stretchpane](#stretchpane)|Streckt einen Bereich vertikal oder horizontal.|  
|[CBasePane::UndockPane](#undockpane)|Entfernt den Bereich aus der DockPosition, Standard-Schieberegler, bzw. Minirahmenfenster, wo sie derzeit angedockt ist.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|Füllt den Hintergrund des Bereichs an.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie möchten eine Bereich-Klasse erstellen, die die erweiterten andockbaren Merkmale, die in MFC unterstützt, leiten Sie ihn von `CBasePane` oder [CPane-Klasse](../../mfc/reference/cpane-class.md).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgenden Anpassungstipps beziehen sich auf die `CBasePane Class` und alle Klassen, die von ihm erben:  
  
-   Wenn Sie einen Bereich erstellen, können Sie mehrere neue Stile anwenden:  
  
    - `AFX_CBRS_FLOAT` Stellt den Bereich "float".  
  
    - `AFX_CBRS_AUTOHIDE` ermöglicht das automatischen Ausblendemodus.  
  
    - `AFX_CBRS_CLOSE` ermöglicht der Bereich (ausgeblendet) geschlossen werden.  
  
     Hierbei handelt es sich um Flags an, denen Sie mit einer bitweisen OR-Operation kombinieren können.  
  
 `CBasePane` implementiert die folgenden virtuellen booleschen Methoden entsprechend dieser Flags: [cbasepane:: Canbeclosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Sie können sie in abgeleiteten Klassen zum Anpassen des Verhaltens zu überschreiben.  
  
-   Sie können Andockverhalten anpassen, indem überschreiben [cbasepane:: Canacceptpane](#canacceptpane). Haben Sie Ihrem Bereich "zurück" `FALSE` aus dieser Methode, um zu verhindern, dass ein weiterer Bereich, andocken.  
  
-   Wenn Sie einen statischen Bereich, die float kann nicht und einen beliebigen anderen Bereich, der verhindert, dass vor dem Andocken (ähnlich wie der Outlook-Leiste in der OutlookDemo-Beispiel) erstellen, erstellen Sie ihn als unverankerte und außer Kraft setzen möchten [cbasepane:: Doesallowdyninsertbefore](#doesallowdyninsertbefore) zurückzugebenden `FALSE`. Gibt die standardmäßige Implementierung `FALSE` , wenn der Bereich, ohne erstellt wird die `AFX_CBRS_FLOAT` Stil.  
  
-   Erstellen Sie alle Bereiche mit IDs, jedoch nicht-1.  
  
-   Verwenden Sie zum Bestimmen der Sichtbarkeit Bereich [CBasePane::IsVisible](#isvisible). Er ordnungsgemäß behandelt den Sichtbarkeitszustand im Registerkartenformat und automatisch im Hintergrund Modi.  
  
-   Wenn Sie einen unverankerte in der Größe veränderbaren Bereich erstellen möchten, erstellen Sie ihn ohne die `AFX_CBRS_FLOAT` Stil und einem Aufruf [CFrameWnd:: DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
-   Rufen Sie eine andocklayout einen Bereich ausgeschlossen oder eine Symbolleiste in der Menüleiste Andocken entfernen, [CBasePane::UndockPane](#undockpane). Rufen Sie diese Methode nicht auf, Bereiche in den automatischen Ausblendemodus oder Bereiche, die sich auf den Registerkarten von Fenstern im Registerkartenformat befinden.  
  
-   Wenn Sie "float möchten" oder einen Bereich, der in den automatischen Ausblendemodus ist die Verankerung aufheben, müssen Sie aufrufen [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) mit `FALSE` als erstes Argument vor dem Aufruf [CBasePane::FloatPane](#floatpane) oder [ CBasePane::UndockPane](#undockpane).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CBasePane` Klasse. Im Beispiel veranschaulicht, wie einen Bereich von abzurufenden der `CFrameWndEx` Klasse und den Andockmodus, die im Bereich Ausrichtung und die Bereichsformat eingerichtet. Der Code stammt aus dem [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
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
 Dies ist eine bequeme Methode, die einen Bereich Dock-Manager hinzufügt. Mithilfe dieser Methode müssen Sie keinen Code schreiben, der den Typ des übergeordneten Frames analysiert.  
  
 Weitere Informationen finden Sie unter [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) und [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).  
  
##  <a name="adjustdockinglayout"></a>  Cbasepane:: Adjustdockinglayout  
 Leitet einen Aufruf Dock-Manager am Layout des Docks anpassen.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] *Hdwp*  
 Ein Handle für eine Struktur, die mehrere Fensterpositionen enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine bequeme Methode, die das andocklayout passt. Mithilfe dieser Methode müssen Sie keinen Code schreiben, der den Typ des übergeordneten Frames analysiert.  
  
 Weitere Informationen finden Sie unter [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>  Cbasepane:: Adjustlayout  
 Wird aufgerufen, durch das Framework das interne Layout eines Bereichs anpassen.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich wurde das interne Layout anpassen. Die basisimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="calcfixedlayout"></a>  Cbasepane:: Calcfixedlayout  
 Berechnet die horizontale Größe einer Steuerleiste.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bStretch*  
 Gibt an, ob die Leiste soll, auf die Größe des Frames gestreckt werden. Die *bStretch* Parameter ist ungleich NULL, wenn die Leiste keine andockleiste (nicht verfügbar für Andocken ist) und 0, ist wenn angedockt oder unverankert ist (zum Andocken verfügbar).  
  
 [in] *bHorz*  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die *bHorz* -Parameter ist ungleich NULL, wenn die Leiste horizontal ausgerichtet ist, und 0, ist wenn es vertikal ausgerichtet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Steuerleiste Größe, in Pixel, der eine `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter die Hinweisen im Abschnitt [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>  Cbasepane:: Canacceptpane  
 Bestimmt, ob es sich bei einem anderen Bereich in den Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pBar*  
 Ein Zeiger auf den Bereich angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie einen anderen Bereich akzeptiert werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode vor dem Bereich gemäß angedockt wird *pBar* in den aktuellen Bereich.  
  
 Verwenden Sie diese Methode und die [CBasePane::CanBeDocked](#canbedocked) Methode, um zu steuern, wie Bereiche auf andere Bereiche in der Anwendung andocken.  
  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
##  <a name="canautohide"></a>  CBasePane::CanAutoHide  
 Bestimmt, ob der Bereich automatisch im Hintergrund-Modus unterstützt.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn in diesem Bereich automatischen Ausblendemodus unterstützt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um zu bestimmen, ob der Bereich automatisch im Hintergrund-Modus unterstützt.  
  
 Sie können diese Fähigkeit durch Übergabe festlegen, während der Erstellung der `AFX_CBRS_AUTOHIDE` flag [cbasepane:: CreateEx](#createex).  
  
 Die standardmäßige Implementierung überprüft, ob die `AFX_CBRS_AUTOHIDE` Flag. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um dieses Verhalten anzupassen.  
  
##  <a name="canbeattached"></a>  CBasePane::CanBeAttached  
 Bestimmt, ob der Bereich in einem anderen Bereich oder der Zielframe, Fenster angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich kann, zu einem anderen Bereich oder der Zielframe, Fenster angedockt werden; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt `FALSE` zurück. Überschreiben Sie diese Methode in einer abgeleiteten Klasse aktiviert oder deaktiviert die Möglichkeit, ohne Aufruf Andocken [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="canbeclosed"></a>  Cbasepane:: Canbeclosed  
 Bestimmt, ob der Bereich geschlossen werden kann.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich geschlossen werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Bereich geschlossen werden kann. Wenn die-Methode zurückgibt `TRUE`, **schließen** Schaltfläche auf der Titelleiste des Bereichs hinzugefügt wird oder wenn der Bereich auf die Titelleiste des im Bereich Minirahmenfenster unverankert ist.  
  
 Sie können diese Fähigkeit durch Übergabe festlegen, während der Erstellung der `AFX_CBRS_CLOSE` flag [cbasepane:: CreateEx](#createex).  
  
 Die standardmäßige Implementierung überprüft, ob die `AFX_CBRS_CLOSE` Flag.  
  
##  <a name="canbedocked"></a>  CBasePane::CanBeDocked  
 Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDockBar*  
 Ein Zeiger auf einen anderen Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn zu einem anderen Bereich; in diesem Bereich angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode vor dem Bereich gemäß angedockt wird *pDockBar* in den aktuellen Bereich.  
  
 Verwenden Sie diese Methode und die [cbasepane:: Canacceptpane](#canacceptpane) Methode, um zu steuern, wie Bereiche auf andere Bereiche in der Anwendung andocken.  
  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
##  <a name="canberesized"></a>  CBasePane::CanBeResized  
 Bestimmt, ob der Bereich, dessen Größe angepasst werden kann.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich angepasst werden kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft die `AFX_CBRS_RESIZE` -Flag, das als Standardwert im angegebenen `CBasePane::OnCreate`. Wenn dieses Flag nicht angegeben ist, kennzeichnet Dock-Manager im Bereich intern als unbeweglichen statt es andocken.  
  
##  <a name="canbetabbeddocument"></a>  CBasePane::CanBeTabbedDocument  
 Gibt an, ob der Bereich in einer MDI-Dokumentfenster im Registerformat konvertiert werden kann.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann; andernfalls `FALSE`. `CBasePane::CanBeTabbedDocument` gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Nur Objekte bestimmter `CBasePane`-abgeleitete Typen, wie die [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md), Dokumente im Registerformat konvertiert werden kann.  
  
##  <a name="canfloat"></a>  CBasePane::CanFloat  
 Bestimmt, ob im Bereich verschieben kann.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich float kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob im Bereich verschieben kann.  
  
 Sie können diese Fähigkeit durch Übergabe festlegen, während der Erstellung der `AFX_CBRS_FLOAT` flag [cbasepane:: CreateEx](#createex).  
  
> [!NOTE]
>  Das Framework davon ausgegangen, dass unverankerte Bereiche statisch sind, dass ihre andockzustand ändern kann. Daher werden das Framework den andockzustand unverankerte Bereiche nicht gespeichert.  
  
 Die standardmäßige Implementierung überprüft, ob die `AFX_CBRS_FLOAT` Stil.  
  
##  <a name="canfocus"></a>  CBasePane::CanFocus  
 Gibt an, ob der Bereich den Fokus erhalten kann.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich den Fokus erhalten kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse den Fokus zu steuern. Z. B. weil Symbolleisten den Fokus erhalten können, gibt diese Methode `FALSE` Wenn es für Symbolleistenobjekte aufgerufen wird.  
  
 Das Framework versucht, den Eingabefokus festgelegt, wenn ein Bereich angedockt oder umfließt ist.  
  
##  <a name="copystate"></a>  CBasePane::CopyState  
 Kopiert den Status eines bestimmten Bereichs an.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pOrgBar*  
 Ein Zeiger auf einen anderen Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Zustand wird von *pOrgBar* in diesen Bereich.  
  
##  <a name="createdefaultminiframe"></a>  CBasePane::CreateDefaultMiniframe  
 Wenn der Bereich float kann, erstellt diese Methode ein Minirahmenfenster.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *RectInitial*  
 Gibt die Anfangskoordinaten des das Minirahmenfenster an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Minirahmenfenster oder `NULL` Wenn Fehler beim Erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich in einen unverankerten Zustand wechselt. Die Methode erstellt ein Minirahmenfenster und fügt den Bereich dieses Fenster.  
  
 Die Standardimplementierung gibt `NULL` zurück.  
  
##  <a name="createex"></a>  Cbasepane:: CreateEx  
 Erstellt das Bereichssteuerelement an.  
  
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
 Die erweiterten Stile (finden Sie unter [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) für Weitere Informationen).  
  
 [in] *LpszClassName*  
 Der Name der Fensterklasse.  
  
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
 `TRUE` Wenn der Bereich erfolgreich erstellt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Fenster der Klasse `lpszClassName`. Bei Angabe von `WS_CAPTION`, diese Methode löscht die `WS_CAPTION` Formatbit und legt `CBasePane::m_bHasCaption` zu `TRUE`, da die Bibliothek mit Untertiteln Bereiche nicht unterstützt.  
  
 Sie können eine beliebige Kombination von untergeordneten Fensterstile und MFC Steuerleiste Stile (CBRS_) verwenden.  
  
 Die Bibliothek fügt mehrere neue Stile für Bereiche. Die folgende Tabelle beschreibt die neuen Formate:  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Der Bereich kann float.|  
|`AFX_CBRS_AUTOHIDE`|Der Bereich unterstützt automatisch im Hintergrund-Modus.|  
|`AFX_CBRS_RESIZE`|Der Bereich kann geändert werden. **Wichtig:** dieser Stil ist nicht implementiert.|  
|`AFX_CBRS_CLOSE`|Der Bereich kann geschlossen werden.|  
|`AFX_CBRS_AUTO_ROLLUP`|Im Bereich kann Rollup werden, wenn er gleitet.|  
|`AFX_CBRS_REGULAR_TABS`|Wenn einem Bereich in einen anderen Bereich, die diesem Format aufweist angedockt, wird ein reguläres Fenster im Registerkartenformat erstellt. (Weitere Informationen finden Sie unter [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md).)|  
|`AFX_CBRS_OUTLOOK_TABS`|Wenn einem Bereich in einen anderen Bereich, die diesem Format aufweist angedockt, wird eine Outlook-Stil Fenster im Registerkartenformat erstellt. (Weitere Informationen finden Sie unter [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 Um die neuen Formate verwenden zu können, geben sie im *DwControlBarStyle*.  
  
##  <a name="dockpane"></a>  Cbasepane:: Dockpane  
 Dockt einen Bereich an, zu einem anderen Bereich oder einem Rahmenfenster.  
  
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
 Gibt die Zielrechtecks an.  
  
 [in] *DockMethod*  
 Gibt die Andock-Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Steuerleiste erfolgreich angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Bereich an einen anderen Bereich oder eine Leiste Andocken andocken ( [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)) angegebenen *pDockBar*, oder um einen Hauptframe Wenn *pDockBar* ist `NULL`.  
  
 *DockMethod* gibt an, wie der Bereich angedockt ist. Finden Sie unter [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) eine Liste der möglichen Werte.  
  
##  <a name="dockpaneusingrtti"></a>  CBasePane::DockPaneUsingRTTI  
 Dockt den Bereich mit der Laufzeit-Typeninformation an.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bUseDockSite*  
 Wenn `TRUE`, andocken, Andocken Standort. Wenn `FALSE`, an den übergeordneten Frame andocken.  
  
##  <a name="docktoframewindow"></a>  CBasePane::DockToFrameWindow  
 Dockt einen andockbaren Bereich mit einem Frame an.  
  
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
 Die Seite des übergeordneten Frames, die Sie im Bereich, um andocken möchten.  
  
 [in] *LpRect*  
 Die gewünschte Größe.  
  
 [in] *DwDockFlags*  
 Ignoriert.  
  
 [in] *pRelativeBar*  
 Ignoriert.  
  
 [in] *nRelativeIndex*  
 Ignoriert.  
  
 [in] *bOuterEdge*  
 Wenn `TRUE` und andere andockbare Bereiche auf der Seite gemäß *DwAlignment*, ist der Bereich außerhalb der anderen Bereichen angedockt näher an den Rand des übergeordneten Frames. Wenn `FALSE`, Bereich näher an das Rechenzentrum des Clientbereichs angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn eine bereichsteiler ( [CPaneDivider Klasse](../../mfc/reference/cpanedivider-class.md)) kann nicht erstellt werden. Andernfalls wird immer zurückgegeben `TRUE`.  
  
##  <a name="doesallowdyninsertbefore"></a>  Cbasepane:: Doesallowdyninsertbefore  
 Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem Bereich und den übergeordneten Frame eingefügt werden kann.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn ein Benutzer einen anderen Bereich eingefügt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob ein Benutzer dynamisch einen Bereich, bevor Sie in diesem Bereich eingefügt werden kann.  
  
 Nehmen Sie beispielsweise an, dass Ihre Anwendung einen Bereich angedockt auf der linken Seite des Rahmens (z. B. der Outlook-Leiste) erstellt. Um zu verhindern, dass den Benutzer einen anderen Bereich auf der linken Seite des Bereichs erste andocken, diese Methode überschreiben und zurückgeben `FALSE`.  
  
 Es wird empfohlen, dass Sie diese Methode überschreiben und zurückgeben `FALSE` für unverankerte Bereiche abgeleitet [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).  
  
 Die Standardimplementierung gibt `TRUE` zurück.  
  
##  <a name="dopaint"></a>  CBasePane::DoPaint  
 Füllt den Hintergrund des Bereichs an.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung Ruft die aktuellen visuellen Manager zum Ausfüllen ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="enabledocking"></a>  CBasePane::EnableDocking  
 Ermöglicht das Andocken des Bereichs zum Hauptframe.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwAlignment*  
 Gibt die andockbare Ausrichtung zu aktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um zum Hauptframe andockbaren Ausrichtung zu aktivieren. Sie können eine Kombination von übergeben `CBRS_ALIGN_` Flags (Weitere Informationen finden Sie unter [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking` Setzt den internen Flag `CBasePane::m_dwEnabledAlignment` und das Framework überprüft dieses Flag an, wenn ein Bereich angedockt wird.  
  
 Rufen Sie [CBasePane::GetEnabledAlignment](#getenabledalignment) um die Ausrichtung des andockbaren für einen Bereich zu bestimmen.  
  
##  <a name="enablegripper"></a>  CBasePane::EnableGripper  
 Aktiviert oder deaktiviert die Ziehpunkte. Wenn ziehelements aktiviert ist, kann der Benutzer es um die Position im Bereichs zu ziehen.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 `TRUE` So aktivieren Sie die Ziehpunkte; `FALSE` zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode zum Aktivieren eines ziehelements anstelle der `WS_CAPTION` Stil.  
  
##  <a name="floatpane"></a>  CBasePane::FloatPane  
 Gleitkommazahlen im Bereich an.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *RectFloat*  
 Gibt die Bildschirmkoordinaten, wo die Gleitkommazahl im Bereich angezeigt wird.  
  
 [in] *DockMethod*  
 Gibt die Dock-Methode zu verwenden, um den Bereich zu verschieben.  
  
 [in] *bShow*  
 Gibt an, ob der unverankerte Bereich angezeigt wird ( `TRUE`) oder ausgeblendet ( `FALSE`).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich erfolgreich umfließt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich an der vom angegebenen Bildschirmposition float *RectFloat*.  
  
##  <a name="get_acchelptopic"></a>  CBasePane::get_accHelpTopic  
 Das Framework ruft diese Methode, um den vollständigen Pfad des Abrufen der `WinHelp` -Datei, die das angegebene Objekt und der Bezeichner des passenden Themas in der Datei zugeordnet ist.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PszHelpFile*  
 Adresse der einen `BSTR` , die den vollständigen Pfad des empfängt die `WinHelp` -Datei, die das angegebene Objekt zugeordnet ist, sofern vorhanden.  
  
 [in] *VarChild*  
 Gibt an, ob das Hilfethema abgerufen werden sollen, die das Objekt oder eine der untergeordneten Elemente des Objekts ist. Dieser Parameter kann es sich um `CHILDID_SELF` (um ein Hilfethema für das Objekt abrufen) oder ein untergeordnetes Element-ID (um ein Hilfethema für eines der untergeordneten Elemente des Objekts abrufen).  
  
 [in] *PidTopic*  
 Identifiziert die `Help` Datei Thema, das das angegebene Objekt zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `CBasePane` Diese Methode ist nicht implementiert werden. Aus diesem Grund `CBasePane::get_accHelpTopic` gibt immer `S_FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der Active Accessibility-Unterstützung in MFC. Überschreiben Sie diese Funktion in einer abgeleiteten Klasse, um Hilfeinformationen zu Ihr Objekt bereitzustellen.  
  
##  <a name="get_accselection"></a>  CBasePane::get_accSelection  
 Das Framework ruft diese Methode, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *PvarChildren*  
 Informationen, die dem ausgewählten, untergeordneten Elemente identifiziert empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 `CBasePane` Diese Methode ist nicht implementiert werden. Wenn *PvarChildren* ist `NULL`, gibt diese Methode `E_INVALIDARG`. Diese Methode hingegen gibt `DISP_E_MEMBERNOTFOUND`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der Active Accessibility-Unterstützung in MFC. Überschreiben Sie diese Funktion in einer abgeleiteten Klasse ein, wenn Sie nicht im Fenstermodus Elemente der Benutzeroberfläche als fensterlose ActiveX-Steuerelemente haben.  
  
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
 Eine bitweise OR-Kombination von AFX_CBRS_-Flags.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert ist eine Kombination aus den folgenden möglichen Werten.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Macht die Steuerelement-Leiste "float".|  
|`AFX_CBRS_AUTOHIDE`|ermöglicht das automatischen Ausblendemodus.|  
|`AFX_CBRS_RESIZE`|Ermöglicht das Ändern der Größe der Steuerleiste. Wenn dieses Flag festgelegt ist, kann die Steuerleiste in einen andockbaren Bereich eingefügt werden.|  
|`AFX_CBRS_CLOSE`|Ermöglicht das Ausblenden der Steuerleiste.|  
  
##  <a name="getcurrentalignment"></a>  CBasePane::GetCurrentAlignment  
 Gibt den aktuellen Bereich Ausrichtung zurück.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Ausrichtung der Steuerleiste. Die folgende Tabelle zeigt die möglichen Werte an:  
  
|Wert|Ausrichtung|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Linksbündige Ausrichtung.|  
|`CBRS_ALIGN_RIGHT`|Rechtsbündige Ausrichtung.|  
|`CBRS_ALIGN_TOP`|Obere Ausrichtung.|  
|`CBRS_ALIGN_BOTTOM`|Unten ausrichten.|  
  
##  <a name="getdockingmode"></a>  Cbasepane:: Getdockingmode  
 Gibt den aktuellen Andockmodus für den Bereich zurück.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 DT_STANDARD, wenn der Bereich ziehen wird durch ein Rechteck auf dem Bildschirm angezeigt. DT_IMMEDIATE, wenn der Inhalt des Bereichs gezogen werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den aktuellen Andockmodus des Bereichs zu bestimmen.  
  
 Wenn `CBasePane::m_dockMode` ist nicht definiert (DT_UNDEFINED), und klicken Sie dann der Andockmodus von globalen Andockmodus abgerufen wird ( `AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 Durch Festlegen von *M_dockMode* oder überschreiben `GetDockingMode` können Sie den Andockmodus für jedes Bereichs steuern.  
  
##  <a name="getdocksiteframewnd"></a>  CBasePane::GetDockSiteFrameWnd  
 Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem der Bereich angedockt ist.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die DockPosition des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Zeiger auf die DockPosition Bereich abzurufen. Der DockPosition kann entweder einem Hauptrahmenfenster, wenn der Bereich zum Hauptframe angedockt ist, oder ein Minirahmenfenster sein, wenn der Bereich unverankert ist.  
  
##  <a name="getenabledalignment"></a>  CBasePane::GetEnabledAlignment  
 Gibt die CBRS_ALIGN_-Formate, die in den Bereich angewendet werden.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von CBRS_ALIGN_ Stile. Die folgende Tabelle zeigt die möglichen Formate:  
  
|Flag|Aktivierte Ausrichtung|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|Nach links.|  
|`CBRS_ALIGN_RIGHT`|Richting.|  
|`CBRS_ALIGN_TOP`|Nach oben.|  
|`CBRS_ALIGN_BOTTOM`|Unten.|  
|`CBRS_ALIGN_ANY`|Die Kombination aller Flags.|  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Ausrichtung aktiviert, für den Bereich zu bestimmen. Aktivierte Ausrichtung bedeutet, dass die Seiten des Hauptrahmenfenster, dem an ein Bereich angedockt werden kann.  
  
 Andockbarer Ausrichtung aktivieren, indem [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="getmfcstyle"></a>  CBasePane::GetMFCStyle  
 Gibt zurück, die im Bereich Formate, die mit MFC spezifisch sind.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Bibliothek spezifischen (AFX_CBRS_) im Bereich Formate.  
  
##  <a name="getpaneicon"></a>  CBasePane::GetPaneIcon  
 Gibt ein Handle auf das Symbol "Bereich" zurück.  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bBigIcon*  
 Ein 32 Pixel von 32 Pixel großes Symbol gibt an, ob `TRUE`; ein 16-Pixel von 16 Pixel großes Symbol gibt an, ob `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Symbol "Bereich". Gibt zurück, wenn dies nicht gelingt, `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung ruft [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).  
  
##  <a name="getpanerow"></a>  CBasePane::GetPaneRow  
 Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem der Bereich angedockt ist.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf `CDockingPanesRow` , wenn der Bereich angedockt ist, oder `NULL` Wenn es unverankert ist.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für den Zugriff auf die Zeile, in dem ein Bereich angedockt ist. Aufrufen, um die Bereiche in einer bestimmten Zeile zu sortieren, z. B. `GetPaneRow` und rufen dann [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).  
  
##  <a name="getpanestyle"></a>  CBasePane::GetPaneStyle  
 Gibt den Schriftschnitt Bereich.  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Leiste Steuerelementtypen (einschließlich CBRS_ Stile), die festgelegt wurde, indem Sie die [CBasePane::SetPaneStyle](#setpanestyle) Methode zum Zeitpunkt der Erstellung.  
  
##  <a name="getparentdocksite"></a>  CBasePane::GetParentDockSite  
 Gibt einen Zeiger auf den übergeordneten Andocken Standort an.  
  
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
 Wenn `TRUE`, überprüft diese Methode nicht für ungültige Zeiger. Wenn Sie diese Methode aufrufen, wenn die Anwendung beendet wird, legen Sie diesen Parameter zu `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf das übergeordnete Minirahmenfenster Wenn Bereich unverankert ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf das übergeordnete Minirahmenfenster abzurufen. Diese Methode durchläuft alle übergeordneten Elemente und sucht nach einem Objekt abgeleitet [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md).  
  
 Verwendung `GetParentMiniFrame` zu bestimmen, ob der Bereich unverankert ist.  
  
##  <a name="getparenttabbedpane"></a>  CBasePane::GetParentTabbedPane  
 Gibt einen Zeiger auf die übergeordnete Seite im Registerformat.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Seite im Registerformat falls vorhanden; andernfalls `NULL`.  
  
##  <a name="getparenttabwnd"></a>  CBasePane::GetParentTabWnd  
 Gibt einen Zeiger auf das übergeordnete Fenster, das innerhalb einer Registerkarte liegt.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] *hWndTab*  
 Wenn der Rückgabewert nicht `NULL`, dieser Parameter enthält das Handle für das übergeordnete Fenster im Registerkartenformat.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf das übergeordnete Fenster im Registerkartenformat zu oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Zeiger auf das übergeordnete Fenster im Registerkartenformat abzurufen. Manchmal ist es nicht ausreichend, um Aufrufen `GetParent`, da ein Bereich in einen andockbaren Wrapper möglicherweise ( [CDockablePaneAdapter-Klasse](../../mfc/reference/cdockablepaneadapter-class.md)) oder in einem Bereich-Adapter ( [CDockablePaneAdapter-Klasse](../../mfc/reference/cdockablepaneadapter-class.md)). Mithilfe von `GetParentTabWnd` Sie einen gültigen Zeiger in diesen Fällen (vorausgesetzt, dass das übergeordnete Objekt ein Fenster im Registerkartenformat ist) abgerufen werden.  
  
##  <a name="getrecentvisiblestate"></a>  CBasePane::GetRecentVisibleState  
 Das Framework ruft diese Methode ein Bereich aus einem Archiv wiederhergestellt wird.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `BOOL` , die den aktuellen Sichtbarkeitsstatus angibt. Wenn `TRUE`, war die Bereich sichtbar, wenn serialisiert und sind sichtbar, wenn Sie wiederhergestellt werden soll. Wenn `FALSE`, Bereich wurde ausgeblendet, wenn serialisiert und ausgeblendet werden sollen, wenn wiederhergestellt.  
  
##  <a name="hideinprintpreviewmode"></a>  CBasePane::HideInPrintPreviewMode  
 Gibt an, ob der Bereich in der Seitenansicht ausgeblendet ist.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich nicht in der Seitenansicht angezeigt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Basis-Bereiche werden nicht in der Seitenansicht angezeigt. Aus diesem Grund diese Methode gibt immer `TRUE`.  
  
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
 Wenn `TRUE`, *pControlBar* eingefügt, nachdem *pTarget*. Wenn `FALSE`, *pControlBar* eingefügt wird, bevor Sie *pTarget*.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Methode erfolgreich ist, `FALSE` andernfalls.  
  
##  <a name="isaccessibilitycompatible"></a>  CBasePane::IsAccessibilityCompatible  
 Gibt an, ob der Bereich Active Accessibility unterstützt.  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich Active Accessibility unterstützt; andernfalls `FALSE`.  
  
##  <a name="isautohidemode"></a>  CBasePane::IsAutoHideMode  
 Bestimmt, ob ein Bereich in den automatischen Ausblendemodus.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in den automatischen Ausblendemodus wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Basis-Bereiche können nicht automatisch im Hintergrund. Diese Methode gibt immer `FALSE` zurück.  
  
##  <a name="isdialogcontrol"></a>  CBasePane::IsDialogControl  
 Gibt an, ob der Bereich ein Dialogfeld-Steuerelement ist.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich ein Dialogfeld-Steuerelement ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode zur Gewährleistung der Konsistenz von Layout für alle Bereiche.  
  
##  <a name="isdocked"></a>  CBasePane::IsDocked  
 Bestimmt, ob der Bereich angedockt ist.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das übergeordnete Element des Bereichs keiner Minirahmenfensters ist oder wenn der Bereich in einer Minirahmenfensters mit einem anderen Bereich; unverankert ist andernfalls `FALSE`.  
  
##  <a name="isfloating"></a>  CBasePane::IsFloating  
 Bestimmt, ob der Bereich unverankert ist.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich unverankert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt den entgegengesetzten Wert von [CBasePane::IsDocked](#isdocked).  
  
##  <a name="ishorizontal"></a>  CBasePane::IsHorizontal  
 Bestimmt, ob der Bereich horizontal angedockt ist.  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich horizontal; angedockt ist andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung überprüft die aktuelle andockbare Ausrichtung für `CBRS_ORIENT_HORZ`.  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CBasePane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Multipane-Rahmenfenster ist ( [CMultiPaneFrameWnd Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in einem Multipane-Rahmenfenster ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können in einem Rahmenfenster Multipane float. Aus diesem Grund `CBasePane::IsInFloatingMultiPaneFrameWnd` gibt immer `FALSE`.  
  
##  <a name="ismditabbed"></a>  CBasePane::IsMDITabbed  
 Bestimmt, ob der Bereich ein untergeordnetes MDI-Fenster als ein Dokument im Registerkartenformat hinzugefügt wurde.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn im Bereich ein untergeordnetes MDI-Fenster als ein Dokument im Registerkartenformat hinzugefügt wurde. andernfalls `FALSE`.  
  
##  <a name="ispanevisible"></a>  CBasePane::IsPaneVisible  
 Gibt an, ob die `WS_VISIBLE` -Flag wird festgelegt, für den Bereich.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn `WS_VISIBLE` festgelegt wurde, andernfalls wird `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBasePane::IsVisible](#isvisible) Bereich Sichtbarkeit zu bestimmen.  
  
##  <a name="ispointneardocksite"></a>  CBasePane::IsPointNearDockSite  
 Bestimmt, ob ein angegebener Punkt in der Nähe der DockPosition ist.  
  
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
 Gibt an, welche Kante, die in der Nähe der Punkt ist. Mögliche Werte sind `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, und `CBRS_ALIGN_BOTTOM`  
  
 [out] *bOuterEdge*  
 `TRUE` Wenn der Punkt in der Nähe von den äußeren Rahmen der DockPosition ist; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Punkt in der Nähe der DockPosition ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt ist in der Nähe der DockPosition auf, wenn es innerhalb der Vertraulichkeit in Dock-Manager festgelegt ist. Die Vertraulichkeit der Standardwert beträgt 15 Pixel.  
  
##  <a name="isresizable"></a>  Cbasepane:: isResizable  
 Bestimmt, ob der Bereich, dessen Größe angepasst werden kann.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich vom Benutzer angepasst werden kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Bereiche von [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) geändert werden kann.  
  
 Die Statusleiste ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) und die Dock-Leiste ( [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)) kann nicht geändert werden.  
  
##  <a name="isrestoredfromregistry"></a>  CBasePane::IsRestoredFromRegistry  
 Bestimmt, ob der Bereich aus der Registrierung wiederhergestellt wird.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich aus der Registrierung wiederhergestellt wird; andernfalls `FALSE`.  
  
##  <a name="istabbed"></a>  CBasePane::IsTabbed  
 Bestimmt, ob der Bereich im Registerkarten-Steuerelement ein Fenster im Registerkartenformat eingefügt wurde.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Steuerleiste in einer Registerkarte des Fensters im Registerkartenformat eingefügt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft einen Zeiger auf das unmittelbar übergeordnete Element und bestimmt, ob die Common Language Runtime-Klasse des übergeordneten Elements ist [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
##  <a name="isvisible"></a>  CBasePane::IsVisible  
 Bestimmt, ob der Bereich angezeigt wird.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Bestimmen der Sichtbarkeit eines Bereichs an. Verwenden Sie nicht `::IsWindowVisible`.  
  
 Wenn der Bereich nicht im Registerkartenformat ist (finden Sie unter [CBasePane::IsTabbed](#istabbed)), überprüft diese Methode die `WS_VISIBLE` Stil. Wenn der Bereich im Registerkartenformat ist, überprüft diese Methode die Sichtbarkeit des übergeordneten Fensters im Registerkartenformat. Wenn das übergeordnete Fenster sichtbar ist, überprüft die Funktion die Sichtbarkeit der Bereich Registerkarte mit [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).  
  
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
 `TRUE` Wenn der Bereich Zustand erfolgreich geladen wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Zustand des Bereichs aus der Registrierung geladen. Überschreiben Sie diese in einer abgeleiteten Klasse zusätzliche Informationen, die Einsparung/laden [CBasePane::SaveState](#savestate).  
  
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
 Ein Rechteck, das die neue Position und Größe des Bereichs angeben.  
  
 [in] *bRepaint*  
 Wenn `TRUE`, der Bereich gezeichnet wird. Wenn `FALSE`, ist der Bereich nicht neu gezeichnet.  
  
 [in] *Hdwp*  
 Handle für eine verzögerte Fenster Position-Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine verzögerte Fenster Position Struktur oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie übergeben `NULL` als die *Hdwp* Parameter, die diese Methode verschiebt das Fenster Normal. Wenn Sie ein Handle übergeben, führt diese Methode eine verzögerte verschieben. Sie können ein Handle abzurufen, durch den Aufruf [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) oder durch Speichern den Rückgabewert von einem vorherigen Aufruf dieser Methode.  
  
##  <a name="onafterchangeparent"></a>  CBasePane::OnAfterChangeParent  
 Nach dem Bereich übergeordneten Änderungen vom Framework aufgerufen.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndOldParent*  
 Ein Zeiger auf das vorherige übergeordnete Element.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode nach dem übergeordneten des Bereichs, in der Regel aufgrund eines andockbaren "oder" Gleitkomma-Vorgangs ändert.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="onbeforechangeparent"></a>  CBasePane::OnBeforeChangeParent  
 Wird vom Framework aufgerufen, kurz bevor die Änderungen des übergeordneten Fensters.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndNewParent*  
 Ein Zeiger auf ein neues übergeordnetes Fenster.  
  
 [in] *bDelay*  
 Gibt an, ob es sich bei Layout Anpassungen verzögert werden müssen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode wird unmittelbar vor der Bereich übergeordneten ändert, in der Regel aufgrund einer andocken, Gleitkomma- oder automatisch im Hintergrund-Vorgang.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="ondrawcaption"></a>  CBasePane::OnDrawCaption  
 Das Framework ruft diese Methode auf, wenn der Titel gezeichnet wird.  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode hat keine Funktion für die `CBasePane` Klasse.  
  
##  <a name="onmovepanedivider"></a>  CBasePane::OnMovePaneDivider  
 Diese Methode wird derzeit nicht verwendet.  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CPaneDivider\**  
 Nicht verwendet.  
  
##  <a name="onpanecontextmenu"></a>  CBasePane::OnPaneContextMenu  
 Vom Framework aufgerufen, wenn sie ein Menü erstellt, das eine Liste von Bereichen verfügt.  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pParentFrame*  
 Ein Zeiger auf den übergeordneten Frame.  
  
 [in] *zeigen*  
 Gibt den Speicherort des Kontextmenüs.  
  
### <a name="remarks"></a>Hinweise  
 `OnPaneContextMenu` Ruft die Dock-Manager, die die Liste von Bereichen verwaltet, die an das aktuelle Rahmenfenster gehören. Diese Methode fügt die Namen der Bereiche in einem Kontextmenü und angezeigt. Die Befehle im Menü ein- und Ausblenden von einzelnen Bereiche.  
  
 Überschreiben Sie diese Methode, um dieses Verhalten anzupassen.  
  
##  <a name="onremovefromminiframe"></a>  CBasePane::OnRemoveFromMiniFrame  
 Vom Framework aufgerufen, wenn ein Bereich aus seiner übergeordneten Mini-Rahmenfensters entfernt wird.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pMiniFrame*  
 Ein Zeiger auf ein Minirahmenfenster, das aus dem Bereich entfernt wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich aus seiner übergeordneten Minirahmenfenster (als Ergebnis andocken, z. B.) entfernt wird.  
  
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
 Diese Methode gibt immer `TRUE` zurück.  
  
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
 Erhöhen Sie den Suchbereich, indem Sie diese Menge. Ein Bereich, die Suchkriterien erfüllen, fällt der angegebene Punkt in der höheren Bereich.  
  
 [in] *bExactBar*  
 `TRUE` ignoriert die *nSensitivity* Parameter ist, andernfalls `FALSE`.  
  
 [in] *pRTCBarType*  
 Wenn dies nicht der `NULL`, sucht die Methode nur Bereiche des angegebenen Typs.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CBasePane`-Objekt, das den angegebenen Punkt enthält abgeleitet oder `NULL` Wenn kein Bereich gefunden wurde.  
  
##  <a name="recalclayout"></a>  CBasePane::RecalcLayout  
 `CBasePane` Diese Methode wird nicht verwendet werden.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>  CBasePane::RemovePaneFromDockManager  
 Hebt die Registrierung auf einen Bereich, und entfernt es aus der Liste im Dock-Manager.  
  
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
 Wenn `TRUE`, entfernte Bereich zerstört wird.  
  
 [in] *bAdjustLayout*  
 Wenn `TRUE`, passen Sie das Layout des Docks sofort.  
  
 [in] *bAutoHide*  
 Wenn `TRUE`, am Layout des Docks bezieht sich auf die Liste der leisten zum automatischen ausblenden. Wenn `FALSE`, am Layout des Docks bezieht sich auf die Liste der regulären Bereiche.  
  
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
 `TRUE` Wenn der Zustand erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn sie den Zustand des Bereichs in der Registrierung gespeichert. Überschreiben Sie `SaveState` in einer abgeleiteten Klasse, um zusätzliche Informationen zu speichern.  
  
##  <a name="selectdefaultfont"></a>  CBasePane::SelectDefaultFont  
 Wählt die Standardschriftart für einen angegebenen Gerätekontext.  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Einem Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Standardwert [CFont-Klasse](../../mfc/reference/cfont-class.md) Objekt.  
  
##  <a name="setcontrolbarstyle"></a>  CBasePane::SetControlBarStyle  
 Legt das Format des Steuerelements Balken an.  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwNewStyle*  
 Eine bitweise OR-Kombination folgende Werte möglich.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Macht die Steuerelement-Leiste "float".|  
|`AFX_CBRS_AUTOHIDE`|ermöglicht das automatischen Ausblendemodus.|  
|`AFX_CBRS_RESIZE`|Ermöglicht das Ändern der Größe der Steuerleiste. Wenn dieses Flag festgelegt ist, kann die Steuerleiste in einen andockbaren Bereich eingefügt werden.|  
|`AFX_CBRS_CLOSE`|Ermöglicht das Ausblenden der Steuerleiste.|  
  
##  <a name="setdockingmode"></a>  CBasePane::SetDockingMode  
 Legt den Andockmodus für den Bereich an.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DockModeNew*  
 Gibt den neuen Andockmodus für den Bereich an.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework unterstützt zwei andockbare Modi: standard und unmittelbare.  
  
 Im Standardmodus andockbaren werden Bereiche und Minirahmenfenster verschoben, um mit einem Rechteck. In den unmittelbaren Andockmodus werden Schiebeleisten-Steuerelemente und Minirahmenfenster sofort mit ihrem Kontext verschoben.  
  
 Der Andockmodus wird zu Beginn von global definiert [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Sie können festlegen, dass den Andockmodus für jeden Bereich einzeln mithilfe der `SetDockingMode` Methode.  
  
##  <a name="setpanealignment"></a>  CBasePane::SetPaneAlignment  
 Legt die Ausrichtung für den Bereich an.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwAlignment*  
 Gibt die neue Ausrichtung an.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ist in der Regel ist, diese Methode aufgerufen, wenn ein Bereich in eine andere aus einer Seite eines Hauptframe angedockt ist.  
  
 Die folgende Tabelle zeigt die möglichen Werte für *DwAlignment*:  
  
|Wert|Ausrichtung|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Linksbündige Ausrichtung.|  
|`CBRS_ALIGN_RIGHT`|Rechtsbündige Ausrichtung.|  
|`CBRS_ALIGN_TOP`|Obere Ausrichtung.|  
|`CBRS_ALIGN_BOTTOM`|Unten ausrichten.|  
  
##  <a name="setpanestyle"></a>  CBasePane::SetPaneStyle  
 Legt das Format des Bereichs.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwNewStyle*  
 Gibt die neue Formatvorlage festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, die Formatvorlagen CBRS_ festlegen, die in afxres.h definiert sind. Da Bereich Stil und einem Fensterbereich Ausrichtung zusammen gespeichert werden, legen Sie die neue Formatvorlage, durch die Kombination mit der aktuellen Ausrichtung wie folgt.  
  
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
 Identifiziert die `CWnd` -Objekt, das dies vorangeht `CWnd` Objekt in der Z-Reihenfolge. Weitere Informationen finden Sie unter [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
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
 Handle für eine Struktur, die Informationen zur Größe und Position für ein oder mehrere Fenster enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine aktualisierte verzögerte Fenster Position Struktur oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn *pWndInsertAfter* ist `NULL`, diese Methode ruft [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Wenn *pWndInsertAfter* nicht `NULL`, diese Methode ruft `DeferWindowPos`.  
  
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
 Gibt an, ob ( `TRUE`) oder ausblenden ( `FALSE`) einen Bereich.  
  
 [in] *bDelay*  
 Wenn `TRUE`, am Layout des Docks Neuberechnen verzögert wird.  
  
 [in] *bActivate*  
 Wenn `TRUE`, Bereich ist aktiv, wenn Sie angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode anzeigen oder ausblenden ein Bereichs. Verwenden Sie diese Methode anstelle von `ShowWindow` , da diese Methode die relevanten Dock-Manager zu Änderungen in den Bereich Sichtbarkeit benachrichtigt.  
  
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
 Die Länge, um den Bereich zu Strecken.  
  
 [in] *bHoriz*  
 Wenn `TRUE`, stretch-Bereich vertikal. Wenn `FALSE`, horizontal stretch-Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Bereichs gestreckt werden soll.  
  
##  <a name="undockpane"></a>  CBasePane::UndockPane  
 Entfernt den Bereich aus der DockPosition, Standard-Schieberegler, bzw. Minirahmenfenster, wo sie derzeit angedockt ist.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *bDelay*  
 Bei "true", ist am Layout des Docks nicht sofort neu berechnet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Zustand des Bereichs zu bearbeiten oder am Layout Docks Bereich ausgeschlossen.  
  
 Wenn Sie weiterhin in diesem Bereich verwenden möchten, rufen Sie entweder [cbasepane:: Dockpane](#dockpane) oder [CBasePane::FloatPane](#floatpane) vor dem Aufrufen dieser Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)
