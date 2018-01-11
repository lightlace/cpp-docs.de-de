---
title: Erstellen ein MFC-DLL-Projekt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfcdll.project
dev_langs: C++
helpviewer_keywords:
- MFC DLLs [MFC], creating projects
- DLLs [MFC], MFC
- projects [MFC], creating
- DLLs [MFC], creating
ms.assetid: 05540b93-4781-4a90-aadf-55158313f5b2
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7c040188db5caf46c0d58720320088967b59ea6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-mfc-dll-project"></a>Erstellen eines MFC-DLL-Projekts
Eine MFC-DLL ist eine Binärdatei und fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig verwendet werden kann. Am einfachsten erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten.  
  
> [!NOTE]
>  Die in der IDE dargestellten Funktionen können sich je nach den aktiven Einstellungen oder der verwendeten Version von den in der Hilfe beschriebenen Funktionen unterscheiden. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-mfc-dll-project-using-the-mfc-dll-wizard"></a>So erstellen Sie ein MFC-DLL-Projekt mit dem MFC-DLL-Assistenten  
  
1.  Befolgen Sie die Anweisungen im Hilfethema [Erstellen eines Projekts mit einem Visual C++-Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
 **Hinweis** In der **neues Projekt** wählen Sie im Dialogfeld die `MFC DLL` Symbol im Bereich "Vorlagen" auf die MFC-DLL-Assistenten zu öffnen.  
  
1.  Definieren Sie die Anwendungseinstellungen mithilfe der [Anwendungseinstellungen](../../mfc/reference/application-settings-mfc-dll-wizard.md) auf der Seite der [MFC-DLL-Assistenten](../../mfc/reference/mfc-dll-wizard.md).  
  
    > [!NOTE]
    >  Überspringen Sie diesen Schritt, um die Standardeinstellungen des Assistenten beizubehalten.  
  
2.  Klicken Sie auf **Fertig stellen** um den Assistenten schließen und öffnen Sie das neue Projekt in **Projektmappen-Explorer**.  
  
 Nachdem Sie das Projekt erstellt haben, können Sie die erstellten Dateien in Projektmappen-Explorer anzeigen. Weitere Informationen zu den vom Assistenten erstellten Dateien im Projekt finden Sie in der projekteigenen Datei "Readme.txt". Weitere Informationen zu den Dateitypen finden Sie unter [für Visual C++-Projekte erstellte Dateitypen](../../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Visual C++-Projekttypen](/visualstudio/debugger/debugging-preparation-visual-cpp-project-types)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Eigenschaftenseiten](../../ide/property-pages-visual-cpp.md)   
 [Bereitstellen von Anwendungen](http://msdn.microsoft.com/en-us/4ff8881d-0daf-47e7-bfe7-774c625031b4)

