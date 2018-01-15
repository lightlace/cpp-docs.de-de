---
title: Wie das Framework Code aufruft | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83eeb1c7fd3032ae33c213f17522b171bdb46e55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-the-framework-calls-your-code"></a>Wie das Framework Code aufruft
Es ist entscheidend, um die Beziehung zwischen Quellcode und den Code in der MFC-Framework zu verstehen. Wenn die Anwendung ausgeführt wird, die meisten die ablaufsteuerung befindet sich in der Framework-Code. Das Framework verwaltet die Nachrichtenschleife, die Nachrichten von Windows Ruft ab, wie der Benutzer Befehle wählt und Bearbeiten von Daten in einer Ansicht an. Ereignisse, die das Framework selbst bewältigt verlassen überhaupt nicht auf den Code. Das Framework beispielsweise weiß, wie Windows schließen und die Anwendung als Reaktion auf Benutzerbefehle zu beenden. Wie sie diese Aufgaben behandelt, verwendet das Framework Meldungshandler und virtuelle C++-Funktionen bieten Möglichkeiten für die Reaktion auf diese Ereignisse auch an. Der Code ist jedoch nicht im Steuerelement. Das Framework ist.  
  
 Das Framework Ruft den Code für anwendungsspezifische Ereignisse. Wenn der Benutzer einen Befehl auswählt, leitet das Framework z. B. den Befehl entlang einer Sequenz von C++-Objekten: der aktuellen Ansicht- und Frame-Fensters, das die Ansicht des Dokuments Dokumentvorlage und des Anwendungsobjekts zugeordnete Dokument. Wenn eines dieser Objekte den Befehl bewältigt werden kann, ist es, den entsprechenden Meldungshandler-Funktion aufrufen. Bei jedem Befehl der Code aufgerufen werden Ihnen, oder möglicherweise des Frameworks.  
  
 Diese Anordnung ist etwas mit herkömmlichen Programmierung für Windows oder ereignisgesteuerte Programmierung erfahrenen Programmierern vertraut.  
  
 Verwandte Themen werden Sie lesen, was das Framework als er initialisiert und führt die Anwendung und dann bereinigt, sobald die Anwendung beendet wird. Es wird auch erläutert, der Code, den Sie schreiben, die einnimmt.  
  
 Weitere Informationen finden Sie unter [Klasse CWinApp: die Anwendungsklasse](../mfc/cwinapp-the-application-class.md) und [Dokumentvorlagen und der Erstellungsvorgang für die Dokument-/Ansichtarchitektur](../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)

