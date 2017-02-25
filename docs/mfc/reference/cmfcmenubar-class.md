---
title: "CMFCMenuBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMenuBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuBar class"
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCMenuBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Menüleiste, die Andocken implementiert.  
  
## Syntax  
  
```  
class CMFCMenuBar : public CMFCToolbar  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCMenuBar::AdjustLocations](../Topic/CMFCMenuBar::AdjustLocations.md)|\(Überschreibungen `CMFCToolBar::AdjustLocations`.\)|  
|[CMFCMenuBar::AllowChangeTextLabels](../Topic/CMFCMenuBar::AllowChangeTextLabels.md)|Gibt an, ob Beschriftungen unter Bilder auf den Symbolleisten\-Schaltflächen angezeigt werden können.  \(Überschreibungen [CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md).\)|  
|[CMFCMenuBar::AllowShowOnPaneMenu](../Topic/CMFCMenuBar::AllowShowOnPaneMenu.md)|\(Überschreibungen `CPane::AllowShowOnPaneMenu`.\)|  
|[CMFCMenuBar::CalcFixedLayout](../Topic/CMFCMenuBar::CalcFixedLayout.md)|Berechnet die horizontale Größe der Symbolleiste.  \(Überschreibungen [CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md).\)|  
|[CMFCMenuBar::CalcLayout](../Topic/CMFCMenuBar::CalcLayout.md)|\(Überschreibungen `CMFCToolBar::CalcLayout`.\)|  
|[CMFCMenuBar::CalcMaxButtonHeight](../Topic/CMFCMenuBar::CalcMaxButtonHeight.md)|Berechnet die maximale Höhe Schaltflächen in der Symbolleiste auf.  \(Überschreibungen [CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md).\)|  
|[CMFCMenuBar::CanBeClosed](../Topic/CMFCMenuBar::CanBeClosed.md)|Gibt an, ob ein Benutzer die Symbolleiste schließen kann.  \(Überschreibungen [CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md).\)|  
|[CMFCMenuBar::CanBeRestored](../Topic/CMFCMenuBar::CanBeRestored.md)|Bestimmt, ob das System eine Symbolleiste in ihren ursprünglichen Zustand nach Anpassung wiederherstellen kann.  \(Überschreibungen [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md).\)|  
|[CMFCMenuBar::Create](../Topic/CMFCMenuBar::Create.md)|Erstellt ein Menüsteuerelement und fügt es zu einem `CMFCMenuBar`\-Objekt.|  
|[CMFCMenuBar::CreateEx](../Topic/CMFCMenuBar::CreateEx.md)|Erstellt ein Objekt `CMFCMenuBar` mit zusätzlichen Formatoptionen.|  
|[CMFCMenuBar::CreateFromMenu](../Topic/CMFCMenuBar::CreateFromMenu.md)|Initialisiert ein `CMFCMenuBar`\-Objekt.  Akzeptiert einen `HMENU`\-Parameter, der als eine Vorlage für gefülltes `CMFCMenuBar` auftritt.|  
|[CMFCMenuBar::EnableHelpCombobox](../Topic/CMFCMenuBar::EnableHelpCombobox.md)|Ermöglicht einem **Hilfe** Kombinationsfeld, das auf der rechten Seite der Menüleiste auf.|  
|[CMFCMenuBar::EnableMenuShadows](../Topic/CMFCMenuBar::EnableMenuShadows.md)|Gibt an, ob Schatten für Popupmenüs anzeigt.|  
|[CMFCMenuBar::GetAvailableExpandSize](../Topic/CMFCMenuBar::GetAvailableExpandSize.md)|\(Überschreibungen [CPane::GetAvailableExpandSize](../Topic/CPane::GetAvailableExpandSize.md).\)|  
|[CMFCMenuBar::GetColumnWidth](../Topic/CMFCMenuBar::GetColumnWidth.md)|Gibt die Breite der Symbolleisten\-Schaltflächen zurück.  \(Überschreibungen [CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md).\)|  
|[CMFCMenuBar::GetDefaultMenu](../Topic/CMFCMenuBar::GetDefaultMenu.md)|Gibt ein Handle für den ursprünglichen Menü in der Ressourcendatei zurück.|  
|[CMFCMenuBar::GetDefaultMenuResId](../Topic/CMFCMenuBar::GetDefaultMenuResId.md)|Gibt den Ressourcenbezeichner für das ursprüngliche Menü in der Ressourcendatei zurück.|  
|[CMFCMenuBar::GetFloatPopupDirection](../Topic/CMFCMenuBar::GetFloatPopupDirection.md)||  
|[CMFCMenuBar::GetForceDownArrows](../Topic/CMFCMenuBar::GetForceDownArrows.md)||  
|[CMFCMenuBar::GetHelpCombobox](../Topic/CMFCMenuBar::GetHelpCombobox.md)|Gibt einen Zeiger auf **Hilfe** Kombinationsfeld zurück.|  
|[CMFCMenuBar::GetHMenu](../Topic/CMFCMenuBar::GetHMenu.md)|Gibt das Handle für das Menü zurück, das dem Objekt `CMFCMenuBar` angefügt wird.|  
|[CMFCMenuBar::GetMenuFont](../Topic/CMFCMenuBar::GetMenuFont.md)|Gibt die aktuelle globale Schriftart für Menüobjekte zurück.|  
|[CMFCMenuBar::GetMenuItem](../Topic/CMFCMenuBar::GetMenuItem.md)|Gibt die Symbolleistenschaltfläche zurück, die mit dem angegebenen Elementindex zugeordnet ist.|  
|[CMFCMenuBar::GetRowHeight](../Topic/CMFCMenuBar::GetRowHeight.md)|Gibt die Höhe Symbolleisten\-Schaltflächen zurück.  \(Überschreibungen [CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md).\)|  
|[CMFCMenuBar::GetSystemButton](../Topic/CMFCMenuBar::GetSystemButton.md)||  
|[CMFCMenuBar::GetSystemButtonsCount](../Topic/CMFCMenuBar::GetSystemButtonsCount.md)||  
|[CMFCMenuBar::GetSystemMenu](../Topic/CMFCMenuBar::GetSystemMenu.md)||  
|[CMFCMenuBar::HighlightDisabledItems](../Topic/CMFCMenuBar::HighlightDisabledItems.md)|Gibt an, ob deaktivierte Menüelemente hervorgehoben werden.|  
|[CMFCMenuBar::IsButtonExtraSizeAvailable](../Topic/CMFCMenuBar::IsButtonExtraSizeAvailable.md)|Bestimmt, ob die Symbolleiste Schaltflächen anzeigen kann, Rahmen erweitert haben.  \(Überschreibungen [CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md).\)|  
|[CMFCMenuBar::IsHighlightDisabledItems](../Topic/CMFCMenuBar::IsHighlightDisabledItems.md)|Gibt an, ob deaktivierte Elemente hervorgehoben werden.|  
|[CMFCMenuBar::IsMenuShadows](../Topic/CMFCMenuBar::IsMenuShadows.md)|Gibt an, ob Schatten für Popupmenüs gezeichnet werden.|  
|[CMFCMenuBar::IsRecentlyUsedMenus](../Topic/CMFCMenuBar::IsRecentlyUsedMenus.md)|Gibt an, ob zuletzt verwendeten Menübefehle auf der Menüleiste angezeigt werden.|  
|[CMFCMenuBar::IsShowAllCommands](../Topic/CMFCMenuBar::IsShowAllCommands.md)|Gibt an, ob Popupmenüs alle Befehle anzeigen.|  
|[CMFCMenuBar::IsShowAllCommandsDelay](../Topic/CMFCMenuBar::IsShowAllCommandsDelay.md)|Gibt an, ob Menüs alle Befehle nach einer kurzen Verzögerung anzeigen.|  
|[CMFCMenuBar::LoadState](../Topic/CMFCMenuBar::LoadState.md)|Lädt den Zustand des `CMFCMenuBar`\-Objekts aus der Registrierung.|  
|[CMFCMenuBar::OnChangeHot](../Topic/CMFCMenuBar::OnChangeHot.md)|Aufgerufen vom Framework, wenn ein Benutzer eine Schaltfläche auf der Symbolleiste auswählt.  \(Überschreibungen [CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md).\)|  
|[CMFCMenuBar::OnDefaultMenuLoaded](../Topic/CMFCMenuBar::OnDefaultMenuLoaded.md)|Aufgerufen vom Framework ausgelöst, wenn ein Rahmenfenster das standardmäßige Menü aus der Ressourcendatei lädt.|  
|[CMFCMenuBar::OnSendCommand](../Topic/CMFCMenuBar::OnSendCommand.md)|\(Überschreibungen `CMFCToolBar::OnSendCommand`.\)|  
|[CMFCMenuBar::OnSetDefaultButtonText](../Topic/CMFCMenuBar::OnSetDefaultButtonText.md)|Aufgerufen vom Framework ausgelöst, wenn ein Menü im Anpassungsmodus und im Benutzer ist, ändert den Text eines Menüelements.|  
|[CMFCMenuBar::OnToolHitTest](../Topic/CMFCMenuBar::OnToolHitTest.md)|\(Überschreibungen `CMFCToolBar::OnToolHitTest`.\)|  
|[CMFCMenuBar::PreTranslateMessage](../Topic/CMFCMenuBar::PreTranslateMessage.md)|\(Überschreibungen `CMFCToolBar::PreTranslateMessage`.\)|  
|[CMFCMenuBar::RestoreOriginalstate](../Topic/CMFCMenuBar::RestoreOriginalstate.md)|Aufgerufen vom Framework ausgelöst, wenn ein Menü im Anpassungsmodus und im Benutzer ist, wählt **Zurücksetzen** für eine Menüleiste aus.|  
|[CMFCMenuBar::SaveState](../Topic/CMFCMenuBar::SaveState.md)|Rettet den Zustand des Objekts `CMFCMenuBar` zur Registrierung.|  
|[CMFCMenuBar::SetDefaultMenuResId](../Topic/CMFCMenuBar::SetDefaultMenuResId.md)|Legt das ursprüngliche Menü in der Ressourcendatei fest.|  
|[CMFCMenuBar::SetForceDownArrows](../Topic/CMFCMenuBar::SetForceDownArrows.md)||  
|[CMFCMenuBar::SetMaximizeMode](../Topic/CMFCMenuBar::SetMaximizeMode.md)|Aufgerufen vom Framework, wenn ein untergeordnetes MDI\-Fenster den Anzeigemodus ändert.  Wenn das untergeordnete MDI\-Fenster neu maximiert wird oder nicht mehr maximiert wird, aktualisiert diese Methode die Menüleiste.|  
|[CMFCMenuBar::SetMenuButtonRTC](../Topic/CMFCMenuBar::SetMenuButtonRTC.md)|Legt die Ablaufklasseninformationen fest, die generiert wird, wenn der Benutzer dynamisch Menüschaltflächen erstellt wird.|  
|[CMFCMenuBar::SetMenuFont](../Topic/CMFCMenuBar::SetMenuFont.md)|Legt die Schriftart für alle Menüs in der Anwendung fest.|  
|[CMFCMenuBar::SetRecentlyUsedMenus](../Topic/CMFCMenuBar::SetRecentlyUsedMenus.md)|Gibt an, ob eine Menüleiste zuletzt verwendeten Menübefehle anzeigt.|  
|[CMFCMenuBar::SetShowAllCommands](../Topic/CMFCMenuBar::SetShowAllCommands.md)|Gibt an, ob die Menüleiste alle Befehle anzeigt.|  
  
## Hinweise  
 Die Klasse `CMFCMenuBar` ist eine andockbare Menüleiste, die Funktionalität implementiert.  Sie ähnelt einer Symbolleiste, obwohl sie nicht geschlossen werden kann \- sie wird immer angezeigt.  
  
 `CMFCMenuBar` unterstützt die Option zum Anzeigen der zuletzt verwendeten Menüelementobjekten.  Wenn diese Option aktiviert ist, wird `CMFCMenuBar` nur eine Teilmenge der verfügbaren Befehle bei der ersten Anzeige an.  Danach werden zuletzt verwendeten Befehle zusammen mit der ursprünglichen Teilmenge von Befehlen angezeigt.  Außerdem kann der Benutzer das Menü immer erweitern, um alle verfügbaren Befehle anzuzeigen.  Somit wird jeder verfügbaren Befehl, um fortlaufend anzuzeigen oder anzuzeigen konfiguriert nur, wenn er zuletzt ausgewählt wurde.  
  
 Um ein `CMFCMenuBar`\-Objekt zu verwenden, müssen Sie es im Hauptfensterframeobjekt ein.  Wenn Sie die `WM_CREATE` Meldung verarbeiten, rufen Sie `CMFCMenuBar::Create` oder `CMFCMenuBar::CreateEx` auf.  Unabhängig davon, welche Erstellungsfunktion Sie verwenden, übergeben Sie einen Zeiger auf das Hauptrahmenfenster.  Aktivieren Sie dann Andocken, indem Sie [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md) aufrufen.  Docken Sie dieses Menü an, indem Sie [CFrameWndEx::DockPane](../Topic/CFrameWndEx::DockPane.md) aufrufen.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCMenuBar` verwendet.  Im Beispiel wird gezeigt, wie das Format des Bereichs, ermöglichen die Anpassensschaltfläche aktivieren, ein Hilfefeld aktivieren, Schatten für Popupmenüs und aktualisieren die Menüleiste festgelegt wird.  Dieser Codeausschnitt ist Teil [IE\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_IEDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_IEDemo#1)]  
[!CODE [NVC_MFC_IEDemo#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_IEDemo#3)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md)  
  
## Anforderungen  
 **Header:** afxmenubar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)