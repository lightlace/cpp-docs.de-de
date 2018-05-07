---
title: Verwenden von Dokumenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48f3bd6c6463bbbe26214a29960260d2be583e20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-documents"></a>Verwenden von Dokumenten
Arbeiten zusammen, Dokumente und Ansichten:  
  
-   Enthalten, verwalten und Anzeigen der anwendungsspezifischen [Daten](../mfc/managing-data-with-document-data-variables.md).  
  
-   Geben Sie eine Schnittstelle, bestehend aus [dokumentieren Datenvariablen](../mfc/managing-data-with-document-data-variables.md) zum Bearbeiten der Daten.  
  
-   Teilnehmen [schreiben und Lesen von Dateien](../mfc/serializing-data-to-and-from-files.md).  
  
-   Teilnehmen [Drucken](../mfc/role-of-the-view-in-printing.md).  
  
-   [Behandeln](../mfc/handling-commands-in-the-document.md) die meisten Befehle und Nachrichten von der Anwendung.  
  
 Das Dokument ist besonders beim Verwalten von Daten. Speichern Sie Ihre Daten in der Regel im Dokument Klasse Membervariablen. Die Sicht verwendet diese Variablen zum Zugriff auf die Daten für die Anzeige und zu aktualisieren. Das Dokument Standardmechanismus für die Serialisierung verwaltet lesen und Schreiben der Daten in und aus Dateien. Dokumente können auch Befehle verarbeiten (jedoch nicht die Windows-Nachrichten außer **WM_COMMAND**).  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Ableiten einer Dokumentklasse von CDocument](../mfc/deriving-a-document-class-from-cdocument.md)  
  
-   [Verwalten von Daten mit Dokumentdatenvariablen](../mfc/managing-data-with-document-data-variables.md)  
  
-   [Serialisieren von Daten in und aus Dateien](../mfc/serializing-data-to-and-from-files.md)  
  
-   [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)  
  
-   [Behandeln von Kommentaren in einem Dokument](../mfc/handling-commands-in-the-document.md)  
  
-   [Die Memberfunktion OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument)  
  
-   [Die Memberfunktion DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

