---
title: "Manuelles Hinzuf&#252;gen von Steuerelementen"
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
  - "Allgemeine Steuerelemente [C++], Hinzufügen"
  - "Kontrollieren des Eingabefokus"
  - "Steuerelemente [MFC], Hinzufügen zu Dialogfeldern"
  - "Dialogfeldsteuerelemente [C++], Hinzufügen zu Dialogfeldern"
  - "Fokus, Kontrollieren von Eingabe"
  - "Eingabefokus-Steuerelemente"
  - "Allgemeine Windows-Steuerelemente [C++], Hinzufügen"
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Manuelles Hinzuf&#252;gen von Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können entweder die [Fügen Sie Steuerelemente einem Dialogfeld mit dem Dialog\-Editor hinzu](../mfc/using-the-dialog-editor-to-add-controls.md) oder hinzuzufügen sie sich, mit Code.  
  
 Um ein Steuerobjekt sich erstellen, müssen Sie normalerweise das C\+\+\-Steuerobjekt im Dialogfeld\- oder Rahmenfensterobjekt eine C\+\+\-Headerdatei ein.  Wie bei vielen anderen Objekte im Framework, benötigen Steuerelemente zweistufige Konstruktion.  Sie sollten die **Erstellen**\-Memberfunktion des Steuerelements als Teil des Erstellens des übergeordneten Dialogfeld oder des Rahmenfensters aufrufen.  Weitere Dialogfelder wird dies normalerweise in [OnInitDialog](../Topic/CDialog::OnInitDialog.md) und für Rahmenfenster, in [OnCreate](../Topic/CWnd::OnCreate.md) erreicht.  
  
 Das folgende Beispiel zeigt, wie Sie ein `CEdit`\-Objekt in der Klassendeklaration einer abgeleiteten Dialogfeldklasse deklarieren und anschließend die **Erstellen**\-Memberfunktion in `OnInitDialog` aufgerufen haben.  Da das `CEdit`\-Objekt als eingebettetes Objekt deklariert ist, wird es automatisch erstellt, wenn das gleichzeitig erstellt wird, jedoch muss mit einer eigenen **Erstellen**\-Memberfunktion noch initialisiert werden.  
  
 [!CODE [NVC_MFCControlLadenDialog#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#1)]  
  
 Die folgende `OnInitDialog`\-Funktion installiert ein Rechteck, ruft **Erstellen** auf, um das Windows\-Bearbeitungssteuerelement zu erstellen und es an nicht initialisierten `CEdit`\-Objekt anfügen.  
  
 [!CODE [NVC_MFCControlLadenDialog#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#2)]  
  
 Nachdem Sie das Bearbeitungsobjekt erstellt haben, können Sie den Eingabefokus auf das Steuerelement festlegen, indem Sie die `SetFocus`\-Memberfunktion aufrufen.  Abschließend geben Sie 0 von `OnInitDialog` zurück, um anzugeben dass legen Sie den Fokus.  Wenn Sie einen Wert ungleich 0 \(null\) zurückgeben, legt der Dialogfeldmanager den Fokus auf das erste Steuerelement in der Dialogfeldelementliste fest.  In den meisten Fällen werden Steuerelemente den Dialogfeldern mit dem Dialog\-Editor hinzufügen.  
  
## Siehe auch  
 [Erstellen und Verwenden von Steuerelementen](../mfc/making-and-using-controls.md)   
 [Steuerelemente](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)