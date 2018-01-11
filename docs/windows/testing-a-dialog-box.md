---
title: Testen eines Dialogfelds | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d81d288453e56acfb02a123075692b907d371578
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="testing-a-dialog-box"></a>Testen eines Dialogfelds
Beim Entwerfen eines Dialogfelds können Sie dessen Laufzeitverhalten simulieren und testen, ohne das Programm zu kompilieren. In diesem Modus können Sie folgende Aufgaben ausführen:  
  
-   Texteingabe, Auswahl aus Kombinationsfeldlisten, Aktivieren oder Deaktivieren von Optionen sowie Auswahl von Befehlen.  
  
-   Testen der Aktivierreihenfolge.  
  
-   Testen der Steuerelementgruppierung (z. B. von Optionsfeldern und Kontrollkästchen).  
  
-   Testen der Tastenkombinationen für Steuerelemente im Dialogfeld.  
  
    > [!NOTE]
    >  Verbindungen mit Dialogfeldcode, die mithilfe des Assistenten hergestellt wurden, sind nicht Teil der Simulation.  
  
 Während des Testverfahrens wird ein Dialogfeld normalerweise relativ zum Hauptprogrammfenster angezeigt. Wenn die Dialogfeldeigenschaft "Absolute Ausrichtung" auf "True" gesetzt ist, wird das Dialogfeld relativ zur oberen linken Bildschirmecke angezeigt.  
  
### <a name="to-test-a-dialog-box"></a>So testen Sie ein Dialogfeld  
  
1.  Wenn der Dialog-Editor das aktuelle Fenster ist, wählen Sie in der Menüleiste **Testdialogfeld**, **Format**aus.  
  
2.  Drücken Sie zum Beenden der Simulation ESC, oder wählen Sie in dem von Ihnen getesteten Dialogfeld die Schaltfläche **Schließen** aus.  
  
 Informationen zur Vorgehensweise beim Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Dialog-Editor](../windows/dialog-editor.md)   
 [Ein- oder Ausblenden der Symbolleiste des Dialog-Editors](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

