---
title: "Gewusst wie: Programmieren des Designerbereichs der Statusleiste"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Designerbereich, Statusleiste"
  - "Statusleisten, Programmierung"
  - "Statusleisten, Designerbereich"
ms.assetid: 735a86bb-80b2-4557-9677-00799856017f
caps.latest.revision: 11
caps.handback.revision: "11"
manager: "douge"
---
# Gewusst wie: Programmieren des Designerbereichs der Statusleiste
Der Designerbereich der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Statusleiste zeigt Informationen an, die Bearbeitungssitzung, z. B. die Zeilennummer und die Spaltennummer die Cursorposition betrifft.  
  
### Zum Programmieren der Designerbereich der Visual Studio\-Statusleiste  
  
1.  Rufen Sie eine Instanz der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Schnittstelle, die von den <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> Dienst bereitgestellt wird.  
  
2.  Aktualisieren Sie den Designerbereich der Statusleiste, indem Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetInsMode*>\-Methode und <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetLineColChar*>\-Methode der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Instanz aufrufen.  
  
## Beispiel  
 In diesem Beispiel wird das Programmieren den Designerbereich der Statusleiste.  
  
 [!CODE [VSSDKDesignerStatusBar#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkdesignerstatusbar#1)]  
  
## Siehe auch  
 [Erweitern Sie die Statusleiste](../Topic/Extending%20the%20Status%20Bar.md)   
 [Gewusst wie: Lesen aus und Schreiben in die Feedbackbereich der Statusleiste](../misc/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar.md)   
 [Gewusst wie: Programmieren des Statusanzeigenbereichs der Statusleiste](../misc/how-to-program-the-progress-bar-region-of-the-status-bar.md)   
 [Gewusst wie: Verwenden des Animationsbereichs der Statusleiste](../misc/how-to-use-the-animation-region-of-the-status-bar.md)