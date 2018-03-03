---
title: Ableiten einer Dokumentklasse von CDocument | Microsoft Docs
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
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5c128a2a2e32b5e4854725354ed484a335ab0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="deriving-a-document-class-from-cdocument"></a>Ableiten einer Dokumentklasse von CDocument
Dokumente enthalten und verwalten Ihre Anwendungsdaten verwendet werden. Um den Assistenten für MFC-Anwendung bereitgestellte Dokumentklasse zu verwenden, müssen Sie Folgendes ausführen:  
  
-   Leiten Sie eine Klasse von **CDocument** für jeden Typ des Dokuments.  
  
-   Hinzufügen von Membervariablen zum Speichern von Daten für jedes Dokument.  
  
-   Überschreiben Sie **CDocument**des `Serialize` Memberfunktion in Ihr Dokumentklasse. `Serialize`Schreibvorgänge und die Daten des Dokuments zum und vom Datenträger gelesen.  
  
## <a name="other-document-functions-often-overridden"></a>Oft überschrieben Dokumentfunktionen für andere  
 Sie können auch andere überschreiben möchten **CDocument** Memberfunktionen. Insbesondere werden häufig müssen Sie überschreiben [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) und [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) zum Initialisieren des Dokuments Datenmembern und [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) zerstören dynamisch zugeordnete Daten. Informationen zu überschreibbaren Membern finden Sie in der Klasse [CDocument](../mfc/reference/cdocument-class.md) in der *MFC-Referenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

