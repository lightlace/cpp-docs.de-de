---
title: Erstellen eines MFC-ActiveX-Steuerelements
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: d35b788910b0c73a3b6da85faf119958ffbccea0
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108443"
---
# <a name="creating-an-mfc-activex-control"></a>Erstellen eines MFC-ActiveX-Steuerelements

ActiveX-Steuerelementprogramme sind modulare Programme, die einer übergeordneten Anwendung eine bestimmte Funktionalität verleihen. Steuerelemente sind beispielsweise Schaltflächen, die in einem Dialogfeld verwendet werden, oder Symbolleisten, die auf einer Webseite verwendet werden.

>[!IMPORTANT]
> ActiveX ist eine ältere Technologie, die nicht für die neue Entwicklung verwendet werden sollte. Weitere Informationen finden Sie unter [ActiveX](../activex-controls.md)-Steuerelemente.

Die einfachste Möglichkeit zum Erstellen eines MFC-ActiveX-Steuer Elements ist die Verwendung des [MFC-ActiveX-Steuer](../../mfc/reference/mfc-activex-control-wizard.md)Element-Assistenten.

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>So erstellen Sie ein MFC-ActiveX-Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten

1. Befolgen Sie die Anweisungen im Hilfethema [Erstellen einer MFC-Anwendung](creating-an-mfc-application.md) , und wählen Sie in der Liste der verfügbaren Vorlagen **MFC-ActiveX-Steuer** Element aus.

1. Definieren Sie die [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [Steuerelement Namen](../../mfc/reference/control-names-mfc-activex-control-wizard.md)und Steuerelement [Einstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) mithilfe des MFC-ActiveX-Steuerelement-Assistenten.

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen und das neue Projekt in der Entwicklungsumgebung zu öffnen.

Nachdem Sie das Projekt erstellt haben, können Sie die in **Projektmappen-Explorer**erstellten Dateien anzeigen. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [Für Visual Studio C++-Projekte erstellte Dateitypen](../../build/reference/file-types-created-for-visual-cpp-projects.md).

Nachdem Sie das Projekt erstellt haben, können Sie die Code-Assistenten verwenden, um [Funktionen](../../ide/add-member-function-wizard.md), [Variablen](../../ide/add-member-variable-wizard.md), [Ereignisse](../../ide/add-event-wizard.md), [Eigenschaften](../../ide/names-add-property-wizard.md)und [Methoden](../../ide/add-method-wizard.md)hinzuzufügen. Weitere Informationen zum Anpassen des ActiveX-Steuer Elements finden Sie unter [MFC-ActiveX](../../mfc/mfc-activex-controls.md)-Steuerelemente.

## <a name="see-also"></a>Siehe auch

[Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../build/reference/property-pages-visual-cpp.md)

