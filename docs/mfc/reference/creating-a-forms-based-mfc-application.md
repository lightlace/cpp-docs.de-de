---
title: "Erstellen einer formularbasierten MFC-Anwendung"
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
  - "vc.appwiz.mfcforms.project"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [MFC], Formularbasiert"
  - "Formularbasierte Anwendungen"
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen einer formularbasierten MFC-Anwendung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Formular ist ein Dialogfeld mit Steuerelementen, die dem Benutzer den Zugriff auf Daten und u. U. auch das Ändern von Daten ermöglichen.  Sie können beispielsweise eine Anwendung entwickeln, in der der Benutzer zwischen einer Reihe von Formularen auswählt.  Normalerweise kann der Benutzer in einer formularbasierten Anwendung auf Formulare zugreifen, indem er im Menü **Datei** auf **Neu** klickt.  Eine auf Dialogfeldern basierende Anwendung, die dem Benutzer keinen Zugriff auf die Option **Neu** im Menü **Datei** bietet, wird auch als formularbasierte Anwendung betrachtet.  
  
 Bei einer formularbasierten SDI \(Single Document Interface\)\-Anwendung kann jeweils nur eine Instanz eines bestimmten Formulars ausgeführt werden.  Es ist jedoch möglich, innerhalb einer formularbasierten SDI\-Anwendung unterschiedliche Formulare zur selben Zeit auszuführen, indem Sie im Menü **Datei** über den Befehl **Neu** ein neues Formular auswählen.  
  
 Wenn Sie eine formularbasierte MDI \(Multiple Document Interface\)\-Anwendung erstellen, kann die Anwendung mehrere Instanzen desselben Formulars unterstützen.  
  
 Wenn Sie eine Anwendung erstellen, die mehrere Dokumente der höchsten Ebene unterstützt, ist der Desktop das implizite übergeordnete Element des Dokuments, und der Dokumentrahmen ist nicht auf den Innenbereich der Anwendung beschränkt.  Sie können mehrere Instanzen des Dokuments öffnen, wobei jede Instanz über einen eigenen Rahmen sowie über ein eigenes Menü und Taskleistensymbol verfügt.  Aufeinander folgende Dokumentinstanzen können unabhängig voneinander geschlossen werden. Wenn Sie jedoch in der zuerst geöffneten Instanz im Menü **Datei** die Option `Exit` auswählen, schließt die Anwendung sämtliche Instanzen.  
  
 SDI\- und MDI\-Anwendungen und solche Anwendungen, die mehrere Dokumente der höchsten Ebene unterstützen, sind ausnahmslos formularbasiert und verwenden die Dokument\-\/Ansichtarchitektur.  
  
 Jede auf Dialogfeldern basierende Anwendung ist per Definition auch formularbasiert.  Da eine auf Dialogfeldern basierende Anwendung keine Dokument\-\/Ansichtarchitektur verwendet, müssen Sie die Erstellungs\- und Zugriffsmethoden für eigene zusätzliche Formulare selbst verwalten.  
  
 Die Basisklasse für formularbasierte Anwendungen ist [CFormView](../../mfc/reference/cformview-class.md).  Wenn die Anwendung Datenbankunterstützung bietet, können Sie auch eine beliebige, von `CFormView` abgeleitete Klasse auswählen.  Ein Formular ist ein beliebiges Fenster, das von `CFormView` oder von einer Klasse abgeleitet ist, die von `CFormView` erbt.  
  
 Selbst bei Verwendung einer Basisklasse, wie [CView](../../mfc/reference/cview-class.md), können die Anwendungen später auf Formularen basiert werden, indem Sie eine von `CFormView` abgeleitete [MFC\-Klasse hinzufügen](../../mfc/reference/adding-an-mfc-class.md) und das Kontrollkästchen **Erstellte DocTemplate\-Ressourcen** im [MFC\-Klassen\-Assistenten](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md) aktivieren.  
  
 Nachdem Sie die Arbeit mit dem Assistenten beendet haben, wird das Projekt geöffnet. Bei Auswahl von `CFormView` \(oder einer Klasse, die von `CFormView` erbt\) bzw. beim Erstellen einer auf Dialogfeldern basierenden Anwendung wird zusätzlich der Dialog\-Editor in Visual C\+\+ geöffnet.  Zu diesem Zeitpunkt können Sie Ihr erstes Formular entwerfen.  
  
### So beginnen Sie mit der Erstellung einer formularbasierten MFC\-Anwendung  
  
1.  Folgen Sie den Anweisungen unter [Erstellen einer MFC\-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Aktivieren Sie auf der Seite [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) des MFC\-Anwendungs\-Assistenten das Kontrollkästchen **Unterstützung für die Dokument\-\/Ansichtarchitektur**.  
  
3.  Wählen Sie **Einfaches Dokument**, **Mehrfaches Dokument** oder **Mehrere Dokumente der höchsten Ebene** aus.  
  
    > [!NOTE]
    >  Bei Auswahl einer SDI\- oder MDI\-Anwendung bzw. einer Anwendung, die mehrere Dokumente der höchsten Ebene unterstützt, wird auf der Seite [Generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) des Assistenten standardmäßig `CView` als Basisklasse für die Anwendungsansicht festgelegt.  Um eine formularbasierte Anwendung zu erstellen, müssen Sie `CFormView` als Basisklasse für die Anwendungsansicht auswählen.  Beachten Sie, dass der Assistent keine Druckunterstützung für formularbasierte Anwendungen bietet.  
  
4.  Legen Sie ggf. weitere Projektoptionen auf den anderen Seiten des Assistenten fest.  
  
5.  Klicken Sie auf **Fertig stellen**, um die Skelettanwendung zu erzeugen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Abgeleitete Ansichtsklassen in MFC](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Alternativen zur Dokument\-\/Ansichtarchitektur](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Überlegungen zum Anwendungsentwurf](../../mfc/application-design-choices.md)  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Formularansichten](../../mfc/form-views-mfc.md)   
 [Erstellen einer MFC\-Anwendung im Stil des Datei\-Explorers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [Erstellen einer MFC\-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)