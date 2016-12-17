---
title: "Gewusst wie: Lesen aus und Schreiben in die Feedbackbereich der Statusleiste"
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
  - "Feedbackbereich, Statusleiste"
  - "Statusleiste, Feedbackbereich"
  - "Statusleiste, Übersicht"
ms.assetid: e639561c-e1e7-4660-b2a2-8bca80f34a29
caps.latest.revision: 12
caps.handback.revision: "12"
manager: "douge"
---
# Gewusst wie: Lesen aus und Schreiben in die Feedbackbereich der Statusleiste
Der Bereich der Statusleiste anzeigen [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Feed\-back simsen.  Sie können Text, wird durch statischen Text festlegen und abrufen und heben Sie den angezeigten Text hervor.  
  
### Um den Bereich der Visual Studio\-Statusleiste Feed\-back verwenden  
  
1.  Rufen Sie eine Instanz der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Schnittstelle, die von den <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> Dienst bereitgestellt wird.  
  
2.  Bestimmen, ob die Statusleiste fixiert ist, indem Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.IsFrozen*>\-Methode der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Instanz aufrufen.  
  
3.  Legen Sie den Text des Bereichs Feed\-back fest, indem Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.SetText*>\-Methode aufgerufen haben und in eine Textzeichenfolge haben.  
  
4.  Lesen Sie den Text des Bereichs Feed\-back, indem Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.GetText*>\-Methode aufgerufen haben.  
  
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie Text im Bereich Feed\-back Text geschrieben und gelesen wird.  
  
 [!CODE [VSSDKFeedbackStatusBar#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkfeedbackstatusbar#1)]  
  
 Im obigen Beispiel wird der Code die folgenden Aufgaben aus:  
  
-   Ruft eine Instanz der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Schnittstelle aus dem <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> Dienst.  
  
-   Überprüft, ob die Statusleiste fixiert werden, indem Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.IsFrozen*>\-Methode aufruft.  
  
-   Unterdrückt weitere Aktualisierungen der Statusleiste durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.FreezeOutput*>\-Methode.  
  
-   Liest den Text von der Statusleiste durch das Aufrufen der Methode <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.GetText*> und in einem Meldungsfeld angezeigt.  
  
-   Ermöglicht die Aktualisierungen der Statusleiste durch Aufrufen von <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.FreezeOutput*> und Übergeben von Parametern in 0.  
  
-   Löscht den Inhalt der Statusleiste durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Clear*>\-Methode.  
  
## Siehe auch  
 [Erweitern Sie die Statusleiste](../Topic/Extending%20the%20Status%20Bar.md)   
 [Gewusst wie: Programmieren des Statusanzeigenbereichs der Statusleiste](../misc/how-to-program-the-progress-bar-region-of-the-status-bar.md)   
 [Gewusst wie: Verwenden des Animationsbereichs der Statusleiste](../misc/how-to-use-the-animation-region-of-the-status-bar.md)   
 [Gewusst wie: Programmieren des Designerbereichs der Statusleiste](../misc/how-to-program-the-designer-region-of-the-status-bar.md)