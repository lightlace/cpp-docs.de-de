---
title: CBasePane-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBasePane::get_accKeyboardShortcut
- CBasePane.get_accKeyboardShortcut
- CBasePane.accSelect
- get_accDefaultAction
- accSelect
- CBasePane.accHitTest
- CBasePane.get_accRole
- get_accKeyboardShortcut
- CBasePane::Serialize
- CBasePane
- CBasePane::get_accDefaultAction
- get_accParent
- CBasePane::accSelect
- accLocation
- CBasePane.get_accDescription
- get_accName
- CBasePane::get_accChildCount
- CBasePane.get_accChild
- CBasePane::accHitTest
- accHitTest
- get_accHelp
- CBasePane.get_accChildCount
- CBasePane.get_accValue
- CBasePane::get_accDescription
- get_accChildCount
- CBasePane.accLocation
- CBasePane.PreTranslateMessage
- CBasePane.get_accName
- PreTranslateMessage
- CBasePane::get_accFocus
- get_accDescription
- CBasePane::get_accRole
- get_accValue
- CBasePane.Serialize
- CBasePane::accLocation
- get_accRole
- CBasePane::get_accChild
- get_accFocus
- CBasePane::get_accHelp
- CBasePane.get_accDefaultAction
- CBasePane.get_accHelp
- CBasePane::PreTranslateMessage
- CBasePane::get_accState
- CBasePane.get_accParent
- CBasePane::get_accParent
- get_accChild
- CBasePane::get_accValue
- Serialize
- get_accState
- CBasePane.get_accState
- CBasePane.get_accFocus
- CBasePane::get_accName
dev_langs:
- C++
helpviewer_keywords:
- get_accState method
- get_accHelp method
- CBasePane class
- accLocation method
- accHitTest method
- get_accDescription method
- get_accDefaultAction method
- get_accName method
- get_accFocus method
- get_accRole method
- get_accValue method
- get_accChild method
- accSelect method
- get_accKeyboardShortcut method
- get_accChildCount method
- Serialize method
- PreTranslateMessage method
- get_accParent method
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
caps.latest.revision: 43
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
ms.openlocfilehash: 0444c0647d83a1e9b431dd0c5bdb369da213b91b
ms.lasthandoff: 02/24/2017

---
# <a name="cbasepane-class"></a>CBasePane-Klasse
Die Basisklasse für alle Bereiche in MFC.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CBasePane::CBasePane`|Standardkonstruktor|  
|`CBasePane::~CBasePane`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CBasePane::accHitTest`|Wird durch das Framework aufgerufen, um das untergeordnete Element oder untergeordnete Objekt an einem bestimmten Punkt auf dem Bildschirm abzurufen. (Überschreibt [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CBasePane::accLocation`|Aufgerufen, um die aktuelle Position für das angegebene Objekt abzurufen. (Überschreibt [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane`Diese Methode wird nicht verwendet werden.|  
|`CBasePane::accSelect`|Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben. (Überschreibt [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CBasePane::AddPane](#addpane)|Fügt einen Bereich zum Andocken Manager hinzu.|  
|[CBasePane::AdjustDockingLayout](#adjustdockinglayout)|Leitet einen Aufruf an die Dockingstation-Manager das Andocken Layout anpassen.|  
|[CBasePane::AdjustLayout](#adjustlayout)|Vom Framework aufgerufen, wenn der Bereich das interne Layout angepasst.|  
|[CBasePane::CalcFixedLayout](#calcfixedlayout)|Berechnet die horizontale Größe einer Steuerleiste.|  
|[CBasePane::CanAcceptPane](#canacceptpane)|Bestimmt, ob ein weiterer Bereich, in den Bereich angedockt werden kann.|  
|[CBasePane::CanAutoHide](#canautohide)|Bestimmt, ob der Bereich automatisch ausgeblendet unterstützt.|  
|[CBasePane::CanBeAttached](#canbeattached)|Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.|  
|[Cbasepane:: Canbeclosed](#canbeclosed)|Bestimmt, ob der Bereich geschlossen werden kann.|  
|[CBasePane::CanBeDocked](#canbedocked)|Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.|  
|[CBasePane::CanBeResized](#canberesized)|Bestimmt, ob der Bereich angepasst werden kann.|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|Gibt an, ob der Bereich in einer MDI-Dokument im Registerkartenformat konvertiert werden kann.|  
|[CBasePane::CanFloat](#canfloat)|Bestimmt, ob der Bereich wechseln kann.|  
|[CBasePane::CanFocus](#canfocus)|Gibt an, ob der Bereich den Fokus erhalten kann.|  
|[CBasePane::CopyState](#copystate)|Kopiert den Status eines bestimmten Bereichs.|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|Wenn der Bereich wechseln kann, erstellt ein Minirahmenfenster.|  
|[CBasePane::CreateEx](#createex)|Das Steuerelement wird erstellt.|  
|[CBasePane::DockPane](#dockpane)|Dockt an einen Bereich in einen anderen Bereich oder einem Rahmenfenster.|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|Dockt den Bereich mit der Laufzeit Typinformationen an.|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|Ein Frame ein andockbares Fenster angedockt.|  
|[CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem und den übergeordneten Frame eingefügt werden kann.|  
|[CBasePane::EnableDocking](#enabledocking)|Ermöglicht das Andocken des Bereichs des Hauptframe.|  
|[CBasePane::EnableGripper](#enablegripper)|Aktiviert oder deaktiviert die Ziehpunkte. Wenn die Ziehpunkte aktiviert ist, kann der Benutzer, um die Position im Bereichs ziehen.|  
|`CBasePane::FillWindowRect`|Wird intern verwendet.|  
|[CBasePane::FloatPane](#floatpane)|Befindet sich im Bereich.|  
|`CBasePane::get_accChild`|Wird durch das Framework aufgerufen, um die Adresse einer `IDispatch`-Schnittstelle für das angegebene, untergeordnete Element abzurufen. (Überschreibt [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|`CBasePane::get_accChildCount`|Aufgerufen, um die Anzahl der untergeordneten Elemente abzurufen, die zu diesem Objekt gehören. (Überschreibt [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CBasePane::get_accDefaultAction`|Aufgerufen, um eine Zeichenfolge abzurufen, die die Standardaktion des Objekts beschreibt. (Überschreibt [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CBasePane::get_accDescription`|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt. (Überschreibt [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|`CBasePane::get_accFocus`|Wird durch das Framework aufgerufen, um das Objekt abzurufen, das den Tastaturfokus hat. (Überschreibt [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|`CBasePane::get_accHelp`|Aufgerufen, um eine Hilfezeichenfolge der Eigenschaft für das Objekt abzurufen. (Überschreibt [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|Aufgerufen, um den vollständigen Pfad der WinHelp-Datei, die mit dem angegebenen Objekt zugeordnet ist und der Bezeichner der im entsprechenden Thema in der Datei abzurufen. (Überschreibt [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|`CBasePane::get_accKeyboardShortcut`|Aufgerufen, um die angegebene Tastenkombination für das Objekt abzurufen. (Überschreibt [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CBasePane::get_accName`|Wird durch das Framework aufgerufen, um den Namen des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CBasePane::get_accParent`|Aufgerufen, zum Abrufen der `IDispatch` -Schnittstelle für das übergeordnete Element des Objekts. (Überschreibt [CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent).)|  
|`CBasePane::get_accRole`|Wird durch das Framework aufgerufen, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreiben. (Überschreibt [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CBasePane::get_accSelection](#get_accselection)|Wird durch das Framework aufgerufen, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen. (Überschreibt [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CBasePane::get_accState`|Wird durch das Framework aufgerufen, um den aktuellen Status des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CBasePane::get_accValue`|Wird durch das Framework aufgerufen, um den Wert des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[Cbasepane:: Getcaptionheight](#getcaptionheight)|Gibt die Beschriftungshöhe zurück.|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|Gibt das Format des Steuerelements angezeigt.|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|Gibt den aktuellen Bereich Ausrichtung zurück.|  
|[Cbasepane:: Getdockingmode](#getdockingmode)|Gibt den aktuellen Andockmodus für den Bereich zurück.|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|Gibt einen Zeiger auf das Fenster, das die Dock-Website für den Bereich ist.|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|Gibt die CBRS_ALIGN_-Formate, die in den Bereich angewendet werden.|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|Gibt die Stile im Bereich bestimmte mit MFC zurück.|  
|[CBasePane::GetPaneIcon](#getpaneicon)|Gibt ein Handle auf das Symbol "Bereich".|  
|`CBasePane::GetPaneRect`|Wird intern verwendet.|  
|[CBasePane::GetPaneRow](#getpanerow)|Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem Bereich angedockt ist.|  
|[CBasePane::GetPaneStyle](#getpanestyle)|Gibt den Bereichsformat zurück.|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|Gibt einen Zeiger auf den übergeordneten Dock-Standort.|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|Gibt einen Zeiger auf das übergeordnete Minirahmenfenster.|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|Gibt einen Zeiger auf die übergeordnete Seite im Registerformat.|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|Gibt einen Zeiger auf das übergeordnete Fenster, das auf einer Registerkarte angezeigt wird.|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|Das Framework ruft diese Methode auf, wenn ein Bereich aus einem Archiv wiederhergestellt wird.|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|Gibt an, ob der Bereich in der Seitenansicht ausgeblendet ist.|  
|[CBasePane::InsertPane](#insertpane)|Registriert den angegebenen Bereich der docking-Manager.|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|Gibt an, ob im Bereich Active Accessibility unterstützt.|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|Bestimmt, ob ein Fenster automatisch ausgeblendet wird.|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|Gibt an, ob der Bereich ein Steuerelement ist.|  
|[CBasePane::IsDocked](#isdocked)|Bestimmt, ob der Bereich angedockt ist.|  
|[CBasePane::IsFloating](#isfloating)|Bestimmt, ob der Bereich verankert ist.|  
|[CBasePane::IsHorizontal](#ishorizontal)|Bestimmt, ob der Bereich horizontal angedockt ist.|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen.|  
|[CBasePane::IsMDITabbed](#ismditabbed)|Bestimmt, ob der Bereich ein untergeordnetes MDI-Fenster als ein Dokument im Registerkartenformat hinzugefügt wurde.|  
|[CBasePane::IsPaneVisible](#ispanevisible)|Gibt an, ob die `WS_VISIBLE` Flag für den Bereich festgelegt ist.|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|Bestimmt, ob es sich bei ein angegebenen Punkt in der Nähe der Dock-Website befindet.|  
|[CBasePane::IsResizable](#isresizable)|Bestimmt, ob der Bereich angepasst werden kann.|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|Bestimmt, ob der Bereich in der Registrierung wiederhergestellt wird.|  
|[CBasePane::IsTabbed](#istabbed)|Bestimmt, ob der Bereich in das Registerkarten-Steuerelement ein Fenster im Registerkartenformat eingefügt wurde.|  
|`CBasePane::IsTooltipTopmost`|Wird intern verwendet.|  
|[CBasePane::IsVisible](#isvisible)|Bestimmt, ob der Bereich angezeigt wird.|  
|[CBasePane::LoadState](#loadstate)|Lädt den Zustand des Bereichs aus der Registrierung.|  
|[CBasePane::MoveWindow](#movewindow)|Verschiebt den Bereich.|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|Vom Framework aufgerufen, wenn der Bereich übergeordneten geändert wurde.|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|Vom Framework aufgerufen, unmittelbar bevor der Bereich des übergeordneten Fensters geändert wird.|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|Das Framework ruft diese Methode auf, wenn der Titel gezeichnet wird.|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|Diese Methode wird derzeit nicht verwendet.|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|Vom Framework aufgerufen, wenn ein Menü erstellt, die eine Liste von Bereichen.|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|Wird vom Framework aufgerufen, wenn ein Bereich aus das übergeordnete Mini-Rahmenfenster entfernt wird.|  
|[Cbasepane:: Onsetaccdata](#onsetaccdata)|`CBasePane`Diese Methode wird nicht verwendet werden.|  
|`CBasePane::OnUpdateCmdUI`|Wird intern verwendet.|  
|[CBasePane::PaneFromPoint](#panefrompoint)|Gibt den Bereich, der den angegebenen Punkt enthält.|  
|`CBasePane::PreTranslateMessage`|Von der Klasse verwendet [CWinApp](../../mfc/reference/cwinapp-class.md) auf fenstermeldungen zu übersetzen, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane`Diese Methode wird nicht verwendet werden.|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|Hebt die Registrierung eines Bereichs, und entfernt sie aus der Liste in der Dockingstation-Manager.|  
|[CBasePane::SaveState](#savestate)|Speichert den Zustand des Bereichs in der Registrierung.|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|Wählt die Schriftart für einen bestimmten Gerätekontext.|  
|`CBasePane::Serialize`|Liest oder schreibt dieses Objekt aus einem oder in ein Archiv. (Überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize).)|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|Legt das Format des Steuerelements angezeigt.|  
|[CBasePane::SetDockingMode](#setdockingmode)|Legt den Andockmodus für den Bereich fest.|  
|`CBasePane::SetMDITabbed`|Wird intern verwendet.|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|Legt die Ausrichtung für den Bereich fest.|  
|`CBasePane::SetPaneRect`|Wird intern verwendet.|  
|[CBasePane::SetPaneStyle](#setpanestyle)|Legt den Stil des Bereichs.|  
|`CBasePane::SetRestoredFromRegistry`|Wird intern verwendet.|  
|[CBasePane::SetWindowPos](#setwindowpos)|Ändert die Größe, Position und Z-Reihenfolge eines Bereichs.|  
|[CBasePane::ShowPane](#showpane)|Blendet den Bereich oder.|  
|[CBasePane::StretchPane](#stretchpane)|Streckt einen Bereich vertikal oder horizontal.|  
|[CBasePane::UndockPane](#undockpane)|Entfernt im Bereich von docksite, Standard-Schieberegler oder Minirahmenfenster, in denen es derzeit angedockt ist.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|Füllt den Hintergrund des Bereichs.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine Klasse im Bereich zu erstellen, die die erweiterten andockbaren Merkmale, die in MFC unterstützt möchten, leiten Sie ihn von `CBasePane` oder [CPane-Klasse](../../mfc/reference/cpane-class.md).  
  
## <a name="customization-tips"></a>Anpassungstipps  
 Die folgenden Anpassungstipps beziehen sich auf die `CBasePane Class` und alle Klassen, die von ihm erben:  
  
-   Wenn Sie einen Bereich erstellen, können Sie mehrere neue Stile anwenden:  
  
    - `AFX_CBRS_FLOAT`Stellt den Bereich Float.  
  
    - `AFX_CBRS_AUTOHIDE`ermöglicht das automatische Ausblenden Modus.  
  
    - `AFX_CBRS_CLOSE`ermöglicht der Bereich (ausgeblendet) geschlossen werden.  
  
     Hierbei handelt es sich um Flags, die mit einer bitweisen OR-Operation kombiniert werden können.  
  
 `CBasePane`implementiert die folgenden Methoden der virtuellen booleschen entsprechend dieser Flags: [cbasepane:: Canbeclosed](#canbeclosed), [CBasePane::CanAutoHide](#canautohide), [CBasePane::CanFloat](#canfloat). Sie können sie in abgeleiteten Klassen zum Anpassen ihres Verhaltens überschreiben.  
  
-   Sie können Andockverhalten anpassen, indem Sie überschreiben [CBasePane::CanAcceptPane](#canacceptpane). Haben Sie Ihr Bereich zurückgeben `FALSE` von dieser Methode, um zu verhindern, dass ein weiterer Bereich, es andocken.  
  
-   Wenn Sie einen statischen Bereich nicht möglich, die float- und einen beliebigen anderen Bereich, die verhindert, dass vor dem Andocken (ähnlich wie der Outlook-Leiste in das OutlookDemo-Beispiel) erstellen möchten, erstellen Sie ihn als verankerte und überschreiben [CBasePane::DoesAllowDynInsertBefore](#doesallowdyninsertbefore) zurückzugebenden `FALSE`. Die standardmäßige Implementierung gibt `FALSE` , wenn der Bereich, ohne erstellt wird die `AFX_CBRS_FLOAT` Stil.  
  
-   Erstellen Sie alle Bereiche mit IDs als-1 fest.  
  
-   Verwenden Sie zum Bestimmen der Sichtbarkeit Bereich [CBasePane::IsVisible](#isvisible). Diese korrekt behandelt des Sichtbarkeitsstatus im Registerkartenformat und automatisch im Hintergrund Modi.  
  
-   Wenn Sie einen verankerte mit veränderbarer Größe Bereich erstellen möchten, erstellen Sie ihn ohne die `AFX_CBRS_FLOAT` Stil und einem Aufruf [CFrameWnd:: DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).  
  
-   Rufen Sie einen Bereich von einer Dockingstation Layout ausschließen oder eine Symbolleiste in der Leiste Dock entfernen, [CBasePane::UndockPane](#undockpane). Rufen Sie diese Methode für den Bereich automatisch ausgeblendet oder Bereiche, die in den Registerkarten im Registerformat befinden.  
  
-   Wenn Sie, Float möchten oder lösen einen Bereich, der automatisch ausgeblendet wird, müssen Sie aufrufen [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode) mit `FALSE` als erstes Argument vor dem Aufruf von [CBasePane::FloatPane](#floatpane) oder [CBasePane::UndockPane](#undockpane).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CBasePane` Klasse. Das Beispiel veranschaulicht das Abrufen ein Bereichs von der `CFrameWndEx` -Klasse und den Andockmodus, die im Bereich Ausrichtung und die Formatvorlage Bereich festlegen. Der Code stammt aus der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#2;](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxbasepane.h  
  
##  <a name="a-nameaccnotifyobjectfocuseventa--cbasepaneaccnotifyobjectfocusevent"></a><a name="accnotifyobjectfocusevent"></a>CBasePane::AccNotifyObjectFocusEvent  
 `CBasePane`Diese Methode wird nicht verwendet werden.  
  
```  
virtual void AccNotifyObjectFocusEvent(int);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `int`  
 Nicht verwendet.  
  
##  <a name="a-nameaddpanea--cbasepaneaddpane"></a><a name="addpane"></a>CBasePane::AddPane  
 Fügt einen Bereich zum Andocken Manager hinzu.  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen Bereich hinzuzufügen.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine Hilfsmethode, die einen Bereich an eine Dockingstation-Manager hinzufügt. Mithilfe dieser Methode müssen Sie keinen Code schreiben, der den Typ des übergeordneten Frames analysiert.  
  
 Weitere Informationen finden Sie unter [CDockingManager Klasse](../../mfc/reference/cdockingmanager-class.md) und [CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane).  
  
##  <a name="a-nameadjustdockinglayouta--cbasepaneadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CBasePane::AdjustDockingLayout  
 Leitet einen Aufruf an die Dockingstation-Manager das Andocken Layout anpassen.  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `hdwp`  
 Ein Handle für eine Struktur mit mehreren Fensterpositionen.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine Hilfsmethode, die das andocklayout angepasst. Mithilfe dieser Methode müssen Sie keinen Code schreiben, der den Typ des übergeordneten Frames analysiert.  
  
 Weitere Informationen finden Sie unter [CDockingManager::AdjustDockingLayout](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="a-nameadjustlayouta--cbasepaneadjustlayout"></a><a name="adjustlayout"></a>CBasePane::AdjustLayout  
 Vom Framework aufgerufen wird, das interne Layout eines Bereichs anzupassen.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich das interne Layout anpassen muss. Die basisimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="a-namecalcfixedlayouta--cbasepanecalcfixedlayout"></a><a name="calcfixedlayout"></a>CBasePane::CalcFixedLayout  
 Berechnet die horizontale Größe einer Steuerleiste.  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bStretch`  
 Gibt an, ob die Leiste auf die Größe des Rahmens gestreckt werden soll. Die `bStretch` Parameter ist ungleich NULL, wenn die Leiste keine andockleiste (nicht verfügbar für andockbare) und 0, ist wenn es angedockt oder unverankert ist (verfügbar für andockbare).  
  
 [in] `bHorz`  
 Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die `bHorz` Parameter ist ungleich NULL, wenn die Leiste horizontal ausgerichtet ist, und 0 ist, wenn sie vertikal ausgerichtet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Steuerleiste Größe, in Pixel, der eine `CSize` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter die Hinweisen im Abschnitt [CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="a-namecanacceptpanea--cbasepanecanacceptpane"></a><a name="canacceptpane"></a>CBasePane::CanAcceptPane  
 Bestimmt, ob ein weiterer Bereich, in den Bereich angedockt werden kann.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich angedockt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn Sie einen anderen Bereich akzeptiert werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor im angegebenen Bereich angedockt wird `pBar` in den aktuellen Bereich.  
  
 Verwenden Sie diese Methode und die [CBasePane::CanBeDocked](#canbedocked) Methode steuern, wie Bereiche auf andere Bereiche in Ihrer Anwendung andocken.  
  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
##  <a name="a-namecanautohidea--cbasepanecanautohide"></a><a name="canautohide"></a>CBasePane::CanAutoHide  
 Bestimmt, ob der Bereich automatisch ausgeblendet unterstützt.  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn dieser Bereich automatisch ausgeblendet unterstützt. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Funktion, um zu bestimmen, ob der Bereich automatisch ausgeblendet unterstützt.  
  
 Während der Konstruktion lassen sich diese Fähigkeit durch Übergeben der `AFX_CBRS_AUTOHIDE` flag auf [CBasePane::CreateEx](#createex).  
  
 Die standardmäßige Implementierung überprüft die `AFX_CBRS_AUTOHIDE` Flag. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, um dieses Verhalten anzupassen.  
  
##  <a name="a-namecanbeattacheda--cbasepanecanbeattached"></a><a name="canbeattached"></a>CBasePane::CanBeAttached  
 Bestimmt, ob der Bereich zu einem anderen Bereich oder Fenster angedockt werden kann.  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich zu einem anderen Bereich oder Fenster angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung gibt `FALSE` zurück. Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Aktivieren oder deaktivieren die Möglichkeit, ohne Aufruf Andocken [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="a-namecanbecloseda--cbasepanecanbeclosed"></a><a name="canbeclosed"></a>Cbasepane:: Canbeclosed  
 Bestimmt, ob der Bereich geschlossen werden kann.  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich geschlossen werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Bereich geschlossen werden kann. Wenn die Methode zurückgibt `TRUE`, **schließen** Schaltfläche auf der Titelleiste hinzugefügt wird oder wenn der Bereich auf der Titelleiste des Bereichs Minirahmenfenster verankert ist.  
  
 Während der Konstruktion lassen sich diese Fähigkeit durch Übergeben der `AFX_CBRS_CLOSE` flag auf [CBasePane::CreateEx](#createex).  
  
 Die standardmäßige Implementierung überprüft die `AFX_CBRS_CLOSE` Flag.  
  
##  <a name="a-namecanbedockeda--cbasepanecanbedocked"></a><a name="canbedocked"></a>CBasePane::CanBeDocked  
 Bestimmt, ob der Bereich in einen anderen Bereich angedockt werden kann.  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockBar`  
 Ein Zeiger auf einen anderen Bereich.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn in diesem Bereich in einen anderen Bereich; angedockt werden kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor im angegebenen Bereich angedockt wird `pDockBar` in den aktuellen Bereich.  
  
 Verwenden Sie diese Methode und die [CBasePane::CanAcceptPane](#canacceptpane) Methode steuern, wie Bereiche auf andere Bereiche in Ihrer Anwendung andocken.  
  
 Die Standardimplementierung gibt `FALSE` zurück.  
  
##  <a name="a-namecanberesizeda--cbasepanecanberesized"></a><a name="canberesized"></a>CBasePane::CanBeResized  
 Bestimmt, ob der Bereich angepasst werden kann.  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich angepasst werden kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überprüft die `AFX_CBRS_RESIZE` -Flag, das als Standardwert im angegebenen `CBasePane::OnCreate`. Wenn dieses Flag nicht angegeben ist, kennzeichnet der Dockingstation Manager Bereich intern als unbeweglichen statt angedockt.  
  
##  <a name="a-namecanbetabbeddocumenta--cbasepanecanbetabbeddocument"></a><a name="canbetabbeddocument"></a>CBasePane::CanBeTabbedDocument  
 Gibt an, ob der Bereich in einer MDI-Dokument im Registerkartenformat konvertiert werden kann.  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in ein Dokument im Registerkartenformat konvertiert werden kann. andernfalls `FALSE`. `CBasePane::CanBeTabbedDocument` gibt immer `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Nur Objekte, die bestimmte `CBasePane`-abgeleiteten Typen, z. B. die [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md), Dokumente im Registerformat konvertiert werden können.  
  
##  <a name="a-namecanfloata--cbasepanecanfloat"></a><a name="canfloat"></a>CBasePane::CanFloat  
 Bestimmt, ob der Bereich wechseln kann.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich wechseln kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Bereich wechseln kann.  
  
 Während der Konstruktion lassen sich diese Fähigkeit durch Übergeben der `AFX_CBRS_FLOAT` flag auf [CBasePane::CreateEx](#createex).  
  
> [!NOTE]
>  Das Framework davon ausgegangen, dass Bereiche verankerte statisch sind ihre docking Status nicht ändern kann. Aus diesem Grund wird das Framework der Andockstatus verankerte Bereichen nicht gespeichert.  
  
 Die standardmäßige Implementierung überprüft die `AFX_CBRS_FLOAT` Stil.  
  
##  <a name="a-namecanfocusa--cbasepanecanfocus"></a><a name="canfocus"></a>CBasePane::CanFocus  
 Gibt an, ob der Bereich den Fokus erhalten kann.  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich den Fokus erhalten kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse den Fokus zu steuern. Z. B. weil Symbolleisten den Fokus erhalten können, diese Methode gibt `FALSE` Wenn sie auf der Symbolleistenobjekte aufgerufen.  
  
 Das Framework versucht, den Eingabefokus festzulegen, wenn ein Bereich angedockt oder abgedockt wird.  
  
##  <a name="a-namecopystatea--cbasepanecopystate"></a><a name="copystate"></a>CBasePane::CopyState  
 Kopiert den Status eines bestimmten Bereichs.  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOrgBar`  
 Ein Zeiger auf einen anderen Bereich.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kopiert den Zustand von `pOrgBar` in diesen Bereich.  
  
##  <a name="a-namecreatedefaultminiframea--cbasepanecreatedefaultminiframe"></a><a name="createdefaultminiframe"></a>CBasePane::CreateDefaultMiniframe  
 Wenn der Bereich wechseln kann, erstellt diese Methode ein Minirahmenfenster.  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectInitial`  
 Gibt die Anfangskoordinaten des Minirahmenfenster an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue Minirahmenfenster oder `NULL` Wenn Fehler bei der Erstellung.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich in einen unverankerten Zustand wechselt. Die Methode erstellt ein Minirahmenfenster und fügt den Bereich dieses Fenster.  
  
 Die Standardimplementierung gibt `NULL` zurück.  
  
##  <a name="a-namecreateexa--cbasepanecreateex"></a><a name="createex"></a>CBasePane::CreateEx  
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
 [in] `dwStyleEx`  
 Die erweiterten Stile (finden Sie unter [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) für Weitere Informationen).  
  
 [in] `lpszClassName`  
 Name der Fensterklasse.  
  
 [in] `lpszWindowName`  
 Der Fenstername.  
  
 [in] `dwStyle`  
 Der Fensterstil (finden Sie unter [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)).  
  
 [in] `rect`  
 Das ursprüngliche Rechteck.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] `nID`  
 Gibt den Bereich-ID an. Muss eindeutig sein.  
  
 [in] `dwControlBarStyle`  
 Formatflags für Bereiche.  
  
 [in] `pContext`  
 Ein Zeiger auf`CcreateContext`  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich erstellt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein Fenster der Klasse `lpszClassName`. Bei Angabe von `WS_CAPTION`, diese Methode löscht die `WS_CAPTION` Formatbit und legt `CBasePane::m_bHasCaption` , `TRUE`, da die Bibliothek mit Untertiteln Bereiche nicht unterstützt.  
  
 Sie können eine beliebige Kombination von untergeordneten Fensterstile und MFC Steuerleiste Stile (CBRS_) verwenden.  
  
 Die Bibliothek fügt mehrere neue Stile für Bereiche. Die folgende Tabelle beschreibt die neuen Formate:  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Der Bereich kann float.|  
|`AFX_CBRS_AUTOHIDE`|Der Bereich unterstützt automatisch im Hintergrund-Modus.|  
|`AFX_CBRS_RESIZE`|Der Bereich kann geändert werden. **Wichtig:** dieses Format ist nicht implementiert.|  
|`AFX_CBRS_CLOSE`|Der Bereich kann geschlossen werden.|  
|`AFX_CBRS_AUTO_ROLLUP`|Der Bereich kann gemacht werden, wenn er gleitet.|  
|`AFX_CBRS_REGULAR_TABS`|Wenn einem Bereich in einen anderen Bereich, das dieses Format verfügt angedockt, wird ein reguläre Fenster im Registerkartenformat erstellt. (Weitere Informationen finden Sie unter [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md).)|  
|`AFX_CBRS_OUTLOOK_TABS`|Wenn einem Bereich in einen anderen Bereich, das dieses Format verfügt angedockt, wird eine Outlook-Stil Fenster im Registerkartenformat erstellt. (Weitere Informationen finden Sie unter [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).)|  
  
 Um die neuen Formate zu verwenden, geben sie im `dwControlBarStyle`.  
  
##  <a name="a-namedockpanea--cbasepanedockpane"></a><a name="dockpane"></a>CBasePane::DockPane  
 Dockt an einen Bereich in einen anderen Bereich oder einem Rahmenfenster.  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDockBar`  
 Ein Zeiger auf einen anderen Bereich.  
  
 [in] `lpRect`  
 Gibt das Zielrechteck.  
  
 [in] `dockMethod`  
 Gibt die Methode andocken.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn erfolgreich; Steuerleiste angedockt wurde andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion können Sie einen Bereich an einem anderen Bereich oder eine Leiste Andocken andocken ( [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)) angegebenen `pDockBar`, oder um einen Hauptframe Wenn `pDockBar` ist `NULL`.  
  
 `dockMethod`Gibt an, wie der Bereich angedockt ist. Finden Sie unter [CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane) eine Liste der möglichen Werte.  
  
##  <a name="a-namedockpaneusingrttia--cbasepanedockpaneusingrtti"></a><a name="dockpaneusingrtti"></a>CBasePane::DockPaneUsingRTTI  
 Dockt den Bereich mit der Laufzeit Typinformationen an.  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bUseDockSite`  
 Wenn `TRUE`, docken Sie an die Dockingstation Website. Wenn `FALSE`, docken Sie an den übergeordneten Frame.  
  
##  <a name="a-namedocktoframewindowa--cbasepanedocktoframewindow"></a><a name="docktoframewindow"></a>CBasePane::DockToFrameWindow  
 Ein Frame ein andockbares Fenster angedockt.  
  
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
 [in] `dwAlignment`  
 Die Seite des übergeordneten Frames, die Sie im Bereich zum andocken möchten.  
  
 [in] `lpRect`  
 Die gewünschte Größe.  
  
 [in] `dwDockFlags`  
 Ignoriert.  
  
 [in] `pRelativeBar`  
 Ignoriert.  
  
 [in] `nRelativeIndex`  
 Ignoriert.  
  
 [in] `bOuterEdge`  
 Wenn `TRUE` , und es gibt andere andockbare Bereiche auf der Seite, die durch angegebene `dwAlignment`, Bereich angedockt ist, außerhalb von den anderen Bereichen näher an den Rand des übergeordneten Rahmens. Wenn `FALSE`, im Bereich in der Mitte des Clientbereichs näher angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn eine Trennlinie ( [CPaneDivider Klasse](../../mfc/reference/cpanedivider-class.md)) kann nicht erstellt werden. Gibt andernfalls immer `TRUE`.  
  
##  <a name="a-namedoesallowdyninsertbeforea--cbasepanedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CBasePane::DoesAllowDynInsertBefore  
 Bestimmt, ob ein weiterer Bereich dynamisch zwischen diesem und den übergeordneten Frame eingefügt werden kann.  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn ein Benutzer einen anderen Bereich einfügen kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob ein Benutzer dynamisch einen Bereich, bevor Sie diesen Bereich einfügen kann.  
  
 Nehmen wir beispielsweise an, dass die Anwendung einen Bereich angedockt auf der linken Seite des Rahmens (z. B. der Outlook-Leiste) erstellt. Um zu verhindern, dass den Benutzer einen anderen Bereich links neben der erste Bereich andocken, diese Methode überschreiben und zurückgeben `FALSE`.  
  
 Es wird empfohlen, diese Methode überschreiben und `FALSE` für abgeleitete Bereiche verankerte aus [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md).  
  
 Die Standardimplementierung gibt `TRUE` zurück.  
  
##  <a name="a-namedopainta--cbasepanedopaint"></a><a name="dopaint"></a>CBasePane::DoPaint  
 Füllt den Hintergrund des Bereichs.  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft die aktuellen visuellen Manager zum Ausfüllen ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground)).  
  
##  <a name="a-nameenabledockinga--cbasepaneenabledocking"></a><a name="enabledocking"></a>CBasePane::EnableDocking  
 Ermöglicht das Andocken des Bereichs des Hauptframe.  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Gibt die Dockingstation Ausrichtung zu aktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Andocken Ausrichtung an den Hauptframe aktivieren. Sie können eine Kombination von übergeben `CBRS_ALIGN_` Flags (Weitere Informationen finden Sie unter [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)).  
  
 `EnableDocking`das interne Flag `CBasePane::m_dwEnabledAlignment` und das Framework überprüft dieses Kennzeichen, wenn ein Bereich angedockt ist.  
  
 Rufen Sie [CBasePane::GetEnabledAlignment](#getenabledalignment) die Dockingstation Ausrichtung für einen Bereich zu bestimmen.  
  
##  <a name="a-nameenablegrippera--cbasepaneenablegripper"></a><a name="enablegripper"></a>CBasePane::EnableGripper  
 Aktiviert oder deaktiviert die Ziehpunkte. Wenn die Ziehpunkte aktiviert ist, kann der Benutzer, um die Position im Bereichs ziehen.  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie die Ziehpunkte; `FALSE` deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode zum Aktivieren eines ziehelements anstelle der `WS_CAPTION` Stil.  
  
##  <a name="a-namefloatpanea--cbasepanefloatpane"></a><a name="floatpane"></a>CBasePane::FloatPane  
 Befindet sich im Bereich.  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rectFloat`  
 Gibt die Bildschirmkoordinaten, wo das nicht verankerte Fenster angezeigt wird.  
  
 [in] `dockMethod`  
 Gibt die Dock-Methode mit dem float-Bereich.  
  
 [in] `bShow`  
 Gibt an, ob das nicht verankerte Fenster angezeigt wird ( `TRUE`) oder ausgeblendet ( `FALSE`).  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich abgedockt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich an der angegebenen Bildschirmposition float `rectFloat`.  
  
##  <a name="a-namegetacchelptopica--cbasepanegetacchelptopic"></a><a name="get_acchelptopic"></a>CBasePane::get_accHelpTopic  
 Das Framework ruft diese Methode, um den vollständigen Pfad der Abrufen der `WinHelp` -Datei, die das angegebene Objekt und den Bezeichner der im entsprechenden Thema in der Datei zugeordnet ist.  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszHelpFile`  
 Adresse der ein `BSTR` , der den vollständigen Pfad der empfängt die `WinHelp` -Datei, die das angegebene Objekt zugeordnet ist, sofern vorhanden.  
  
 [in] `varChild`  
 Gibt an, ob das Hilfethema abgerufen werden sollen, die der Objekts oder eines der untergeordneten Elemente des Objekts. Dieser Parameter kann entweder `CHILDID_SELF` (um ein Hilfethema für das Objekt zu erhalten) oder untergeordnete ID (um ein Hilfethema für eines der untergeordneten Elemente des Objekts erhalten).  
  
 [in] `pidTopic`  
 Identifiziert die `Help` Thema, das dem angegebenen Objekt zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `CBasePane`Diese Methode implementiert nicht. Aus diesem Grund `CBasePane::get_accHelpTopic` gibt immer `S_FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der Active Accessibility-Unterstützung in MFC. Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Bereitstellen von Hilfeinformationen zu dem Objekt.  
  
##  <a name="a-namegetaccselectiona--cbasepanegetaccselection"></a><a name="get_accselection"></a>CBasePane::get_accSelection  
 Das Framework ruft diese Methode, um die ausgewählten untergeordneten Elemente dieses Objekts abzurufen.  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pvarChildren`  
 Empfängt Informationen, die der ausgewählten untergeordneten Elemente identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 `CBasePane`Diese Methode implementiert nicht. Wenn `pvarChildren` gleich `NULL` ist, gibt die Methode `E_INVALIDARG` zurück. Diese Methode andernfalls `DISP_E_MEMBERNOTFOUND`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist Teil der Active Accessibility-Unterstützung in MFC. Überschreiben Sie diese Funktion in einer abgeleiteten Klasse, wenn Sie nicht im Fenstermodus Elemente der Benutzeroberfläche als fensterlose ActiveX-Steuerelemente haben.  
  
##  <a name="a-namegetcaptionheighta--cbasepanegetcaptionheight"></a><a name="getcaptionheight"></a>Cbasepane:: Getcaptionheight  
 Gibt die Beschriftungshöhe zurück.  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Überschriftenhöhe.  
  
##  <a name="a-namegetcontrolbarstylea--cbasepanegetcontrolbarstyle"></a><a name="getcontrolbarstyle"></a>CBasePane::GetControlBarStyle  
 Gibt das Format des Steuerelements angezeigt.  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine bitweise OR-Kombination von AFX_CBRS_-Flags.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert ist eine Kombination aus den folgenden möglichen Werten.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Macht die Steuerelement-Leiste Float.|  
|`AFX_CBRS_AUTOHIDE`|Ermöglicht das automatische Ausblenden Modus.|  
|`AFX_CBRS_RESIZE`|Ermöglicht das Ändern der Größe der Steuerleiste. Wenn dieses Flag festgelegt ist, kann die Steuerleiste in einen andockbaren Bereich eingefügt werden.|  
|`AFX_CBRS_CLOSE`|Ermöglicht das Ausblenden der Steuerleiste.|  
  
##  <a name="a-namegetcurrentalignmenta--cbasepanegetcurrentalignment"></a><a name="getcurrentalignment"></a>CBasePane::GetCurrentAlignment  
 Gibt den aktuellen Bereich Ausrichtung zurück.  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Ausrichtung der Steuerleiste. In der folgenden Tabelle sind die möglichen Werte:  
  
|Wert|Ausrichtung|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Linksbündige Ausrichtung.|  
|`CBRS_ALIGN_RIGHT`|Rechtsbündige Ausrichtung.|  
|`CBRS_ALIGN_TOP`|Obere Ausrichtung.|  
|`CBRS_ALIGN_BOTTOM`|Unten ausrichten.|  
  
##  <a name="a-namegetdockingmodea--cbasepanegetdockingmode"></a><a name="getdockingmode"></a>Cbasepane:: Getdockingmode  
 Gibt den aktuellen Andockmodus für den Bereich zurück.  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 DT_STANDARD, wenn den Bereich ziehen wird durch ein Rechteck auf dem Bildschirm angezeigt. DT_IMMEDIATE, wenn der Inhalt des Bereichs gezogen werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den aktuellen Andockmodus des Bereichs zu ermitteln.  
  
 Wenn `CBasePane::m_dockMode` ist nicht definiert (DT_UNDEFINED), und klicken Sie dann der Andockmodus, die globale Andockmodus entnommen wird ( `AFX_GLOBAL_DATA::m_dockModeGlobal`).  
  
 Durch Festlegen von `m_dockMode` oder überschreiben `GetDockingMode` können Sie den Andockmodus für jeden Bereich steuern.  
  
##  <a name="a-namegetdocksiteframewnda--cbasepanegetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CBasePane::GetDockSiteFrameWnd  
 Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem Bereich angedockt ist.  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Website Andocken des Bereichs.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Zeiger auf die Dock-Website im Bereich abzurufen. Die docksite kann entweder ein Hauptrahmenfenster, wenn der Bereich der Hauptframe angedockt wird, oder ein Minirahmenfenster sein, wenn im Bereich verankert ist.  
  
##  <a name="a-namegetenabledalignmenta--cbasepanegetenabledalignment"></a><a name="getenabledalignment"></a>CBasePane::GetEnabledAlignment  
 Gibt die CBRS_ALIGN_-Formate, die in den Bereich angewendet werden.  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von CBRS_ALIGN_ Formate. Die folgende Tabelle zeigt die möglichen Formate:  
  
|Flag|Aktiviert-Ausrichtung|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|Nach links.|  
|`CBRS_ALIGN_RIGHT`|Richting.|  
|`CBRS_ALIGN_TOP`|Nach oben.|  
|`CBRS_ALIGN_BOTTOM`|Unten.|  
|`CBRS_ALIGN_ANY`|Kombination aller Flags.|  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Ausrichtung des aktiviert für den Bereich zu bestimmen. Aktiviert Ausrichtung bedeutet, dass die Seiten des Hauptrahmenfenster, dem ein Bereich angedockt werden kann.  
  
 Aktivieren andockbaren Ausrichtung mit [CBasePane::EnableDocking](#enabledocking).  
  
##  <a name="a-namegetmfcstylea--cbasepanegetmfcstyle"></a><a name="getmfcstyle"></a>CBasePane::GetMFCStyle  
 Gibt die Bereich-Stile, die mit MFC spezifisch sind.  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Bibliothek spezifischen (AFX_CBRS_) im Bereich Formate.  
  
##  <a name="a-namegetpaneicona--cbasepanegetpaneicon"></a><a name="getpaneicon"></a>CBasePane::GetPaneIcon  
 Gibt ein Handle auf das Symbol "Bereich".  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bBigIcon`  
 Ein 32 Pixel von 32 Pixel großes Symbol gibt an, ob `TRUE`; ein 16 Pixel von 16 Pixel großes Symbol gibt an, ob `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Symbol "Bereich". Gibt zurück, wenn dies nicht gelingt, `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung ruft [CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon).  
  
##  <a name="a-namegetpanerowa--cbasepanegetpanerow"></a><a name="getpanerow"></a>CBasePane::GetPaneRow  
 Gibt einen Zeiger auf die [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)Objekt, in dem Bereich angedockt ist.  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf `CDockingPanesRow` ist der Bereich angedockt, oder `NULL` Wenn schwimmen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Zeile zugreifen, wo ein Bereich angedockt wird. Aufrufen, um die Bereiche in einer bestimmten Zeile anzuordnen, z. B. `GetPaneRow` und rufen dann [CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes).  
  
##  <a name="a-namegetpanestylea--cbasepanegetpanestyle"></a><a name="getpanestyle"></a>CBasePane::GetPaneStyle  
 Gibt den Bereichsformat zurück.  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination von Balken Steuerelementtypen (einschließlich CBRS_), die festgelegt wurde, indem die [CBasePane::SetPaneStyle](#setpanestyle) Methode zum Zeitpunkt der Erstellung.  
  
##  <a name="a-namegetparentdocksitea--cbasepanegetparentdocksite"></a><a name="getparentdocksite"></a>CBasePane::GetParentDockSite  
 Gibt einen Zeiger auf den übergeordneten Dock-Standort.  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der übergeordnete Standort andocken.  
  
##  <a name="a-namegetparentminiframea--cbasepanegetparentminiframe"></a><a name="getparentminiframe"></a>CBasePane::GetParentMiniFrame  
 Gibt einen Zeiger auf das übergeordnete Minirahmenfenster.  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bNoAssert`  
 Wenn `TRUE`, diese Methode nicht nach ungültigen Zeiger. Wenn Sie diese Methode aufrufen, wenn die Anwendung beendet wird, legen Sie diesen Parameter auf `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf das übergeordnete Minirahmenfenster Wenn Bereich verankert ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um einen Zeiger auf das übergeordnete Minirahmenfenster abzurufen. Diese Methode durchläuft alle übergeordneten Elemente und überprüft, ob ein Objekt abgeleitet [CPaneFrameWnd Klasse](../../mfc/reference/cpaneframewnd-class.md).  
  
 Verwendung `GetParentMiniFrame` zu bestimmen, ob der Bereich verankert ist.  
  
##  <a name="a-namegetparenttabbedpanea--cbasepanegetparenttabbedpane"></a><a name="getparenttabbedpane"></a>CBasePane::GetParentTabbedPane  
 Gibt einen Zeiger auf die übergeordnete Seite im Registerformat.  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die übergeordnete Seite im Registerformat falls vorhanden; andernfalls `NULL`.  
  
##  <a name="a-namegetparenttabwnda--cbasepanegetparenttabwnd"></a><a name="getparenttabwnd"></a>CBasePane::GetParentTabWnd  
 Gibt einen Zeiger auf das übergeordnete Fenster, das auf einer Registerkarte angezeigt wird.  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `hWndTab`  
 Wenn der Rückgabewert nicht `NULL`, dieser Parameter enthält das Handle für das übergeordnete Fenster im Registerkartenformat.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf das übergeordnete Fenster im Registerkartenformat zu oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um einen Zeiger auf das übergeordnete Fenster im Registerkartenformat abzurufen. Manchmal ist es nicht ausreichend, rufen Sie `GetParent`, da ein Bereich in einen andockbaren Wrapper möglicherweise ( [CDockablePaneAdapter-Klasse](../../mfc/reference/cdockablepaneadapter-class.md)) oder in einem Bereich-Adapter ( [CDockablePaneAdapter-Klasse](../../mfc/reference/cdockablepaneadapter-class.md)). Mithilfe von `GetParentTabWnd` werden einen gültigen Zeiger in diesen Fällen (vorausgesetzt, dass das übergeordnete Objekt ein Fenster im Registerkartenformat ist) abrufen können.  
  
##  <a name="a-namegetrecentvisiblestatea--cbasepanegetrecentvisiblestate"></a><a name="getrecentvisiblestate"></a>CBasePane::GetRecentVisibleState  
 Das Framework ruft diese Methode auf, wenn ein Bereich aus einem Archiv wiederhergestellt wird.  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `BOOL` , der den aktuellen Sichtbarkeitsstatus angibt. Wenn `TRUE`, war der Bereich sichtbar, wenn serialisiert und angezeigt, wenn wiederhergestellt werden. Wenn `FALSE`, Bereich wurde ausgeblendet, wenn serialisiert und ausgeblendet werden soll, wenn wiederhergestellt.  
  
##  <a name="a-namehideinprintpreviewmodea--cbasepanehideinprintpreviewmode"></a><a name="hideinprintpreviewmode"></a>CBasePane::HideInPrintPreviewMode  
 Gibt an, ob der Bereich in der Seitenansicht ausgeblendet ist.  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich nicht in der Seitenansicht angezeigt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Grundlegende Bereiche werden nicht in der Seitenansicht angezeigt. Daher diese Methode gibt immer `TRUE`.  
  
##  <a name="a-nameinsertpanea--cbasepaneinsertpane"></a><a name="insertpane"></a>CBasePane::InsertPane  
 Registriert den angegebenen Bereich der docking-Manager.  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pControlBar`  
 Ein Zeiger auf den Bereich eingefügt.  
  
 [in] `pTarget`  
 Ein Zeiger auf angrenzenden Bereich.  
  
 [in] `bAfter`  
 Wenn `TRUE`, `pControlBar` eingefügt wird, nachdem `pTarget`. Wenn `FALSE`, `pControlBar` wird eingefügt, bevor Sie `pTarget`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist, `FALSE` andernfalls.  
  
##  <a name="a-nameisaccessibilitycompatiblea--cbasepaneisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>CBasePane::IsAccessibilityCompatible  
 Gibt an, ob im Bereich Active Accessibility unterstützt.  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn im Bereich Active Accessibility unterstützt. andernfalls `FALSE`.  
  
##  <a name="a-nameisautohidemodea--cbasepaneisautohidemode"></a><a name="isautohidemode"></a>CBasePane::IsAutoHideMode  
 Bestimmt, ob ein Fenster automatisch ausgeblendet wird.  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich automatisch ausgeblendet wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Grundlegende Bereiche können nicht automatisch im Hintergrund. Diese Methode gibt immer `FALSE` zurück.  
  
##  <a name="a-nameisdialogcontrola--cbasepaneisdialogcontrol"></a><a name="isdialogcontrol"></a>CBasePane::IsDialogControl  
 Gibt an, ob der Bereich ein Dialogfeld-Steuerelement ist.  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich ein Dialogfeld-Steuerelement wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode, um das Layout Konsistenz für alle Bereiche.  
  
##  <a name="a-nameisdockeda--cbasepaneisdocked"></a><a name="isdocked"></a>CBasePane::IsDocked  
 Bestimmt, ob der Bereich angedockt ist.  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`ist das übergeordnete Element des Bereichs keiner Minirahmenfensters oder wenn der Bereich in einem Mini-Frame mit einem anderen Bereich; verankert ist andernfalls `FALSE`.  
  
##  <a name="a-nameisfloatinga--cbasepaneisfloating"></a><a name="isfloating"></a>CBasePane::IsFloating  
 Bestimmt, ob der Bereich verankert ist.  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich verankert ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt den entgegengesetzten Wert von [CBasePane::IsDocked](#isdocked).  
  
##  <a name="a-nameishorizontala--cbasepaneishorizontal"></a><a name="ishorizontal"></a>CBasePane::IsHorizontal  
 Bestimmt, ob der Bereich horizontal angedockt ist.  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich horizontal; angedockt ist andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung überprüft die aktuelle andockbare Ausrichtung für `CBRS_ORIENT_HORZ`.  
  
##  <a name="a-nameisinfloatingmultipaneframewnda--cbasepaneisinfloatingmultipaneframewnd"></a><a name="isinfloatingmultipaneframewnd"></a>CBasePane::IsInFloatingMultiPaneFrameWnd  
 Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen ist ( [CMultiPaneFrameWnd Klasse](../../mfc/reference/cmultipaneframewnd-class.md)).  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in einem Rahmenfenster mit mehreren Bereichen wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Nur andockbare Bereiche können in einem Rahmenfenster mit mehreren Bereichen float. Aus diesem Grund `CBasePane::IsInFloatingMultiPaneFrameWnd` gibt immer `FALSE`.  
  
##  <a name="a-nameismditabbeda--cbasepaneismditabbed"></a><a name="ismditabbed"></a>CBasePane::IsMDITabbed  
 Bestimmt, ob der Bereich ein untergeordnetes MDI-Fenster als ein Dokument im Registerkartenformat hinzugefügt wurde.  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn im Bereich ein untergeordnetes MDI-Fenster als ein Dokument im Registerkartenformat hinzugefügt wurde. andernfalls `FALSE`.  
  
##  <a name="a-nameispanevisiblea--cbasepaneispanevisible"></a><a name="ispanevisible"></a>CBasePane::IsPaneVisible  
 Gibt an, ob die `WS_VISIBLE` Flag für den Bereich festgelegt ist.  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn `WS_VISIBLE` festgelegt ist; andernfalls, `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [CBasePane::IsVisible](#isvisible) zum Bereich ermitteln.  
  
##  <a name="a-nameispointneardocksitea--cbasepaneispointneardocksite"></a><a name="ispointneardocksite"></a>CBasePane::IsPointNearDockSite  
 Bestimmt, ob es sich bei ein angegebenen Punkt in der Nähe der Dock-Website befindet.  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Der angegebene Punkt.  
  
 [out] `dwBarAlignment`  
 Gibt an, welchen Rand in der Nähe der Punkt ist. Mögliche Werte sind `CBRS_ALIGN_LEFT`, `CBRS_ALIGN_RIGHT`, `CBRS_ALIGN_TOP`, und`CBRS_ALIGN_BOTTOM`  
  
 [out] `bOuterEdge`  
 `TRUE`Wenn der Punkt in der Nähe von den äußeren Rahmen des Standorts Dock ist; `FALSE` andernfalls.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Punkt in der Nähe der Dock-Website ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Punkt ist in der Nähe der docksite, wenn es innerhalb der Vertraulichkeit in der Dockingstation Manager festgelegt ist. Die Vertraulichkeit der Standardwert beträgt 15 Pixel.  
  
##  <a name="a-nameisresizablea--cbasepaneisresizable"></a><a name="isresizable"></a>CBasePane::IsResizable  
 Bestimmt, ob der Bereich angepasst werden kann.  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich vom Benutzer angepasst werden kann. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Bereiche der [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) geändert werden kann.  
  
 Die Statusleiste ( [CMFCStatusBar-Klasse](../../mfc/reference/cmfcstatusbar-class.md)) und die Dock-Leiste ( [CDockSite-Klasse](../../mfc/reference/cdocksite-class.md)) kann nicht geändert werden.  
  
##  <a name="a-nameisrestoredfromregistrya--cbasepaneisrestoredfromregistry"></a><a name="isrestoredfromregistry"></a>CBasePane::IsRestoredFromRegistry  
 Bestimmt, ob der Bereich in der Registrierung wiederhergestellt wird.  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich in der Registrierung wiederhergestellt wird. andernfalls `FALSE`.  
  
##  <a name="a-nameistabbeda--cbasepaneistabbed"></a><a name="istabbed"></a>CBasePane::IsTabbed  
 Bestimmt, ob der Bereich in das Registerkarten-Steuerelement ein Fenster im Registerkartenformat eingefügt wurde.  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Steuerleiste auf einer Registerkarte der ein Fenster im Registerkartenformat eingefügt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft einen Zeiger auf das unmittelbar übergeordnete Element und legt fest, ob die Common Language Runtime-Klasse des übergeordneten Elements ist [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md).  
  
##  <a name="a-nameisvisiblea--cbasepaneisvisible"></a><a name="isvisible"></a>CBasePane::IsVisible  
 Bestimmt, ob der Bereich angezeigt wird.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Fenster sichtbar ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Bestimmen der Sichtbarkeit eines Bereichs ein. Verwenden Sie nicht `::IsWindowVisible`.  
  
 Wenn der Bereich nicht im Registerkartenformat ist (finden Sie unter [CBasePane::IsTabbed](#istabbed)), überprüft diese Methode die `WS_VISIBLE` Stil. Wenn der Bereich mit Registerkarten ist, überprüft diese Methode die Sichtbarkeit des übergeordneten Fensters im Registerkartenformat. Wenn das übergeordnete Fenster angezeigt wird, überprüft die Funktion die Sichtbarkeit der Bereich Registerkarte mit [CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible).  
  
##  <a name="a-nameloadstatea--cbasepaneloadstate"></a><a name="loadstate"></a>CBasePane::LoadState  
 Lädt den Zustand des Bereichs aus der Registrierung.  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Profilname.  
  
 [in] `nIndex`  
 Profil-Index.  
  
 [in] `uiID`  
 Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand des Bereichs erfolgreich geladen wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Bereich Status aus der Registrierung laden. Überschreiben Sie diese in einer abgeleiteten Klasse zusätzliche Informationen gespeichert, indem laden [CBasePane::SaveState](#savestate).  
  
##  <a name="a-namemovewindowa--cbasepanemovewindow"></a><a name="movewindow"></a>CBasePane::MoveWindow  
 Verschiebt den Bereich.  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Ein Rechteck, das die neue Position und Größe des Bereichs angeben.  
  
 [in] `bRepaint`  
 Wenn `TRUE`, Bereich neu gezeichnet wird. Wenn `FALSE`, der Bereich wird nicht aktualisiert.  
  
 [in] `hdwp`  
 Handle für eine verzögerte Fenster Position-Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine verzögerte Position Fensterstruktur oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie übergeben `NULL` als die `hdwp` Parameter, die diese Methode verschiebt das Fenster Normal. Wenn Sie ein Handle übergeben, führt diese Methode eine verzögerte verschieben. Sie erhalten ein Handle durch Aufrufen von [BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672) oder durch einen vorherigen Aufruf dieser Methode den Rückgabewert zu speichern.  
  
##  <a name="a-nameonafterchangeparenta--cbasepaneonafterchangeparent"></a><a name="onafterchangeparent"></a>CBasePane::OnAfterChangeParent  
 Vom Framework aufgerufen, nachdem der Bereich übergeordnete geändert.  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndOldParent`  
 Ein Zeiger auf das vorherige übergeordnete Element.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode nach übergeordneten im Bereich, in der Regel aufgrund eines Vorgangs andocken oder frei verschiebbaren Änderungen.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="a-nameonbeforechangeparenta--cbasepaneonbeforechangeparent"></a><a name="onbeforechangeparent"></a>CBasePane::OnBeforeChangeParent  
 Vom Framework aufgerufen, unmittelbar bevor der Bereich des übergeordneten Fensters geändert wird.  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndNewParent`  
 Ein Zeiger auf ein neues übergeordnetes Fenster.  
  
 [in] `bDelay`  
 Gibt an, ob Layout Anpassungen verzögert werden müssen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode nur vor den Bereich übergeordneten ändert, in der Regel aufgrund einer andocken, Gleitkomma- oder automatisch im Hintergrund-Vorgang.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="a-nameondrawcaptiona--cbasepaneondrawcaption"></a><a name="ondrawcaption"></a>CBasePane::OnDrawCaption  
 Das Framework ruft diese Methode auf, wenn der Titel gezeichnet wird.  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode hat keine Funktion für die `CBasePane` Klasse.  
  
##  <a name="a-nameonmovepanedividera--cbasepaneonmovepanedivider"></a><a name="onmovepanedivider"></a>CBasePane::OnMovePaneDivider  
 Diese Methode wird derzeit nicht verwendet.  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `CPaneDivider*`  
 Nicht verwendet.  
  
##  <a name="a-nameonpanecontextmenua--cbasepaneonpanecontextmenu"></a><a name="onpanecontextmenu"></a>CBasePane::OnPaneContextMenu  
 Vom Framework aufgerufen, wenn ein Menü erstellt, die eine Liste von Bereichen.  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParentFrame`  
 Ein Zeiger auf den übergeordneten Frame.  
  
 [in] `point`  
 Gibt die Position des Kontextmenüs.  
  
### <a name="remarks"></a>Hinweise  
 `OnPaneContextMenu`Ruft die docking-Manager, die die Liste von Bereichen verwaltet, die an das aktuelle Rahmenfenster gehören. Diese Methode die Namen der Bereiche in einem Kontextmenü hinzugefügt und angezeigt. Die Befehle im Menü anzeigen oder Ausblenden von einzelne Bereiche.  
  
 Überschreiben Sie diese Methode, um dieses Verhalten anzupassen.  
  
##  <a name="a-nameonremovefromminiframea--cbasepaneonremovefromminiframe"></a><a name="onremovefromminiframe"></a>CBasePane::OnRemoveFromMiniFrame  
 Wird vom Framework aufgerufen, wenn ein Bereich aus das übergeordnete Mini-Rahmenfenster entfernt wird.  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMiniFrame`  
 Ein Zeiger auf ein Minirahmenfenster, das aus dem Bereich entfernt wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Bereich aus seiner übergeordneten Minirahmenfenster (aufgrund von andocken, z. B.) entfernt wird.  
  
 Bei der Standardimplementierung wird keine Aktion ausgeführt.  
  
##  <a name="a-nameonsetaccdataa--cbasepaneonsetaccdata"></a><a name="onsetaccdata"></a>Cbasepane:: Onsetaccdata  
 `CBasePane`Diese Methode wird nicht verwendet werden.  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lVal`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt immer `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namepanefrompointa--cbasepanepanefrompoint"></a><a name="panefrompoint"></a>CBasePane::PaneFromPoint  
 Gibt den Bereich, der den angegebenen Punkt enthält.  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Gibt den Punkt in Bildschirmkoordinaten, um zu überprüfen.  
  
 [in] `nSensitivity`  
 Erhöhen Sie den Suchbereich, um diesen Betrag. Ein Bereich, die Suchkriterien erfüllen, fällt der angegebene Punkt im Bereich erhöhte.  
  
 [in] `bExactBar`  
 `TRUE`ignoriert die `nSensitivity` Parameter ist, andernfalls `FALSE`.  
  
 [in] `pRTCBarType`  
 Wenn dies nicht `NULL`, die-Methode sucht nur die Bereiche des angegebenen Typs.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `CBasePane`-abgeleitetes Objekt mit dem angegebenen Punkt oder `NULL` Wenn kein Bereich gefunden wurde.  
  
##  <a name="a-namerecalclayouta--cbasepanerecalclayout"></a><a name="recalclayout"></a>CBasePane::RecalcLayout  
 `CBasePane`Diese Methode wird nicht verwendet werden.  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="a-nameremovepanefromdockmanagera--cbasepaneremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CBasePane::RemovePaneFromDockManager  
 Hebt die Registrierung eines Bereichs, und entfernt sie aus der Liste in der Dockingstation-Manager.  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf einen Bereich entfernt werden soll.  
  
 [in] `bDestroy`  
 Wenn `TRUE`, entfernte Bereich zerstört wird.  
  
 [in] `bAdjustLayout`  
 Wenn `TRUE`, passen Sie das Andocken Layout sofort.  
  
 [in] `bAutoHide`  
 Wenn `TRUE`, die andocklayout bezieht sich auf die Liste der Balken automatisch im Hintergrund. Wenn `FALSE`, die andocklayout bezieht sich auf die Liste der regulären Bereiche.  
  
 [in] `pBarReplacement`  
 Ein Zeiger auf einen Bereich, der Bereich entfernten ersetzt.  
  
##  <a name="a-namesavestatea--cbasepanesavestate"></a><a name="savestate"></a>CBasePane::SaveState  
 Speichert den Zustand des Bereichs in der Registrierung.  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Profilname.  
  
 [in] `nIndex`  
 Profil-Index.  
  
 [in] `uiID`  
 Bereich-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Zustand erfolgreich gespeichert wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn er den Zustand des Bereichs in der Registrierung speichert. Überschreiben Sie `SaveState` in einer abgeleiteten Klasse zum Speichern zusätzlicher Informationen.  
  
##  <a name="a-nameselectdefaultfonta--cbasepaneselectdefaultfont"></a><a name="selectdefaultfont"></a>CBasePane::SelectDefaultFont  
 Wählt die Schriftart für einen bestimmten Gerätekontext.  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Einen Gerätekontext.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Standardwert [CFont-Klasse](../../mfc/reference/cfont-class.md) Objekt.  
  
##  <a name="a-namesetcontrolbarstylea--cbasepanesetcontrolbarstyle"></a><a name="setcontrolbarstyle"></a>CBasePane::SetControlBarStyle  
 Legt das Format des Steuerelements angezeigt.  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwNewStyle`  
 Eine bitweise OR-Kombination der folgenden möglichen Werte.  
  
|Stil|Beschreibung|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|Macht die Steuerelement-Leiste Float.|  
|`AFX_CBRS_AUTOHIDE`|Ermöglicht das automatische Ausblenden Modus.|  
|`AFX_CBRS_RESIZE`|Ermöglicht das Ändern der Größe der Steuerleiste. Wenn dieses Flag festgelegt ist, kann die Steuerleiste in einen andockbaren Bereich eingefügt werden.|  
|`AFX_CBRS_CLOSE`|Ermöglicht das Ausblenden der Steuerleiste.|  
  
##  <a name="a-namesetdockingmodea--cbasepanesetdockingmode"></a><a name="setdockingmode"></a>CBasePane::SetDockingMode  
 Legt den Andockmodus für den Bereich fest.  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dockModeNew`  
 Gibt den neuen Andockmodus für den Bereich an.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework unterstützt die andockbaren Modi: standard und unmittelbare.  
  
 Im Standardmodus andockbaren werden Bereiche und Minirahmenfenster verschoben, um mit einem Rechteck. In der unmittelbaren Andockmodus werden Steuerleisten und Minirahmenfenster sofort mit ihrem Kontext verschoben.  
  
 Der Andockmodus wird anfänglich durch definiert [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal). Sie können festlegen, dass den Andockmodus für jeden Bereich einzeln mit der `SetDockingMode` Methode.  
  
##  <a name="a-namesetpanealignmenta--cbasepanesetpanealignment"></a><a name="setpanealignment"></a>CBasePane::SetPaneAlignment  
 Legt die Ausrichtung für den Bereich fest.  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwAlignment`  
 Gibt die neue Ausrichtung.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel ruft das Framework diese Methode, wenn ein Bereich von einer Seite des Hauptframe auf einen anderen angedockt wird.  
  
 In der folgenden Tabelle sind die möglichen Werte für `dwAlignment`:  
  
|Wert|Ausrichtung|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|Linksbündige Ausrichtung.|  
|`CBRS_ALIGN_RIGHT`|Rechtsbündige Ausrichtung.|  
|`CBRS_ALIGN_TOP`|Obere Ausrichtung.|  
|`CBRS_ALIGN_BOTTOM`|Unten ausrichten.|  
  
##  <a name="a-namesetpanestylea--cbasepanesetpanestyle"></a><a name="setpanestyle"></a>CBasePane::SetPaneStyle  
 Legt den Stil des Bereichs.  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwNewStyle`  
 Gibt den neuen Stil fest.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann verwendet werden, die Formatvorlagen CBRS_ festlegen, die in afxres.h definiert sind. Da Bereich Stil und im Bereich Ausrichtung zusammen gespeichert werden, legen Sie die neue Formatvorlage, durch die Kombination mit der aktuellen Ausrichtung wie folgt.  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="a-namesetwindowposa--cbasepanesetwindowpos"></a><a name="setwindowpos"></a>CBasePane::SetWindowPos  
 Ändert die Größe, Position und Z-Reihenfolge eines Bereichs.  
  
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
 [in] `pWndInsertAfter`  
 Identifiziert die `CWnd` -Objekt, das vor dieser `CWnd` Objekt in der Z-Reihenfolge. Weitere Informationen finden Sie unter [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] `x`  
 Gibt die Position der linken Seite des Fensters.  
  
 [in] `y`  
 Gibt die Position des oberen Rand des Fensters.  
  
 [in] `cx`  
 Gibt die Breite des Fensters.  
  
 [in] `cy`  
 Gibt die Höhe des Fensters.  
  
 [in] `nFlags`  
 Gibt Optionen für Größe und Position. Weitere Informationen finden Sie unter [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos).  
  
 [in] `hdwp`  
 Handle für eine Struktur, die Größe und Position für ein oder mehrere Fenster enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für eine aktualisierte verzögerte Fenster Position Struktur oder `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `pWndInsertAfter` ist `NULL`, ruft diese Methode [CWnd:: SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos). Wenn `pWndInsertAfter` nicht `NULL`, ruft diese Methode `DeferWindowPos`.  
  
##  <a name="a-nameshowpanea--cbasepaneshowpane"></a><a name="showpane"></a>CBasePane::ShowPane  
 Blendet den Bereich oder.  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Gibt an, ob ( `TRUE`) oder ausblenden ( `FALSE`) einen Bereich.  
  
 [in] `bDelay`  
 Wenn `TRUE`, Neuberechnen der andocklayout verzögert wird.  
  
 [in] `bActivate`  
 Wenn `TRUE`, der Bereich ist aktiv, wenn dargestellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode Blendet einen Bereich. Verwenden Sie diese Methode anstelle von `ShowWindow` , da diese Methode die relevanten docking-Manager zu Änderungen in den Bereich Sichtbarkeit benachrichtigt.  
  
 Verwendung [CBasePane::IsVisible](#isvisible) zum Bestimmen der aktuellen Sichtbarkeit eines Bereichs.  
  
##  <a name="a-namestretchpanea--cbasepanestretchpane"></a><a name="stretchpane"></a>CBasePane::StretchPane  
 Streckt einen Bereich vertikal oder horizontal.  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nLength`  
 Die Länge, um den Bereich zu vergrößern.  
  
 [in] `bVert`  
 Wenn `TRUE`, vertikal gestreckt werden im Bereich. Wenn `FALSE`, vergrößern Sie den Bereich horizontal.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Bereichs gestreckt.  
  
##  <a name="a-nameundockpanea--cbasepaneundockpane"></a><a name="undockpane"></a>CBasePane::UndockPane  
 Entfernt im Bereich von docksite, Standard-Schieberegler oder Minirahmenfenster, in denen es derzeit angedockt ist.  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `bDelay`  
 Wenn TRUE, wird das andocklayout nicht sofort neu berechnet.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den Bereich Zustand zu ändern oder den andocklayout Bereich ausgeschlossen.  
  
 Wenn Sie diesen Bereich verwenden möchten, rufen Sie entweder [CBasePane::DockPane](#dockpane) oder [CBasePane::FloatPane](#floatpane) vor dem Aufrufen dieser Methode.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)

