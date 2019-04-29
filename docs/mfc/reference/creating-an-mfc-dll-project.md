---
title: Erstellen eines MFC-DLL-Projekts
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfcdll.project
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
ms.openlocfilehash: 6ddc32ac3a2de5993e6755df0cd9fc7d3546094e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372282"
---
# <a name="creating-an-mfc-dll-project"></a>Erstellen eines MFC-DLL-Projekts

Eine MFC-DLL ist eine Binärdatei und fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig verwendet werden kann. Am einfachsten erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten.

> [!NOTE]
>  Die in der IDE dargestellten Features können sich je nach den aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Features unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>So erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten

1. Befolgen Sie die Anweisungen im Hilfethema [erstellen Sie eine C++-Konsolen-app-Projekts](../../get-started/tutorial-console-cpp.md).

**Beachten Sie** In die **neues Projekt** wählen Sie im Dialogfeld die `MFC DLL` Symbol im Bereich "Vorlagen" auf die MFC-DLL-Assistenten zu öffnen.

1. Definieren Sie Ihre Anwendungseinstellungen mit dem [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-dll-wizard.md) auf der Seite die [MFC DLL-Assistenten](../../mfc/reference/mfc-dll-wizard.md).

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen** den Assistenten zu schließen, und öffnen das neue Projekt in **Projektmappen-Explorer**.

Nachdem das Projekt erstellt wurde, sehen Sie die Dateien im **Projektmappen-Explorer**. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [für Visual C++-Projekte erstellte Dateitypen](../../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Siehe auch

[Visual C++-Projekttypen](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../build/reference/property-pages-visual-cpp.md)

