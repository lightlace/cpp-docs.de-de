---
title: Interpretieren der Benutzereingaben in einer Ansicht | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e3ade658046ad789a92bce044d12e5a6e76f7ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

