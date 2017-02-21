---
title: "CMFCTasksPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPane class"
ms.assetid: b456328e-2525-4642-b78b-9edd1a1a7d3f
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCTasksPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Die `CMFCTasksPane`\-Klasse implementiert eine Liste anklickbarer Elemente \(Aufgaben\).  
  
## Syntax  
  
```  
class CMFCTasksPane : public CDockablePane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCTasksPane::CMFCTasksPane](../Topic/CMFCTasksPane::CMFCTasksPane.md)|Erstellt ein `CMFCTasksPane`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCTasksPane::AddGroup](../Topic/CMFCTasksPane::AddGroup.md)|Fügt dem Aufgabenbereich\-Steuerelement eine neue Gruppe von Aufgaben hinzu.|  
|[CMFCTasksPane::AddLabel](../Topic/CMFCTasksPane::AddLabel.md)|Fügt der angegebenen Aufgabengruppe eine neue statische Bezeichnung hinzu.|  
|[CMFCTasksPane::AddMRUFilesList](../Topic/CMFCTasksPane::AddMRUFilesList.md)|Fügt Aufgaben anhand einer Dateiliste zuletzt verwendeter Aufgaben in einer Gruppe hinzu.|  
|[CMFCTasksPane::AddPage](../Topic/CMFCTasksPane::AddPage.md)|Fügt dem Aufgabenbereich eine neue Seite hinzu.|  
|[CMFCTasksPane::AddSeparator](../Topic/CMFCTasksPane::AddSeparator.md)||  
|[CMFCTasksPane::AddTask](../Topic/CMFCTasksPane::AddTask.md)|Fügt der angegebenen Aufgabengruppe eine neue Aufgabe hinzu.|  
|[CMFCTasksPane::AddWindow](../Topic/CMFCTasksPane::AddWindow.md)|Fügt dem Aufgabenbereich ein untergeordnetes Fenster hinzu.|  
|[CMFCTasksPane::CollapseAllGroups](../Topic/CMFCTasksPane::CollapseAllGroups.md)||  
|[CMFCTasksPane::CollapseGroup](../Topic/CMFCTasksPane::CollapseGroup.md)|Reduziert eine Gruppe programmgesteuert.|  
|[CMFCTasksPane::CreateDefaultMiniframe](../Topic/CMFCTasksPane::CreateDefaultMiniframe.md)|\(Überschreibt [CPane::CreateDefaultMiniframe](../Topic/CPane::CreateDefaultMiniframe.md).\)|  
|[CMFCTasksPane::CreateMenu](../Topic/CMFCTasksPane::CreateMenu.md)|Wird von dem Framework aufgerufen, um ein Menü für die**Andere Aufgabenbereiche**\-Menüschaltfläche hinzuzufügen.|  
|[CMFCTasksPane::EnableAnimation](../Topic/CMFCTasksPane::EnableAnimation.md)|Aktiviert oder deaktiviert die Animation beim Reduzieren oder Erweitern von Aufgabengruppen.|  
|[CMFCTasksPane::EnableGroupCollapse](../Topic/CMFCTasksPane::EnableGroupCollapse.md)|Gibt an, ob Aufgabengruppen reduziert werden können.|  
|[CMFCTasksPane::EnableHistoryMenuButtons](../Topic/CMFCTasksPane::EnableHistoryMenuButtons.md)|Aktiviert oder deaktiviert die Dropdown\-Menüs in den Navigationsschaltflächen **Weiter** und **Zurück**.|  
|[CMFCTasksPane::EnableNavigationToolbar](../Topic/CMFCTasksPane::EnableNavigationToolbar.md)|Aktiviert oder deaktiviert die Navigationssymbolleiste.|  
|[CMFCTasksPane::EnableOffsetCustomControls](../Topic/CMFCTasksPane::EnableOffsetCustomControls.md)||  
|[CMFCTasksPane::EnableScrollButtons](../Topic/CMFCTasksPane::EnableScrollButtons.md)|Aktiviert die Schaltflächen für Bildlauf statt der Bildlaufleiste.|  
|[CMFCTasksPane::EnableWrapLabels](../Topic/CMFCTasksPane::EnableWrapLabels.md)|Aktiviert oder deaktiviert den Wortumbruch für Bezeichnungen.|  
|[CMFCTasksPane::EnableWrapTasks](../Topic/CMFCTasksPane::EnableWrapTasks.md)|Aktiviert oder deaktiviert den Wortumbruch für Aufgaben.|  
|[CMFCTasksPane::GetActivePage](../Topic/CMFCTasksPane::GetActivePage.md)|Gibt den nullbasierten Index für die aktive Seite zurück.|  
|[CMFCTasksPane::GetGroupCaptionHeight](../Topic/CMFCTasksPane::GetGroupCaptionHeight.md)|Gibt die Höhe der Gruppenbeschriftungen zurück.|  
|[CMFCTasksPane::GetGroupCaptionHorzOffset](../Topic/CMFCTasksPane::GetGroupCaptionHorzOffset.md)|Gibt den aktuellen Offset einer Gruppenbeschriftung vom linken und rechten Rand des Aufgabenbereichs zurück.|  
|[CMFCTasksPane::GetGroupCaptionVertOffset](../Topic/CMFCTasksPane::GetGroupCaptionVertOffset.md)|Gibt den aktuellen Offset einer Gruppenbeschriftung vom oberen und unteren Rand des Aufgabenbereichs zurück.|  
|[CMFCTasksPane::GetGroupCount](../Topic/CMFCTasksPane::GetGroupCount.md)|Ruft die Gesamtanzahl von Gruppen zurück.|  
|[CMFCTasksPane::GetGroupLocation](../Topic/CMFCTasksPane::GetGroupLocation.md)|Gibt den internen Gruppenindex für eine angegebene Gruppe zurück.|  
|[CMFCTasksPane::GetGroupVertOffset](../Topic/CMFCTasksPane::GetGroupVertOffset.md)|Gibt den vertikalen Offset einer Gruppe zurück.|  
|[CMFCTasksPane::GetHorzMargin](../Topic/CMFCTasksPane::GetHorzMargin.md)|Gibt den horizontalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs zurück.|  
|[CMFCTasksPane::GetNextPages](../Topic/CMFCTasksPane::GetNextPages.md)||  
|[CMFCTasksPane::GetPageByGroup](../Topic/CMFCTasksPane::GetPageByGroup.md)|Ruft den Seitenindex für eine angegebene Gruppe ab.|  
|[CMFCTasksPane::GetPagesCount](../Topic/CMFCTasksPane::GetPagesCount.md)|Gibt die Anzahl der Seiten zurück.|  
|[CMFCTasksPane::GetPreviousPages](../Topic/CMFCTasksPane::GetPreviousPages.md)||  
|[CMFCTasksPane::GetScrollBarCtrl](../Topic/CMFCTasksPane::GetScrollBarCtrl.md)|\(Überschreibt [CWnd::GetScrollBarCtrl](../Topic/CWnd::GetScrollBarCtrl.md).\)|  
|[CMFCTasksPane::GetTask](../Topic/CMFCTasksPane::GetTask.md)|Ruft eine Aufgabe ab.|  
|[CMFCTasksPane::GetTaskCount](../Topic/CMFCTasksPane::GetTaskCount.md)|Gibt die Anzahl von Aufgabenelementen in einer angegebenen Gruppe zurück.|  
|[CMFCTasksPane::GetTaskGroup](../Topic/CMFCTasksPane::GetTaskGroup.md)|Gibt eine Aufgabengruppe für einen angegebenen Gruppenindex zurück.|  
|[CMFCTasksPane::GetTaskLocation](../Topic/CMFCTasksPane::GetTaskLocation.md)|Gibt die Gruppe und den Index für eine angegebene Aufgabe zurück.|  
|[CMFCTasksPane::GetTasksHorzOffset](../Topic/CMFCTasksPane::GetTasksHorzOffset.md)|Gibt den horizontale Offset von Aufgaben vom linken und rechten Rand der übergeordneten Gruppen zurück.|  
|[CMFCTasksPane::GetTasksIconHorzOffset](../Topic/CMFCTasksPane::GetTasksIconHorzOffset.md)||  
|[CMFCTasksPane::GetTasksIconVertOffset](../Topic/CMFCTasksPane::GetTasksIconVertOffset.md)||  
|[CMFCTasksPane::GetVertMargin](../Topic/CMFCTasksPane::GetVertMargin.md)|Gibt den horizontalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs zurück.|  
|[CMFCTasksPane::IsAccessibilityCompatible](../Topic/CMFCTasksPane::IsAccessibilityCompatible.md)|\(Überschreibt `CDockablePane::IsAccessibilityCompatible`.\)|  
|[CMFCTasksPane::IsAnimationEnabled](../Topic/CMFCTasksPane::IsAnimationEnabled.md)|Gibt an, ob die Animation aktiviert ist.|  
|[CMFCTasksPane::IsBackButtonEnabled](../Topic/CMFCTasksPane::IsBackButtonEnabled.md)|Gibt an, ob die Zurück\-Schaltfläche aktiviert ist.|  
|[CMFCTasksPane::IsForwardButtonEnabled](../Topic/CMFCTasksPane::IsForwardButtonEnabled.md)|Gibt an, ob die Weiter\-Schaltfläche aktiviert ist.|  
|[CMFCTasksPane::IsGroupCollapseEnabled](../Topic/CMFCTasksPane::IsGroupCollapseEnabled.md)||  
|[CMFCTasksPane::IsHistoryMenuButtonsEnabled](../Topic/CMFCTasksPane::IsHistoryMenuButtonsEnabled.md)|Gibt an, ob die Navigationsschaltflächen **Weiter** und **Zurück** Dropdown\-Menüs besitzen.|  
|[CMFCTasksPane::IsNavigationToolbarEnabled](../Topic/CMFCTasksPane::IsNavigationToolbarEnabled.md)|Gibt an, ob die Navigationssymbolleiste aktiviert ist.|  
|[CMFCTasksPane::IsToolBox](../Topic/CMFCTasksPane::IsToolBox.md)||  
|[CMFCTasksPane::IsWrapLabelsEnabled](../Topic/CMFCTasksPane::IsWrapLabelsEnabled.md)|Gibt an, ob der Aufgabenbereich Wörter in Bezeichnungen umbricht.|  
|[CMFCTasksPane::IsWrapTasksEnabled](../Topic/CMFCTasksPane::IsWrapTasksEnabled.md)|Gibt an, ob der Aufgabenbereich Wörter in Aufgaben umbricht.|  
|[CMFCTasksPane::LoadState](../Topic/CMFCTasksPane::LoadState.md)|\(Überschreibt [CDockablePane::LoadState](assetId:///96110136-4f46-4764-8a76-3b4abaf77917).\)|  
|[CMFCTasksPane::OnCancel](../Topic/CMFCTasksPane::OnCancel.md)||  
|[CMFCTasksPane::OnClickTask](../Topic/CMFCTasksPane::OnClickTask.md)|Wird vom Framework aufgerufen, wenn der Benutzer auf ein Element im Aufgabenbereich klickt.|  
|[CMFCTasksPane::OnOK](../Topic/CMFCTasksPane::OnOK.md)||  
|[CMFCTasksPane::OnPressBackButton](../Topic/CMFCTasksPane::OnPressBackButton.md)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Zurück\-Schaltfläche klickt.|  
|[CMFCTasksPane::OnPressForwardButton](../Topic/CMFCTasksPane::OnPressForwardButton.md)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Navigationsschaltfläche Weiter klickt.|  
|[CMFCTasksPane::OnPressHomeButton](../Topic/CMFCTasksPane::OnPressHomeButton.md)|Wird vom Framework aufgerufen, wenn der Benutzer auf die Navigationsschaltfläche Startseite klickt.|  
|[CMFCTasksPane::OnPressOtherButton](../Topic/CMFCTasksPane::OnPressOtherButton.md)||  
|[CMFCTasksPane::OnSetAccData](../Topic/CMFCTasksPane::OnSetAccData.md)|\(Überschreibt [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCTasksPane::OnUpdateCmdUI](../Topic/CMFCTasksPane::OnUpdateCmdUI.md)|\(Überschreibt [CDockablePane::OnUpdateCmdUI](assetId:///5dd61606-1c12-40d4-b024-f3839aa5e2e0).\)|  
|[CMFCTasksPane::PreTranslateMessage](../Topic/CMFCTasksPane::PreTranslateMessage.md)|\(Überschreibt [CDockablePane::PreTranslateMessage](assetId:///49a242cc-b158-400e-9e01-0345ec9c3ffd).\)|  
|[CMFCTasksPane::RecalcLayout](../Topic/CMFCTasksPane::RecalcLayout.md)|\(Überschreibt [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CMFCTasksPane::RemoveAllGroups](../Topic/CMFCTasksPane::RemoveAllGroups.md)|Entfernt alle Gruppen auf der angegebenen Seite.|  
|[CMFCTasksPane::RemoveAllPages](../Topic/CMFCTasksPane::RemoveAllPages.md)|Entfernt alle Seiten aus dem Aufgabenbereich mit Ausnahme der Standardseite \(erste\).|  
|[CMFCTasksPane::RemoveAllTasks](../Topic/CMFCTasksPane::RemoveAllTasks.md)|Entfernt alle Aufgaben aus der Gruppe.|  
|[CMFCTasksPane::RemoveGroup](../Topic/CMFCTasksPane::RemoveGroup.md)|Entfernt eine Gruppe.|  
|[CMFCTasksPane::RemovePage](../Topic/CMFCTasksPane::RemovePage.md)|Entfernt eine angegebene Seite aus dem Aufgabenbereich.|  
|[CMFCTasksPane::RemoveTask](../Topic/CMFCTasksPane::RemoveTask.md)|Entfernt eine Aufgabe aus einer Aufgabengruppe.|  
|[CMFCTasksPane::SaveState](../Topic/CMFCTasksPane::SaveState.md)|\(Überschreibt [CDockablePane::SaveState](assetId:///c5c24249-8d0d-46cb-96d9-9f5c6dc191db).\)|  
|[CMFCTasksPane::Serialize](../Topic/CMFCTasksPane::Serialize.md)|\(Überschreibt [CDockablePane::Serialize](assetId:///09787e59-e446-4e76-894b-206d303dcfd6).\)|  
|[CMFCTasksPane::SetActivePage](../Topic/CMFCTasksPane::SetActivePage.md)|Aktiviert eine angegebene Seite im Aufgabenbereich.|  
|[CMFCTasksPane::SetCaption](../Topic/CMFCTasksPane::SetCaption.md)|Legt den Beschriftungsnamen eines Aufgabenbereichs fest.|  
|[CMFCTasksPane::SetGroupCaptionHeight](../Topic/CMFCTasksPane::SetGroupCaptionHeight.md)|Legt die Höhe einer Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupCaptionHorzOffset](../Topic/CMFCTasksPane::SetGroupCaptionHorzOffset.md)|Legt den horizontalen Offset einer Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupCaptionVertOffset](../Topic/CMFCTasksPane::SetGroupCaptionVertOffset.md)|Legt den vertikalen Offset einer Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupName](../Topic/CMFCTasksPane::SetGroupName.md)|Legt einen Gruppennamen fest.|  
|[CMFCTasksPane::SetGroupTextColor](../Topic/CMFCTasksPane::SetGroupTextColor.md)|Legt die Textfarbe für eine Gruppenbeschriftung fest.|  
|[CMFCTasksPane::SetGroupVertOffset](../Topic/CMFCTasksPane::SetGroupVertOffset.md)|Legt den vertikalen Offset für eine Gruppe fest.|  
|[CMFCTasksPane::SetHorzMargin](../Topic/CMFCTasksPane::SetHorzMargin.md)|Legt den horizontalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs fest.|  
|[CMFCTasksPane::SetIconsList](../Topic/CMFCTasksPane::SetIconsList.md)|Legt die den Aufgaben zugeordnete Bilderliste fest.|  
|[CMFCTasksPane::SetPageCaption](../Topic/CMFCTasksPane::SetPageCaption.md)|Legt den Beschriftungstext für eine Aufgabenbereichsseite fest.|  
|[CMFCTasksPane::SetTaskName](../Topic/CMFCTasksPane::SetTaskName.md)|Legt den Namen für eine Aufgabe fest.|  
|[CMFCTasksPane::SetTasksIconHorzOffset](../Topic/CMFCTasksPane::SetTasksIconHorzOffset.md)||  
|[CMFCTasksPane::SetTasksIconVertOffset](../Topic/CMFCTasksPane::SetTasksIconVertOffset.md)||  
|[CMFCTasksPane::SetTaskTextColor](../Topic/CMFCTasksPane::SetTaskTextColor.md)|Legt die Textfarbe für eine Aufgabe fest.|  
|[CMFCTasksPane::SetTasksHorzOffset](../Topic/CMFCTasksPane::SetTasksHorzOffset.md)|Legt den horizontale Offset von Aufgaben vom linken und rechten Rand der übergeordneten Gruppen fest.|  
|[CMFCTasksPane::SetVertMargin](../Topic/CMFCTasksPane::SetVertMargin.md)|Legt den vertikalen Abstand zwischen einem Aufgabenbereich und den Rändern des Clientbereichs fest.|  
|[CMFCTasksPane::SetWindowHeight](../Topic/CMFCTasksPane::SetWindowHeight.md)|Legt die Höhe eines Fensters fest.|  
|[CMFCTasksPane::ShowCommandMessageString](../Topic/CMFCTasksPane::ShowCommandMessageString.md)||  
|[CMFCTasksPane::ShowTask](../Topic/CMFCTasksPane::ShowTask.md)|Blendet eine Aufgabe ein oder aus.|  
|[CMFCTasksPane::ShowTaskByCmdId](../Topic/CMFCTasksPane::ShowTaskByCmdId.md)|Blendet eine Aufgabe basierend auf der Befehls\-ID ein oder aus.|  
|[CMFCTasksPane::Update](../Topic/CMFCTasksPane::Update.md)|Aktualisiert die GUI\-Elemente, die zu einem Aufgabenbereich gehören.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCTasksPane::OnActivateTasksPanePage](../Topic/CMFCTasksPane::OnActivateTasksPanePage.md)|Wird vom Framework aufgerufen, wenn eine neue Aufgabenbereichsseite aktiviert wird.|  
  
## Hinweise  
 Die `CMFCTasksPane`\-Klasse implementiert folgende Funktionen:  
  
-   Elemente können gruppiert werden und jede Elementgruppierung kann eine zugeordnete Beschriftung besitzen.  
  
-   Elementgruppierungen können reduzierte oder erweitert werden.  
  
-   Jedem Element im Aufgabenbereich kann ein Symbol zugewiesen werden.  
  
-   Einzelnen Elementen kann eine Befehls\-ID zugeordnet werden, die ausgeführt wird, wenn ein Benutzer auf das Element klickt.  Beim Klicken wird die `WM_COMMAND`\-Nachricht an den Besitzer des Aufgabenbereich\-Steuerelements gesendet.  
  
 Befolgen Sie folgende Schritte, um das `CMFCTasksPane`\-Steuerelement in Ihrer Anwendung zu verwenden:  
  
1.  Betten Sie ein `CMFCTasksPane`\-Objekt in die Hauptframe\-Fensterklasse ein.  
  
2.  Rufen Sie bei der Verarbeitung der `WM_CREATE`\-Meldung die `Create`\-Methode auf.  Sie können reguläre [CControlBar](../../mfc/reference/ccontrolbar-class.md)\-Formate verwenden.  Weitere Informationen finden Sie unter `CControlBar::Create`.  
  
3.  Rufen Sie die [CMFCTasksPane::AddGroup](../Topic/CMFCTasksPane::AddGroup.md)\-Methode auf, um verschiedene Gruppen hinzuzufügen.  
  
4.  Rufen Sie die [CMFCTasksPane::AddTask](../Topic/CMFCTasksPane::AddTask.md)\-, [CMFCTasksPane::AddLabel](../Topic/CMFCTasksPane::AddLabel.md)\- oder [CMFCTasksPane::AddMRUFilesList](../Topic/CMFCTasksPane::AddMRUFilesList.md)\-Elementfunktion auf, um den einzelnen Gruppen neue Elemente \(Aufgaben\) hinzuzufügen.  
  
5.  Rufen Sie [CMFCTasksPane::EnableGroupCollapse](../Topic/CMFCTasksPane::EnableGroupCollapse.md) auf, um anzugeben, ob Elementgruppen reduziert werden können.  
  
 Die folgende Abbildung zeigt ein typisches Aufgabenbereich\-Steuerelement.  Die erste Gruppe ist eine *besondere* Gruppe und die Beschriftung weist eine dunklere Farbe auf.  Die dritte Gruppe wird reduziert.  Die letzte Gruppe orientiert sich am unteren Rand des Aufgabenbereichs und besitzt keine Beschriftung und die letzte Aufgabe in der Gruppe ist eine einfache Beschriftung:  
  
 ![Beispiel für den Aufgabenbereich](../../mfc/reference/media/nexttaskpane.png "NextTaskPane")  
  
 Sie können die Darstellung des Aufgabenbereichs anpassen, indem Sie verschiedene Ränder und Offsets anpassen.  Die folgende Abbildung verdeutlicht die Bedeutung dieser Variablen:  
  
 ![Benutzerdefinierte Aufgabengruppe](../../mfc/reference/media/nexttaskgrpcustom.png "NextTaskGrpCustom")  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen eines `CMFCTasksPane`\-Objekts, und die Verwendung verschiedener Methoden in der `CMFCTasksPane`\-Klasse.  Im Beispiel wird veranschaulicht, wie das Reduzieren von Aufgabengruppen aktiviert werden kann, wie Dropdown\-Menüs bei den Navigationsschaltflächen **Weiter** und **urück** aktiviert werden können, wie Bildlaufschaltflächen statt einer Bildlaufleiste aktiviert werden, wie der Wortumbruch für Texte in Beschriftungen aktiviert wird, wie der Beschriftungsname des Aufgabenbereichs festgelegt werden kann, wie die Textfarbe für eine Gruppenbeschriftung festgelegt wird und wie horizontale und vertikale Ränder festgelegt werden.  
  
 [!CODE [NVC_MFC_RibbonApp#28](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#28)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)  
  
## Anforderungen  
 **Header:** afxTasksPane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)