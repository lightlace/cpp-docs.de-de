---
title: Erstellen einer formularbasierten MFC-Anwendung
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 95c7f6061933245b2eb2b796e7a678e1e6b010a6
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108463"
---
# <a name="creating-a-forms-based-mfc-application"></a>Erstellen einer formularbasierten MFC-Anwendung

Ein Formular ist ein Dialogfeld mit Steuerelementen, die dem Benutzer den Zugriff auf Daten und u. U. auch das Ändern von Daten ermöglichen. Sie können beispielsweise eine Anwendung entwickeln, in der der Benutzer zwischen einer Reihe von Formularen auswählt. Häufig ermöglicht eine Formular basierte Anwendung dem Benutzer den Zugriff auf Formulare, indem Sie im Menü **Datei** auf **neu** klicken. Eine dialogbasierte Anwendung, die Benutzern keinen Zugriff auf eine **neue** Option im Menü **Datei** gewährt, wird auch als Formular basierte Anwendung angesehen.

Bei einer formularbasierten SDI (Single Document Interface)-Anwendung kann jeweils nur eine Instanz eines bestimmten Formulars ausgeführt werden. Es ist möglich, unterschiedliche Formulare gleichzeitig aus einer SDI-Formular basierten Anwendung auszuführen, indem Sie im Menü **Datei** ein neues Formular aus der Option **neu** auswählen.

Wenn Sie eine formularbasierte MDI (Multiple Document Interface)-Anwendung erstellen, kann die Anwendung mehrere Instanzen desselben Formulars unterstützen.

Wenn Sie eine Anwendung erstellen, die mehrere Dokumente der höchsten Ebene unterstützt, ist der Desktop das implizite übergeordnete Element des Dokuments, und der Dokumentrahmen ist nicht auf den Innenbereich der Anwendung beschränkt. Sie können mehrere Instanzen des Dokuments öffnen, wobei jede Instanz über einen eigenen Rahmen sowie über ein eigenes Menü und Taskleistensymbol verfügt. Sie können nachfolgende Instanzen von Dokumenten einzeln schließen. Wenn Sie jedoch die Option **Exit** im Menü **Datei** der ursprünglichen Instanz auswählen, schließt die Anwendung alle Instanzen.

SDI- und MDI-Anwendungen und solche Anwendungen, die mehrere Dokumente der höchsten Ebene unterstützen, sind ausnahmslos formularbasiert und verwenden die Dokument-/Ansichtarchitektur.

Jede auf Dialogfeldern basierende Anwendung ist per Definition auch formularbasiert. Da eine auf Dialogfeldern basierende Anwendung keine Dokument-/Ansichtarchitektur verwendet, müssen Sie die Erstellungs- und Zugriffsmethoden für eigene zusätzliche Formulare selbst verwalten.

Die Basisklasse für Formular basierte Anwendungen ist [CFormView](cformview-class.md). Wenn die Anwendung Datenbankunterstützung bietet, können Sie auch eine beliebige, von `CFormView` abgeleitete Klasse auswählen. Ein Formular ist ein beliebiges Fenster, das von `CFormView` oder von einer Klasse abgeleitet ist, die von `CFormView` erbt.

Auch wenn Sie eine Basisklasse, z. b. [CView](cview-class.md), verwenden, können Sie Ihre Anwendungen zu einem späteren Zeitpunkt erstellen, indem Sie eine `CFormView` von abgeleitete [MFC-Klasse hinzufügen](adding-an-mfc-class.md) und im [MFC-Klassen-Assistenten](document-template-strings-mfc-add-class-wizard.md)das Kontrollkästchen **DocTemplate-Ressourcen generieren** aktivieren.

Nachdem Sie die Arbeit mit dem Assistenten beendet haben, wird das Projekt geöffnet. Bei Auswahl von `CFormView` (oder einer Klasse, die von `CFormView` erbt) bzw. beim Erstellen einer auf Dialogfeldern basierenden Anwendung wird zusätzlich der Dialog-Editor in Visual C++ geöffnet. Zu diesem Zeitpunkt können Sie Ihr erstes Formular entwerfen.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>So beginnen Sie mit der Erstellung einer formularbasierten MFC-Anwendung

1. Befolgen Sie die Anweisungen unter [Erstellen einer MFC-Anwendung](creating-an-mfc-application.md) für eine Formular basierte MFC-Anwendung.

1. Aktivieren Sie auf der Seite [Anwendungstyp](application-type-mfc-application-wizard.md) des MFC-Anwendungs-Assistenten das Kontrollkästchen **Unterstützung für Dokument-/Ansichtarchitektur** .

1. Wählen Sie **ein einzelnes Dokument**, **mehrere Dokumente**oder **mehrere Dokumente der obersten Ebene**aus.

    > [!NOTE]
    >  Wenn Sie eine SDI-, MDI-oder mehrere Dokument Schnittstellen Anwendung der obersten Ebene auswählen, `CView` wird standardmäßig als Basisklasse für die Ansicht Ihrer Anwendung auf der Seite [generierte Klassen](generated-classes-mfc-application-wizard.md) des Assistenten festgelegt. Um eine formularbasierte Anwendung zu erstellen, müssen Sie `CFormView` als Basisklasse für die Anwendungsansicht auswählen. Beachten Sie, dass der Assistent keine Druckunterstützung für formularbasierte Anwendungen bietet.

1. Legen Sie ggf. weitere Projektoptionen auf den anderen Seiten des Assistenten fest.

1. Klicken Sie zum Generieren der Skeleton-Anwendung auf **Fertig** stellen.

Weitere Informationen finden Sie unter:

- [Abgeleitete Ansichts Klassen](../derived-view-classes-available-in-mfc.md)

- [Alternativen zur Dokument-/Ansichtarchitektur](../alternatives-to-the-document-view-architecture.md)

- [Überlegungen zum Anwendungsentwurf](../application-design-choices.md)

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](mfc-application-wizard.md)<br/>
[Formular Ansichten](../form-views-mfc.md)<br/>
[Erstellen einer MFC-Anwendung im Stil des Datei-Explorers](creating-a-file-explorer-style-mfc-application.md)<br/>
[Erstellen einer MFC-Anwendung im Webbrowserstil](creating-a-web-browser-style-mfc-application.md)
