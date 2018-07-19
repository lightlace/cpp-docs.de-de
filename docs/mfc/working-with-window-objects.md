---
title: Arbeiten mit Fensterobjekten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c00649c51e34bbbac7adbf7aa5f3c7d04790ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383366"
---
# <a name="working-with-window-objects"></a>Arbeiten mit Fensterobjekten
Arbeiten mit Windows-Aufrufe für zwei Arten von Aktivitäten:  
  
-   Behandlung von Windows-Meldungen  
  
-   Zeichnung im Fenster  
  
 Behandeln von Windows-Meldungen in einem beliebigen Fenster eigene untergeordnete Fenster, einschließlich finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md) , die Nachrichten an die C++-Fensterklasse zuzuordnen. Klicken Sie dann schreiben Sie Meldungshandler Memberfunktionen in der Klasse.  
  
 Die meisten Zeichnen in einem Framework-Anwendung tritt in der Ansicht, deren [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion aufgerufen wird, wenn der Inhalt des Fensters gezeichnet werden müssen. Wenn das Fenster ein untergeordnetes Element der Ansicht ist, können Sie Teil der Ansicht auf Ihr untergeordnetes Fenster delegieren, indem Sie mit `OnDraw` rufen Sie eine der Memberfunktionen des Fensters.  
  
 In jedem Fall benötigen Sie einen Gerätekontext für das Zeichnen. Sie können die vordefinierten Stift, Pinsel und andere Grafikobjekte enthalten, die in den Gerätekontext, der das Fenster zugeordnet sind. Oder Sie können diese Objekte, um die Zeichnungseffekte erhalten, die Sie benötigen. Der Gerätekontext einrichten, wie Sie möchten, rufen Sie Memberfunktionen der Klasse [CDC](../mfc/reference/cdc-class.md) (Gerätekontextklasse) zum Zeichnen von Linien, Formen und Text; verwenden Sie Farben; auch zum Arbeiten mit einem Koordinatensystem.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
-   [Gerätekontexte](../mfc/device-contexts.md)  
  
-   [Grafikobjekte](../mfc/graphic-objects.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

