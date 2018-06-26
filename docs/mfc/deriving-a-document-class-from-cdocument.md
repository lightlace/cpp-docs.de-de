---
title: Ableiten einer Dokumentklasse von CDocument | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a81f3c3a36f049e3f47401efa31b36677b3b9ba6
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931748"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Ableiten einer Dokumentklasse von CDocument
Dokumente enthalten und verwalten Ihre Anwendungsdaten verwendet werden. Um den Assistenten für MFC-Anwendung bereitgestellte Dokumentklasse zu verwenden, müssen Sie Folgendes ausführen:  
  
-   Leiten Sie eine Klasse von `CDocument` für jeden Typ des Dokuments.  
  
-   Hinzufügen von Membervariablen zum Speichern von Daten für jedes Dokument.  
  
-   Überschreiben Sie `CDocument`des `Serialize` Memberfunktion in Ihr Dokumentklasse. `Serialize` Schreibvorgänge und die Daten des Dokuments zum und vom Datenträger gelesen.  
  
## <a name="other-document-functions-often-overridden"></a>Oft überschrieben Dokumentfunktionen für andere  
 Sie können auch andere überschreiben möchten `CDocument` Memberfunktionen. Insbesondere werden häufig müssen Sie überschreiben [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) und [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) zum Initialisieren des Dokuments Datenmembern und [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) zerstören dynamisch zugeordnete Daten. Informationen zu überschreibbaren Membern finden Sie in der Klasse [CDocument](../mfc/reference/cdocument-class.md) in der *MFC-Referenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

