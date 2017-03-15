---
title: "ActiveX-Steuerelementcontainer | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelementcontainer [C++]"
  - "OLE-Steuerelemente [C++], Container"
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ActiveX-Steuerelementcontainer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein ActiveX\-Steuerelementcontainer ist ein Container, die vollständig ActiveX\-Steuerelemente unterstützt und in eigene Fenster oder in Dialogfeldern enthalten kann.  Ein ActiveX\-Steuerelement ist ein wiederverwendbares Software\-Element, das Sie in vielen Entwicklungsprojekten verwenden können.  Steuerelemente lassen den Benutzer der Anwendung den Zugriffsdatenbanken, überwachen Daten und machen verschiedene Auswahl in den Anwendungen.  Weitere Informationen zum ActiveX\-Steuerelement, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md).  
  
 Steuerelementcontainer nehmen in der Regel zwei Arten in einem Projekt dargestellt:  
  
-   Dialogfelder und Dialogfeld ähnliche wie Fenster Formularansichten, in der ein ActiveX\-Steuerelement irgendwo im Dialogfeld verwendet wird.  
  
-   Windows in einer Anwendung, in der ein ActiveX\-Steuerelement in einer Symbolleiste verwendet wird, oder in anderen Speicherort im Benutzerfenster.  
  
 Der ActiveX\-Steuerelementcontainer interagiert mit dem Steuerelement über verfügbar gemachtes [Methoden](../mfc/mfc-activex-controls-methods.md) und [Eigenschaften](../mfc/mfc-activex-controls-properties.md).  Auf diese Methoden und Eigenschaften, auf die durch den Steuerelementcontainer zugegriffen werden können, werden durch eine Wrapperklasse im ActiveX\-Steuerelement\-Containerprojekt zugegriffen.  Das ActiveX\-Steuerelement eingebettete kann mit dem Container auch interagieren, indem es \(Senden\) [Ereignisse](../mfc/mfc-activex-controls-events.md) auslöst, um den Container zu benachrichtigen, dass eine Aktion beschreiben.  Der Steuerelementcontainer kann auswählen, zu reagieren nach solchen Benachrichtigungen oder nicht.  
  
 Zusätzliche Artikel wird erläutert einige Themen, vom Erstellen eines ActiveX\-Steuerelement\-Containerprojekts zu grundlegenden Implementierungsproblemen, die den ActiveX\-Steuerelement\-Containern verknüpft werden, die mit Visual C\+\+ erstellt werden:  
  
-   [Erstellen eines MFC\-ActiveX\-Steuerelement\-Containers](../mfc/reference/creating-an-mfc-activex-control-container.md)  
  
-   [Container für ActiveX\-Steuerelemente](../mfc/containers-for-activex-controls.md)  
  
-   [ActiveX\-Steuerelementcontainer: ActiveX\-Steuerelement\-Kapselung manuell aktivieren](../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)  
  
-   [ActiveX\-Steuerelementcontainer: Einfügen eines Steuerelements in eine Steuerelementcontainer\-Anwendung](../mfc/inserting-a-control-into-a-control-container-application.md)  
  
-   [ActiveX\-Steuerelementcontainer: Verbinden eines ActiveX\-Steuerelements eine Membervariable an](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)  
  
-   [ActiveX\-Steuerelementcontainer: Behandeln von Ereignissen aus einem ActiveX\-Steuerelement](../mfc/activex-control-containers-handling-events-from-an-activex-control.md)  
  
-   [ActiveX\-Steuerelementcontainer: Steuerelementeigenschaften Anzeigen und Ändern](../mfc/activex-control-containers-viewing-and-modifying-control-properties.md)  
  
-   [ActiveX\-Steuerelementcontainer: Programmierungsactivex\-Kontrollen in einen ActiveX\-Steuerelementcontainer](../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
-   [ActiveX\-Steuerelementcontainer: Verwenden von Steuerelementen in einem Nicht\-Dialogfeld\-Container](../mfc/activex-control-containers-using-controls-in-a-non-dialog-container.md)  
  
 Weitere Informationen über die Verwendung von ActiveX\-Steuerelementen in einem Dialogfeld, finden Sie die Themen [Dialog\-Editor](../mfc/dialog-editor.md).  
  
 Eine Liste der Elemente, die die Details Entwickeln von ActiveX\-Steuerelementen mit Visual C\+\+ und der MFC\-ActiveX\-Steuerelement\-Klassen beschreiben, finden Sie unter [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md).  Die Artikel werden von funktionalen Kategorien gruppiert.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)