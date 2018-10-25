---
title: Erstellen einer Containeranwendung für aktive Dokument | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1b20dd592e180122e119b08ab59babfdaae8d54
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052804"
---
# <a name="creating-an-active-document-container-application"></a>Erstellen einer Containeranwendung für aktive Dokumente

Die einfachste und am häufigsten empfohlene Möglichkeit zum Erstellen einer containeranwendung für aktive Dokument ist zum Erstellen einer MFC-EXE-Container-Anwendung mithilfe des MFC-Assistenten, und passen Sie die Anwendung zur Unterstützung von active Document-Container.

#### <a name="to-create-an-active-document-container-application"></a>Zum Erstellen einer containeranwendung für aktive Dokument

1. Von der **Datei** Menü klicken Sie auf **Projekt**aus der **neu** Untermenü.

1. Klicken Sie im linken Bereich auf **Visual C++** Projekttyp.

1. Wählen Sie **MFC-Anwendung** im rechten Bereich.

1. Nennen Sie das Projekt *MyProj*, klicken Sie auf **OK**.

1. Wählen Sie die **Verbunddokumente** Seite.

1. Wählen Sie die **Container** oder **Container/Vollserver** Option.

1. Wählen Sie die **Active Document-Container** Kontrollkästchen.

1. Klicken Sie auf **Fertig stellen**.

9. Wenn der MFC-Anwendung-Assistent abgeschlossen ist, generieren die Anwendung, öffnen Sie mithilfe des Projektmappen-Explorer die folgenden Dateien:

   - *MyProjview.cpp*

10. In *MyProjview.cpp*, nehmen Sie die folgenden Änderungen:

   - In `CMyProjView::OnPreparePrinting`, ersetzen Sie den Inhalt für die Funktion, mit dem folgenden Code:

         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]

   `OnPreparePrinting` bietet Unterstützung für den Druck. Dieser Code ersetzt `DoPreparePrinting`, dies ist die Standard-print-Vorbereitung.

   Active Document-Container bietet es sich um ein verbessertes Drucken Schema:

   - Zunächst können Sie das aktive Dokument durch Aufrufen der `IPrint` Schnittstelle, und teilen Sie es selbst zu drucken. Dies unterscheidet sich vom vorherigen OLE-Kapselung, in dem der Container ein Bild des enthaltenen Elements auf den Drucker rendern musste `CDC` Objekt.

   - Wenn dies fehlschlägt, teilen Sie enthaltenen Elements so drucken Sie selbst über seine `IOleCommandTarget` Schnittstelle

   - Wenn dies fehlschlägt, stellen Sie Ihr eigenes Rendering des Elements.

   Die statische Memberfunktionen `COleDocObjectItem::OnPrint` und `COleDocObjectItem::OnPreparePrinting`, wie im vorherigen Code, implementiert dieses verbesserte drucken-Schema verarbeiten.

11. Fügen Sie eigene Implementierung, und erstellen Sie die Anwendung.

## <a name="see-also"></a>Siehe auch

[Aktive Dokumente-Container](../mfc/active-document-containment.md)

