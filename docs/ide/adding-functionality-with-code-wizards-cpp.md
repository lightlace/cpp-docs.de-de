---
title: "Hinzuf&#252;gen neuer Funktionen mit Code-Assistenten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen-Assistenten [C++]"
  - "Code-Assistenten [C++]"
  - "Projekte [C++], Hinzufügen von Funktionalität"
  - "Visual C++-Projekte, Hinzufügen von Funktionalität"
  - "Assistenten [C++], Code"
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen neuer Funktionen mit Code-Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie ein Projekt erstellt haben, möchten Sie dessen Funktionen möglicherweise ändern oder erweitern.  Dazu gehört das Erstellen neuer Klassen, das Hinzufügen neuer Memberfunktionen und \-Variablen sowie das Hinzufügen von Automatisierungsmethoden und \-eigenschaften.  Diese Tasks lassen sich alle mithilfe der Code\-Assistenten erledigen.  
  
> [!NOTE]
>  Jetzt haben Sie die Möglichkeit, Meldungshandler hinzuzufügen und Meldungen zuzuordnen sowie virtuelle MFC\-Funktionen im [Eigenschaftenfenster](../Topic/Properties%20Window.md) zu überschreiben.  
  
## Zugreifen auf Code\-Assistenten in Visual C\+\+  
 An drei Stellen in Visual C\+\+ können Sie auf die Code\-Assistenten zugreifen:  
  
-   Im Menü **Projekt** können Sie über den Befehl **Neues Element hinzufügen** das Dialogfeld `Add New Item` aufrufen. Dieses Dialogfeld erleichtert Ihnen das Hinzufügen neuer Dateien zum Projekt.  Durch den Befehl **Klasse hinzufügen** wird das Dialogfeld [Klasse hinzufügen](../ide/add-class-dialog-box.md) aufgerufen, das wiederum Assistenten für jeden Klassentyp öffnet, den Sie dem Projekt hinzufügen können.  Durch den Befehl **Ressource hinzufügen** wird das Dialogfeld [Ressource hinzufügen](../windows/add-resource-dialog-box.md) aufgerufen, in dem Sie eine Ressource erstellen oder auswählen können, die dem Projekt hinzugefügt wird.  
  
     Wenn Sie in der Klassenansicht eine Klasse oder eine Schnittstelle des Projekts markieren, enthält das Menü **Projekt** außerdem die folgenden Befehle:  
  
    -   **Schnittstelle implementieren** \(nur aus einer Steuerelementklasse\)  
  
    -   **Funktion hinzufügen**  
  
    -   **Variable hinzufügen**  
  
    -   **Verbindungspunkt hinzufügen** \(nur ATL\-Klasse\)  
  
    -   **Methode hinzufügen** \(nur aus einer Schnittstelle\)  
  
    -   **Eigenschaft hinzufügen** \(nur aus einer Schnittstelle\)  
  
    -   **Ereignis hinzufügen** \(nur aus einer Steuerelementklasse\)  
  
-   Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf einen Ordner, und klicken Sie im Kontextmenü auf **Hinzufügen**, um dem Projekt neue oder vorhandene Dateien, weitere Ordner, Elemente, Klassen, Ressourcen und Webverweise hinzuzufügen.  
  
-   Klicken Sie im [Fenster "Klassenansicht"](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den entsprechenden Knoten, und klicken Sie im Kontextmenü auf **Hinzufügen**, um dem Projekt Funktionen, Variablen, Klassen, Eigenschaften, Methoden, Ereignisse, Schnittstellen, Verbindungspunkte oder sonstigen Code hinzuzufügen.  
  
    > [!NOTE]
    >  Visual Studio bietet keinen Assistenten zum Hinzufügen von Schnittstellen zu Projekten.  Sie können einem ATL\-Projekt eine Schnittstelle oder einem [MFC\-Projekt ATL\-Unterstützung hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), indem Sie mit dem [ATL\-Assistenten für einfache Objekte](../atl/reference/atl-simple-object-wizard.md) ein einfaches Objekt hinzufügen.  Alternativ können Sie die IDL\-Datei des Projekts öffnen und die Schnittstelle durch folgenden Code erstellen:  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     Weitere Informationen finden Sie unter [Implementieren einer Schnittstelle](../ide/implementing-an-interface-visual-cpp.md) und [Hinzufügen von Objekten und Steuerelementen zu einem ATL\-Projekt](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
    |Ausgangspunkt für den Assistentenzugriff|Beschreibung|  
    |----------------------------------------------|------------------|  
    |Neues Element hinzufügen|Mit den Code\-Assistenten zum Hinzufügen neuer Elemente können Sie dem Projekt Quelldateien hinzufügen.  Falls erforderlich, werden zusätzliche Verzeichnisse erstellt, in denen die Buildroutine des Projekts nach Dateien sucht.  Über das Symbol Element hinzufügen können Code\-Assistenten für folgende Tasks aufgerufen werden:<br /><br /> -   Hinzufügen von C\+\+\-Quelldateien \(.cpp, .h, .idl, .rc, .srf, .def, .rgs\).<br />-   Hinzufügen von Webentwicklungsdateien \(.html, .asp, .css, .xml\).<br />-   Hinzufügen von Dienstprogramm\- und Ressourcendateien \(.bmp, .cur, .ico, .rct, .sql, .txt\).<br /><br /> Diese Code\-Assistenten fordern im Allgemeinen keine Eingaben an, sondern fügen der Entwicklungsstruktur eine Datei hinzu.  Sie können die Datei im Eigenschaftenfenster umbenennen.|  
    |Projektmappen\-Explorer|Welche Code\-Assistenten in Projektmappen\-Explorer verfügbar sind, hängt davon ab, wo der Cursorfokus sich befindet, wenn Sie mit der rechten Maustaste auf ein Element klicken.  Wenn die Option **Hinzufügen** nicht angezeigt wird, nachdem Sie mit der rechten Maustaste auf ein Element geklickt haben, bewegen Sie den Cursor in der Entwicklungsstruktur um eine Ebene nach oben und wiederholen den Vorgang.  Zusätzlicher Code wird, unabhängig davon, wo sich der Cursor befindet, von den Code\-Assistenten immer an der richtigen Stelle in die Entwicklungsstruktur eingefügt.  in Projektmappen\-Explorer können folgende Code\-Assistenten aufgerufen werden:<br /><br /> -   Klasse hinzufügen \(öffnet das Dialogfeld **Klasse hinzufügen**, das die neuen Code\-Assistenten enthält\).<br />-   Ressource hinzufügen \(Neu, Importieren oder Benutzerdefiniert\)<br />-   Webverweis hinzufügen|  
    |Klassenansicht|Welche Code\-Assistenten in der Klassenansicht verfügbar sind, hängt davon ab, wo der Cursorfokus sich befindet, wenn Sie mit der rechten Maustaste auf ein Element klicken.  Wenn die Option **Hinzufügen** nicht angezeigt wird, nachdem Sie mit der rechten Maustaste auf ein Element geklickt haben, bewegen Sie den Cursor in der Klassenstruktur um eine Ebene nach oben und wiederholen den Vorgang.  Zusätzlicher Code wird, unabhängig davon, wo sich der Cursor befindet, von den Code\-Assistenten immer an der richtigen Stelle in die Entwicklungsstruktur eingefügt.  In der Klassenansicht können Code\-Assistenten für die folgenden Tasks aufgerufen werden:<br /><br /> -   [Hinzufügen von Memberfunktionen](../ide/adding-a-member-function-visual-cpp.md).<br />-   [Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md).<br />-   [Klasse hinzufügen](../ide/adding-a-class-visual-cpp.md).<br />-   [Schnittstelle implementieren](../ide/implement-interface-wizard.md) \(nur aus einer Steuerelementklasse\)<br />-   [Verbindungspunkt hinzufügen](../ide/implement-connection-point-wizard.md) \(nur ATL\-Klasse\)<br />-   [Methode hinzufügen](../ide/add-method-wizard.md) \(nur aus einer Schnittstelle\)<br />-   [Eigenschaft hinzufügen](../ide/names-add-property-wizard.md) \(nur aus einer Schnittstelle\)<br />-   [Ereignis hinzufügen](../ide/add-event-wizard.md) \(nur aus einer Steuerelementklasse\)<br /><br /> Durch die Option zum Hinzufügen von Klassen wird das Dialogfeld **Klasse hinzufügen** geöffnet, in dem Sie auf alle neuen Code\-Assistenten zum Hinzufügen von Klassen zugreifen können.|  
  
## Siehe auch  
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Navigieren in der Klassenstruktur](../ide/navigating-the-class-structure-visual-cpp.md)   
 [Erstellen von Desktopprojekten mit Anwendungs\-Assistenten](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C\+\+\-Projekttypen](../ide/visual-cpp-project-types.md)   
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)