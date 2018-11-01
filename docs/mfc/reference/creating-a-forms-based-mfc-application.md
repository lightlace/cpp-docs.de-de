---
title: Erstellen einer formularbasierten MFC-Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcforms.project
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 692370e06668152cb6f5d5ecc762a3bbe991af08
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374656"
---
# <a name="creating-a-forms-based-mfc-application"></a>Erstellen einer formularbasierten MFC-Anwendung

Ein Formular ist ein Dialogfeld mit Steuerelementen, die dem Benutzer den Zugriff auf Daten und u. U. auch das Ändern von Daten ermöglichen. Sie können beispielsweise eine Anwendung entwickeln, in der der Benutzer zwischen einer Reihe von Formularen auswählt. In der Regel eine formularbasierte Anwendung kann der Benutzer Zugriff Formulare durch Klicken **neu** aus der **Datei** Menü. Eine auf Dialogfeldern basierende Anwendung, die dem Benutzer keinen Zugriff auf wird eine **neu** option die **Datei** Menü wird auch eine formularbasierte Anwendung betrachtet.

Bei einer formularbasierten SDI (Single Document Interface)-Anwendung kann jeweils nur eine Instanz eines bestimmten Formulars ausgeführt werden. Es ist möglich, verschiedene Formen zur gleichen Zeit einer formularbasierten SDI-Anwendung ausgeführt, indem Sie ein neues Formular über die **neu** option die **Datei** Menü.

Wenn Sie eine formularbasierte MDI (Multiple Document Interface)-Anwendung erstellen, kann die Anwendung mehrere Instanzen desselben Formulars unterstützen.

Wenn Sie eine Anwendung erstellen, die mehrere Dokumente der höchsten Ebene unterstützt, ist der Desktop das implizite übergeordnete Element des Dokuments, und der Dokumentrahmen ist nicht auf den Innenbereich der Anwendung beschränkt. Sie können mehrere Instanzen des Dokuments öffnen, wobei jede Instanz über einen eigenen Rahmen sowie über ein eigenes Menü und Taskleistensymbol verfügt. Sie können aufeinander folgende Dokumentinstanzen Dokumente einzeln schließen, aber, wenn Sie wählen die **beenden** option die **Datei** Menü mit der ursprünglichen Instanz, die Anwendung schließt alle Instanzen.

SDI- und MDI-Anwendungen und solche Anwendungen, die mehrere Dokumente der höchsten Ebene unterstützen, sind ausnahmslos formularbasiert und verwenden die Dokument-/Ansichtarchitektur.

Jede auf Dialogfeldern basierende Anwendung ist per Definition auch formularbasiert. Da eine auf Dialogfeldern basierende Anwendung keine Dokument-/Ansichtarchitektur verwendet, müssen Sie die Erstellungs- und Zugriffsmethoden für eigene zusätzliche Formulare selbst verwalten.

Die Basisklasse für formularbasierte Anwendungen ist [CFormView](../../mfc/reference/cformview-class.md). Wenn die Anwendung Datenbankunterstützung bietet, können Sie auch eine beliebige, von `CFormView` abgeleitete Klasse auswählen. Ein Formular ist ein beliebiges Fenster, das von `CFormView` oder von einer Klasse abgeleitet ist, die von `CFormView` erbt.

Auch wenn Sie eine Basisklasse, z. B. verwenden [CView](../../mfc/reference/cview-class.md), Sie können später machen, Ihre Anwendungen vom Forms-basierten [Hinzufügen einer MFC-Klasse](../../mfc/reference/adding-an-mfc-class.md) abgeleitet `CFormView` und die Überprüfung der **DocTemplate generieren Ressourcen** Kontrollkästchen in der [MFC-Klassenassistent](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md).

Nachdem Sie die Arbeit mit dem Assistenten beendet haben, wird das Projekt geöffnet. Bei Auswahl von `CFormView` (oder einer Klasse, die von `CFormView` erbt) bzw. beim Erstellen einer auf Dialogfeldern basierenden Anwendung wird zusätzlich der Dialog-Editor in Visual C++ geöffnet. Zu diesem Zeitpunkt können Sie Ihr erstes Formular entwerfen.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>So beginnen Sie mit der Erstellung einer formularbasierten MFC-Anwendung

1. Befolgen Sie die Anweisungen [Erstellen einer MFC-Anwendung](../../mfc/reference/creating-an-mfc-application.md).

1. Im MFC-Anwendungs-Assistenten [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite die **Unterstützung für die Dokument-/Ansicht** Kontrollkästchen.

1. Wählen Sie **einzelnes Dokument**, **mehrere Dokumente**, oder **mehrere Dokumente mit der höchsten Ebene**.

    > [!NOTE]
    >  Wenn Sie einer SDI- oder MDI, bzw. mehrere Dokumente der höchsten Ebene Anwendung, die in der Standardeinstellung ausgewählt haben `CView` festgelegt ist, als die Basisklasse für die Anwendungsansicht in der [generierte Klassen](../../mfc/reference/generated-classes-mfc-application-wizard.md) Seite des Assistenten. Um eine formularbasierte Anwendung zu erstellen, müssen Sie `CFormView` als Basisklasse für die Anwendungsansicht auswählen. Beachten Sie, dass der Assistent keine Druckunterstützung für formularbasierte Anwendungen bietet.

1. Legen Sie ggf. weitere Projektoptionen auf den anderen Seiten des Assistenten fest.

1. Klicken Sie auf **Fertig stellen** um die skelettanwendung zu erzeugen.

Weitere Informationen finden Sie unter:

- [Abgeleitete Ansichtsklassen](../../mfc/derived-view-classes-available-in-mfc.md)

- [Alternativen zur Dokument-/Ansichtarchitektur](../../mfc/alternatives-to-the-document-view-architecture.md)

- [Überlegungen zum Anwendungsentwurf](../../mfc/application-design-choices.md)

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)<br/>
[Formularansichten](../../mfc/form-views-mfc.md)<br/>
[Erstellen einer MFC-Anwendung im Stil des Datei-Explorers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)<br/>
[Erstellen einer MFC-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

