---
title: "Erstellen einer Containeranwendung für aktive Dokument | Microsoft Docs"
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
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 077d15837ed857ac983c3c9f9d4e7853b45aeee5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-active-document-container-application"></a>Erstellen einer Containeranwendung für aktive Dokumente
Die einfachste und die empfohlene Methode zum Erstellen einer containeranwendung für aktive Dokument besteht darin, eine MFC-EXE-Container-Anwendung mit dem MFC-Anwendung-Assistenten erstellen, und ändern die Anwendung zur Unterstützung von active Document-Container.  
  
#### <a name="to-create-an-active-document-container-application"></a>Zum Erstellen einer containeranwendung für aktive Dokument  
  
1.  Aus der **Datei** Menü klicken Sie auf **Projekt**aus der **neu** Untermenü.  
  
2.  Klicken Sie im linken Bereich auf **Visual C++** Projekttyp.  
  
3.  Wählen Sie **MFC-Anwendung** aus dem rechten Bereich.  
  
4.  Nennen Sie das Projekt `MyProj`, klicken Sie auf **OK**.  
  
5.  Wählen Sie die **Verbunddokumente** Seite.  
  
6.  Wählen Sie die **Container** oder **Container/Vollserver** Option.  
  
7.  Wählen Sie die **Active Document-Container** Kontrollkästchen.  
  
8.  Klicken Sie auf **Fertig stellen**.  
  
9. Öffnen Sie die folgenden Dateien, die mit dem Projektmappen-Explorer, Beendigung des MFC-Assistenten zum Generieren der Anwendung:  
  
    -   MyProjview.cpp  
  
10. Nehmen Sie in MyProjview.cpp die folgenden Änderungen:  
  
    -   In `CMyProjView::OnPreparePrinting`, ersetzen Sie den Inhalt für die Funktion, durch den folgenden Code:  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting`Drucken unterstützt. Dieser Code ersetzt `DoPreparePrinting`, dies ist der Standard-drucken-Vorbereitung.  
  
     Active Document-Container bietet ein verbessertes Schema für Druckens:  
  
    -   Sie können zuerst das aktive Dokument durch Aufrufen seiner `IPrint` Schnittstelle, und teilen Sie es selbst zu drucken. Dies unterscheidet sich von früheren OLE-Einkapselung, in dem der Container ein Bild des enthaltenen Elements auf den Drucker rendern musste `CDC` Objekt.  
  
    -   Wenn dies fehlschlägt, teilen Sie enthaltenen Elements so drucken Sie selbst über seine `IOleCommandTarget` Schnittstelle  
  
    -   Wenn dies fehlschlägt, stellen Sie Ihr eigenes Rendering des Elements an.  
  
     Die statische Memberfunktionen `COleDocObjectItem::OnPrint` und `COleDocObjectItem::OnPreparePrinting`, wie im vorherigen Code implementiert dieses verbesserte drucken Schema zu behandeln.  
  
11. Fügen Sie eine eigene Implementierung hinzu, und erstellen Sie die Anwendung.  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)

