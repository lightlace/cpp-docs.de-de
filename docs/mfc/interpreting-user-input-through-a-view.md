---
title: Interpretieren der Benutzereingaben in einer Ansicht | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 263afe7b444722174d1787594f869087d606a235
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interpreting-user-input-through-a-view"></a>Interpretieren der Benutzereingaben in einer Ansicht
Andere Memberfunktionen der Ansicht zu behandeln und interpretieren alle Benutzereingaben. Definieren Sie Meldungshandler Memberfunktionen in der Regel in Ihrer Ansichtsklasse verarbeiten:  
  
-   Windows [Nachrichten](../mfc/messages.md) von Maus- und Tastaturereignissen Aktionen generiert.  
  
-   [Befehle](../mfc/user-interface-objects-and-command-ids.md) von Menüs, Symbolleisten-Schaltflächen und Zugriffstasten.  
  
 Diese Meldungshandler Memberfunktionen interpretieren die folgenden Aktionen als Dateneingabe, Auswahl oder bearbeiten, einschließlich des Verschiebens von Daten in und aus der Zwischenablage:  
  
-   Maus und klickt, zieht und Doppelklicks  
  
-   Tastenkombinationen  
  
-   Menübefehle  
  
 Welche Windows-Nachrichten die Handles für die Sicht hängt Anforderungen Ihrer Anwendung ab.  
  
 [Behandlung und Themen Zuordnen von Meldungen](../mfc/message-handling-and-mapping.md) wird erläutert, wie Befehle Menüelemente und andere Objekte der Benutzeroberfläche zugewiesen und wie die Befehle mit Handlerfunktionen gebunden. [Behandlung und Themen Zuordnen von Meldungen](../mfc/message-handling-and-mapping.md) auch erläutert, wie MFC Befehle weiterleitet und sendet Sie standardmäßige Windows-Meldungen an den Objekten, die Handler für diese enthalten.  
  
 Beispielsweise müssen Ihre Anwendung möglicherweise direkte Maus zeichnen in der Ansicht zu implementieren. Das Scribble-Beispiel veranschaulicht die Behandlung der `WM_LBUTTONDOWN`, `WM_MOUSEMOVE`, und `WM_LBUTTONUP` Nachrichten bzw. um zu beginnen, fortsetzen und Beenden des Zeichnens des Liniensegment. Andererseits, müssen Sie manchmal einen Mausklick in der Ansicht als eine Auswahl zu interpretieren. Der Ansicht `OnLButtonDown` Handlerfunktion würde zu bestimmen, ob der Benutzer auswählen oder wurde zeichnen. Wenn auswählen, würde der Handler bestimmen, ob der auf innerhalb der Grenzen eines Objekts in der Sicht wurde und wenn dies der Fall ist, ändern die Anzeige auf das Objekt als ausgewählt.  
  
 Die Ansicht möglicherweise auch bestimmte Menübefehlen, z. B. solche aus dem Menü "Bearbeiten" zum Ausschneiden, kopieren, einfügen oder löschen die ausgewählten Daten über die Zwischenablage behandeln. Ein Handler aufrufen würde einige des Elements Zwischenablage-bezogenen Funktionen der Klasse `CWnd` zu oder aus der Zwischenablage in ein ausgewählte Datenelement zu übertragen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)

