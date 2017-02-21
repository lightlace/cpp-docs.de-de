---
title: "Testing the Modified ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls, Testen"
  - "HTML-Steuerelemente, Testen"
  - "testing controls"
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Testing the Modified ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testen Sie das neue Steuerelement aus, um zu sehen, wie sie jetzt funktioniert.  
  
#### Um das geänderte Steuerelement erstellen und testen  
  
1.  Erstellen Sie das Projekt neu und öffnen Sie es im Testcontainer.  Siehe [Tests\-Eigenschaften und Ereignisse mit Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) zu Informationen dazu, wie Sie auf Testcontainer zugreift.  
  
     Ändern Sie die Größe des Steuerelements, um alle Schaltflächen anzuzeigen, die Sie hinzugefügt haben.  
  
2.  Überprüfen Sie die zwei Schaltflächen, die eingefügte, indem Sie das HTML ändern.  Jede Schaltfläche trägt die Bezeichnung, die Sie in [Ändern des Steuerelements ATL DHTML](../atl/modifying-the-atl-dhtml-control.md) identifizierten: **Aktualisieren** und **HelloHTML**.  
  
3.  Testen Sie die beiden neuen Schaltflächen, um zu sehen, wie sie funktionieren.  
  
 Testen Sie jetzt die Methoden, die nicht Teil der Benutzeroberfläche sind.  
  
1.  Markieren Sie das Steuerelement hervorgehoben, sodass der Rahmen aktiviert.  
  
2.  Klicken Sie im Menü auf **SystemMethoden aufrufen**.  
  
 Die Methoden in der Liste, die **Methodenname** Bezeichnung, sind die Methoden, die der Container aufrufen kann: `MethodInvoked` und `GoToURL`.  Alle anderen Methoden werden durch die Benutzeroberfläche gesteuert.  
  
1.  Wählen Sie eine Methode auf, um auf `Invoke` aufzurufen und auf, um das Meldungsfeld der Methode anzuzeigen oder www.microsoft.com zu navigieren.  
  
2.  **Methoden aufrufen** im Dialogfeld auf **Schließen**.  
  
 Weitere Informationen über die verschiedenen Elemente und die Dateien zu erfahren die ein Steuerelement ATL DHTML bilden, finden Sie unter [Identifizieren der DHTML\-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
## Siehe auch  
 [Unterstützung für DHTML\-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)