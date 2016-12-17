---
title: "CMFCRibbonBar Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBar class"
ms.assetid: a65d06fa-1a28-4cc0-8971-bc9d7c9198fe
caps.latest.revision: 41
caps.handback.revision: "31"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCRibbonBar`\-Klasse implementiert eine Menübandleiste, die der in Office 2007 verwendeten ähnlich ist.  
  
## Syntax  
  
```  
class CMFCRibbonBar : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CMFCRibbonBar::CMFCRibbonBar`|Standardkonstruktor|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCRibbonBar::ActivateContextCategory](../Topic/CMFCRibbonBar::ActivateContextCategory.md)|Aktiviert eine bereits angezeigte Kontextkategorie.|  
|[CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md)|Fügt dem Menüband eine neue Menübandkategorie hinzu.|  
|[CMFCRibbonBar::AddContextCategory](../Topic/CMFCRibbonBar::AddContextCategory.md)|Fügt eine Kontextkategorie hinzu.|  
|[CMFCRibbonBar::AddMainCategory](../Topic/CMFCRibbonBar::AddMainCategory.md)|Fügt dem Menüband eine neue Hauptkategorie hinzu.|  
|[CMFCRibbonBar::AddPrintPreviewCategory](../Topic/CMFCRibbonBar::AddPrintPreviewCategory.md)||  
|[CMFCRibbonBar::AddQATOnlyCategory](../Topic/CMFCRibbonBar::AddQATOnlyCategory.md)||  
|[CMFCRibbonBar::AddToTabs](../Topic/CMFCRibbonBar::AddToTabs.md)|Fügt der rechten Seite einer Menübandleiste ein Menübandelement hinzu.|  
|[CMFCRibbonBar::CreateEx](../Topic/CMFCRibbonBar::CreateEx.md)|Erstellt eine Steuerleiste und fügt sie an das [CPane](../../mfc/reference/cpane-class.md)\-Objekt an.  \(Überschreibt [CPane::CreateEx](../Topic/CPane::CreateEx.md).\)|  
|[CMFCRibbonBar::Create](../Topic/CMFCRibbonBar::Create.md)|Erstellt ein Menübandsteuerelement und fügt es einer Menübandleiste hinzu.|  
|[CMFCRibbonBar::DeactivateKeyboardFocus](../Topic/CMFCRibbonBar::DeactivateKeyboardFocus.md)||  
|[CMFCRibbonBar::DrawMenuImage](../Topic/CMFCRibbonBar::DrawMenuImage.md)||  
|[CMFCRibbonBar::DWMCompositionChanged](../Topic/CMFCRibbonBar::DWMCompositionChanged.md)||  
|[CMFCRibbonBar::EnableKeyTips](../Topic/CMFCRibbonBar::EnableKeyTips.md)|Aktiviert bzw. deaktiviert Zugriffstasteninfos für das Menübandsteuerelement.|  
|[CMFCRibbonBar::EnablePrintPreview](../Topic/CMFCRibbonBar::EnablePrintPreview.md)|Aktiviert die Registerkarte **Seitenansicht**.|  
|[CMFCRibbonBar::EnableToolTips](../Topic/CMFCRibbonBar::EnableToolTips.md)|Aktiviert oder deaktiviert QuickInfos und QuickInfo\-Beschreibungen auf der Menübandleiste.|  
|[CMFCRibbonBar::FindByData](../Topic/CMFCRibbonBar::FindByData.md)|Sucht anhand der vom Benutzer angegebenen Daten nach einem Menübandelement.|  
|[CMFCRibbonBar::FindByID](../Topic/CMFCRibbonBar::FindByID.md)|Sucht nach einem Menübandelement mit der angegebenen Befehls\-ID.|  
|[CMFCRibbonBar::FindCategoryIndexByData](../Topic/CMFCRibbonBar::FindCategoryIndexByData.md)|Sucht den Index der Menübandkategorie, die die benutzerdefinierten Daten enthält.|  
|[CMFCRibbonBar::ForceRecalcLayout](../Topic/CMFCRibbonBar::ForceRecalcLayout.md)||  
|[CMFCRibbonBar::GetActiveCategory](../Topic/CMFCRibbonBar::GetActiveCategory.md)|Ruft einen Zeiger auf eine aktive Kategorie ab.|  
|[CMFCRibbonBar::GetCaptionHeight](../Topic/CMFCRibbonBar::GetCaptionHeight.md)|Gibt die Beschriftungshöhe zurück.  \(Überschreibt [CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md).\)|  
|[CMFCRibbonBar::GetCategory](../Topic/CMFCRibbonBar::GetCategory.md)|Ruft den Zeiger auf eine Kategorie ab, die sich an einem angegebenen Index befindet.|  
|[CMFCRibbonBar::GetCategoryCount](../Topic/CMFCRibbonBar::GetCategoryCount.md)|Ruft die Anzahl der Menübandkategorien in der Menübandleiste ab.|  
|[CMFCRibbonBar::GetCategoryHeight](../Topic/CMFCRibbonBar::GetCategoryHeight.md)||  
|[CMFCRibbonBar::GetCategoryIndex](../Topic/CMFCRibbonBar::GetCategoryIndex.md)|Gibt den Index einer Menübandkategorie zurück.|  
|[CMFCRibbonBar::GetContextName](../Topic/CMFCRibbonBar::GetContextName.md)|Ruft den Namen der Kontextkategoriebeschriftung ab, die Sie mit einer ID angeben.|  
|[CMFCRibbonBar::GetDroppedDown](../Topic/CMFCRibbonBar::GetDroppedDown.md)||  
|[CMFCRibbonBar::GetElementsByID](../Topic/CMFCRibbonBar::GetElementsByID.md)|Ruft ein Array ab, das die Zeiger auf alle Menübandelemente enthält, die die angegebene ID aufweisen.|  
|[CMFCRibbonBar::GetApplicationButton](../Topic/CMFCRibbonBar::GetApplicationButton.md)|Ruft einen Zeiger auf eine Menübandschaltfläche ab.|  
|[CMFCRibbonBar::GetFocused](../Topic/CMFCRibbonBar::GetFocused.md)|Gibt ein Fokuselement zurück.|  
|[CMFCRibbonBar::GetHideFlags](../Topic/CMFCRibbonBar::GetHideFlags.md)||  
|[CMFCRibbonBar::GetItemIDsList](../Topic/CMFCRibbonBar::GetItemIDsList.md)||  
|[CMFCRibbonBar::GetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::GetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelCurrent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelCurrent.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelParent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelParent.md)||  
|[CMFCRibbonBar::GetMainCategory](../Topic/CMFCRibbonBar::GetMainCategory.md)|Gibt einen Zeiger auf die aktuell ausgewählte Menübandkategorie zurück.|  
|[CMFCRibbonBar::GetQATCommandsLocation](../Topic/CMFCRibbonBar::GetQATCommandsLocation.md)||  
|[CMFCRibbonBar::GetQATDroppedDown](../Topic/CMFCRibbonBar::GetQATDroppedDown.md)||  
|[CMFCRibbonBar::GetQuickAccessCommands](../Topic/CMFCRibbonBar::GetQuickAccessCommands.md)|Füllt eine Liste aus, die die Befehls\-IDs aller Elemente in der Symbolleiste für den Schnellzugriff enthält.|  
|[CMFCRibbonBar::GetQuickAccessToolbarLocation](../Topic/CMFCRibbonBar::GetQuickAccessToolbarLocation.md)||  
|[CMFCRibbonBar::GetTabTrancateRatio](../Topic/CMFCRibbonBar::GetTabTrancateRatio.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthLargeImage](../Topic/CMFCRibbonBar::GetTooltipFixedWidthLargeImage.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthRegular](../Topic/CMFCRibbonBar::GetTooltipFixedWidthRegular.md)||  
|[CMFCRibbonBar::GetVisibleCategoryCount](../Topic/CMFCRibbonBar::GetVisibleCategoryCount.md)||  
|[CMFCRibbonBar::HideAllContextCategories](../Topic/CMFCRibbonBar::HideAllContextCategories.md)|Blendet alle aktiven und sichtbaren Kategorien aus.|  
|[CMFCRibbonBar::HideKeyTips](../Topic/CMFCRibbonBar::HideKeyTips.md)||  
|[CMFCRibbonBar::HitTest](../Topic/CMFCRibbonBar::HitTest.md)|Sucht einen Zeiger auf das Menübandelement, das sich am angegebenen Punkt der Clientkoordinaten des Menübands befindet.|  
|[CMFCRibbonBar::IsKeyTipEnabled](../Topic/CMFCRibbonBar::IsKeyTipEnabled.md)|Legt fest, ob die Zugriffstasteninfos aktiviert sind.|  
|[CMFCRibbonBar::IsMainRibbonBar](../Topic/CMFCRibbonBar::IsMainRibbonBar.md)||  
|[CMFCRibbonBar::IsPrintPreviewEnabled](../Topic/CMFCRibbonBar::IsPrintPreviewEnabled.md)|Legt fest, ob die Registerkarte **Seitenansicht** aktiviert ist.|  
|[CMFCRibbonBar::IsQATEmpty](../Topic/CMFCRibbonBar::IsQATEmpty.md)||  
|[CMFCRibbonBar::IsQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::IsQuickAccessToolbarOnTop.md)|Gibt an, ob sich die Symbolleiste für den Schnellzugriff oberhalb der Menübandleiste befindet.|  
|[CMFCRibbonBar::IsReplaceFrameCaption](../Topic/CMFCRibbonBar::IsReplaceFrameCaption.md)|Legt fest, ob die Menübandleiste die Beschriftung des Hauptrahmens ersetzt oder unterhalb des Hauptrahmens hinzugefügt wird.|  
|[CMFCRibbonBar::IsShowGroupBorder](../Topic/CMFCRibbonBar::IsShowGroupBorder.md)||  
|[CMFCRibbonBar::IsToolTipDescrEnabled](../Topic/CMFCRibbonBar::IsToolTipDescrEnabled.md)|Legt fest, ob QuickInfo\-Beschreibungen aktiviert sind.|  
|[CMFCRibbonBar::IsToolTipEnabled](../Topic/CMFCRibbonBar::IsToolTipEnabled.md)|Legt fest, ob die QuickInfos für die Menübandleiste aktiviert sind.|  
|[CMFCRibbonBar::IsTransparentCaption](../Topic/CMFCRibbonBar::IsTransparentCaption.md)||  
|[CMFCRibbonBar::IsWindows7Look](../Topic/CMFCRibbonBar::IsWindows7Look.md)|Gibt an, ob das Menüband im Stil von Windows 7 angezeigt wird \(kleine rechteckige Anwendungsschaltfläche\).|  
|[CMFCRibbonBar::LoadFromResource](../Topic/CMFCRibbonBar::LoadFromResource.md)|Überladen.  Lädt eine Menübandleiste aus den Anwendungsressourcen.|  
|[CMFCRibbonBar::OnClickButton](../Topic/CMFCRibbonBar::OnClickButton.md)||  
|[CMFCRibbonBar::OnEditContextMenu](../Topic/CMFCRibbonBar::OnEditContextMenu.md)||  
|[CMFCRibbonBar::OnRTLChanged](../Topic/CMFCRibbonBar::OnRTLChanged.md)|\(Überschreibt `CPane::OnRTLChanged`.\)|  
|[CMFCRibbonBar::OnSetAccData](../Topic/CMFCRibbonBar::OnSetAccData.md)|\(Überschreibt [CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md).\)|  
|[CMFCRibbonBar::OnShowRibbonContextMenu](../Topic/CMFCRibbonBar::OnShowRibbonContextMenu.md)||  
|[CMFCRibbonBar::OnShowRibbonQATMenu](../Topic/CMFCRibbonBar::OnShowRibbonQATMenu.md)||  
|[CMFCRibbonBar::OnSysKeyDown](../Topic/CMFCRibbonBar::OnSysKeyDown.md)||  
|[CMFCRibbonBar::OnSysKeyUp](../Topic/CMFCRibbonBar::OnSysKeyUp.md)||  
|[CMFCRibbonBar::PopTooltip](../Topic/CMFCRibbonBar::PopTooltip.md)||  
|[CMFCRibbonBar::PreTranslateMessage](../Topic/CMFCRibbonBar::PreTranslateMessage.md)|\(Überschreibt `CBasePane::PreTranslateMessage`.\)|  
|[CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md)|\(Überschreibt [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CMFCRibbonBar::RemoveAllCategories](../Topic/CMFCRibbonBar::RemoveAllCategories.md)|Entfernt alle Menübandkategorien von der Menübandleiste.|  
|[CMFCRibbonBar::RemoveAllFromTabs](../Topic/CMFCRibbonBar::RemoveAllFromTabs.md)|Entfernt alle Menübandelemente aus dem Registerkartenbereich.|  
|[CMFCRibbonBar::RemoveCategory](../Topic/CMFCRibbonBar::RemoveCategory.md)|Entfernt die Menübandkategorie, die sich am angegebenen Index befindet.|  
|[CMFCRibbonBar::SaveToXMLBuffer](../Topic/CMFCRibbonBar::SaveToXMLBuffer.md)|Speichert die Menübandleiste in einem Puffer.|  
|[CMFCRibbonBar::SaveToXMLFile](../Topic/CMFCRibbonBar::SaveToXMLFile.md)|Speichert die Menübandleiste in einer XML\-Datei.|  
|[CMFCRibbonBar::SetActiveCategory](../Topic/CMFCRibbonBar::SetActiveCategory.md)|Legt eine angegebenen Menübandkategorie als aktiv fest.|  
|[CMFCRibbonBar::SetActiveMDIChild](../Topic/CMFCRibbonBar::SetActiveMDIChild.md)||  
|[CMFCRibbonBar::SetElementKeys](../Topic/CMFCRibbonBar::SetElementKeys.md)|Legt die angegebenen Zugriffstasteninfos für alle Menübandelemente fest, die über die angegebene Befehls\-ID verfügen.|  
|[CMFCRibbonBar::SetApplicationButton](../Topic/CMFCRibbonBar::SetApplicationButton.md)|Weist der Menübandleiste eine Anwendungsschaltfläche zu.|  
|[CMFCRibbonBar::SetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::SetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::SetMaximizeMode](../Topic/CMFCRibbonBar::SetMaximizeMode.md)||  
|[CMFCRibbonBar::SetQuickAccessCommands](../Topic/CMFCRibbonBar::SetQuickAccessCommands.md)|Fügt der Symbolleiste für den Schnellzugriff eines oder mehrere Menübandelemente hinzu.|  
|[CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)|Gibt den Standardzustand für die Symbolleiste für den Schnellzugriff an.|  
|[CMFCRibbonBar::SetQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::SetQuickAccessToolbarOnTop.md)|Positioniert die Symbolleiste für den Schnellzugriff oberhalb oder unterhalb der Menübandleiste.|  
|[CMFCRibbonBar::SetTooltipFixedWidth](../Topic/CMFCRibbonBar::SetTooltipFixedWidth.md)||  
|[CMFCRibbonBar::SetWindows7Look](../Topic/CMFCRibbonBar::SetWindows7Look.md)|Aktiviert\/deaktiviert das Menüband im Stil von Windows 7 \(kleine rechteckige Anwendungsschaltfläche\).|  
|[CMFCRibbonBar::ShowCategory](../Topic/CMFCRibbonBar::ShowCategory.md)|Blendet die angegebene Menübandkategorie ein oder aus.|  
|[CMFCRibbonBar::ShowContextCategories](../Topic/CMFCRibbonBar::ShowContextCategories.md)|Blendet die Kontextkategorien mit der angegebenen ID ein oder aus.|  
|[CMFCRibbonBar::ShowKeyTips](../Topic/CMFCRibbonBar::ShowKeyTips.md)||  
|[CMFCRibbonBar::ToggleMimimizeState](../Topic/CMFCRibbonBar::ToggleMimimizeState.md)|Wechselt zwischen dem minimierten und maximierten Zustand der Menübandleiste.|  
|[CMFCRibbonBar::TranslateChar](../Topic/CMFCRibbonBar::TranslateChar.md)||  
  
## Hinweise  
 Microsoft hat das Office Fluent\-Menüband zusammen mit Microsoft Office 2007 eingeführt.  Dies Menübandleiste ist nicht nur ein neues Steuerelement.  Sie stellt auch eine neue Sichtweise der Benutzeroberfläche dar.  Das Menüband ist ein Bereich mit einer Reihe von Registerkarten, die als „Kategorien“ bezeichnet werden.  Jede Kategorie ist logisch in Menübandbereiche aufgeteilt, und jeder Bereich kann verschiedene Steuerelemente und Befehlsschaltflächen enthalten.  
  
 Die Elemente auf der Menübandleiste werden je nach Bedarf ein\- und ausgeblendet, um den verfügbaren Platz optimal zu nutzen.  Wenn ein Menübandbereich zum Beispiel nicht über ausreichend Platz verfügt, um alle Elemente anzuzeigen, wird er zu einer Menüschaltfläche, in dem untergeordnete Elemente in einem Popupmenü angezeigt werden.  Die Menübandleiste verhält sich wie eine statische \(unverankerte\) Steuerleiste und kann am oberen Rand des Rahmens verankert werden.  
  
 Mit der `CMFCRibbonStatusBar`\-Klasse können Sie eine Statusleiste implementieren, die der in Office 2007 verwendeten Statusleiste ähnelt.  Eine Menübandkategorie enthält eine Gruppe von [Menübandbereichen](../../mfc/reference/cmfcribbonpanel-class.md) \(und zeigt diese an\).  Jeder Menübandbereich umfasst eines oder mehrere Menübandelemente, die von [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md) abgeleitet werden.  
  
 Informationen zum Hinzufügen einer Menübandleiste zur einer vorhandenen MFC\-Anwendung finden Sie unter [Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble\-Anwendung](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
## Anforderungen  
 **Header:** afxribbonbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble\-Anwendung](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)