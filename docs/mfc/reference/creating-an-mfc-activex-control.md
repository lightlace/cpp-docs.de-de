---
title: Erstellen eines MFC-ActiveX-Steuerelements
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: 031c8596e568f01cdecd7139d959a77923c341eb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294953"
---
# <a name="creating-an-mfc-activex-control"></a>Erstellen eines MFC-ActiveX-Steuerelements

ActiveX-Steuerelementprogramme sind modulare Programme, die einer übergeordneten Anwendung eine bestimmte Funktionalität verleihen. Steuerelemente sind beispielsweise Schaltflächen, die in einem Dialogfeld verwendet werden, oder Symbolleisten, die auf einer Webseite verwendet werden.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen finden Sie unter [ActiveX-Steuerelemente](../activex-controls.md).

Die einfachste Möglichkeit zum Erstellen eines MFC-ActiveX-Steuerelements ist die Verwendung der [MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md).

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>So erstellen Sie ein MFC-ActiveX-Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten

1. Führen Sie die Anweisungen im Artikel [Creating a Project with a Visual C++ Application Wizard (Erstellen eines Projekts mit einem Visual C++-Anwendungs-Assistenten)](../../ide/creating-desktop-projects-by-using-application-wizards.md) durch.

1. In der **neues Projekt** wählen Sie im Dialogfeld die **MFC-ActiveX-Steuerelement** Symbol im Bereich "Vorlagen" MFC-ActiveX-Steuerelement-Assistenten zu öffnen.

1. Definieren Sie Ihre [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [Steuerelementnamen](../../mfc/reference/control-names-mfc-activex-control-wizard.md), und [steuerelementeinstellungen](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) mithilfe von MFC-ActiveX-Steuerelement-Assistenten.

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen** den Assistenten zu schließen und öffnen Sie das neue Projekt in der Entwicklungsumgebung.

Nachdem Sie Ihr Projekt erstellt haben, können Sie anzeigen, dass die Dateien im **Projektmappen-Explorer**. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md).

Nachdem Sie Ihr Projekt erstellt haben, können Sie die Code-Assistenten hinzufügen [Funktionen](../../ide/add-member-function-wizard.md), [Variablen](../../ide/add-member-variable-wizard.md), [Ereignisse](../../ide/add-event-wizard.md), [Eigenschaften](../../ide/names-add-property-wizard.md), und [Methoden](../../ide/add-method-wizard.md). Weitere Informationen zum Anpassen von ActiveX-Steuerelement finden Sie unter [MFC-ActiveX-Steuerelemente](../../mfc/mfc-activex-controls.md).

## <a name="see-also"></a>Siehe auch

[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)
