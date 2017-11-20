---
title: "Verwalten von Menüs, Steuerleisten und Zugriffstasten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3a1909702f148855b127af937364d815123ac7b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="managing-menus-control-bars-and-accelerators"></a>Verwalten von Menüs, Steuerleisten und Zugriffstasten
Das Rahmenfenster verwaltet aktualisieren Benutzeroberflächenobjekten, einschließlich Menüs, Symbolleisten-Schaltflächen, die Statusleiste und Zugriffstasten. Ebenso wird die Freigabe der Menüleiste im MDI-Anwendungen verwaltet.  
  
## <a name="managing-menus"></a>Verwalten von Menüs  
 Das Rahmenfenster beteiligt ist, Aktualisieren von Elementen der Benutzeroberfläche mithilfe der `ON_UPDATE_COMMAND_UI` Mechanismus in beschriebenen [wie Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md). Schaltflächen in Symbolleisten und anderen Steuerleisten werden während der Leerlaufschleife aktualisiert. Menüelemente im Dropdown-Menüs in der Menüleiste werden aktualisiert, kurz bevor das Dropdownmenü.  
  
 Verwaltet die MDI-Rahmenfenster für MDI-Anwendungen die Menüleiste und die Beschriftung. Ein MDI-Rahmenfenster besitzt ein Standardmenü, die als Menüleiste verwendet wird, wenn keine aktive untergeordnete MDI-Fenster vorhanden sind. Beim aktiven untergeordneten Elemente vorhanden sind, ist die Menüleiste des MDI-Rahmenfensters von des Menüs für das aktive untergeordnete MDI-Fenster übernommen. Wenn eine MDI-Anwendung mehrere Dokumenttypen, z. B. Diagramm bzw. Arbeitsblatt Dokumente unterstützt jeder versetzt eigene Menüs in der Menüleiste und ändert das Hauptrahmenfenster Beschriftung.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) standardimplementierungen für die standard-Befehle im Menü Fenster für MDI-Anwendungen enthält. Insbesondere die neuen Fenster-Befehl (**ID_WINDOW_NEW**) wird implementiert, um eine neue Rahmenfenster und die Sicht auf das aktuelle Dokument erstellen. Sie müssen diese Implementierungen zu überschreiben, nur dann, wenn Sie erweiterte Anpassung benötigen.  
  
 Mehrere untergeordnete MDI denselben Dokumenttyp freigeben Menüressourcen. Wenn mehrere untergeordnete MDI-Fenster von der gleichen Dokumentvorlage erstellt werden, können alle die gleiche Menüressource, Systemressourcen in Windows speichern verwenden.  
  
## <a name="managing-the-status-bar"></a>Verwalten der Statusleiste  
 Das Rahmenfenster ist auch die Statusleiste im Clientbereich positioniert und verwaltet den Status des Balkens Indikatoren. Das Rahmenfenster löscht und den Bereich in der Statusleiste bei Bedarf aktualisiert und eingabeaufforderungs-Zeichenfolgen wie der Benutzer, Menüelemente und Symbolleisten-Schaltflächen auswählt, zeigt, wie in beschrieben [zum Anzeigen von Befehlsinformationen in der Statusleiste](../mfc/how-to-display-command-information-in-the-status-bar.md).  
  
## <a name="managing-accelerators"></a>Verwalten von Zugriffstasten  
 Jede Rahmenfenster verwaltet eine optionale Accelerator-Tabelle, die Zugriffstaste Übersetzung für Sie automatisch Tastatur. Dieser Mechanismus erleichtert die Zugriffstasten (auch als Tastenkombinationen bezeichnet) zu definieren, mit denen Befehle im Menü aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)

