---
title: Drucken und Druckvorschau | Microsoft Docs
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
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bedcf1ecf851ed6d9dd396ee6a82d6d2c058930b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
