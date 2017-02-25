---
title: "CBaseTabbedPane-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBaseTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTabbedPane-Klasse"
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CBaseTabbedPane-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erweitert die Funktionalität [CDockablePane Class](../../mfc/reference/cdockablepane-class.md), um die Erstellung von Fenstern zu unterstützen im Registerkartenformat.  
  
## Syntax  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Standardkonstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md)|Fügt eine neue Registerkarte einer Seite im Registerformat hinzu.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md)|Gibt an, ob eine leere Seite im Registerformat zerstört werden kann.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](../Topic/CBaseTabbedPane::ApplyRestoredTabInfo.md)|Gilt Tabstoppoptionen, die aus der Registrierung geladen werden, auf eine Seite im Registerformat zu.|  
|[CBaseTabbedPane::CanFloat](../Topic/CBaseTabbedPane::CanFloat.md)|Bestimmt, ob der Bereich Float kann.  \(Überschreibungen [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).\)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md)|Bestimmt, ob die Beschriftung für die Seite im Registerformat den gleichen Text wie die aktive Registerkarte anzeigen soll.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](../Topic/CBaseTabbedPane::ConvertToTabbedDocument.md)|\(Überschreibungen [CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md).\)|  
|[CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md)|Konvertiert eine oder mehrere andockbare Fenster zu MDI mit den versehenen Dokumenten.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](../Topic/CBaseTabbedPane::EnableSetCaptionTextToTabName.md)|Aktiviert oder deaktiviert die Möglichkeit der Seite im Registerformat, Beschriftungstext mit dem Bezeichnungstext auf der aktiven Registerkarte zu synchronisieren.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](../Topic/CBaseTabbedPane::FillDefaultTabsOrderArray.md)|Stellt die interne Aktivierreihenfolge zu einem Standardzustand zurückgesetzt.|  
|[CBaseTabbedPane::FindBarByTabNumber](../Topic/CBaseTabbedPane::FindBarByTabNumber.md)|Gibt einen Bereich zurück, der in einer Registerkarte befinden, wenn die Registerkarte durch einen nullbasierten Registerkartenindex identifiziert wird.|  
|||  
|[CBaseTabbedPane::FindPaneByID](../Topic/CBaseTabbedPane::FindPaneByID.md)|Gibt einen Bereich zurück, der durch den ID identifiziert wird|  
|[CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)|Schwimmt einen Bereich, jedoch nur, wenn der Bereich sich gegenwärtig in einer abnehmbaren Registerkarte befindet.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](../Topic/CBaseTabbedPane::GetDefaultTabsOrder.md)|Gibt die Standardreihenfolge von Registerkarten im Bereich zurück.|  
|[CBaseTabbedPane::GetFirstVisibleTab](../Topic/CBaseTabbedPane::GetFirstVisibleTab.md)|Ruft einen Zeiger auf die zuerst angezeigten Registerkarte ab.|  
|[CBaseTabbedPane::GetMinSize](../Topic/CBaseTabbedPane::GetMinSize.md)|Ruft das Minimum ab, dessen Größe für den Bereich zulässig ist.  \(Überschreibungen [CPane::GetMinSize](../Topic/CPane::GetMinSize.md).\)|  
|[CBaseTabbedPane::GetPaneIcon](../Topic/CBaseTabbedPane::GetPaneIcon.md)|Gibt ein Handle für Bereichssymbol zurück.  \(Überschreibungen [CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md).\)|  
|[CBaseTabbedPane::GetPaneList](../Topic/CBaseTabbedPane::GetPaneList.md)|Gibt eine Liste von Bereichen zurück, die auf der Seite im Registerformat enthalten sind.|  
|[CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md)|Gibt die umgebenden Rechtecke für die Menüelemente und Unterseitenregisterkartenbereiche zurück.|  
|[CBaseTabbedPane::GetTabsNum](../Topic/CBaseTabbedPane::GetTabsNum.md)|Gibt die Anzahl von Registerkarten in einem Registerkartenfenster zurück.|  
|[CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md)|Ruft das zugrunde liegende \(umschlossene\) Registerkartenfenster ab.|  
|[CBaseTabbedPane::GetVisibleTabsNum](../Topic/CBaseTabbedPane::GetVisibleTabsNum.md)|Gibt die Anzahl der angezeigten Registerkarten zurück.|  
|[CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md)|Bestimmt, ob die Seite im Registerformat für den Modus "Automatisches Ausblenden" umgeschaltet werden kann.|  
|[CBaseTabbedPane::IsHideSingleTab](../Topic/CBaseTabbedPane::IsHideSingleTab.md)|Bestimmt, ob die Seite im Registerformat ausgeblendet wird, wenn nur eine Registerkarte angezeigt wird.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Wird intern während der Serialisierung.|  
|[CBaseTabbedPane::RecalcLayout](../Topic/CBaseTabbedPane::RecalcLayout.md)|Berechnet Layoutinformationen für den Bereich neu.  \(Überschreibungen [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CBaseTabbedPane::RemovePane](../Topic/CBaseTabbedPane::RemovePane.md)|Entfernt einen Bereich von der Seite im Registerformat.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Wird intern während der Serialisierung.|  
|`CBaseTabbedPane::Serialize`|\(Überschreibungen [CDockablePane::Serialize](assetId:///09787e59-e446-4e76-894b-206d303dcfd6).\)|  
|`CBaseTabbedPane::SerializeTabWindow`|Wird intern während der Serialisierung.|  
|[CBaseTabbedPane::SetAutoDestroy](../Topic/CBaseTabbedPane::SetAutoDestroy.md)|Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.|  
|[CBaseTabbedPane::SetAutoHideMode](../Topic/CBaseTabbedPane::SetAutoHideMode.md)|Schaltet den Hauptandockbereich zwischen angezeigt und Modus "Automatisches Ausblenden" um.  \(Überschreibungen [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md).\)|  
|[CBaseTabbedPane::ShowTab](../Topic/CBaseTabbedPane::ShowTab.md)|In oder aus einer Registerkarte.|  
  
## Hinweise  
 Diese Klasse ist eine abstrakte Klasse und kann nicht instanziiert werden.  Sie implementiert die Dienste, die mit allen Arten vonseiten im Registerformat gemeinsam sind.  
  
 Derzeit enthält die Bibliothek zwei berechnete Seite im Registerformaten\-Klassen ein: [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) und [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Ein \- Objekt `CBaseTabbedPane` bindet einen Zeiger auf einen [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md)\-Objekt ein.  [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) wird dann ein untergeordnetes Fenster der Seite im Registerformat.  
  
 Weitere Informationen dazu, wie Seiten im Registerformat, finden Sie unter [CDockablePane Class](../../mfc/reference/cdockablepane-class.md), [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) und [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md) erstellt wird.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
## Anforderungen  
 **Header:** afxBaseTabbedPane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)