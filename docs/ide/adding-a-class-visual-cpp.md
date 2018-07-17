---
title: Hinzufügen einer Klasse (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes.adding
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding classes
- classes [C++], creating
- classes [C++], adding
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14e16d8b5c15939adb792a96a828bafd07ba4041
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33333283"
---
# <a name="adding-a-class-visual-c"></a>Hinzufügen einer Klasse (Visual C++)
Klicken Sie zum Hinzufügen einer Klasse in ein Visual C++-Projekt im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, klicken Sie auf **Hinzufügen** und dann auf **Klasse**. Daraufhin wird das [Dialogfeld „Klasse hinzufügen“](../ide/add-class-dialog-box.md) geöffnet.  
  
 Wenn Sie eine Klasse hinzufügen, müssen Sie einen Namen angeben, der sich von Klassen unterscheidet, die bereits in MFC oder ATL vorhanden sind. Wenn Sie einen Namen festlegen, der bereits in einer Bibliothek vorhanden ist, zeigt die IDE eine Fehlermeldung an.  
  
 Wenn Ihre Namenskonvention für das Projekt erfordert, dass Sie einen vorhandenen Namen verwenden, können Sie auch einfach die Groß-/Kleinschreibung von mindestens einem Buchstaben im Namen ändern, da C++ die Groß-/Kleinschreibung beachtet. Wenn Sie eine Klasse beispielsweise nicht `CDocument` nennen können, können Sie sie dennoch `cdocument` nennen.  
  
## <a name="what-kind-of-class-do-you-want-to-add"></a>Welche Art von Klasse möchten Sie hinzufügen?  
 Wenn Sie im Dialogfeld **Klasse hinzufügen** den Knoten **Visual C++** erweitern, werden mehrere Gruppierungen von installierten Vorlagen im linken Bereich angezeigt. Zu diesen Gruppen gehören **CLR**, **ATL**, **MFC** und **C++**. Wenn Sie eine Gruppe auswählen, wird eine Liste der verfügbaren Vorlagen dieser Gruppe im mittleren Bereich angezeigt. Jede Vorlage enthält die Dateien und den Quellcode, die für eine Klasse erforderlich sind.  
  
 Wählen Sie zum Erstellen einer neuen Klasse eine Vorlage im mittleren Bereich aus, geben Sie im Feld **Name** einen Namen für die Klasse ein, und klicken Sie auf **Hinzufügen**. Daraufhin wird der **Assistent zum Hinzufügen von Klassen** geöffnet, damit Sie die Optionen für die Klasse festlegen können.  
  
-   Weitere Informationen zum Erstellen von MFC-Klassen finden Sie unter [MFC Class (MFC-Klasse)](../mfc/reference/adding-an-mfc-class.md).  
  
-   Weitere Informationen zum Erstellen von ATL-Klassen finden Sie unter [ATL Simple Object (Einfaches ATL-Objekt)](../atl/reference/adding-an-atl-simple-object.md).  
  
> [!NOTE]
>  Die Vorlage **ATL-Unterstützung zu MFC hinzufügen** erstellt keine Klasse. Stattdessen konfiguriert sie für das Projekt die Verwendung von ATL. Weitere Informationen finden Sie unter [ATL Support in an MFC Project (ATL-Unterstützung in einem MFC-Projekt)](../mfc/reference/adding-atl-support-to-your-mfc-project.md).  
  
 Verwenden Sie die Vorlage **C++-Klasse** in der **C++**-Gruppe installierter Vorlagen, um eine C++-Klasse zu erstellen, die MFC, ATL und CLR nicht verwendet. Weitere Informationen finden Sie unter [Adding a Generic C++ Class (Hinzufügen einer allgemeinen C++-Klasse)](../ide/adding-a-generic-cpp-class.md).  
  
 Es stehen zwei Arten von formularbasierten C++-Klassen zur Verfügung. Die erste Klasse, die [CFormView-Klasse](../mfc/reference/cformview-class.md), erstellt eine MFC-Klasse. Die zweite Klasse erstellt eine CLR-Windows Forms-Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 [Creating a Forms-Based MFC Application (Erstellen einer formularbasierten MFC-Anwendung)](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [Add Class Dialog Box (Dialogfeld „Klasse hinzufügen“)](../ide/add-class-dialog-box.md)   
 [Creating Desktop Projects By Using Application Wizards (Erstellen von Desktopprojekten mit Anwendungs-Assistenten)](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../ide/adding-functionality-with-code-wizards-cpp.md)