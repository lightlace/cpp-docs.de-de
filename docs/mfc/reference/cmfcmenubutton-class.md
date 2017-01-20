---
title: "CMFCMenuButton-Klasse"
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
  - "CMFCMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCMenuButton-Klasse"
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCMenuButton-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Schaltfläche, die ein Popupmenü angezeigt und über die Benutzermenü\-Auswahl gemeldet.  
  
## Syntax  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCMenuButton::CMFCMenuButton](../Topic/CMFCMenuButton::CMFCMenuButton.md)|Erstellt ein `CMFCMenuButton`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCMenuButton::PreTranslateMessage](../Topic/CMFCMenuButton::PreTranslateMessage.md)|Aufgerufen durch das Framework, um Fenstermeldungen zu übersetzen, bevor sie weitergeleitet werden.  \(Überschreibungen `CMFCButton::PreTranslateMessage`.\)|  
|[CMFCMenuButton::SizeToContent](../Topic/CMFCMenuButton::SizeToContent.md)|Ändert die Größe der Schaltfläche entsprechend dem Text und Imagegröße.|  
  
### Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CMFCMenuButton::m\_bOSMenu](../Topic/CMFCMenuButton::m_bOSMenu.md)|Gibt an, ob das standardmäßige Systempopupmenü angezeigt oder [CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md) verwendet.|  
|[CMFCMenuButton::m\_bRightArrow](../Topic/CMFCMenuButton::m_bRightArrow.md)|Die gibt an, ob das Popupmenü oder rechts neben der Schaltfläche angezeigt wird.|  
|[CMFCMenuButton::m\_bStayPressed](../Topic/CMFCMenuButton::m_bStayPressed.md)|Gibt an, ob die Menütaste Zustand geändert, nachdem der Benutzer die Schaltfläche freigibt.|  
|[CMFCMenuButton::m\_hMenu](../Topic/CMFCMenuButton::m_hMenu.md)|Ein Handle das verknüpfte Menü Fenster.|  
|[CMFCMenuButton::m\_nMenuResult](../Topic/CMFCMenuButton::m_nMenuResult.md)|Ein Bezeichner, der angibt, das Element der Benutzer vom Popupmenü ausgewählt hat.|  
  
## Hinweise  
 Die `CMFCMenuButton`\-Klasse wird von [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md) abgeleitet, die wiederum von [CButton Class](../../mfc/reference/cbutton-class.md) abgeleitet wird.  Daher können Sie `CMFCMenuButton` im Code verwenden dieselbe Methode, die Sie `CButton` verwenden würden.  
  
 Wenn Sie `CMFCMenuButton` erstellen, müssen Sie in ein Handle für den zugeordneten Popupmenü übergeben.  Rufen Sie anschließend die Funktion `CMFCMenuButton::SizeToContent` auf.  `CMFCMenuButton::SizeToContent` Überprüfungen, die die Schaltflächengröße ausreichend ist, einen Pfeil einzuschließen, der dem Speicherort zeigt, in dem das Popupfenster wird \- und zwar, unter oder rechts neben der Schaltfläche.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das Handle des Menüs festlegt, das der Schaltfläche angefügt wird, ändert sich die Schaltfläche entsprechend dem Text und Bildgröße Größe und für das Kontextmenü fest, das vom Framework angezeigt wird.  Dieser Codeausschnitt ist Teil [Neue Kontrollprobe](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_NewControls#38](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#38)]  
[!CODE [NVC_MFC_NewControls#39](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_NewControls#39)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## Anforderungen  
 **Header:** afxmenubutton.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)