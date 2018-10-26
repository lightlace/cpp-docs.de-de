---
title: Erstellen eines MFC-DLL-Projekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfcdll.project
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e787eb7e638751fa369923f8f4059f40fae34104
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061247"
---
# <a name="creating-an-mfc-dll-project"></a>Erstellen eines MFC-DLL-Projekts

Eine MFC-DLL ist eine Binärdatei und fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig verwendet werden kann. Am einfachsten erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten.

> [!NOTE]
>  Die in der IDE dargestellten Funktionen können sich je nach den aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Funktionen unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>So erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten

1. Führen Sie die Anweisungen im Artikel [Creating a Project with a Visual C++ Application Wizard (Erstellen eines Projekts mit einem Visual C++-Anwendungs-Assistenten)](../../ide/creating-desktop-projects-by-using-application-wizards.md) durch.

**Beachten Sie** In die **neues Projekt** wählen Sie im Dialogfeld die `MFC DLL` Symbol im Bereich "Vorlagen" auf die MFC-DLL-Assistenten zu öffnen.

1. Definieren Sie Ihre Anwendungseinstellungen mit dem [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-dll-wizard.md) auf der Seite die [MFC DLL-Assistenten](../../mfc/reference/mfc-dll-wizard.md).

    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.

1. Klicken Sie auf **Fertig stellen** den Assistenten zu schließen, und öffnen das neue Projekt in **Projektmappen-Explorer**.

Nachdem das Projekt erstellt wurde, sehen Sie die Dateien im **Projektmappen-Explorer**. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Siehe auch

[Visual C++-Projekttypen](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)

