---
title: "Gerätekontexte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26d4a0e32a8b24a72447cf4227be128659316c0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="device-contexts"></a>Gerätekontexte
Ein Gerätekontext ist eine Windows-Datenstruktur mit Informationen über die Zeichnungsattribute von einem Gerät wie einer Bildschirmanzeige oder einen Drucker. Alle zeichnen-Aufrufe erfolgen über einen gerätkontextobjekt, die Windows-APIs für das Zeichnen von Linien, Formen und Text kapselt. Gerätekontexte ermöglichen geräteunabhängige Zeichnung in Windows. Gerätekontexte können verwendet werden, auf dem Bildschirm, an den Drucker oder in eine Metadatei gezeichnet werden soll.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md) Objekte zu kapseln, die allgemeine Vorgehensweise von Windows, das Aufrufen der `BeginPaint` -Funktion, in den Gerätekontext zeichnen dann Aufrufen der `EndPaint` Funktion. Die `CPaintDC` Konstruktoraufrufe `BeginPaint` für Sie und der Destruktor ruft `EndPaint`. Die vereinfachte Vorgehensweise besteht darin, erstellen Sie die [CDC](../mfc/reference/cdc-class.md) -Objekt, gezeichnet werden soll, und entfernen Sie dann die `CDC` Objekt. In das Framework wird viel auch dieser Prozess automatisiert. Insbesondere die `OnDraw` Funktion übergeben wird eine `CPaintDC` bereits vorbereitet (über `OnPrepareDC`), und zeichnen Sie einfach hinein. Es wird durch das Framework zerstört und der zugrunde liegenden Gerätekontext für Windows freigegeben ist, nach der Rückgabe des Aufrufs von Ihrem `OnDraw` Funktion.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md) Objekte zu kapseln, arbeiten mit einem Gerätekontext, der nur der Clientbereich eines Fensters darstellt. Die `CClientDC` Konstruktoraufrufe der `GetDC` -Funktion und der Destruktor ruft die `ReleaseDC` Funktion. [CWindowDC](../mfc/reference/cwindowdc-class.md) Objekte kapseln einen Gerätekontext, der das gesamte Fenster, einschließlich des Rahmens darstellt.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) Objekte kapseln Zeichnung in eine Windows-Metadatei. Im Gegensatz zu den `CPaintDC` übergeben `OnDraw`, müssen Sie in diesem Fall aufrufen [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) selbst.  
  
## <a name="mouse-drawing"></a>Zeichnen mit der Maus  
 Die meisten Zeichnen in einem Frameworkprogramm – und somit die meisten Gerätekontext Arbeit – erfolgt in der Ansicht `OnDraw` Memberfunktion. Sie können jedoch weiterhin gerätekontextobjekten für andere Zwecke verwenden. Beispielsweise, um Feedback der Überwachung für mausbewegungen in einer Ansicht zu gewährleisten, müssen Sie direkt in der Ansicht gezeichnet werden soll, ohne zu warten `OnDraw` aufgerufen werden.  
  
 In diesem Fall können Sie eine [CClientDC](../mfc/reference/cclientdc-class.md) gerätkontextobjekt direkt in der Ansicht gezeichnet werden soll.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Gerätekontexte (Definition)](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
-   [Interpretieren der Benutzereingaben in einer Ansicht](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Linien und Kurven](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [Gefüllte Formen](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [Schriftarten und text](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [Farben](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [Koordinatensysteme und Transformationen](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

