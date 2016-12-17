---
title: "Formularansichten (MFC)"
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
  - "Anwendungen [MFC], Formularbasiert"
  - "Formulare [C++]"
  - "Formulare [C++], Hinzufügen zu Anwendungen"
  - "Formularbasierte Anwendungen"
  - "Benutzeroberflächen, Formulare"
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Formularansichten (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Formen jeder Visual C\+\+\-Anwendung, die die MFC\-Bibliotheken unterstützt, einschließlich [formularbasierten Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md) \(eines, dessen Ansichtsklasse von `CFormView` abgeleitet ist\) hinzufügen.  Wenn Sie nicht zuerst die Anwendung erstellt haben, zu unterstützen Formulare, fügt Visual C\+\+ dieser Unterstützung für Sie hinzu, wenn Sie ein neues Formular einfügen.  In einer SDI\- oder MDI\-Anwendung die das standardmäßige [Dokument\-\/Ansichtarchitektur](../mfc/document-view-architecture.md) implementiert, wenn der Benutzer den Befehl `New` \(standardmäßig, im Menü **Datei** \) auswählt, Visual C\+\+ den Benutzer auffordert, aus verfügbaren Formularen auszuwählen.  
  
 Mit einer SDI\-Anwendung wenn der Benutzer den Befehl auswählt `New`, wird die aktuelle Instanz des Formulars fort, um ausgeführt, jedoch eine neue Instanz der Anwendung mit dem ausgewählten Formular wird erstellt, wenn nicht gefunden wird.  In einer MDI\-Anwendung wird die aktuelle Instanz des Formulars fort, um ausgeführt zu werden, wenn der Benutzer den Befehl auswählt. `New`  
  
> [!NOTE]
>  Sie können ein Formular in eine auf Dialogfeldern basierende Anwendung \(eine Anwendung, deren Dialogfeldklasse auf `CDialog` und eine, in der keine Ansichtsklasse implementiert wird\) einfügen.  jedoch ohne Dokument\-\/Ansichtarchitektur, implementiert Visual C\+\+ nicht automatisch **Datei** &#124;**Neu**\-Funktionen.  Sie müssen eine Methode erstellen, damit der Benutzer zusätzliche Formulare, anzeigt, indem wie Sie ein Dialogfeld im Registerformat mit verschiedenen Eigenschaftenseiten implementieren.  
  
 Wenn Sie ein neues Formular in der Anwendung einfügen, erstellt Visual C\+\+ das folgende:  
  
-   Erstellt eine Klasse auf einer der FormularFormatklassen, die Sie auswählen \(`CFormView`, `CRecordView`, `CDaoRecordView` oder `CDialog`\).  
  
-   Erstellt eine Dialogfeldressource mit entsprechenden Formate \(oder Sie können eine vorhandene Dialogfeldressource verwenden, die noch nicht mit einer Klasse zugeordnet wurde\).  
  
     Wenn bereits eine Dialogfeldressource auswählen, müssen Sie diese Formate festlegen, indem Sie die Eigenschaftenseite für das Dialogfeld verwenden.  Formate für ein Dialogfeld müssen:  
  
     **WS\_CHILD**\=On  
  
     `WS_BORDER`\=Off  
  
     **WS\_VISIBLE**\=Off  
  
     **WS\_CAPTION\=** weg  
  
 Für Anwendungen auf der Dokument\-\/Ansichtarchitektur, der Befehl **Neues Formular** \(mit der rechten Maustaste in der Klassenansicht auch:\)  
  
-   Erstellt eine C\-basierte Klasse **CDocument**  
  
     Anstatt, eine neue Klasse erstellen können, können Sie eine bestehende \- Klasse **CDocument** im Projekt verwenden.  
  
-   Generiert eine Normal\-Vorlage \(abgeleitet von **CDocument**\) mit Zeichenfolge, Menü und Symbolressourcen.  
  
     Sie können auch eine neue Klasse erstellen, die auf der Vorlage basieren.  
  
-   Fügt einen Aufruf **AddDocumentTemplate** in `InitInstance` Code der Anwendung hinzu.  
  
     Visual C\+\+ wird diesem Code für jedes neue Formular hinzu, das Sie erstellen, das die Form der Liste verfügbarer Formularen hinzugefügt wird, wenn der Benutzer den Befehl auswählt. `New` Dieser Code enthält des zugeordneten die Ressourcen\-ID und die Namen Formulars des zugeordneten Dokuments, Ansicht und der Frameklassen, die zusammen das neue Formularobjekt bilden.  
  
     Dokumentvorlagen dienen als die Verbindung zwischen Dokumenten, Rahmenfenstern und Ansichten.  Einen einzelnen Dokument können Sie zahlreiche Vorlagen erstellen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Erstellen einer formularbasierten Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md)  
  
-   [Einfügen eines Formulars in ein Projekt](../mfc/inserting-a-form-into-a-project.md)  
  
## Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)