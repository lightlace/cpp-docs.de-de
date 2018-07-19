---
title: Drucken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7df782e3c30b9120fe7eb6728f1b622750d160f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348229"
---
# <a name="printing"></a>Drucken
Microsoft Windows implementiert geräteunabhängige anzeigen. In MFC, dies bedeutet, dass die gleichen zeichnen-Aufrufe die `OnDraw` Memberfunktion von Ihrer Ansichtsklasse sind verantwortlich für das Zeichnen für die Anzeige und auf anderen Geräten, z. B. Drucker. Für die Seitenansicht ist das Zielgerät eine simulierte Druckerausgabe auf dem Bildschirm.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Ihre Rolle beim Drucken im Vergleich zu der Framework-Rolle  
 View-Klasse hat die folgenden Verantwortungen:  
  
-   Informieren Sie das Framework, wie viele Seiten im Dokument sind.  
  
-   Wenn Sie aufgefordert werden, die eine angegebene Seite zu drucken, zeichnen Sie diesen Teil des Dokuments.  
  
-   Zuordnen von speichern und Schriftarten oder andere Graphics Device Interface (GDI) Ressourcen, die für das Drucken benötigten.  
  
-   Falls erforderlich, senden Sie eine Escapesequenzen, die erforderlich sind, den Druckermodus vor dem Drucken z. B. einer gegebenen Seite zu ändern, um die Drucken Ausrichtung regelmäßig pro Seite ändern.  
  
 Das Framework Zuständigkeiten lauten wie folgt:  
  
-   Anzeigen der **Drucken** (Dialogfeld).  
  
-   Erstellen einer [CDC](../mfc/reference/cdc-class.md) Objekt für den Drucker.  
  
-   Rufen Sie die [StartDoc](../mfc/reference/cdc-class.md#startdoc) und [EndDoc](../mfc/reference/cdc-class.md#enddoc) Memberfunktionen von der `CDC` Objekt.  
  
-   Wiederholt Aufrufen der [StartPage](../mfc/reference/cdc-class.md#startpage) Memberfunktion von der `CDC` -Objekts informiert die View-Klasse, welche Seite gedruckt werden soll, und rufen Sie, die [EndPage](../mfc/reference/cdc-class.md#endpage) Memberfunktion der `CDC` Objekt.  
  
-   Rufen Sie in der Ansicht zu den entsprechenden Zeitpunkten überschreibbare-Funktionen.  
  
 Die folgenden Artikel wird erläutert, wie das Framework drucken und Druckvorschau unterstützt:  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Wie standarddrucks](../mfc/how-default-printing-is-done.md)  
  
-   [Mehrseitige Dokumente](../mfc/multipage-documents.md)  
  
-   [Kopf- und Fußzeilen](../mfc/headers-and-footers.md)  
  
-   [Zuordnen von GDI-Ressourcen für das Drucken](../mfc/allocating-gdi-resources.md)  
  
-   [Seitenansicht](../mfc/print-preview-architecture.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken und Druckvorschau](../mfc/printing-and-print-preview.md)

