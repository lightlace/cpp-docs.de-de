---
title: Erstellen einer MFC-Anwendung
ms.date: 07/28/2019
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: 454a994da6db2841317d41ea1cdacfd36b0705e4
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606479"
---
# <a name="creating-an-mfc-application"></a>Erstellen einer MFC-Anwendung

Eine MFC-Anwendung ist eine ausführbare Anwendung für Windows, die auf der Microsoft Foundation Class (MFC)-Bibliothek basiert. Die einfachste Möglichkeit zum Erstellen einer MFC-Anwendung ist die Verwendung des MFC-Anwendungs-Assistenten (**MFC-App-Projekt** in Visual Studio 2019). Verwenden Sie zum Erstellen einer MFC-Konsolenanwendung den Windows-Desktop-Assistenten, und wählen Sie die Optionen **Konsolenanwendung** und **MFC-Header** aus.

> [!IMPORTANT]
>  MFC-Projekte werden in Visual Studio Express-Editionen nicht unterstützt.

Ausführbare MFC-Dateien werden im Allgemeinen in fünf Typen unterteilt: standardmäßige Windows-Anwendungen, Dialogfelder, Formular basierte Anwendungen, Explorer-Anwendungen und Webbrowser-Anwendungen. Weitere Informationen finden Sie unter:

- [Verwenden der Klassen zum Schreiben von Windows-Anwendungen](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [Erstellen und Anzeigen von Dialogfeldern](../../mfc/creating-and-displaying-dialog-boxes.md)

- [Erstellen einer formularbasierten MFC-Anwendung](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [Erstellen einer MFC-Anwendung im Stil des Datei-Explorers](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [Erstellen einer MFC-Anwendung im Webbrowserstil](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

Abhängig von den im Assistenten ausgewählten Optionen erstellt der MFC-Anwendungs-Assistent die geeigneten Klassen und Dateien für diese Anwendungstypen.

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>So erstellen Sie eine MFC-Anwendung mit dem MFC-Anwendungs-Assistenten

1. Befolgen Sie die Anweisungen im Hilfethema [Erstellen eines C++ Konsolen-App-Projekts](../../get-started/tutorial-console-cpp.md).

1. Wählen Sie im Dialogfeld **Neues Projekt** im Bereich Vorlagen die Option **MFC-Anwendung** aus, um den Assistenten zu öffnen.

1. Definieren Sie die Anwendungseinstellungen mithilfe des [MFC-Anwendungs-Assistenten](../../mfc/reference/mfc-application-wizard.md).

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neue Projekt in der Entwicklungsumgebung zu öffnen.

Nachdem das Projekt erstellt wurde, können Sie die generierten Dateien im **Projektmappen-Explorer** anzeigen lassen. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual Studio C++-Projekte erstellte Dateitypen](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Siehe auch

[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../build/reference/property-pages-visual-cpp.md)

