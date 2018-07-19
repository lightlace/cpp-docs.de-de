---
title: Drucken und Druckvorschau | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a26bac196dbddc6c05df5850225d05f432bc566
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346255"
---
# <a name="printing-and-print-preview"></a>Drucken und Druckvorschau
MFC unterstützt drucken und Druckvorschau für das Programm Dokumente über die Klasse [CView](../mfc/reference/cview-class.md). Für grundlegende drucken und Druckvorschau, überschreiben Sie einfach Ihrer Ansichtsklasse [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion, wozu Sie dennoch verwenden müssen. Diese Funktion kann auf die Ansicht auf dem Bildschirm zu einem Drucker-Gerätekontext für einen Drucker, zeichnen, oder für einen Gerätekontext simuliert, die Ihre Drucker auf dem Bildschirm.  
  
 Sie können auch Code zum Drucken von mehrseitigen Dokumenten und Vorschau, um die gedruckte Dokumente zu paginieren und Kopf- und Fußzeilen hinzugefügt werden verwalten hinzufügen.  
  
 Diese Artikelreihe wird erläutert, wie das Drucken in der Microsoft Foundation Class-Bibliothek (MFC) implementiert wird und die Drucken Architektur, die bereits in das Framework integriert nutzen. Der Artikel wird auch erläutert, wie MFC für einfache Implementierung von Seitenansichtsfunktionen unterstützt und wie Sie verwenden können, und ändern diese Funktion.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Drucken](../mfc/printing.md)  
  
-   [Druckvorschauarchitektur](../mfc/print-preview-architecture.md)  
  
-   [Beispiel](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)
