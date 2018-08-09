---
title: Testen eines Dialogfelds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes, testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf9e5e24e77a14b3baf86c1b83d653dd833ebbbb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652069"
---
# <a name="testing-a-dialog-box"></a>Testen eines Dialogfelds
Beim Entwerfen eines Dialogfelds können Sie dessen Laufzeitverhalten simulieren und testen, ohne das Programm zu kompilieren. In diesem Modus können Sie folgende Aufgaben ausführen:  
  
-   Texteingabe, Auswahl aus Kombinationsfeldlisten, Aktivieren oder Deaktivieren von Optionen sowie Auswahl von Befehlen.  
  
-   Testen der Aktivierreihenfolge.  
  
-   Testen der Steuerelementgruppierung (z. B. von Optionsfeldern und Kontrollkästchen).  
  
-   Testen der Tastenkombinationen für Steuerelemente im Dialogfeld.  
  
    > [!NOTE]
    >  Verbindungen mit Dialogfeldcode, die mithilfe des Assistenten hergestellt wurden, sind nicht Teil der Simulation.  
  
 Während des Testverfahrens wird ein Dialogfeld normalerweise relativ zum Hauptprogrammfenster angezeigt. Wenn Sie des Dialogfelds festgelegt haben **Absolute Ausrichtung** Eigenschaft **"true"**, im Dialogfeld angezeigt, an der Position, die relativ zu der oberen linken Ecke des Bildschirms ist.  
  
### <a name="to-test-a-dialog-box"></a>So testen Sie ein Dialogfeld  
  
1.  Wenn der Dialog-Editor das aktuelle Fenster ist, wählen Sie in der Menüleiste **Testdialogfeld**, **Format**aus.  
  
2.  Um die Simulation zu beenden, drücken Sie die **Esc**, oder wählen Sie einfach die **schließen** Schaltfläche im Dialogfeld für die Tests.  
  
 Weitere Informationen zur Vorgehensweise beim Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Dialog-Editor](../windows/dialog-editor.md)   
 [Ein- oder Ausblenden der Symbolleiste des Dialog-Editors](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)