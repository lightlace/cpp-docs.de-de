---
title: "Defining Member Variables for Dialog Controls"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "member variables, defining for controls"
  - "variables, dialog box control member variables"
  - "controls [C++], member variables"
  - "Dialog editor, defining member variables for controls"
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Member Variables for Dialog Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit der folgenden Methode können Sie eine Membervariable für beliebige Dialogfenster\-Steuerelemente außer Schaltflächen definieren.  
  
> [!NOTE]
>  Dieser Artikel gilt nur für Dialogfeld\-Steuerelemente innerhalb eines MFC\-Projekts.  ATL\-Projekte sollten das Dialogfeld **Neue Windows\-Meldungen und Ereignishandler** verwenden.  
  
### So definieren Sie eine Membervariable für ein Dialogfeld\-Steuerelement \(kein Schaltflächen\-Steuerelement\)  
  
1.  Wählen Sie im [Dialog\-Editor](../mfc/dialog-editor.md) ein Steuerelement aus.  
  
2.  Doppelklicken Sie auf das Dialogfeld\-Steuerelement, während Sie **STRG**\-Taste gedrückt halten.  
  
     Es wird der [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) angezeigt.  
  
3.  Geben Sie im **Assistenten zum Hinzufügen von Membervariablen** die entsprechenden Informationen an.  Weitere Informationen finden Sie unter [Dialogdatenaustausch](../mfc/dialog-data-exchange.md).  
  
4.  Klicken Sie auf **OK**, um zum Dialog\-Editor zurückzukehren.  
  
    > [!TIP]
    >  Doppelklicken Sie auf das Steuerelement, um von einem Dialogfeld\-Steuerelement zu seinem vorhandenen Handler zu wechseln.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Sie können auch mithilfe der Registerkarte  **Membervariablen** im **MFC\-Klassen\-Assistenten** neue Membervariablen für eine angegebene Klasse hinzufügen und bereits definierte Variablen anzeigen.  
  
 Anforderungen  
  
 MFC  
  
## Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC\-Klassen\-Assistent](../mfc/reference/mfc-class-wizard.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)