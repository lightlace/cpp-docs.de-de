---
title: "CMFCToolBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBar class"
ms.assetid: e7679c01-fb94-44c0-98c6-3af955292fb5
caps.latest.revision: 48
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 50
---
# CMFCToolBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klasse ähnelt `CMFCToolBar`[CToolBar Class](../../mfc/reference/ctoolbar-class.md), aber bietet zusätzliche Unterstützung für Benutzeroberflächenfunktionen.  Diese schließen flache Symbolleisten, Symbolleisten mit heißen Bilder, große Symbole, Pagerschaltflächen gesperrte, Symbolleisten, Infoleistensteuerelemente, Text mit Bildern, Hintergrundbilder und Symbolleisten im Registerkartenformat.  Die `CMFCToolBar`\-Klasse enthält auch integrierte Unterstützung für Benutzeranpassung Symbolleisten und Menüs, Drag & Drop zwischen Symbolleisten und Menüs, Kombinationsfeldschaltflächen, Eingabefeldschaltflächen, Farben\-Auswahlen und Rolle\-oben Schaltflächen.  
  
## Syntax  
  
```  
class CMFCToolBar : public CMFCBaseToolBar  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCToolBar::CMFCToolBar`|Standardkonstruktor.|  
|`CMFCToolBar::~CMFCToolBar`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBar::AddBasicCommand](../Topic/CMFCToolBar::AddBasicCommand.md)|Fügt einen Menübefehl der Liste von Befehlen hinzu, die immer angezeigt werden, wenn ein Benutzer ein Menü öffnen.|  
|[CMFCToolBar::AddCommandUsage](../Topic/CMFCToolBar::AddCommandUsage.md)|Inkremente durch eines der Indikator, der mit dem angegebenen Befehl zugeordnet ist.|  
|[CMFCToolBar::AddToolBarForImageCollection](../Topic/CMFCToolBar::AddToolBarForImageCollection.md)|Fügt Bilder von den Benutzeroberflächenressourcen der Auflistung von Bildern in der Anwendung hinzu.|  
|[CMFCToolBar::AdjustLayout](../Topic/CMFCToolBar::AdjustLayout.md)|Berechnet die Größe und die Position einer Symbolleiste neu.  \(Überschreibt [CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md)\).|  
|[CMFCToolBar::AdjustSize](../Topic/CMFCToolBar::AdjustSize.md)|Berechnet die Größe der Symbolleiste neu.|  
|[CMFCToolBar::AllowChangeTextLabels](../Topic/CMFCToolBar::AllowChangeTextLabels.md)|Gibt an, ob Beschriftungen unter Bilder auf den Symbolleisten\-Schaltflächen angezeigt werden können.|  
|[CMFCToolBar::AreTextLabels](../Topic/CMFCToolBar::AreTextLabels.md)|Gibt an, ob Beschriftungen unter Bilder nur auf den Symbolleisten\-Schaltflächen angezeigt werden.|  
|[CMFCToolBar::AutoGrayInactiveImages](../Topic/CMFCToolBar::AutoGrayInactiveImages.md)|Aktiviert oder deaktiviert die automatische Generierung von inaktiven Schaltflächenbilder.|  
|[CMFCToolBar::ButtonToIndex](../Topic/CMFCToolBar::ButtonToIndex.md)|Gibt den Index eines angegebenen Objekts [CMFCToolBarButton Class](../../mfc/reference/cmfctoolbarbutton-class.md) in dieser Symbolleiste zurück.|  
|[CMFCToolBar::CalcFixedLayout](../Topic/CMFCToolBar::CalcFixedLayout.md)|Berechnet die horizontale Größe der Symbolleiste.  \(Überschreibungen [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCToolBar::CalcSize](../Topic/CMFCToolBar::CalcSize.md)|Aufgerufen vom Framework als Teil des Layoutrechenvorgangs.  \(Überschreibungen [CPane::CalcSize](../Topic/CPane::CalcSize.md).\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|Bestimmt, ob die Symbolleiste und sein gleichgeordnetes Element auf demselben Bereich positioniert werden.|  
|[CMFCToolBar::CleanUpImages](../Topic/CMFCToolBar::CleanUpImages.md)|Gibt die Systemressourcen frei, die für Symbolleistenimages zugeordnet werden.|  
|[CMFCToolBar::CleanUpLockedImages](../Topic/CMFCToolBar::CleanUpLockedImages.md)|Gibt die Systemressourcen frei, die für gesperrte Symbolleistenimages zugeordnet werden.|  
|[CMFCToolBar::CanBeClosed](../Topic/CMFCToolBar::CanBeClosed.md)|Gibt an, ob ein Benutzer die Symbolleiste schließen kann.  \(Überschreibungen [CBasePane::CanBeClosed](../Topic/CBasePane::CanBeClosed.md).\)|  
|[CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md)|Bestimmt, ob das System eine Symbolleiste in ihren ursprünglichen Zustand nach Anpassung wiederherstellen kann.|  
|[CMFCToolBar::CanFocus](../Topic/CMFCToolBar::CanFocus.md)|Gibt an, ob der Bereich den Fokus erhalten kann.  \(Überschreibungen [CBasePane::CanFocus](../Topic/CBasePane::CanFocus.md).\)|  
|[CMFCToolBar::CanHandleSiblings](../Topic/CMFCToolBar::CanHandleSiblings.md)|Bestimmt, ob die Symbolleiste und sein gleichgeordnetes Element auf demselben Bereich positioniert werden.|  
|[CMFCToolBar::CommandToIndex](../Topic/CMFCToolBar::CommandToIndex.md)|Gibt den Index der Schaltfläche in der Symbolleiste mit einer angegebenen Befehl ID zurück|  
|[CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md)|Erstellt ein `CMFCToolBar`\-Objekt.|  
|[CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md)|Erstellt ein `CMFCToolBar`\-Objekt, das zusätzliche Formatoptionen verwendet, wie große Symbole.|  
|[CMFCToolBar::Deactivate](../Topic/CMFCToolBar::Deactivate.md)|Deaktiviert die Symbolleiste.|  
|[CMFCToolBar::EnableCustomizeButton](../Topic/CMFCToolBar::EnableCustomizeButton.md)|Aktiviert oder deaktiviert die Schaltfläche **Schaltflächen hinzufügen oder entfernen** , die am Ende der Symbolleiste angezeigt wird.|  
|[CMFCToolBar::EnableDocking](../Topic/CMFCToolBar::EnableDocking.md)|Aktiviert Andocken des Bereichs zum Großrechner.  \(Überschreibungen [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md).\)|  
|[CMFCToolBar::EnableLargeIcons](../Topic/CMFCToolBar::EnableLargeIcons.md)|Aktiviert oder deaktiviert große Symbole auf Symbolleisten\-Schaltflächen.|  
|[CMFCToolBar::EnableQuickCustomization](../Topic/CMFCToolBar::EnableQuickCustomization.md)|Aktiviert oder deaktiviert die schnelle Anpassung von Symbolleisten, damit der Benutzer die **ALT** Taste drücken und eine Schaltfläche auf eine neue Position ziehen kann.|  
|[CMFCToolBar::EnableReflections](../Topic/CMFCToolBar::EnableReflections.md)|Aktiviert oder Sperrungsbefehlsreflektion.|  
|[CMFCToolBar::EnableTextLabels](../Topic/CMFCToolBar::EnableTextLabels.md)|Aktiviert oder deaktiviert Beschriftungen unter Symbolleistenschaltflächenimages.|  
|[CMFCToolBar::FromHandlePermanent](../Topic/CMFCToolBar::FromHandlePermanent.md)|Ruft einen Zeiger auf das `CMFCToolBar`\-Objekt ab, das das angegebene Fensterhandle enthält.|  
|[CMFCToolBar::GetAllButtons](../Topic/CMFCToolBar::GetAllButtons.md)|Gibt eine schreibgeschützte Liste von Schaltflächen in einer Symbolleiste zurück.|  
|[CMFCToolBar::GetAllToolbars](../Topic/CMFCToolBar::GetAllToolbars.md)|Gibt eine schreibgeschützte Liste aller Symbolleisten in der Anwendung zurück.|  
|[CMFCToolBar::GetBasicCommands](../Topic/CMFCToolBar::GetBasicCommands.md)|Gibt eine schreibgeschützte Liste der grundlegenden Befehle zurück, die in der Anwendung definiert sind.|  
|[CMFCToolBar::GetButton](../Topic/CMFCToolBar::GetButton.md)|Gibt einen Zeiger auf `CMFCToolBarButton`\-Objekt zurück, das einen angegebenen Symbolleistenschaltflächenindex verfügt.|  
|[CMFCToolBar::GetButtonInfo](../Topic/CMFCToolBar::GetButtonInfo.md)|Gibt die Befehls\-ID, das Format und den Bildindex der Schaltfläche an einem angegebenen Index zurück.|  
|[CMFCToolBar::GetButtonSize](../Topic/CMFCToolBar::GetButtonSize.md)|Gibt die Dimensionen jeder Schaltfläche auf der Symbolleiste zurück.|  
|[CMFCToolBar::GetButtonStyle](../Topic/CMFCToolBar::GetButtonStyle.md)|Gibt das aktuelle Format der Symbolleisten\-Schaltfläche zurück, die am angegebenen Index befinden.|  
|[CMFCToolBar::GetButtonText](../Topic/CMFCToolBar::GetButtonText.md)|Gibt die Beschriftung einer Schaltfläche zurück, die einen angegebenen Index verfügt.|  
|[CMFCToolBar::GetColdImages](../Topic/CMFCToolBar::GetColdImages.md)|Gibt einen Zeiger auf die Auflistung von kalten Symbolleistenschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetColumnWidth](../Topic/CMFCToolBar::GetColumnWidth.md)|Gibt die Breite der Symbolleisten\-Schaltflächen zurück.|  
|[CMFCToolBar::GetCommandButtons](../Topic/CMFCToolBar::GetCommandButtons.md)|Gibt eine Liste von Schaltflächen zurück, die eine angegebene Befehls\-ID aus allen Symbolleisten in der Anwendung verfügen.|  
|[CMFCToolBar::GetCount](../Topic/CMFCToolBar::GetCount.md)|Gibt die Anzahl von Schaltflächen und Trennzeichen auf der Symbolleiste zurück.|  
|[CMFCToolBar::GetCustomizeButton](../Topic/CMFCToolBar::GetCustomizeButton.md)|Ruft einen Zeiger auf das `CMFCCustomizeButton`\-Objekt ab, das der Symbolleiste zugeordnet ist.|  
|[CMFCToolBar::GetDefaultImage](../Topic/CMFCToolBar::GetDefaultImage.md)|Gibt den Index des Standardbildern für eine Symbolleisten\-Schaltfläche mit einer angegebenen Befehl ID zurück|  
|[CMFCToolBar::GetDisabledImages](../Topic/CMFCToolBar::GetDisabledImages.md)|Gibt einen Zeiger auf die Auflistung von Bildern zurück, die für deaktivierte Schaltflächen in der Anwendung verwendet werden.|  
|[CMFCToolBar::GetDisabledMenuImages](../Topic/CMFCToolBar::GetDisabledMenuImages.md)|Gibt einen Zeiger auf die Auflistung von Bildern zurück, die für deaktivierte Menüschaltflächen in der Anwendung verwendet werden.|  
|[CMFCToolBar::GetDroppedDownMenu](../Topic/CMFCToolBar::GetDroppedDownMenu.md)|Ruft einen Zeiger auf das Menüschaltflächenobjekt ab, das gerade sein Untermenü anzeigt.|  
|[CMFCToolBar::GetGrayDisabledButtons](../Topic/CMFCToolBar::GetGrayDisabledButtons.md)|Gibt an, ob die Bilder von deaktivierten Schaltflächen abgeblendete Versionen der regulären Schaltflächenbilder kann sind, oder die der Auflistung von deaktivierten Schaltflächenbilder.|  
|[CMFCToolBar::GetHighlightedButton](../Topic/CMFCToolBar::GetHighlightedButton.md)|Gibt einen Zeiger auf die Symbolleistenschaltfläche zurück, die derzeit ausgewählt ist.|  
|[CMFCToolBar::GetHotBorder](../Topic/CMFCToolBar::GetHotBorder.md)|Bestimmt, ob die Symbolleisten\-Schaltflächen vorselektiert sind.|  
|[CMFCToolBar::GetHotTextColor](../Topic/CMFCToolBar::GetHotTextColor.md)|Gibt die Textfarbe der markierten Symbolleisten\-Schaltflächen zurück.|  
|[CMFCToolBar::GetHwndLastFocus](../Topic/CMFCToolBar::GetHwndLastFocus.md)|Gibt ein Handle für das Fenster zurück, das den Eingabefokus hatte, kurz bevor die Symbolleiste geändert.|  
|[CMFCToolBar::GetIgnoreSetText](../Topic/CMFCToolBar::GetIgnoreSetText.md)|Gibt an, ob Aufrufe der festgelegten Schaltflächenbezeichnungen ignoriert werden.|  
|[CMFCToolBar::GetImageSize](../Topic/CMFCToolBar::GetImageSize.md)|Gibt die aktuelle Größe von Symbolleistenschaltflächenimages zurück.|  
|[CMFCToolBar::GetImages](../Topic/CMFCToolBar::GetImages.md)|Gibt einen Zeiger auf die Auflistung von Standardschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetImagesOffset](../Topic/CMFCToolBar::GetImagesOffset.md)|Gibt den Index ausgeglichen verwendet, um die Symbolleistenschaltflächenimages für diese Symbolleiste in der globalen Liste von Symbolleistenschaltflächenimages zu suchen zurück.|  
|[CMFCToolBar::GetInvalidateItemRect](../Topic/CMFCToolBar::GetInvalidateItemRect.md)|Ruft den des Innenbereichs ab, der für die Schaltfläche am angegebenen Index neu gezeichnet werden muss.|  
|[CMFCToolBar::GetItemID](../Topic/CMFCToolBar::GetItemID.md)|Gibt die Befehls\-ID der Symbolleisten\-Schaltfläche an einem angegebenen Index zurück.|  
|[CMFCToolBar::GetItemRect](../Topic/CMFCToolBar::GetItemRect.md)|Gibt das umschließende Rechteck der Schaltfläche an einem angegebenen Index zurück.|  
|[CMFCToolBar::GetLargeColdImages](../Topic/CMFCToolBar::GetLargeColdImages.md)|Gibt einen Zeiger auf die Auflistung von großen kalten Symbolleistenschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetLargeDisabledImages](../Topic/CMFCToolBar::GetLargeDisabledImages.md)|Gibt einen Zeiger auf die Auflistung von großen deaktivierten Symbolleistenschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetLargeImages](../Topic/CMFCToolBar::GetLargeImages.md)|Gibt einen Zeiger auf die Auflistung von großen Symbolleistenschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetLockedColdImages](../Topic/CMFCToolBar::GetLockedColdImages.md)|Gibt einen Zeiger auf die Auflistung von gesperrten kalten Bilder in der Symbolleiste zurück.|  
|[CMFCToolBar::GetLockedDisabledImages](../Topic/CMFCToolBar::GetLockedDisabledImages.md)|Gibt einen Zeiger auf die Auflistung von gesperrten deaktivierten Bilder in der Symbolleiste zurück.|  
|[CMFCToolBar::GetLockedImages](../Topic/CMFCToolBar::GetLockedImages.md)|Gibt einen Zeiger auf die Auflistung von gesperrten Schaltflächenbilder in der Symbolleiste zurück.|  
|[CMFCToolBar::GetLockedImageSize](../Topic/CMFCToolBar::GetLockedImageSize.md)|Gibt die Standardgröße von gesperrten Symbolleistenimages zurück.|  
|[CMFCToolBar::GetLockedMenuImages](../Topic/CMFCToolBar::GetLockedMenuImages.md)|Gibt einen Zeiger auf die Auflistung von gesperrten Symbolleistenmenüimages in der Symbolleiste zurück.|  
|[CMFCToolBar::GetMenuButtonSize](../Topic/CMFCToolBar::GetMenuButtonSize.md)|Gibt die Größe von Menüschaltflächen in der Anwendung zurück.|  
|[CMFCToolBar::GetMenuImageSize](../Topic/CMFCToolBar::GetMenuImageSize.md)|Gibt die Größe von Menüschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetMenuImages](../Topic/CMFCToolBar::GetMenuImages.md)|Gibt einen Zeiger auf die Auflistung von Menüschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::GetOrigButtons](../Topic/CMFCToolBar::GetOrigButtons.md)|Ruft die Auflistung von nicht\-angepassten Schaltflächen der Symbolleiste ab.|  
|[CMFCToolBar::GetOrigResetButtons](../Topic/CMFCToolBar::GetOrigResetButtons.md)|Ruft die Auflistung von nicht\-angepassten Rücksetzschaltflächen der Symbolleiste ab.|  
|[CMFCToolBar::GetResourceID](../Topic/CMFCToolBar::GetResourceID.md)|Ruft das Ressourcen\-ID der Symbolleiste ab.|  
|[CMFCToolBar::GetRouteCommandsViaFrame](../Topic/CMFCToolBar::GetRouteCommandsViaFrame.md)|Bestimmt das Objekt, die übergeordneten Frames oder der Besitzer, Befehle zur Symbolleiste sendet.|  
|[CMFCToolBar::GetRowHeight](../Topic/CMFCToolBar::GetRowHeight.md)|Gibt die Höhe Symbolleisten\-Schaltflächen zurück.|  
|[CMFCToolBar::GetShowTooltips](../Topic/CMFCToolBar::GetShowTooltips.md)|Gibt an, ob QuickInfos für Symbolleisten\-Schaltflächen angezeigt werden.|  
|[CMFCToolBar::GetSiblingToolBar](../Topic/CMFCToolBar::GetSiblingToolBar.md)|Ruft das gleichgeordnete Element der Symbolleiste ab.|  
|[CMFCToolBar::GetUserImages](../Topic/CMFCToolBar::GetUserImages.md)|Gibt einen Zeiger auf die Auflistung von benutzerdefinierten Symbolleistenschaltflächenimages in der Anwendung zurück.|  
|[CMFCToolBar::HitTest](../Topic/CMFCToolBar::HitTest.md)|Gibt den Index der Symbolleisten\-Schaltfläche zurück, die in der angegebenen Position befinden.|  
|[CMFCToolBar::InsertButton](../Topic/CMFCToolBar::InsertButton.md)|Fügt eine Schaltfläche in die Symbolleiste ein.|  
|[CMFCToolBar::InsertSeparator](../Topic/CMFCToolBar::InsertSeparator.md)|Fügt ein Trennzeichen in die Symbolleiste ein.|  
|[CMFCToolBar::InvalidateButton](../Topic/CMFCToolBar::InvalidateButton.md)|Löscht den Clientbereich der Symbolleisten\-Schaltfläche ungültig die am angegebenen Index vorhanden ist.|  
|[CMFCToolBar::IsAddRemoveQuickCustomize](../Topic/CMFCToolBar::IsAddRemoveQuickCustomize.md)|Bestimmt, ob ein Benutzer Symbolleisten\-Schaltflächen hinzufügen oder entfernen kann, indem er die **Anpassen** Menüoption verwendet.|  
|[CMFCToolBar::IsAltCustomizeMode](../Topic/CMFCToolBar::IsAltCustomizeMode.md)|Gibt an, ob *schnelle Anpassung* verwendet wird, um eine Schaltfläche zu ziehen.|  
|[CMFCToolBar::IsAutoGrayInactiveImages](../Topic/CMFCToolBar::IsAutoGrayInactiveImages.md)|Gibt an, ob die automatische Generierung von inaktiven \(nicht hervorgehobenen\) Schaltflächenbilder aktiviert ist.|  
|[CMFCToolBar::IsBasicCommand](../Topic/CMFCToolBar::IsBasicCommand.md)|Bestimmt, ob ein Befehl auf der Liste grundlegender Befehlen ist.|  
|[CMFCToolBar::IsButtonExtraSizeAvailable](../Topic/CMFCToolBar::IsButtonExtraSizeAvailable.md)|Bestimmt, ob die Symbolleiste Schaltflächen anzeigen kann, Rahmen erweitert haben.|  
|[CMFCToolBar::IsButtonHighlighted](../Topic/CMFCToolBar::IsButtonHighlighted.md)|Bestimmt, ob eine Schaltfläche auf der Symbolleiste hervorgehoben wird.|  
|[CMFCToolBar::IsCommandPermitted](../Topic/CMFCToolBar::IsCommandPermitted.md)|Bestimmt, ob ein Befehl nicht zulässig ist.|  
|[CMFCToolBar::IsCommandRarelyUsed](../Topic/CMFCToolBar::IsCommandRarelyUsed.md)|Bestimmt, ob ein Befehl selten verwendet wird \(siehe [CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)\).|  
|[CMFCToolBar::IsCustomizeMode](../Topic/CMFCToolBar::IsCustomizeMode.md)|Gibt an, ob das Symbolleistenframework im Anpassungsmodus ist.|  
|[CMFCToolBar::IsDragButton](../Topic/CMFCToolBar::IsDragButton.md)|Bestimmt, ob eine Symbolleisten\-Schaltfläche gezogen wird.|  
|[CMFCToolBar::IsExistCustomizeButton](../Topic/CMFCToolBar::IsExistCustomizeButton.md)|Bestimmt, ob die Symbolleiste die Schaltfläche **Anpassen** enthält.|  
|[CMFCToolBar::IsFloating](../Topic/CMFCToolBar::IsFloating.md)|Bestimmt, ob die Symbolleiste unverankert ist.|  
|[CMFCToolBar::IsLargeIcons](../Topic/CMFCToolBar::IsLargeIcons.md)|Gibt an, ob Symbolleisten in der Anwendung derzeit große Symbole anzeigen.|  
|[CMFCToolBar::IsLastCommandFromButton](../Topic/CMFCToolBar::IsLastCommandFromButton.md)|Bestimmt, ob der zuletzt ausgeführte Befehl aus der angegebenen Symbolleisten\-Schaltfläche gesendet wurde.|  
|[CMFCToolBar::IsLocked](../Topic/CMFCToolBar::IsLocked.md)|Bestimmt, ob die Symbolleiste gesperrt ist.|  
|[CMFCToolBar::IsOneRowWithSibling](../Topic/CMFCToolBar::IsOneRowWithSibling.md)|Bestimmt, ob die Symbolleiste und die gleichgeordnete Symbolleiste auf derselben Zeile positioniert werden.|  
|[CMFCToolBar::IsUserDefined](../Topic/CMFCToolBar::IsUserDefined.md)|Gibt an, ob die Symbolleiste benutzerdefiniert ist.|  
|[CMFCToolBar::LoadBitmap](../Topic/CMFCToolBar::LoadBitmap.md)|Lädt Symbolleistenimages aus Anwendungsressourcen.|  
|[CMFCToolBar::LoadBitmapEx](../Topic/CMFCToolBar::LoadBitmapEx.md)|Lädt Symbolleistenimages aus Anwendungsressourcen.  Schließt große Bildern.|  
|[CMFCToolBar::LoadParameters](../Topic/CMFCToolBar::LoadParameters.md)|Lädt globale Symbolleistenoptionen aus der Windows\-Registrierung.|  
|[CMFCToolBar::LoadState](../Topic/CMFCToolBar::LoadState.md)|Lädt die Symbolleistenzustandsinformationen aus der Windows\-Registrierung.  \(Überschreibungen [CPane::LoadState](../Topic/CPane::LoadState.md).\)|  
|[CMFCToolBar::LoadToolBar](../Topic/CMFCToolBar::LoadToolBar.md)|Lädt die Symbolleiste aus Anwendungsressourcen.|  
|[CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)|Lädt die Symbolleiste aus Anwendungsressourcen mithilfe der `CMFCToolBarInfo` Hilfsklasse, um die Anwendung zu aktivieren, große Bilder zu verwenden.|  
|[CMFCToolBar::OnChangeHot](../Topic/CMFCToolBar::OnChangeHot.md)|Aufgerufen vom Framework, wenn ein Benutzer eine Schaltfläche auf der Symbolleiste auswählt.|  
|[CMFCToolBar::OnFillBackground](../Topic/CMFCToolBar::OnFillBackground.md)|Aufgerufen vom Framework von [CBasePane::DoPaint](../Topic/CBasePane::DoPaint.md), um den Symbolleistenhintergrund auszufüllen.|  
|[CMFCToolBar::OnReset](../Topic/CMFCToolBar::OnReset.md)|Stellt die Symbolleiste in ihren ursprünglichen Zustand zurück.|  
|[CMFCToolBar::OnSetAccData](../Topic/CMFCToolBar::OnSetAccData.md)|\(Überschreibungen [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCToolBar::OnSetDefaultButtonText](../Topic/CMFCToolBar::OnSetDefaultButtonText.md)|Enthält den Text einer Symbolleistenschaltfläche in ihren Standardzustand zurückgesetzt.|  
|`CMFCToolBar::OnUpdateCmdUI`|Wird intern verwendet.|  
|[CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md)|Entfernt alle Schaltflächen der Symbolleiste.|  
|[CMFCToolBar::RemoveButton](../Topic/CMFCToolBar::RemoveButton.md)|Entfernt die Schaltfläche mit dem angegebenen Index aus der Symbolleiste.|  
|[CMFCToolBar::RemoveStateFromRegistry](../Topic/CMFCToolBar::RemoveStateFromRegistry.md)|Löscht die Zustandsinformationen für die Symbolleiste aus der Windows\-Registrierung.|  
|[CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)|Ersetzt eine Symbolleisten\-Schaltfläche durch eine andere Symbolleistenschaltfläche.|  
|[CMFCToolBar::ResetAll](../Topic/CMFCToolBar::ResetAll.md)|Stellt alle Symbolleisten zu den ursprünglichen Status wiederhergestellt.|  
|[CMFCToolBar::ResetAllImages](../Topic/CMFCToolBar::ResetAllImages.md)|Löscht alle Symbolleistenimageauflistungen in der Anwendung.|  
|[CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md)|Stellt den ursprünglichen Zustand einer Symbolleiste wiederher.|  
|[CMFCToolBar::SaveState](../Topic/CMFCToolBar::SaveState.md)|Speichert die Zustandsinformationen für die Symbolleiste in der Windows\-Registrierung.  \(Überschreibungen [CPane::SaveState](../Topic/CPane::SaveState.md).\)|  
|`CMFCToolBar::Serialize`|\(Überschreibungen `CBasePane::Serialize`.\)|  
|[CMFCToolBar::SetBasicCommands](../Topic/CMFCToolBar::SetBasicCommands.md)|Legt die Liste von Befehlen fest, die immer angezeigt werden, wenn ein Benutzer ein Menü öffnen.|  
|[CMFCToolBar::SetButtonInfo](../Topic/CMFCToolBar::SetButtonInfo.md)|Legt die Befehls\-ID, das Format und die Bild ID einer Symbolleisten\-Schaltfläche fest.|  
|[CMFCToolBar::SetButtonStyle](../Topic/CMFCToolBar::SetButtonStyle.md)|Legt das Format der Symbolleisten\-Schaltfläche am angegebenen Index fest.|  
|[CMFCToolBar::SetButtonText](../Topic/CMFCToolBar::SetButtonText.md)|Legt die Beschriftung einer Symbolleisten\-Schaltfläche fest.|  
|[CMFCToolBar::SetButtons](../Topic/CMFCToolBar::SetButtons.md)|Legt die Schaltflächen für die Symbolleiste fest.|  
|[CMFCToolBar::SetCommandUsageOptions](../Topic/CMFCToolBar::SetCommandUsageOptions.md)|Gibt an, ob selten verwendete Befehle nicht im Menü der Anwendung angezeigt werden.|  
|[CMFCToolBar::SetCustomizeMode](../Topic/CMFCToolBar::SetCustomizeMode.md)|Aktiviert oder deaktiviert den Anpassungsmodus für alle Symbolleisten in der Anwendung.|  
|[CMFCToolBar::SetGrayDisabledButtons](../Topic/CMFCToolBar::SetGrayDisabledButtons.md)|Gibt an, ob die deaktivierten Schaltflächen der Symbolleiste abgeblendet angezeigt werden, oder wenn deaktivierte Bilder für die deaktivierten Schaltflächen verwendet werden.|  
|[CMFCToolBar::SetHeight](../Topic/CMFCToolBar::SetHeight.md)|Gibt die Höhe der Symbolleiste fest.|  
|[CMFCToolBar::SetHotBorder](../Topic/CMFCToolBar::SetHotBorder.md)|Gibt an, ob Symbolleisten\-Schaltflächen vorselektiert sind.|  
|[CMFCToolBar::SetHotTextColor](../Topic/CMFCToolBar::SetHotTextColor.md)|Legt die Textfarbe für heiße Symbolleisten\-Schaltflächen fest.|  
|[CMFCToolBar::SetLargeIcons](../Topic/CMFCToolBar::SetLargeIcons.md)|Gibt an, ob Symbolleisten\-Schaltflächen große Symbole anzeigen.|  
|[CMFCToolBar::SetLockedSizes](../Topic/CMFCToolBar::SetLockedSizes.md)|Legt die Größen gesperrten Schaltflächen und die gesperrten Bilder auf der Symbolleiste fest.|  
|[CMFCToolBar::SetMenuSizes](../Topic/CMFCToolBar::SetMenuSizes.md)|Legt die Größe von Symbolleistenmenüschaltflächen und deren Bilds fest.|  
|[CMFCToolBar::SetNonPermittedCommands](../Topic/CMFCToolBar::SetNonPermittedCommands.md)|Legt die Liste von Befehlen fest, die nicht vom Benutzer ausgeführt werden können.|  
|[CMFCToolBar::SetOneRowWithSibling](../Topic/CMFCToolBar::SetOneRowWithSibling.md)|Positioniert die Symbolleiste und sein gleichgeordnetes Element auf derselben Zeile.|  
|[CMFCToolBar::SetPermament](../Topic/CMFCToolBar::SetPermament.md)|Gibt an, ob ein Benutzer die Symbolleiste schließen kann.|  
|[CMFCToolBar::SetRouteCommandsViaFrame](../Topic/CMFCToolBar::SetRouteCommandsViaFrame.md)|Gibt an, ob die übergeordneten Frames oder der Besitzer Befehle zur Symbolleiste sendet.|  
|[CMFCToolBar::SetShowTooltips](../Topic/CMFCToolBar::SetShowTooltips.md)|Gibt an, ob das Framework QuickInfo anzeigt.|  
|[CMFCToolBar::SetSiblingToolBar](../Topic/CMFCToolBar::SetSiblingToolBar.md)|Gibt das gleichgeordnete Element der Symbolleiste an.|  
|[CMFCToolBar::SetSizes](../Topic/CMFCToolBar::SetSizes.md)|Gibt die Größen von Schaltflächen und die Bilder auf allen Symbolleisten an.|  
|[CMFCToolBar::SetToolBarBtnText](../Topic/CMFCToolBar::SetToolBarBtnText.md)|Gibt die Eigenschaften einer Schaltfläche auf der Symbolleiste an.|  
|[CMFCToolBar::SetTwoRowsWithSibling](../Topic/CMFCToolBar::SetTwoRowsWithSibling.md)|Positioniert die Symbolleiste und sein gleichgeordnetes Element auf separaten Zeilen.|  
|[CMFCToolBar::SetUserImages](../Topic/CMFCToolBar::SetUserImages.md)|Legt die Auflistung benutzerdefinierter Bilder in der Anwendung fest.|  
|[CMFCToolBar::StretchPane](../Topic/CMFCToolBar::StretchPane.md)|Streckt die Symbolleiste vertikal oder horizontal. \(Überschreibungen [CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md).\)|  
|[CMFCToolBar::TranslateChar](../Topic/CMFCToolBar::TranslateChar.md)|Führt einen Schaltflächenbefehl aus, wenn der Code des angegebenen Schlüssels in einer gültigen Tastenkombination entspricht.|  
|[CMFCToolBar::UpdateButton](../Topic/CMFCToolBar::UpdateButton.md)|Aktualisiert den Zustand der angegebenen Schaltfläche.|  
|[CMFCToolBar::WrapToolBar](../Topic/CMFCToolBar::WrapToolBar.md)|Ordnet Symbolleisten\-Schaltflächen innerhalb der angegebenen Dimensionen neu.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBar::AllowShowOnList](../Topic/CMFCToolBar::AllowShowOnList.md)|Bestimmt, ob die Symbolleiste in der Liste auf dem **Symbolleisten** Bereich **Anpassen** des Dialogfelds angezeigt wird.|  
|[CMFCToolBar::CalcMaxButtonHeight](../Topic/CMFCToolBar::CalcMaxButtonHeight.md)|Berechnet die maximale Höhe einer Schaltfläche in der Symbolleiste auf.|  
|[CMFCToolBar::DoPaint](../Topic/CMFCToolBar::DoPaint.md)|Streicht eine Symbolleiste neu.|  
|[CMFCToolBar::DrawButton](../Topic/CMFCToolBar::DrawButton.md)|Streicht eine Symbolleisten\-Schaltfläche neu.|  
|[CMFCToolBar::DrawSeparator](../Topic/CMFCToolBar::DrawSeparator.md)|Streicht ein Trennzeichen auf einer Symbolleiste neu.|  
|[CMFCToolBar::OnUserToolTip](../Topic/CMFCToolBar::OnUserToolTip.md)|Aufgerufen vom Framework, wenn die QuickInfo für eine Schaltfläche im Begriff ist angezeigt werden.|  
  
### Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCToolBar::m\_bDontScaleImages](../Topic/CMFCToolBar::m_bDontScaleImages.md)|Gibt an, ob Sie oder nicht Symbolleistenimages im Modus für hohe DPI\-Auflösungen skaliert.|  
|[CMFCToolBar::m\_dblLargeImageRatio](../Topic/CMFCToolBar::m_dblLargeImageRatio.md)|Gibt das Verhältnis zwischen der Dimension \(Höhe oder Breite\) großer Bilder und der Dimension regulärer Bilder.|  
  
## Hinweise  
 Um ein `CMFCToolBar`\-Objekt in die Anwendung zu speichern, führen Sie folgende Schritte aus:  
  
1.  Fügen Sie ein Objekt an den `CMFCToolBar` Hauptrahmenfenster hinzu.  
  
2.  Wenn Sie die `WM_CREATE` Meldung für das Hauptrahmenfenster verarbeiten, rufen Sie entweder [CMFCToolBar::Create](../Topic/CMFCToolBar::Create.md) oder [CMFCToolBar::CreateEx](../Topic/CMFCToolBar::CreateEx.md) auf, um die Symbolleiste erstellen und sein Format angeben.  
  
3.  Rufen Sie [CBasePane::EnableDocking](../Topic/CBasePane::EnableDocking.md) auf, um das andockbare Format angeben.  
  
 Um eine spezielle Schaltfläche, beispielsweise ein Kombinationsfeld oder eine Dropdownsymbolleiste einzufügen, reservieren Sie eine blinde Schaltfläche in der übergeordneten Ressource, und ersetzen Sie die blinde Schaltfläche zur Laufzeit indem Sie [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md) verwenden.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
 `CMFCToolBar` ist die Basisklasse für die MFC\-Bibliotheksklassen [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md), [CMFCPopupMenuBar\-Klasse](../../mfc/reference/cmfcpopupmenubar-class.md) und [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCToolBar` verwendet.  Im Beispiel wird gezeigt, wie Sie den Text der Fensterbezeichnung der Symbolleiste festlegen, Rahmen festlegen, das Format des Bereichs festlegen und die Schaltfläche **Schaltflächen hinzufügen oder entfernen** aktiviert, die am Ende der Symbolleiste angezeigt wird.  Dieser Codeausschnitt ist Teil [IE\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_IEDemo#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_IEDemo#6)]  
[!CODE [NVC_MFC_IEDemo#8](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_IEDemo#8)]  
  
## Anforderungen  
 **Header:** afxtoolbar.h  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCMenuBar Class](../../mfc/reference/cmfcmenubar-class.md)   
 [CMFCPopupMenuBar\-Klasse](../../mfc/reference/cmfcpopupmenubar-class.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)