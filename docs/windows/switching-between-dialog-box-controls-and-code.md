---
title: "Switching Between Dialog Box Controls and Code | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "events [C++], viewing for controls"
  - "Windows messages [C++], controls"
  - "messages [C++], viewing for dialog boxes"
  - "Dialog editor, accessing code"
  - "code [C++], switching from Dialog Editor"
  - "controls [C++], jumping to code"
  - "Dialog editor, switching between controls and code"
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Switching Between Dialog Box Controls and Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In MFC\-Anwendungen können Sie auf Dialogfeld\-Steuerelemente doppelklicken, um direkt zum Handlercode zu gelangen oder schnell und einfach Stubhandlerfunktionen zu erstellen.  
  
 Um eine vollständige Liste der für das ausgewählte Element verfügbaren Windows\-Meldungen und \-Ereignisse zu erhalten, klicken Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) auf die Schaltfläche **Ereignisse** oder **Meldungen**, während ein Steuerelement ausgewählt ist.  Wählen Sie eine Option aus der Liste aus, oder bearbeiten Sie die Handlerfunktionen.  
  
### So wechseln Sie im Dialog\-Editor direkt zum Code  
  
1.  Doppelklicken Sie innerhalb des Dialogfelds auf ein Steuerelement, um zur Deklaration seiner zuletzt implementierten Meldungsbehandlungsfunktion zu springen.  \(Bei ATL\-basierten Dialogfeldklassen wechseln Sie stets zur Konstruktordefinition.\)  
  
### So zeigen Sie Ereignisse für ein Steuerelement an  
  
1.  Klicken Sie, während ein Steuerelement ausgewählt ist, im [Eigenschaftenfenster](../Topic/Properties%20Window.md) auf die Schaltfläche **Ereignisse**.  
  
    > [!NOTE]
    >  Wenn Sie auf die Schaltfläche **Steuerelementereignisse** klicken, während sich der Fokus im *Dialogfeld* befindet, wird eine Liste aller im Dialogfeld enthaltenen Steuerelemente angezeigt. Diese Liste kann erweitert werden, um Ereignisse einzelner Steuerelemente zu bearbeiten.  
  
     Wenn ein einzelnes Steuerelement im Dialogfeld den Fokus besitzt, können Sie mit der rechten Maustaste darauf klicken und im Kontextmenü die Option **Ereignishandler hinzufügen** auswählen.  Auf diese Weise können Sie die Klasse festlegen, der der Handler hinzugefügt wird.  Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).  
  
### So zeigen Sie Meldungen für ein Dialogfeld an  
  
1.  Klicken Sie, während das Dialogfeld ausgewählt ist, im [Eigenschaftenfenster](../Topic/Properties%20Window.md) auf die Schaltfläche **Meldungen**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Dialog Editor](../mfc/dialog-editor.md)