---
title: Initialisieren und Bereinigen von Dokumenten und Ansichten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0546bfc0a5226c6cd22497acae1bb364ceba107b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Initialisieren und Bereinigen von Dokumenten und Ansichten
Verwenden Sie die folgenden Richtlinien für das Initialisieren und Bereinigen von nach Dokumenten und Ansichten:  
  
-   Die MFC-Grundstruktur initialisiert, Dokumente und Ansichten. Sie initialisieren alle Daten, die Sie werden hinzugefügt.  
  
-   Das Framework als Dokumente bereinigt, und schließen Sie die Sichten; Sie müssen den Arbeitsspeicher freigeben, den Sie auf dem Heap aus den Memberfunktionen dieser Dokumente und Ansichten zugeordnet.  
  
> [!NOTE]
>  Denken Sie daran, dass die Initialisierung für die gesamte Anwendung am besten in Ihre Überschreibung erfolgt die [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) Memberfunktion der Klasse `CWinApp`, und der Cleanup für die gesamte Anwendung erfolgt am besten in Ihre Überschreibung der `CWinApp`Memberfunktion [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).  
  
 Der Lebenszyklus eines Dokuments (und seine Rahmenfenster und Ansicht oder Sichten) in einer MDI-ist die Anwendung wie folgt:  
  
1.  Während der dynamischen Erstellung wird das Dokumentkonstruktor aufgerufen.  
  
2.  Für jedes neue Dokuments, das Dokument des [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) oder [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) aufgerufen wird.  
  
3.  Der Benutzer interagiert mit dem Dokument in der gesamten Lebensdauer. In diesem Fall in der Regel, wenn der Benutzer auf Daten über die Sicht arbeitet, auswählen und die Daten bearbeiten. Die Ansicht übergeben, ändert sich das Dokument für die Speicherung und Aktualisieren von anderen Sichten. Während dieses Zeitraums können das Dokument und die Ansicht Befehle zu behandeln.  
  
4.  Das Framework ruft [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) zum Löschen von Daten, die spezifisch für ein Dokument.  
  
5.  Das Dokument Destruktor aufgerufen.  
  
 Schritt 1 wird in einer SDI-Anwendung ausgeführt, einmal auf, wenn das Dokument zuerst erstellt wird. Dann werden die Schritte 2 bis 4 wiederholt jedes Mal ausgeführt, die ein neues Dokument geöffnet wird. Das neue Dokument verwendet den vorhandenen Document-Objekt. Schließlich ist Schritt 5 ausgeführt, wenn die Anwendung beendet.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Initialisieren von Dokumenten und Ansichten](../mfc/initializing-documents-and-views.md)  
  
-   [Bereinigen von Dokumenten und Ansichten](../mfc/cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

