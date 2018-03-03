---
title: Erstellen einer formularbasierten MFC-Anwendung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfcforms.project
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e5d43412da21edce2633c17b5a38e4b1b787495
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-forms-based-mfc-application"></a>Erstellen einer formularbasierten MFC-Anwendung
Ein Formular ist ein Dialogfeld mit Steuerelementen, die dem Benutzer den Zugriff auf Daten und u. U. auch das Ändern von Daten ermöglichen. Sie können beispielsweise eine Anwendung entwickeln, in der der Benutzer zwischen einer Reihe von Formularen auswählt. In der Regel eine formularbasierte Anwendung kann der Benutzer Zugriff Formulare durch Klicken **neu** aus der **Datei** Menü. Eine auf Dialogfeldern basierende Anwendung, die dem Benutzer keinen Zugriff auf wird eine **neu** -Option in der **Datei** Menü wird auch eine formularbasierte Anwendung betrachtet.  
  
 Bei einer formularbasierten SDI (Single Document Interface)-Anwendung kann jeweils nur eine Instanz eines bestimmten Formulars ausgeführt werden. Es ist möglich, unterschiedliche Formen gleichzeitig aus einer formularbasierten SDI-Anwendung ausführen, durch Auswahl eines neuen Formulars aus der **neu** -Option in der **Datei** Menü.  
  
 Wenn Sie eine formularbasierte MDI (Multiple Document Interface)-Anwendung erstellen, kann die Anwendung mehrere Instanzen desselben Formulars unterstützen.  
  
 Wenn Sie eine Anwendung erstellen, die mehrere Dokumente der höchsten Ebene unterstützt, ist der Desktop das implizite übergeordnete Element des Dokuments, und der Dokumentrahmen ist nicht auf den Innenbereich der Anwendung beschränkt. Sie können mehrere Instanzen des Dokuments öffnen, wobei jede Instanz über einen eigenen Rahmen sowie über ein eigenes Menü und Taskleistensymbol verfügt. Sie können nachfolgende Instanzen von Dokumenten einzeln, schließen Sie jedoch, wenn Sie wählen die `Exit` option die **Datei** Menü der ersten Instanz der Anwendung schließt alle Instanzen.  
  
 SDI- und MDI-Anwendungen und solche Anwendungen, die mehrere Dokumente der höchsten Ebene unterstützen, sind ausnahmslos formularbasiert und verwenden die Dokument-/Ansichtarchitektur.  
  
 Jede auf Dialogfeldern basierende Anwendung ist per Definition auch formularbasiert. Da eine auf Dialogfeldern basierende Anwendung keine Dokument-/Ansichtarchitektur verwendet, müssen Sie die Erstellungs- und Zugriffsmethoden für eigene zusätzliche Formulare selbst verwalten.  
  
 Ist die Basisklasse für formularbasierte Anwendungen [CFormView](../../mfc/reference/cformview-class.md). Wenn die Anwendung Datenbankunterstützung bietet, können Sie auch eine beliebige, von `CFormView` abgeleitete Klasse auswählen. Ein Formular ist ein beliebiges Fenster, das von `CFormView` oder von einer Klasse abgeleitet ist, die von `CFormView` erbt.  
  
 Auch wenn Sie eine Basisklasse, z. B. verwenden [CView](../../mfc/reference/cview-class.md), später möglich die Anwendungen von formularbasierten [Hinzufügen einer MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md) abgeleitet `CFormView` und Überprüfen der **DocTemplate generieren Ressourcen** Kontrollkästchen in der [MFC-Klassen-Assistent](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md).  
  
 Nachdem Sie die Arbeit mit dem Assistenten beendet haben, wird das Projekt geöffnet. Bei Auswahl von `CFormView` (oder einer Klasse, die von `CFormView` erbt) bzw. beim Erstellen einer auf Dialogfeldern basierenden Anwendung wird zusätzlich der Dialog-Editor in Visual C++ geöffnet. Zu diesem Zeitpunkt können Sie Ihr erstes Formular entwerfen.  
  
### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>So beginnen Sie mit der Erstellung einer formularbasierten MFC-Anwendung  
  
1.  Befolgen Sie die Anweisungen im [Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  Im MFC-Anwendungs-Assistenten [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite der **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** Kontrollkästchen.  
  
3.  Wählen Sie **einzelnes Dokument**, **mehrere Dokumente**, oder **mehrere Dokumente der höchsten Ebene**.  
  
    > [!NOTE]
    >  Wenn Sie einer SDI- oder MDI, bzw. mehrere Dokumente der höchsten Ebene Anwendung, die standardmäßig ausgewählten `CView` als Basisklasse für die Anwendungsansicht festgelegt ist die [generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten. Um eine formularbasierte Anwendung zu erstellen, müssen Sie `CFormView` als Basisklasse für die Anwendungsansicht auswählen. Beachten Sie, dass der Assistent keine Druckunterstützung für formularbasierte Anwendungen bietet.  
  
4.  Legen Sie ggf. weitere Projektoptionen auf den anderen Seiten des Assistenten fest.  
  
5.  Klicken Sie auf **Fertig stellen** um die skelettanwendung zu erzeugen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Abgeleitete Ansichtsklassen](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Alternativen zur Dokument-/Ansichtarchitektur](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Überlegungen zum Anwendungsentwurf](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendung-Assistent](../../mfc/reference/mfc-application-wizard.md)   
 [Formularansichten](../../mfc/form-views-mfc.md)   
 [Erstellen einer Datei-Explorer-ähnliche MFC-Anwendung](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [Erstellen einer MFC-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

