---
title: "CDockablePane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockablePane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePane class"
ms.assetid: e2495f4c-765f-48f9-a2e2-e45e47608d91
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CDockablePane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Bereich, der entweder in eine Docksite angedockt oder in einer Seite im Registerformat enthalten sein kann.  
  
## Syntax  
  
```  
class CDockablePane : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDockablePane::CDockablePane](../Topic/CDockablePane::CDockablePane.md)|erstellt und initialisiert ein `CDockablePane`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md)|Fügt einen Bereich zu einem anderen Bereich an.  Dadurch wird eine Seite im Registerformat erstellt.|  
|[CDockablePane::CalcFixedLayout](../Topic/CDockablePane::CalcFixedLayout.md)|Gibt die Größe des Bereichsrechtecks zurück.|  
|[CDockablePane::CanAcceptMiniFrame](../Topic/CDockablePane::CanAcceptMiniFrame.md)|Bestimmt, ob die angegebenen Miniframe zum Bereich angedockt werden können.|  
|[CDockablePane::CanAcceptPane](../Topic/CDockablePane::CanAcceptPane.md)|Bestimmt, ob ein anderer Bereich auf den aktuellen Bereich angedockt werden kann.|  
|[CDockablePane::CanAutoHide](../Topic/CDockablePane::CanAutoHide.md)|Bestimmt, ob der Bereich Modus "Automatisches Ausblenden" unterstützt.  \(Überschreibungen [CBasePane::CanAutoHide](../Topic/CBasePane::CanAutoHide.md).\)|  
|[CDockablePane::CanBeAttached](../Topic/CDockablePane::CanBeAttached.md)|Bestimmt, ob der aktuelle Bereich zu einem anderen Bereich angedockt werden kann.|  
|[CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md)|Konvertiert eine oder mehrere andockbare Fenster zu MDI mit den versehenen Dokumenten.|  
|[CDockablePane::CopyState](../Topic/CDockablePane::CopyState.md)|Kopiert den Zustand eines andockbaren Fensters.|  
|[CDockablePane::Create](../Topic/CDockablePane::Create.md)|Erstellt das Windows\-Steuerelement und fügt es dem `CDockablePane`\-Objekt.|  
|[CDockablePane::CreateDefaultPaneDivider](../Topic/CDockablePane::CreateDefaultPaneDivider.md)|Erstellt einen standardmäßigen Unterteiler für den Bereich, während er einem Rahmenfenster angedockt ist.|  
|[CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md)|Erstellt das Windows\-Steuerelement und fügt es dem `CDockablePane`\-Objekt.|  
|[CDockablePane::CreateTabbedPane](../Topic/CDockablePane::CreateTabbedPane.md)|Stellt eine Seite im Registerformat im aktuellen Bereich erstellt.|  
|[CDockablePane::DockPaneContainer](../Topic/CDockablePane::DockPaneContainer.md)|Dockt einen Container zum Bereich an.|  
|[CDockablePane::DockPaneStandard](../Topic/CDockablePane::DockPaneStandard.md)|Dockt einen Bereich mithilfe des durch Andocken der Kontur \(Standard\) an.|  
|`CDockablePane::DockToFrameWindow`|Wird intern verwendet.  Um einen Bereich anzudocken, verwenden Sie [CPane::DockPane](../Topic/CPane::DockPane.md) oder [CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md).|  
|[CDockablePane::DockToRecentPos](../Topic/CDockablePane::DockToRecentPos.md)|Dockt einen Bereich zu der neuen gespeicherten Andockenposition an.|  
|[CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md)|wird ein Andocker Bereich zu einem anderen Hauptandockbereich.|  
|[CDockablePane::EnableAutohideAll](../Topic/CDockablePane::EnableAutohideAll.md)|Aktiviert oder deaktiviert Modus "Automatisches Ausblenden" für diesen Bereich zusammen mit anderen Bereichen im Container.|  
|[CDockablePane::EnableGripper](../Topic/CDockablePane::EnableGripper.md)|In oder aus die Beschriftung \(Ziehpunkt\).|  
|[CDockablePane::GetAHRestoredRect](../Topic/CDockablePane::GetAHRestoredRect.md)|Gibt die Position des Bereichs an, wenn sichtbar im Modus "Automatisches Ausblenden".|  
|[CDockablePane::GetAHSlideMode](../Topic/CDockablePane::GetAHSlideMode.md)|Ruft den Folienmodus der automatischen Ausblenden für den Bereich.|  
|`CDockablePane::GetAutoHideButton`|Wird intern verwendet.|  
|`CDockablePane::GetAutoHideToolBar`|Wird intern verwendet.|  
|[CDockablePane::GetCaptionHeight](../Topic/CDockablePane::GetCaptionHeight.md)|Gibt die Höhe der aktuellen Beschriftung zurück.|  
|[CDockablePane::GetDefaultPaneDivider](../Topic/CDockablePane::GetDefaultPaneDivider.md)|Gibt den Standardwert Bereichsteiler für den Container des Bereichs zurück.|  
|[CDockablePane::GetDockingStatus](../Topic/CDockablePane::GetDockingStatus.md)|Bestimmt die Fähigkeit eines Bereichs, anhand des bereitgestellten Zeigerposition angedockt werden.|  
|[CDockablePane::GetDragSensitivity](../Topic/CDockablePane::GetDragSensitivity.md)|Gibt die Ziehempfindlichkeit eines andockbaren Bereichs zurück.|  
|[CDockablePane::GetLastPercentInPaneContainer](../Topic/CDockablePane::GetLastPercentInPaneContainer.md)|Ruft den Prozentsatz des Speichers ab, den ein Bereich innerhalb seines Containers belegt.|  
|[CDockablePane::GetTabArea](../Topic/CDockablePane::GetTabArea.md)|Ruft den Registerkartenbereich für den Bereich.|  
|[CDockablePane::GetTabbedPaneRTC](../Topic/CDockablePane::GetTabbedPaneRTC.md)|Gibt die Ablaufklasseninformationen über ein Fenster im Registerkartenformat zurück, das erstellt wird, wenn ein anderer Bereich auf den aktuellen Bereich angedockt werden.|  
|[CDockablePane::HasAutoHideMode](../Topic/CDockablePane::HasAutoHideMode.md)|Gibt an, ob ein Andocker Bereich den Modus "Automatisches Ausblenden" umgeschaltet werden kann.|  
|[CDockablePane::HitTest](../Topic/CDockablePane::HitTest.md)|Gibt den bestimmten Position in einem Bereich, in dem der Benutzer auf eine Maus klickt.|  
|`CDockablePane::IsAccessibilityCompatible`|Wird intern verwendet.|  
|[CDockablePane::IsAutohideAllEnabled](../Topic/CDockablePane::IsAutohideAllEnabled.md)|Gibt an, ob der andockbare Bereich und alle anderen Bereiche im Container im Modus "Automatisches Ausblenden" eingefügt werden können.|  
|[CDockablePane::IsAutoHideMode](../Topic/CDockablePane::IsAutoHideMode.md)|Bestimmt, ob ein Bereich im Modus "Automatisches Ausblenden" ist.|  
|`CDockablePane::IsChangeState`|Wird intern verwendet.|  
|[CDockablePane::IsDocked](../Topic/CDockablePane::IsDocked.md)|Bestimmt, ob der aktuelle Bereich angedockt ist.|  
|[CDockablePane::IsHideInAutoHideMode](../Topic/CDockablePane::IsHideInAutoHideMode.md)|Bestimmt das Verhalten eines Bereichs, der im Modus "Automatisches Ausblenden" ist, wenn es wird angezeigt \(oder ausgeblendet\), indem `ShowPane` aufruft.|  
|[CDockablePane::IsInFloatingMultiPaneFrameWnd](../Topic/CDockablePane::IsInFloatingMultiPaneFrameWnd.md)|Gibt an, ob der Bereich in einem Rahmenfenster mit mehreren Bereichen ist.|  
|[CDockablePane::IsResizable](../Topic/CDockablePane::IsResizable.md)|Gibt an, ob der Bereich veränderbar ist.|  
|[CDockablePane::IsTabLocationBottom](../Topic/CDockablePane::IsTabLocationBottom.md)|Gibt an, ob Registerkarten oben oder unter im Bereich befinden.|  
|[CDockablePane::IsTracked](../Topic/CDockablePane::IsTracked.md)|Gibt an, ob ein Bereich vom Benutzer gezogen wird.|  
|[CDockablePane::IsVisible](../Topic/CDockablePane::IsVisible.md)|Bestimmt, ob der aktuelle Bereich sichtbar ist.|  
|[CDockablePane::LoadState](assetId:///96110136-4f46-4764-8a76-3b4abaf77917)|Wird intern verwendet.|  
|[CDockablePane::OnAfterChangeParent](../Topic/CDockablePane::OnAfterChangeParent.md)|Aufgerufen vom Framework, wenn das übergeordnete Element eines Bereichs geändert hat.  \(Überschreibungen [CPane::OnAfterChangeParent](../Topic/CPane::OnAfterChangeParent.md).\)|  
|[CDockablePane::OnAfterDockFromMiniFrame](../Topic/CDockablePane::OnAfterDockFromMiniFrame.md)|Aufgerufen vom Framework wenn wird eine unverankerte Andockenleiste an einem Rahmenfenster.|  
|[CDockablePane::OnBeforeChangeParent](../Topic/CDockablePane::OnBeforeChangeParent.md)|Aufgerufen vom Framework, wenn das übergeordnete Element des Bereichs im Begriff ist zu ändern.  \(Überschreibungen [CPane::OnBeforeChangeParent](../Topic/CPane::OnBeforeChangeParent.md).\)|  
|[CDockablePane::OnBeforeFloat](../Topic/CDockablePane::OnBeforeFloat.md)|Aufgerufen vom Framework ausgelöst, wenn ein Bereich im Begriff ist von Fenstern.  \(Überschreibungen [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md).\)|  
|[CDockablePane::RemoveFromDefaultPaneDividier](../Topic/CDockablePane::RemoveFromDefaultPaneDividier.md)|Das Framework ruft diese Methode auf, wenn ein Bereich abgedockt wird.|  
|[CDockablePane::ReplacePane](../Topic/CDockablePane::ReplacePane.md)|Ersetzt den Bereich durch einen angegebenen Bereich.|  
|[CDockablePane::RestoreDefaultPaneDivider](../Topic/CDockablePane::RestoreDefaultPaneDivider.md)|Das Framework ruft diese Methode auf, während ein Bereich deserialisiert wird, um den standardmäßigen Bereichsteiler wiederherzustellen.|  
|`CDockablePane::SaveState`|Wird intern verwendet.|  
|`CDockablePane::Serialize`|Serialisiert den Bereich.  \(Überschreibungen `CBasePane::Serialize`.\)|  
|[CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)|Schaltet den Hauptandockbereich zwischen und und Modus "Automatisches Ausblenden" um.|  
|[CDockablePane::SetAutoHideParents](../Topic/CDockablePane::SetAutoHideParents.md)|Legt die Schaltfläche der automatische Ausblendenen automatische Ausblenden und die Symbolleiste der automatische Ausblendenen automatische Ausblenden für den Bereich fest.|  
|`CDockablePane::SetDefaultPaneDivider`|Wird intern verwendet.|  
|[CDockablePane::SetLastPercentInPaneContainer](../Topic/CDockablePane::SetLastPercentInPaneContainer.md)|Legt den Prozentsatz des Bereichs fest, den ein Bereich innerhalb seines Containers belegt.|  
|`CDockablePane::SetResizeMode`|Wird intern verwendet.|  
|[CDockablePane::SetRestoredDefaultPaneDivider](../Topic/CDockablePane::SetRestoredDefaultPaneDivider.md)|Legt den wiederhergestellten Standard Bereichsteiler fest.|  
|[CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md)|Legt die Ablaufklasseninformationen für ein Fenster im Registerkartenformat fest, das erstellt wird, wenn zwei Bereiche zusammen andocken.|  
|[CDockablePane::ShowPane](../Topic/CDockablePane::ShowPane.md)|In oder aus ein Bereich.|  
|[CDockablePane::Slide](../Topic/CDockablePane::Slide.md)|Zeigt an oder blendet einen Bereich mit einer gleitenden Animation aus, das angezeigt wird, wenn der Bereich im Modus "Automatisches Ausblenden" ist.|  
|[CDockablePane::ToggleAutoHide](../Topic/CDockablePane::ToggleAutoHide.md)|Schaltet Modus "Automatisches Ausblenden" um.  \(Überschreibungen [CPane::ToggleAutoHide](../Topic/CPane::ToggleAutoHide.md) .\)|  
|[CDockablePane::UndockPane](../Topic/CDockablePane::UndockPane.md)|Dockt einen Bereich entweder vom Hauptrahmenfenster oder einem Minirahmenfenstercontainer ab.|  
|`CDockablePane::UnSetAutoHideMode`|Wird intern verwendet.  Um den Modus "Automatisches Ausblenden" festzulegen, verwenden Sie [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md)|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDockablePane::CheckAutoHideCondition](../Topic/CDockablePane::CheckAutoHideCondition.md)|Bestimmt, ob der andockbare Bereich ausgeblendet wird \(im Modus "Automatisches Ausblenden"\).|  
|[CDockablePane::CheckStopSlideCondition](../Topic/CDockablePane::CheckStopSlideCondition.md)|Bestimmt, ob ein Andocker Bereich der automatische Ausblendenen automatische Ausblenden zu schieben beendet werden soll.|  
|[CDockablePane::DrawCaption](../Topic/CDockablePane::DrawCaption.md)|Zeichnet die andockbare Bereichsbeschriftung \(Ziehpunkt\).|  
|[CDockablePane::OnPressButtons](../Topic/CDockablePane::OnPressButtons.md)|Aufgerufen, wenn der Benutzer eine Beschriftungsschaltfläche als die `AFX_HTCLOSE` und `AFX_HTMAXBUTTON` Schaltflächen drückt.|  
|[CDockablePane::OnSlide](../Topic/CDockablePane::OnSlide.md)|Aufgerufen vom Framework, um den Folieneffekt der automatische Ausblendenen automatische Ausblenden zu rendern, wenn der Bereich entweder ein\- oder ausgeblendet wird.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDockablePane::m\_bDisableAnimation](../Topic/CDockablePane::m_bDisableAnimation.md)|Gibt an, ob der Animation automatische Ausblendenen automatische Ausblenden des andockbaren Fensters deaktiviert ist.|  
|[CDockablePane::m\_bHideInAutoHideMode](../Topic/CDockablePane::m_bHideInAutoHideMode.md)|Bestimmt das Verhalten des Bereichs, wenn der Bereich im Modus "Automatisches Ausblenden" ist.|  
|[CDockablePane::m\_nSlideSteps](../Topic/CDockablePane::m_nSlideSteps.md)|Gibt die Animationsgeschwindigkeit des Bereichs an, wenn sie sich im Modus "Automatisches Ausblenden" angezeigt oder ausgeblendet wird.|  
  
## Hinweise  
 `CDockablePane` implementiert die folgende Funktionalität:  
  
-   Andocken eines Bereichs einen Hauptrahmenfenster.  
  
-   Umschalten eines Bereichs für den Modus "Automatisches Ausblenden".  
  
-   Anfügen eines Bereichs in ein Fenster im Registerkartenformat.  
  
-   unverankert eines Bereichs in einem Minirahmenfenster.  
  
-   Markieren eines Bereichs zu einem anderen Bereich andocken, der in einem Minirahmenfenster unverankert ist.  
  
-   Ändern der Größe eines Bereichs.  
  
-   Laden und Einsparungszustand für einen Hauptandockbereich.  
  
    > [!NOTE]
    >  Zustandsinformationen werden zur Windows\-Registrierung gespeichert.  
  
-   Erstellen eines Bereichs mit oder ohne eine Beschriftung.  Die Beschriftung kann eine Beschriftung haben und kann mit einer Farbverlaufsfarbe gefüllt werden.  
  
-   Ziehen eines Bereichs beim Anzeigen des Inhalts des Bereichs  
  
-   Ziehen eines Bereichs beim Anzeigen eines Ziehrechtecks.  
  
 Um einen Hauptandockbereich in der Anwendung zu verwenden, leiten Sie die Bereichsklasse aus der `CDockablePane`\-Klasse.  Entweder betten Sie das abgeleitete Objekt in das Hauptrahmenfensterobjekt oder in ein Fensterobjekt ein, das die Instanz des Bereichs steuert.  Rufen Sie dann die [CDockablePane::Create](../Topic/CDockablePane::Create.md)[CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md)\-Methode oder die Methode auf, wenn Sie die `WM_CREATE` Meldung im Hauptrahmenfenster verarbeiten.  Schließlich installieren Sie das Bereichsobjekt, indem Sie [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md), [CBasePane::DockPane](../Topic/CBasePane::DockPane.md) oder [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) aufrufen.  
  
## Anpassungs\-Tipps  
 Die folgenden Tipps gelten für `CDockablePane`\-Objekte:  
  
-   Wenn Sie [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) für zwei nicht\-imRegisterkartenformat aufrufen, werden andockbare Fenster, ein Zeiger auf ein Fenster im Registerkartenformat im `ppTabbedControlBar`\-Parameter zurückgegeben.  Sie können weiterhin, um Registerkarten zum Fenster im Registerkartenformat hinzuzufügen, indem Sie diesen Parameter verwenden.  
  
-   Die Art der Seite im Registerformat, die von [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md) erstellt wird, wird durch das `CDockablePane`\-Objekt im `pTabControlBarAttachTo`\-Parameter bestimmt.  Sie können [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md) aufrufen, um die Art der Seite im Registerformat festzulegen, die `CDockablePane` erstellt.  Der Standardtyp wird durch `dwTabbedStyle` von [CDockablePane::Create](../Topic/CDockablePane::Create.md) bestimmt, wenn Sie zuerst `CDockablePane` erstellen.  Wenn `dwTabbedStyle` AFX\_CBRS\_OUTLOOK\_TABS ist, ist der Standardtyp [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md); wenn `dwTabbedStyle` AFX\_CBRS\_REGULAR\_TABS ist, ist der Standardtyp [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md).  
  
-   Wenn Sie ein andockbares Fenster zu anderen andocken möchten, rufen Sie die [CDockablePane::DockToWindow](../Topic/CDockablePane::DockToWindow.md)\-Methode auf.  Der ursprüngliche Bereich muss irgendwo angedockt werden, bevor Sie diese Methode aufrufen.  
  
-   Die Membervariable [CDockablePane::m\_bHideInAutoHideMode](../Topic/CDockablePane::m_bHideInAutoHideMode.md)\-Steuerelemente, wie andockbare Fenster im Modus der automatischen Ausblenden verhalten, wenn Sie [CDockablePane::ShowPane](../Topic/CDockablePane::ShowPane.md) aufrufen.  Wenn diese Membervariable zu `TRUE` festgelegt ist, werden andockbare Fenster und ihre Schaltflächen der automatischen Ausblenden ausgeblendet.  Andernfalls schieben diese in und aus.  
  
-   Sie können Animation der automatische Ausblendenen automatische Ausblenden deaktivieren, indem Sie die [CDockablePane::m\_bDisableAnimation](../Topic/CDockablePane::m_bDisableAnimation.md)\-Membervariable zu `TRUE` festlegen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Objekt `CDockablePane` konfiguriert, indem verschiedene Methoden in der `CDockablePane`\-Klasse angewendet wird.  Das Beispiel veranschaulicht, wie die automatische Ausblendenen automatische Ausblenden alle Funktion für das andockbare Fenster aktiviert, die Beschriftung oder den Ziehpunkt aktiviert, den Modus "Automatisches Ausblenden" aktiviert, den Bereich anzeigt und einen Bereich animiert, der im Modus "Automatisches Ausblenden" ist.  Dieser Codeausschnitt ist Teil [Visual Studio\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_VisualStudioDemo#27](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#27)]  
[!CODE [NVC_MFC_VisualStudioDemo#28](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#28)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
## Anforderungen  
 **Header:** afxDockablePane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)