---
title: "CMFCStatusBar Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCStatusBar class"
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
caps.latest.revision: 36
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 38
---
# CMFCStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `CMFCStatusBar`\-Klasse implementiert eine Statusleiste, die zur `CStatusBar`\-Klasse ähnelt.  hat jedoch die `CMFCStatusBar`\-Klasse die Funktionen, die nicht von den `CStatusBar`\-Klasse, wie die Fähigkeit Bilder, Animationen und Statusanzeigen bereitgestellt werden; und die Möglichkeit, auf Mausdoppelklicke zu reagieren.  
  
## Syntax  
  
```  
class CMFCStatusBar : public CPane  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCStatusBar::CalcFixedLayout](../Topic/CMFCStatusBar::CalcFixedLayout.md)|\(Überschreibungen [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CMFCStatusBar::CommandToIndex](../Topic/CMFCStatusBar::CommandToIndex.md)||  
|[CMFCStatusBar::Create](../Topic/CMFCStatusBar::Create.md)|Erstellt eine Steuerleiste und fügt sie dem [CPane](../../mfc/reference/cpane-class.md)\-Objekt.  \(Überschreibungen [CPane::Create](../Topic/CPane::Create.md).\)|  
|[CMFCStatusBar::CreateEx](../Topic/CMFCStatusBar::CreateEx.md)|Erstellt eine Steuerleiste und fügt sie dem [CPane](../../mfc/reference/cpane-class.md)\-Objekt.  \(Überschreibungen [CPane::CreateEx](../Topic/CPane::CreateEx.md).\)|  
|[CMFCStatusBar::DoesAllowDynInsertBefore](../Topic/CMFCStatusBar::DoesAllowDynInsertBefore.md)|Bestimmt, ob ein anderer Bereich zwischen diesen Bereich und die übergeordneten Frames dynamisch eingefügt werden kann.  \(Überschreibungen [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CMFCStatusBar::EnablePaneDoubleClick](../Topic/CMFCStatusBar::EnablePaneDoubleClick.md)|Aktiviert oder deaktiviert die Behandlung von Mausdoppelklicke auf der Statusleiste.|  
|[CMFCStatusBar::EnablePaneProgressBar](../Topic/CMFCStatusBar::EnablePaneProgressBar.md)|Zeigt eine Statusanzeige auf dem angegebenen Bereich an.|  
|[CMFCStatusBar::GetCount](../Topic/CMFCStatusBar::GetCount.md)|Gibt die Anzahl von Bereichen auf der Statusleiste zurück.|  
|[CMFCStatusBar::GetDrawExtendedArea](../Topic/CMFCStatusBar::GetDrawExtendedArea.md)||  
|[CMFCStatusBar::GetExtendedArea](../Topic/CMFCStatusBar::GetExtendedArea.md)||  
|[CMFCStatusBar::GetItemID](../Topic/CMFCStatusBar::GetItemID.md)||  
|[CMFCStatusBar::GetItemRect](../Topic/CMFCStatusBar::GetItemRect.md)||  
|[CMFCStatusBar::GetPaneInfo](../Topic/CMFCStatusBar::GetPaneInfo.md)||  
|[CMFCStatusBar::GetPaneProgress](../Topic/CMFCStatusBar::GetPaneProgress.md)||  
|[CMFCStatusBar::GetPaneStyle](../Topic/CMFCStatusBar::GetPaneStyle.md)|Gibt das Bereichsformat zurück.  \(Überschreibungen [CBasePane::GetPaneStyle](../Topic/CBasePane::GetPaneStyle.md).\)|  
|[CMFCStatusBar::GetPaneText](../Topic/CMFCStatusBar::GetPaneText.md)||  
|[CMFCStatusBar::GetPaneWidth](../Topic/CMFCStatusBar::GetPaneWidth.md)|Gibt die Breite, in Pixel, des angegebenen Bereichs der Statusleiste zurück.|  
|[CMFCStatusBar::GetTipText](../Topic/CMFCStatusBar::GetTipText.md)|Gibt den QuickInfo\-Text für den angegebenen Bereich der Statusleiste zurück.|  
|[CMFCStatusBar::InvalidatePaneContent](../Topic/CMFCStatusBar::InvalidatePaneContent.md)|Löscht den angegebenen Bereich ungültig und zeichnet Inhalt neu.|  
|[CMFCStatusBar::PreCreateWindow](../Topic/CMFCStatusBar::PreCreateWindow.md)|Aufgerufen durch das Framework vor der Erstellung der Windows\-Fensters angefügt `CWnd` zu diesem Objekt.  \(Überschreibungen [CWnd::PreCreateWindow](../Topic/CWnd::PreCreateWindow.md).\)|  
|[CMFCStatusBar::SetDrawExtendedArea](../Topic/CMFCStatusBar::SetDrawExtendedArea.md)||  
|[CMFCStatusBar::SetIndicators](../Topic/CMFCStatusBar::SetIndicators.md)||  
|[CMFCStatusBar::SetPaneAnimation](../Topic/CMFCStatusBar::SetPaneAnimation.md)|Weist eine Animation für den angegebenen Bereich zu.|  
|[CMFCStatusBar::SetPaneBackgroundColor](../Topic/CMFCStatusBar::SetPaneBackgroundColor.md)|Legt die Hintergrundfarbe für den angegebenen Bereich der Statusleiste fest.|  
|[CMFCStatusBar::SetPaneIcon](../Topic/CMFCStatusBar::SetPaneIcon.md)|Legt das Indikatorsymbol für den angegebenen Bereich der Statusleiste fest.|  
|[CMFCStatusBar::SetPaneInfo](../Topic/CMFCStatusBar::SetPaneInfo.md)||  
|[CMFCStatusBar::SetPaneProgress](../Topic/CMFCStatusBar::SetPaneProgress.md)|Legt den aktuellen Status der Statusanzeige für den angegebenen Bereich der Statusleiste fest.|  
|[CMFCStatusBar::SetPaneStyle](../Topic/CMFCStatusBar::SetPaneStyle.md)|Legt das Format des Bereichs fest.  \(Überschreibungen [CBasePane::SetPaneStyle](../Topic/CBasePane::SetPaneStyle.md).\)|  
|[CMFCStatusBar::SetPaneText](../Topic/CMFCStatusBar::SetPaneText.md)||  
|[CMFCStatusBar::SetPaneTextColor](../Topic/CMFCStatusBar::SetPaneTextColor.md)|Legt die Textfarbe für den angegebenen Bereich der Statusleiste fest.|  
|[CMFCStatusBar::SetPaneWidth](../Topic/CMFCStatusBar::SetPaneWidth.md)|Gibt die Breite in Pixel des angegebenen Bereichs der Statusleiste fest.|  
|[CMFCStatusBar::SetTipText](../Topic/CMFCStatusBar::SetTipText.md)|Legt den QuickInfo\-Text für den angegebenen Bereich der Statusleiste fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMFCStatusBar::OnDrawPane](../Topic/CMFCStatusBar::OnDrawPane.md)|Aufgerufen vom Framework, wenn sie den Bereich der Statusleiste neu gezeichnet wird.|  
  
## Hinweise  
 Das folgende Diagramm zeigt eine Abbildung der Statusleiste von [Statusleisten\-Demobeispiel](../../top/visual-cpp-samples.md) Anwendung.  
  
 ![Beispiel für CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar")  
  
## Beispiel  
 Im folgenden Beispiel wird die lokalen Variablen, die die Anwendung verwendet, um aufzurufen verschiedene Methoden in der Klasse `CMFCStatusBar`.  Diese Variablen werden in StatusBarDemoView.h deklariert.  Der Hauptframes wird in MainFrm.h deklariert, wird das Dokument in StatusBarDemoDoc.h deklariert, und die Ansicht wird in StatusBarDemoView.h deklariert.  Dieser Codeausschnitt ist Teil [Statusleisten\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_StatusBarDemo#9](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#9)]  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie ein Verweis auf `CMFCStatusBar`\-Objekt abrufen, indem die `GetStatusBar`\-Methode in MainFrm.h einführt und diese Methode anschließend aus der `GetStatusBar`\-Methode in StatusBarDemoView.h aufruft.  Dieser Codeausschnitt ist Teil [Statusleisten\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_StatusBarDemo#7](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#7)]  
[!CODE [NVC_MFC_StatusBarDemo#8](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#8)]  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie verschiedene Methoden in der Klasse `CMFCStatusBar` in StatusBarDemoView.cpp aufruft.  Die Konstanten sind in MainFrm.h deklariert.  Im Beispiel wird gezeigt, wie das Symbol, legen Sie den QuickInfo\-Text des Statusleistenbereichs, zeigt eine Statusanzeige auf dem angegebenen Bereich, weist eine Animation auf den angegebenen Bereich, legen Sie den Text und die Breite des Statusleistenbereichs und legen Sie die aktuelle Statusanzeige der Statusanzeige für den Statusleistenbereich festgelegt wird.  Dieser Codeausschnitt ist Teil [Statusleisten\-Demobeispiel](../../top/visual-cpp-samples.md).  
  
 [!CODE [NVC_MFC_StatusBarDemo#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#6)]  
[!CODE [NVC_MFC_StatusBarDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#1)]  
[!CODE [NVC_MFC_StatusBarDemo#2](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#2)]  
[!CODE [NVC_MFC_StatusBarDemo#3](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#3)]  
[!CODE [NVC_MFC_StatusBarDemo#4](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#4)]  
[!CODE [NVC_MFC_StatusBarDemo#5](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_StatusBarDemo#5)]  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)  
  
## Anforderungen  
 **Header:** afxstatusbar.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CStatusBar Class](../../mfc/reference/cstatusbar-class.md)