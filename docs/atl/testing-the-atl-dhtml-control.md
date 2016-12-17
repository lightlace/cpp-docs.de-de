---
title: "Testing the ATL DHTML Control"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHTML controls"
  - "DHTML controls, Testen"
  - "HTML-Steuerelemente, Testen"
  - "testing controls"
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Testing the ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Nachdem Sie das Projekt erstellt haben, können Sie das Beispielsteuerelement erstellen und testen.  Bevor Sie dies tun, Verwendung Klassenansicht und den Projektmappen\-Explorer, um das Projekt zu überprüfen.  Die Elemente des Projekts werden ausführlich in [Identifizieren der DHTML\-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md) beschrieben.  
  
#### Um das Steuerelement ATL DHTML erstellen und testen  
  
1.  Erstellen Sie das Projekt.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
2.  Wenn der Build abgeschlossen wird, öffnen Sie Testcontainer.  Siehe [Tests\-Eigenschaften und Ereignisse mit Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) zu Informationen dazu, wie Sie auf Testcontainer zugreift.  
  
3.  im Testcontainer vom **Bearbeiten** Menü, auf **Neues Steuerelement einfügen**.  
  
4.  Im Dialogfeld **Insert Control** wählen Sie das Steuerelement aus dem Listenfeld aus.  Bedenken Sie, sein Name basiert auf den kurzen Namen, den Sie im ATL\-Steuerelement\-Assistenten angegeben haben.  Klicken Sie auf **OK**.  
  
5.  Überprüfen Sie das Steuerelement.  Beachten Sie, dass es eine Bildlaufleiste verfügt.  Verwenden Sie die Handles des Steuerelements, um die Größe des Steuerelements zu ändern, um die Bildlaufleiste zu aktivieren.  
  
6.  Testen Sie die Schaltflächen des Steuerelements.  Die Hintergrundfarbe ändert die Farbe an, die durch die Schaltfläche angegeben wird.  
  
7.  Schließen Sie Testcontainer.  
  
 Als Nächstes Versuch [Ändern des DHTML\-Steuerelements](../atl/modifying-the-atl-dhtml-control.md).  
  
## Siehe auch  
 [Unterstützung für DHTML\-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)