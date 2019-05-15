---
title: Erstellen einer MFC-Anwendung
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 0f16fe577f1dc02dc9a2fc0cffb5899b16ad8cca
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708236"
---
# <a name="creating-an-mfc-application"></a>Erstellen einer MFC-Anwendung

Eine MFC-Anwendung ist eine ausführbare Anwendung für Windows, die auf der Microsoft Foundation Class (MFC)-Bibliothek basiert. Der MFC-Anwendungs-Assistent bietet die einfachste Möglichkeit, eine MFC-Anwendung zu erstellen.

> [!IMPORTANT]
>  MFC-Projekte werden in Visual Studio Express-Editionen nicht unterstützt.

MFC-ausführbare Dateien fallen in der Regel in fünf Typen: Windows-Standardanwendungen, Dialogfelder, formularbasierte Anwendungen, Explorer-ähnliche Anwendungen und im Webbrowserstil Webanwendungen. Weitere Informationen finden Sie unter:

- [Verwenden der Klassen zum Schreiben von Windows-Anwendungen](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [Erstellen und Anzeigen von Dialogfeldern](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Erstellen einer formularbasierten MFC-Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Erstellen einer MFC-Anwendung im Stil des Datei-Explorers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Erstellen einer MFC-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

Abhängig von den im Assistenten ausgewählten Optionen erstellt der MFC-Anwendungs-Assistent die geeigneten Klassen und Dateien für diese Anwendungstypen.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>So erstellen Sie eine MFC-Anwendung mit dem MFC-Anwendungs-Assistenten

1. Befolgen Sie die Anweisungen im Hilfethema [erstellen Sie eine C++-Konsolen-app-Projekts](../../get-started/tutorial-console-cpp.md).

1. In der **neues Projekt** wählen Sie im Dialogfeld **MFC-Anwendung** im Bereich "Vorlagen" um den Assistenten zu öffnen.

1. Definieren Sie Ihre Anwendungseinstellungen mit dem [MFS-Anwendungsassistenten](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen** den Assistenten zu schließen und öffnen Sie das neue Projekt in der Entwicklungsumgebung.

Nachdem das Projekt erstellt wurde, sehen Sie die Dateien im **Projektmappen-Explorer**. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [für Visual Studio erstellte Dateitypen C++ Projekte](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../build/reference/property-pages-visual-cpp.md)

