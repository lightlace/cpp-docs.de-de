---
title: "Hinzuf&#252;gen einer Klasse (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes.adding"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Klassen"
  - "Klassen [C++], Hinzufügen"
  - "Klassen [C++], Erstellen"
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer Klasse (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um eine Klasse in einem Visual C\+\+\-Projekt hinzuzufügen, klicken Sie in **Projektmappen\-Explorer**, mit der rechten Maustaste auf das Projekt, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Klasse**.  Dadurch wird das Dialogfeld [Dialogfeld "Klasse hinzufügen"](../ide/add-class-dialog-box.md) geöffnet.  
  
 Beim Hinzufügen einer Klasse müssen Sie einen Namen angeben, der noch nicht für andere Klassen in MFC oder ATL verwendet wurde.  Wenn Sie einen Namen verwenden, der in einer der beiden Bibliotheken bereits vorhanden ist, zeigt Visual C\+\+ durch eine Fehlermeldung an, dass der angegebene Name reserviert ist.  
  
 Wenn die Projektnamenskonvention die Verwendung eines vorhandenen Namens erfordert, können Sie die Schreibweise von mindestens einem Buchstaben im Namen ändern, da in Visual C\+\+ Groß\-\/Kleinschreibung beachtet wird.  Beispiel: Sie können eine Klasse nicht `CDocument` nennen, jedoch `cdocument`.  
  
## Welche Art von Klasse möchten Sie hinzufügen?  
 Im Dialogfeld **Klasse hinzufügen** werden beim Erweitern des Knotens **Visual C\+\+** im linken Bereich mehrere Gruppierungen von installierten Vorlagen angezeigt.  Dazu zählen **CLR**, **ATL**, **MFC** und **C\+\+**.  Wenn Sie eine Gruppe auswählen, wird eine Liste der verfügbaren Vorlagen in dieser Gruppe im mittleren Bereich angezeigt.  Jede Vorlage enthält die Dateien und den Quellcode, die für eine Klasse erforderlich sind.  
  
 Um eine neue Klasse zu generieren, wählen Sie im mittleren Bereich eine Vorlage aus, geben Sie einen Namen für die Klasse im Feld **Name** ein, und klicken Sie auf **Hinzufügen**.  Daraufhin wird der **Assistent zum Hinzufügen von Klassen** geöffnet, damit Sie Optionen für die Klasse angeben können.  
  
-   Weitere Informationen zum Erstellen von MFC\-Klassen finden Sie unter [MFC\-Klasse](../mfc/reference/adding-an-mfc-class.md).  
  
-   Weitere Informationen zum Erstellen von ATL\-Klassen finden Sie unter [ATL Simple Object](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Die Vorlage **ATL\-Unterstützung zu MFC hinzufügen** erstellt keine Klasse, sondern konfiguriert stattdessen das Projekt für die Verwendung von ATL.  Weitere Informationen finden Sie unter [ATL\-Unterstützung in einem MFC\-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 Um eine C\+\+\-Klasse zu erstellen, für die nicht MFC, ATL oder CLR verwendet wird, verwenden Sie die Vorlage **C\+\+\-Klasse** in der Gruppe **C\+\+** der installierten Vorlagen.  Weitere Informationen finden Sie unter [Hinzufügen einer generischen C\+\+\-Klasse](../ide/adding-a-generic-cpp-class.md).  
  
 Zwei Arten von formularbasierten C\+\+\-Klassen sind verfügbar.  Die Erste, [CFormView Class](../mfc/reference/cformview-class.md), erstellt eine MFC\-Klasse.  Mit der zweiten wird eine CLR\-Klasse \(Windows Forms\) erstellt.  
  
## Siehe auch  
 [Erstellen einer formularbasierten MFC\-Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Dialogfeld "Klasse hinzufügen"](../ide/add-class-dialog-box.md)   
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)