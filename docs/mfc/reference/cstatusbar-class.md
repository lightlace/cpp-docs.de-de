---
title: "CStatusBar Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CStatusBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBar class"
  - "indicators"
  - "indicators, status bar"
  - "Statusleisten"
  - "status indicators"
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Steuerleiste mit einer Zeile von Textausgabebereichen oder "von Indikatoren".  
  
## Syntax  
  
```  
class CStatusBar : public CControlBar  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](../Topic/CStatusBar::CStatusBar.md)|Erstellt ein `CStatusBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](../Topic/CStatusBar::CommandToIndex.md)|Ruft Index für eine angegebene Indikator ID ab|  
|[CStatusBar::Create](../Topic/CStatusBar::Create.md)|Erstellt die Statusleiste, fügt sie dem `CStatusBar`\-Objekt an und legt die ursprüngliche Schriftart\- und Leistehöhe fest.|  
|[CStatusBar::CreateEx](../Topic/CStatusBar::CreateEx.md)|Erstellt ein Objekt `CStatusBar` mit zusätzlichen Formaten für das eingebettete `CStatusBarCtrl`\-Objekt.|  
|[CStatusBar::DrawItem](../Topic/CStatusBar::DrawItem.md)|Aufgerufen, wenn ein visueller Aspekt eines Ownerdrawnstatusbar\-steuerelements ändert.|  
|[CStatusBar::GetItemID](../Topic/CStatusBar::GetItemID.md)|Ruft Indikator ID für einen angegebenen Index ab.|  
|[CStatusBar::GetItemRect](../Topic/CStatusBar::GetItemRect.md)|Ruft Anzeigenrechteck für einen angegebenen Index ab.|  
|[CStatusBar::GetPaneInfo](../Topic/CStatusBar::GetPaneInfo.md)|Ruft Indikator\-ID, \-Format und \- breite für einen angegebenen Index ab.|  
|[CStatusBar::GetPaneStyle](../Topic/CStatusBar::GetPaneStyle.md)|Ruft Indikatorformat für einen angegebenen Index ab.|  
|[CStatusBar::GetPaneText](../Topic/CStatusBar::GetPaneText.md)|Ruft Indikatortext für einen angegebenen Index ab.|  
|[CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md)|Ermöglicht Zugriff auf die zugrunde liegenden allgemeine Steuerelemente.|  
|[CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)|Legt Indikator IDs fest.|  
|[CStatusBar::SetPaneInfo](../Topic/CStatusBar::SetPaneInfo.md)|Legt Indikator\-ID, \-Format und \- breite für einen angegebenen Index fest.|  
|[CStatusBar::SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md)|Legt Indikatorformat für einen angegebenen Index fest.|  
|[CStatusBar::SetPaneText](../Topic/CStatusBar::SetPaneText.md)|Legt Indikatortext für einen angegebenen Index fest.|  
  
## Hinweise  
 Die Ausgabebereiche werden häufig als Meldungszeilen und als Statusanzeigen verwendet.  Beispiele sind die Menü HilfeMeldung Zeilen, die den ausgewählten kurz Menübefehl für und die Indikatoren, die den Status ROLLENs anzeigen, NUM und andere verschlüsselt.  
  
 [CStatusBar::GetStatusBarCtrl](../Topic/CStatusBar::GetStatusBarCtrl.md), eine Memberfunktion, die MFC 4.0 neu ist, ermöglicht es Ihnen, die Unterstützung des allgemeinen Windows\-Steuerelements für Statusleistenanpassung und \-zusätzliche Funktionen zu nutzen.  `CStatusBar`\-Memberfunktionen geben Sie den Großteil der Funktionalität der allgemeinen Windows\-Steuerelemente; Wenn Sie jedoch `GetStatusBarCtrl` aufrufen, können Sie den Statusleisten noch mehr der Eigenschaften einer Windows 95\/98\-Statusleiste geben.  Wenn Sie `GetStatusBarCtrl` aufrufen, gibt es einen Verweis auf ein Objekt `CStatusBarCtrl` zurück.  Siehe [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) weitere Informationen zum Entwerfen von Symbolleisten mithilfe der allgemeinen Windows\-Steuerelemente.  Weitere allgemeine Informationen über allgemeine Steuerelemente finden Sie unter [Allgemeine Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775493) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Das Framework speichert Indikatorinformationen in einem Array mit dem äußersten linken Indikator an Position 0.  Wenn Sie eine Statusleiste erstellen, verwenden Sie ein Array Zeichenfolge IDs, die das Framework mit den entsprechenden Indikatoren zuordnet.  Sie können entweder Zeichenfolgen\-ID oder einen Index dann verwenden, um auf einen Indikator zuzugreifen.  
  
 Standardmäßig ist der erste Indikator "Gummiband": er nimmt die Statusleistenlänge auf, der nicht von anderen Indikatorbereiche verwendet werden, damit die anderen Bereiche rechtsbündig ausgerichtet sind.  
  
 Um eine Statusleiste zu erstellen, führen Sie folgende Schritte aus:  
  
1.  Erstellen Sie das `CStatusBar`\-Objekt.  
  
2.  Rufen Sie die Funktion [Erstellen Sie](../Topic/CStatusBar::Create.md) \(oder [CreateEx](../Topic/CStatusBar::CreateEx.md)\) auf, um das Statusleistenfenster zu erstellen und auf den `CStatusBar`\-Objekt anzufügen.  
  
3.  Rufen Sie auf, um [SetIndicators](../Topic/CStatusBar::SetIndicators.md) Zeichenfolgen\-ID mit jedem Indikator zuzuordnen.  
  
 Es gibt drei Möglichkeiten, den Text in einem Statusleistenbereich zu aktualisieren:  
  
1.  Aufruf [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md), um Text in Bereich 0 nur zu aktualisieren.  
  
2.  Aufruf [CCmdUI::SetText](../Topic/CCmdUI::SetText.md) im `ON_UPDATE_COMMAND_UI`\-Handler der Statusleiste.  
  
3.  Aufruf [SetPaneText](../Topic/CStatusBar::SetPaneText.md), um Text für jeden Bereich zu aktualisieren.  
  
 Aufruf [SetPaneStyle](../Topic/CStatusBar::SetPaneStyle.md), die das Format des eines Statusleistenbereichs zu aktualisieren.  
  
 Weitere Informationen zur Verwendung von `CStatusBar`, finden Sie im Artikel [Statusleisten\-Implementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [Technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [MFC Sampling CTRLBARS](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DLGCBR32](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [CWnd::SetWindowText](../Topic/CWnd::SetWindowText.md)   
 [CStatusBar::SetIndicators](../Topic/CStatusBar::SetIndicators.md)