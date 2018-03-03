---
title: Verwenden von Ansichten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99493657313d480559d232bf9033dfb7a7a585c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-views"></a>Verwenden von Ansichten
Die Ansicht Aufgaben sind Dokumentdaten für den Benutzer grafisch anzuzeigen und zu akzeptieren und Interpretieren der Benutzereingaben als Vorgänge für das Dokument. Die Vorgänge in Ihrer Ansichtsklasse geschrieben werden:  
  
-   Schreiben Sie Ihre Ansichtsklasse [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion, die die Daten des Dokuments rendert.  
  
-   Verbinden Sie die entsprechenden Windows-Meldungen und Benutzeroberflächen-Objekten, z. B. Menüelemente mit Meldungshandler Memberfunktionen in der Ansichtsklasse.  
  
-   Implementieren Sie diese Ereignishandler, um Benutzereingaben zu interpretieren.  
  
 Darüber hinaus möglicherweise andere überschreiben `CView` Memberfunktionen in der Sicht der abgeleiteten Klasse. Sie möchten insbesondere außer Kraft setzen [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) für die spezielle Initialisierung für die Ansicht und [OnUpdate](../mfc/reference/cview-class.md#onupdate) Vorgehensweise jegliche spezielle Verarbeitung erforderlich, kurz bevor die Sicht, die sich selbst neu zeichnet. Bei mehrseitigen Dokumenten Außerdem müssen Sie überschreiben [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) um das Dialogfeld "Drucken" mit der Anzahl der zu druckenden Seiten sowie weitere Informationen zu initialisieren. Weitere Informationen zum Überschreiben `CView` Memberfunktionen, finden Sie unter Klasse [CView](../mfc/reference/cview-class.md) in der *MFC-Referenz*.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [In MFC verfügbare Abgeleitete Ansichtsklassen](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)  
  
-   [Interpretieren von Benutzereingaben über eine Sicht](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Die Rolle der Ansicht beim Drucken](../mfc/role-of-the-view-in-printing.md)  
  
-   [Bildlauf und Skalierung für Ansichten](../mfc/scrolling-and-scaling-views.md)  
  
-   [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)   
 [CFormView-Klasse](../mfc/reference/cformview-class.md)   
 [Datensatzansichten (MFC-Datenzugriff)](../data/record-views-mfc-data-access.md)   
 [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)

