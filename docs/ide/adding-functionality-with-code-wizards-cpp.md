---
title: "Hinzufügen neuer Funktionen mit Code-Assistenten (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes
dev_langs:
- C++
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c27aeb10a58c828b6503ce96ddaadf138c258f27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-functionality-with-code-wizards-c"></a>Hinzufügen neuer Funktionen mit Code-Assistenten (C++)
Nachdem Sie ein Projekt erstellt haben, sollten Sie zu der Funktionalität des Projekts ändern oder hinzufügen. Zu diesen Aufgaben gehört das Erstellen neuer Klassen, das Hinzufügen neuer Member-Funktionen und Variablen, und Hinzufügen von Automatisierungsmethoden und Eigenschaften. Die Code-Assistenten sollen Sie alle diese Aktionen ausgeführt werden können.  
  
> [!NOTE]
>  Sie können jetzt Meldungshandler hinzufügen, und Nachrichten zuordnen, und überschreiben virtuelle MFC-Funktionen mit dem [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).  
  
## <a name="accessing-visual-c-code-wizards"></a>Zugreifen auf Visual C++-Code-Assistenten  
 Es gibt drei Orte, wo Sie Visual C++-Code-Assistenten zugreifen können:  
  
-   Auf der **Projekt** im Menü der **neues Element hinzufügen** Befehl können Sie, um die `Add New Item` (Dialogfeld), das Sie zum Hinzufügen neuer Dateien zu Ihrem Projekt unterstützt. Die **Klasse hinzufügen** Befehl zeigt die [Klasse hinzufügen](../ide/add-class-dialog-box.md) (Dialogfeld), die wiederum Assistenten öffnen, für jede Klasse Ihnen Typen zu Ihrem Projekt hinzufügen kann. Die **Ressource hinzufügen** Befehl zeigt die [Ressource hinzufügen](../windows/add-resource-dialog-box.md) (Dialogfeld), in dem Sie erstellen oder wählen Sie eine Ressource zu Ihrem Projekt hinzufügen können.  
  
     Wenn Sie eine Klasse oder Schnittstelle in Ihrem Projekt in der Klassenansicht, markieren Sie die **Projekt** Menü zeigt auch die folgenden Befehle:  
  
    -   **Schnittstelle implementieren** (von nur einer Control-Klasse)  
  
    -   **Add-Funktion**  
  
    -   **Variable hinzufügen**  
  
    -   **Hinzufügen von Verbindungspunkt** (nur ATL-Klasse)  
  
    -   **Add-Methode** (nur aus einer Schnittstelle)  
  
    -   **Fügen Sie die Eigenschaft** (nur aus einer Schnittstelle)  
  
    -   **Fügen Sie Ereignis** (von nur einer Control-Klasse)  
  
-   In **Projektmappen-Explorer**mit der rechten Maustaste auf einen beliebigen Ordner, und klicken Sie auf **hinzufügen** über die Verknüpfung im Menü ermöglicht Ihnen das Hinzufügen von neuen oder vorhandenen Dateien, weitere Ordner, Elemente, Klassen, Ressourcen und "Webverweise" auf der Projekt.  
  
-   Aus der [Fenster "Klassenansicht"](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)mit der rechten Maustaste auf den entsprechenden Knoten, und klicken Sie auf **hinzufügen** über die Verknüpfung im Menü ermöglicht Ihnen das Hinzufügen von Funktionen, Variablen, Klassen, Eigenschaften, Methoden, Ereignisse, Schnittstellen, Verbindungspunkte oder einem anderen Code zu Ihrem Projekt.  
  
    > [!NOTE]
    >  Visual Studio bietet keinen Assistenten, um eine Schnittstelle zu einem Projekt hinzufügen. Sie können eine Schnittstelle zu einem ATL-Projekt oder hinzufügen ein [Hinzufügen von ATL-Unterstützung auf MFC-Projekt](../mfc/reference/adding-atl-support-to-your-mfc-project.md) ein einfaches Objekt mithilfe der [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md). Alternativ öffnen Sie das Projekt IDL-Datei, und erstellen Sie die Schnittstelle, indem Sie Folgendes eingeben:  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     Finden Sie unter [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md) und [Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) für Weitere Informationen.  
  
    |Zugangscode-Assistenten aus|Beschreibung|  
    |-----------------------------|-----------------|  
    |Neues Element hinzufügen|Neues Element hinzufügen-Code-Assistenten fügen Sie Quelldateien zu Ihrem Projekt hinzu. Ggf. werden weitere Verzeichnisse erstellt, um die Dateien enthalten, in denen das Buildmodul Projekt erwartet, um Sie zu finden. Code-Assistenten über das Symbol "Element hinzufügen" verfügbar sind:<br /><br /> -C++-Quelldateien (.cpp,. h, .idl, rc, .srf, DEF, .rgs) hinzufügen.<br />-Web-Entwicklungsdateien (HTML, ASP, CSS, XML) hinzufügen.<br />-Dienstprogramm und Resource-Dateien (.bmp, .cur, .ico, .rct, SQL, ".txt") hinzufügen.<br /><br /> Dieser Code-Assistenten bitten Sie Sie keine Informationen im Allgemeinen jedoch die Entwicklungsstruktur eine Datei hinzufügen. Sie können die Datei im Eigenschaftenfenster umbenennen.|  
    |Projektmappen-Explorer|Die Code-Assistenten im Projektmappen-Explorer verfügbar, hängen davon ab, in dem sich der Fokus des Cursors ist, wenn Sie ein Element mit der rechten Maustaste. Wenn die **hinzufügen** Option wird nicht angezeigt, wenn Sie ein Element mit der rechten Maustaste klicken Sie dann der Cursor in der Entwicklungsstruktur eine Ebene nach oben verschieben, und wiederholen Sie den Vorgang. Die Code-Assistenten werden immer den zusätzlichen Code in die entsprechende Stelle in der Entwicklungsstruktur unabhängig davon platzieren, in dem sich der Cursor befindet. Code-Assistenten im Projektmappen-Explorer verfügbar sind:<br /><br /> -Klasse hinzufügen (öffnet die **Klasse hinzufügen** (Dialogfeld), enthält der neue Code-Assistenten).<br />-Ressource hinzufügen (neuer, importieren oder Benutzerdefiniert).<br />-Webverweis hinzufügen.|  
    |Klassenansicht|Die Code-Assistenten, der Klassenansicht hängen davon ab, in dem sich der Fokus des Cursors ist, wenn Sie mit der rechten Maustaste auf ein Element klicken. Wenn die **hinzufügen** Option wird nicht angezeigt, wenn Sie mit der rechten Maustaste auf ein Element, klicken Sie dann in der Klassenstruktur eine Ebene nach oben bewegen Sie den Cursor, und wiederholen Sie den Vorgang. Die Code-Assistenten werden immer den zusätzlichen Code in die entsprechende Stelle in der Entwicklungsstruktur unabhängig davon platzieren, in dem sich der Cursor befindet. Code-Assistenten in der Klassenansicht verfügbar sind:<br /><br /> -   [Hinzufügen von Memberfunktionen](../ide/adding-a-member-function-visual-cpp.md).<br />-   [Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md).<br />-   [Fügen Sie Klasse](../ide/adding-a-class-visual-cpp.md).<br />-   [Schnittstelle implementieren](../ide/implement-interface-wizard.md) (von nur einer Control-Klasse)<br />-   [Hinzufügen von Verbindungspunkt](../ide/implement-connection-point-wizard.md) (nur ATL-Klasse)<br />-   [Add-Methode](../ide/add-method-wizard.md) (nur aus einer Schnittstelle)<br />-   [Fügen Sie die Eigenschaft](../ide/names-add-property-wizard.md) (nur aus einer Schnittstelle)<br />-   [Fügen Sie Ereignis](../ide/add-event-wizard.md) (von nur einer Control-Klasse)<br /><br /> Die Klasse hinzufügen Auswahl öffnet die **Klasse hinzufügen** (Dialogfeld), die Sie Zugriff auf alle neuen Code-Assistenten zum Hinzufügen von Klassen gewährt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C++-Projekttypen](../ide/visual-cpp-project-types.md)   
 [Für Visual C++-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)