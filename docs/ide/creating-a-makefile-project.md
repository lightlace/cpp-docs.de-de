---
title: Erstellen eines Makefile-Projekts | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5e86bedbf83cd417cfc41317e5887304cda7ee76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-makefile-project"></a>Erstellen eines Makefile-Projekts
Wenn Sie ein Projekt von der Befehlszeile mit einem Makefile erstellen, wird das Projekt in der Visual Studio-Entwicklungsumgebung nicht erkannt. Öffnen und erstellen das Projekt mithilfe [!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)], Visual Studio Professional oder Visual Studio Express für Windows Desktop, müssen Sie ein leeres Projekt zuerst erstellen, indem Sie die MakeFile-Projektvorlage auswählen. Anschließend können Sie Ihr Projekt auf der Grundlage dieses Projekts in der Visual Studio-Entwicklungsumgebung erstellen.  
  
 Im Projektmappen-Explorer werden keine Dateien dieses Projekts angezeigt. Die Buildeinstellungen, die auf der Eigenschaftenseite des Projekts angezeigt werden, werden vom Projekt festgelegt.  
  
 Die Ausgabedatei, die Sie im Projekt festlegen, hat keinen Einfluss auf den vom Buildskript erstellten Namen; sie deklariert lediglich die Bestimmung.  
  
### <a name="to-create-a-makefile-project"></a>So erstellen Sie ein Makefile-Projekt  
  
1.  Befolgen Sie die Anweisungen im Hilfethema [Erstellen eines Projekts mit einem Visual C++-Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md).  
  
2.  In der **neues Projekt** wählen Sie im Dialogfeld **Makefile-Projekt** im Bereich Vorlagen aus, um den Assistenten zu öffnen.  
  
3.  In der [Anwendungseinstellungen](../ide/application-settings-makefile-project-wizard.md) Seite, geben Sie den Befehl ausgeben, bereinigen und neuerstellungsinformationen.  
  
4.  Klicken Sie auf **Fertig stellen** um den Assistenten schließen und öffnen Sie das neu erstellte Projekt in **Projektmappen-Explorer**.  
  
 Sie können die Projekteigenschaften auf der Eigenschaftenseite des Projekts anzeigen und bearbeiten. Finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../ide/working-with-project-properties.md) Informationen zum Anzeigen der Eigenschaftenseite.  
  
## <a name="see-also"></a>Siehe auch  
 [Makefile-Projekt-Assistent](../ide/makefile-project-wizard.md)   
 [Sonderzeichen in einem Makefile](../build/special-characters-in-a-makefile.md)   
 [Inhalt eines Makefiles](../build/contents-of-a-makefile.md)