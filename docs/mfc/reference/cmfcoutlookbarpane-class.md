---
title: "CMFCOutlookBarPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCOutlookBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanBeRestored method"
  - "CMFCOutlookBarPane class"
  - "Dock method"
  - "IsChangeState method"
  - "OnBeforeFloat method"
  - "RestoreOriginalstate method"
  - "SmartUpdate method"
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCOutlookBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Ein Steuerelement berechnete von [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md), das in einer Outlook\-Leiste \([CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)\) eingefügt werden kann.  Der Outlook\-Leistebereich enthält eine Spalte großer Schaltflächen.  Der Benutzer kann auf ab und die Liste der Schaltflächen, wenn sie größer als, ist der Bereich wechseln.  Wenn der Benutzer einen Outlook\-Leistebereich von der Outlook\-Leiste trennt, kann sie in das Hauptrahmenfenster Float oder andocken.  
  
## Syntax  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Standardkonstruktor.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCOutlookBarPane::AddButton](../Topic/CMFCOutlookBarPane::AddButton.md)|Fügt eine Schaltfläche dem Outlook\-Leistebereich hinzu.|  
|[CMFCOutlookBarPane::CanBeAttached](../Topic/CMFCOutlookBarPane::CanBeAttached.md)|Bestimmt, ob der Bereich zu einem anderen Bereich oder zu Rahmenfenster angedockt werden kann.  \(Überschreibungen [CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md).\)|  
|`CMFCOutlookBarPane::CanBeRestored`|Bestimmt, ob das System eine Symbolleiste in ihren ursprünglichen Zustand nach Anpassung wiederherstellen kann.  \(Überschreibungen [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md).\)|  
|[CMFCOutlookBarPane::ClearAll](../Topic/CMFCOutlookBarPane::ClearAll.md)|Gibt die Ressourcen frei, die durch die Bilder im Outlook\-Leistebereich verwendet werden.|  
|[CMFCOutlookBarPane::Create](../Topic/CMFCOutlookBarPane::Create.md)|Stellt den Outlook\-Leistebereich erstellt.|  
|`CMFCOutlookBarPane::CreateObject`|Wird vom Framework, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CMFCOutlookBarPane::Dock`|Aufgerufen vom Framework, um den Outlook\-Leistebereich anzudocken. \(Überschreibungen `CPane::Dock`.\)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](../Topic/CMFCOutlookBarPane::EnablePageScrollMode.md)|Gibt die Bildlaufpfeile ob auf dem Outlook\-Leistebereichsfortschritt die Liste der Schaltflächen nach Seite oder durch Schaltfläche an.|  
|[CMFCOutlookBarPane::GetRegularColor](../Topic/CMFCOutlookBarPane::GetRegularColor.md)|Gibt die reguläre \(nicht ausgewählte\) Textfarbe des Outlook\-Leistebereichs zurück.|  
|`CMFCOutlookBarPane::GetThisClass`|Wird vom Framework, um ein Zeiger auf [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)\-Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](../Topic/CMFCOutlookBarPane::IsBackgroundTexture.md)|Bestimmt, ob ein Hintergrundbild gibt, das für den Outlook\-Leistebereich geladen wird.|  
|`CMFCOutlookBarPane::IsChangeState`|Bestimmt, ob ein beweglicher Bereich möglicherweise angedockt ist.  \(Überschreibungen `CPane::IsChangeState`.\)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](../Topic/CMFCOutlookBarPane::IsDrawShadedHighlight.md)|Bestimmt, ob die Knopfleiste schattiert ist, wenn eine Schaltfläche hervorgehoben wird und ein Hintergrundbild angezeigt wird.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Aufgerufen vom Framework ausgelöst, wenn ein Bereich im Begriff ist von Fenstern.  \(Überschreibungen [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md).\)|  
|[CMFCOutlookBarPane::RemoveButton](../Topic/CMFCOutlookBarPane::RemoveButton.md)|Entfernt die Schaltfläche, die eine angegebene Befehl ID besitzt|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Stellt den ursprünglichen Zustand einer Symbolleiste wiederher.  \(Überschreibungen [CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md).\)|  
|[CMFCOutlookBarPane::SetBackColor](../Topic/CMFCOutlookBarPane::SetBackColor.md)|Legt die Hintergrundfarbe fest.|  
|[CMFCOutlookBarPane::SetBackImage](../Topic/CMFCOutlookBarPane::SetBackImage.md)|Legt das Hintergrundbild fest.|  
|[CMFCOutlookBarPane::SetDefaultState](../Topic/CMFCOutlookBarPane::SetDefaultState.md)|Setzt den Outlook\-Leistebereich zur Vorlage zurück, die von den Schaltflächen festgelegt ist.|  
|[CMFCOutlookBarPane::SetExtraSpace](../Topic/CMFCOutlookBarPane::SetExtraSpace.md)|Legt die Anzahl der Pixel Padding verwendet um Schaltflächen im Outlook\-Leistebereich fest.|  
|[CMFCOutlookBarPane::SetTextColor](../Topic/CMFCOutlookBarPane::SetTextColor.md)|Legt die Farben des regulären und markierten Text im Outlook\-Leistebereich fest.|  
|[CMFCOutlookBarPane::SetTransparentColor](../Topic/CMFCOutlookBarPane::SetTransparentColor.md)|Legt die transparente Farbe für den Outlook\-Leistebereich fest.|  
|`CMFCOutlookBarPane::SmartUpdate`|Wird intern verwendet, um die Outlook\-Leiste zu aktualisieren.  \(Überschreibungen `CMFCToolBar::SmartUpdate`.\)|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](../Topic/CMFCOutlookBarPane::EnableContextMenuItems.md)|Gibt an, welche Kontextmenüelemente im Anpassungsmodus angezeigt werden.|  
|[CMFCOutlookBarPane::RemoveAllButtons](../Topic/CMFCOutlookBarPane::RemoveAllButtons.md)|Entfernt alle Schaltflächen vom Outlook\-Leistebereich.  \(Überschreibungen [CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md).\)|  
  
## Hinweise  
 Informationen darüber, wie eine Outlook\-Leiste, finden Sie unter [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md) implementiert.  
  
 Ein Beispiel einer Outlook\-Leiste, finden Sie das OutlookDemo\-Beispiel zu projizieren.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden der Klasse `CMFCOutlookBarPane` verwendet.  Im Beispiel wird gezeigt, wie ein Outlook\-Leistebereich, ermöglichen die Seitenbilddurchlaufmodus, aktivieren Andocken und legen die Hintergrundfarbe der Outlook\-Leiste erstellt wird.  Dieser Codeausschnitt ist Teil [Multi Ansichtsbeispiel Outlook\-Projekt](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_OutlookMultiViews#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookMultiViews#3)]  
[!CODE [NVC_MFC_OutlookMultiViews#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_OutlookMultiViews#4)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## Anforderungen  
 **Header:** afxoutlookbarpane.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar\-Klasse](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)