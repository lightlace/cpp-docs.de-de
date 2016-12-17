---
title: "Gewusst wie: Programmieren des Statusanzeigenbereichs der Statusleiste"
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
  - "Statusleiste, Statusanzeigenbereich"
  - "Statusanzeige, Statusleiste"
  - "Statusleiste, Programmierung"
ms.assetid: 4b54616a-8c20-436d-b764-f2380e5760f2
caps.latest.revision: 11
caps.handback.revision: "11"
manager: "douge"
---
# Gewusst wie: Programmieren des Statusanzeigenbereichs der Statusleiste
Der Statusanzeige [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Bereich der Statusleiste wird der inkrementellen Status von Operationen schneller an, z. B. eine Datei auf dem Datenträger gespeichert.  
  
### Um den Bereich der Statusanzeige Visual Studio\-Statusleiste verwenden  
  
1.  Rufen Sie eine Instanz der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Schnittstelle, die von den <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> Dienst bereitgestellt wird.  
  
2.  Initialisieren Sie die Statusanzeige auf die Anfangswerte, indem Sie die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress*>\-Methode aufrufen.  
  
3.  Aktualisieren Sie die Statusanzeige, wie der Vorgang fortgesetzt wird, indem die <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress*>\-Methode, um neue Werte festlegen.  
  
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie die Statusanzeige initialisiert und aktualisiert.  
  
 [!CODE [VSSDKProgressStatusBar#1](../CodeSnippet/VS_Snippets_VSSDK/vssdkprogressstatusbar#1)]  
  
 Im Beispiel der Code:  
  
-   Ruft eine Instanz der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>\-Schnittstelle aus dem <xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> Dienst.  
  
-   Initialisiert die Statusanzeige den angegebenen Anfangswerten durch Aufrufen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress*>\-Methode.  
  
-   Simuliert einen Vorgang indem das Durchlaufen einer `for` Schleife und Aktualisieren der Statusanzeige Attributwerte mithilfe der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Progress*>\-Methode.  
  
-   Löscht die Statusanzeige mit der <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar.Clear*>\-Methode.  
  
## Siehe auch  
 [Erweitern Sie die Statusleiste](../Topic/Extending%20the%20Status%20Bar.md)   
 [Gewusst wie: Lesen aus und Schreiben in die Feedbackbereich der Statusleiste](../misc/how-to-read-from-and-write-to-the-feedback-region-of-the-status-bar.md)   
 [Gewusst wie: Verwenden des Animationsbereichs der Statusleiste](../misc/how-to-use-the-animation-region-of-the-status-bar.md)   
 [Gewusst wie: Programmieren des Designerbereichs der Statusleiste](../misc/how-to-program-the-designer-region-of-the-status-bar.md)