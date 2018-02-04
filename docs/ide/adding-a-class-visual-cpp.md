---
title: "Hinzufügen einer Klasse (Visual C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac87368f2bd38c32425799103fa3999dd11b3298
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="adding-a-class-visual-c"></a>Hinzufügen einer Klasse (Visual C++)
Hinzufügen eine Klasse in einem Visual C++-Projekt in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt, klicken Sie auf **hinzufügen**, und klicken Sie dann auf **Klasse**. Daraufhin wird die [Klasse Dialogfeld hinzufügen](../ide/add-class-dialog-box.md) (Dialogfeld).  
  
 Wenn Sie eine Klasse hinzufügen, müssen Sie einen Namen angeben, das sich von Klassen, die in MFC oder ATL bereits vorhanden sind Wenn Sie einen Namen, der bereits in einer Bibliothek vorhanden ist angeben, zeigt die IDE eine Fehlermeldung angezeigt.  
  
 Wenn Ihr Projekt Benennungskonvention verwenden Sie den Namen einen vorhandenen erforderlich ist, können Sie nur die Groß-/Kleinschreibung eines oder mehrerer Buchstaben im Namen ändern da C++ Groß-/Kleinschreibung beachtet wird. Angenommen, obwohl Sie eine Klasse Namen können nicht `CDocument`, nennen Sie sie `cdocument`.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>Welche Art von Klasse, die möchten Sie hinzufügen?  
 In der **Klasse hinzufügen** (Dialogfeld), erweitern Sie die **Visual C++** Knoten im linken Bereich werden mehrere Gruppierungen der installierten Vorlagen angezeigt. Dazu zählen **CLR**, **ATL**, **MFC**, und **C++**. Wenn Sie eine Gruppe auswählen, wird eine Liste der verfügbaren Vorlagen in dieser Gruppe im mittleren Bereich angezeigt. Jede Vorlage enthält die Dateien und Quellcode, die für eine Klasse erforderlich sind.  
  
 Um eine neue Klasse zu generieren, wählen Sie im mittleren Bereich eine Vorlage aus, geben Sie einen Namen für die Klasse in der **Namen** ein, und klicken Sie auf **hinzufügen**. Daraufhin wird die **Assistenten zum Hinzufügen von Klasse** , damit Sie die Optionen für die Klasse angeben können.  
  
-   Weitere Informationen zum Erstellen von MFC-Klassen finden Sie unter [MFC-Klasse](../mfc/reference/adding-an-mfc-class.md).  
  
-   Weitere Informationen zum Erstellen von ATL-Klassen finden Sie unter [einfaches ATL-Objekt](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Die Vorlage **ATL-Unterstützung zu MFC hinzufügen** keine Klasse erstellt, aber stattdessen wird konfiguriert, dass das Projekt, um die ATL verwenden. Weitere Informationen finden Sie unter [ATL-Unterstützung in MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 Um eine C++-Klasse zu machen, die nicht MFC, ATL oder CLR verwendet, verwenden die **C++-Klasse** Vorlage in der **C++** Gruppe der installierten Vorlagen. Weitere Informationen finden Sie unter [Hinzufügen einer generischen C++-Klasse](../ide/adding-a-generic-cpp-class.md).  
  
 Es stehen zwei Arten von formularbasierten C++-Klassen. Die erste Vorlage [CFormView-Klasse](../mfc/reference/cformview-class.md) erstellt eine MFC-Klasse. Im zweiten Beispiel erstellt eine CLR-Windows Forms-Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer formularbasierten MFC-Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Fügen Sie im Dialogfeld Klasse hinzu.](../ide/add-class-dialog-box.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)