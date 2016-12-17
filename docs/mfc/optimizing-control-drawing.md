---
title: "Optimieren der Steuerelementdarstellung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelemente, Optimieren"
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Optimieren der Steuerelementdarstellung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Steuerelement angewiesen wird, die in einen Container\-angegebenen Gerätekontext zu zeichnen, wird es in der Regel GDI\-Objekte \(wie Pinsel, Stifte und Schriftarten\) in den Gerätekontext aus, führt die Zeichenvorgänge aus und stellt die vorherigen GDI\-Objekte zurückgesetzt.  Wenn der Container mehrere Steuerelemente, die in gezeichnet werden sollen, demselben Gerätekontext hat und jedes Steuerelement die GDI\-Objekte auswählt, die es benötigt, kann Zeit gespeichert werden, wenn die Steuerelemente nicht einzeln zuvor ausgewählte Objekte wiederherstellen.  Schließlich sind Steuerelemente, der Container können die ursprünglichen Objekte automatisch wiederhergestellt gezeichnet wurden.  
  
 Um zu erkennen ob ein Container diese Technik unterstützt, kann ein Steuerelement die [COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md)\-Memberfunktion aufrufen.  Wenn diese Funktion **TRUE** zurückgibt, kann das Steuerelement den normalen Schritt der Wiederherstellung der vorher ausgewählten Objekte überspringen.  
  
 Betrachten Sie ein Steuerelement, das über die folgende \(nicht optimierte\) `OnDraw`\-Funktion verfügt:  
  
 [!CODE [NVC_MFC_AxOpt#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#15)]  
  
 Der Stift und der Pinsel in diesem Beispiel sind die Variablen heißt, dass ihre als Destruktoren bezeichnet werden, wenn sie den Gültigkeitsbereich verlassen \(wenn die `OnDraw`\-Funktion beendet\).  Die Destruktoren versuchen, die entsprechenden GDI\-Objekte zu löschen.  Aber sie sollten nicht gelöscht werden, wenn Sie planen, diese werden ausgewählt in den Gerätekontext nach der Rückgabe von `OnDraw`.  
  
 Um die [CPen](../mfc/reference/cpen-class.md) und [CBrush](../mfc/reference/cbrush-class.md) an Objekte zerstört werden zu verhindern wenn `OnDraw` endet, speichern Sie sie in die Membervariablen statt der lokalen Variablen.  In der Klassendeklaration des Steuerelements fügen Sie Deklarationen für zwei neue Membervariablen hinzu:  
  
 [!CODE [NVC_MFC_AxOpt#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#16)]  
[!CODE [NVC_MFC_AxOpt#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#17)]  
  
 Anschließend kann die `OnDraw` umgeschrieben Funktion werden, wie folgt:  
  
 [!CODE [NVC_MFC_AxOpt#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#18)]  
  
 Diese Vorgehensweise vermeidet Erstellen des Stiftes und des Pinsels, wenn `OnDraw` aufgerufen wird.  Die Geschwindigkeitsverbesserung stammt auf Kosten der Sicherung von zusätzlichen Instanzdaten.  
  
 Wenn die Eigenschaft \- oder BackColor ändert, muss der Stift oder der Pinsel erneut erstellt werden.  Hierzu, überschreiben Sie die [OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md) und [OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md)\-Memberfunktionen:  
  
 [!CODE [NVC_MFC_AxOpt#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#19)]  
  
 Schließlich unnötige Aufrufe `SelectObject` zu vermeiden, ändern Sie `OnDraw`, wie folgt:  
  
 [!CODE [NVC_MFC_AxOpt#20](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#20)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)   
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC\-ActiveX\-Steuerelemente: Darstellen eines ActiveX\-Steuerelements](../mfc/mfc-activex-controls-painting-an-activex-control.md)