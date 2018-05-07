---
title: Kopf- und Fußzeilen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], multipage documents
- page headers [MFC], printing
- headers [MFC], printing
- footers [MFC], printing
- page footers [MFC], printing
- page headers [MFC]
- printing [MFC], headers and footers
- page footers [MFC]
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c82df1a77cdbf677a6b5e6f84c371da243b9b08d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="headers-and-footers"></a>Kopf- und Fußzeilen
In diesem Artikel wird das Hinzufügen von Kopf- und Fußzeilen in einem gedruckten Dokument erläutert.  
  
 Wenn Sie ein Dokument auf dem Bildschirm ansehen, wird der Name des Dokuments und Ihres aktuellen Speicherorts in das Dokument im Allgemeinen in eine Titelleiste und eine Statusleiste angezeigt. Bei Betrachtung der gedruckter eines Dokuments ist es hilfreich, den Namen und die Seitenzahl in einer Kopf- oder Fußzeile angezeigt haben. Dies ist eine verbreitete Methode, die im welche selbst WYSIWYG-Programme wie der auszuführende von drucken und Bildschirmanzeige unterscheiden sich.  
  
 Die [OnPrint](../mfc/reference/cview-class.md#onprint) Memberfunktion wird die entsprechende Stelle Kopf- oder Fußzeilen gedruckt werden, da sie für jede Seite aufgerufen wird, und sie nur für das Drucken nicht für die Bildschirmanzeige aufgerufen wird. Sie können definieren Sie eine separate Funktion, um eine Kopf- oder Fußzeile zu drucken und übergeben sie den Drucker-Gerätekontext aus `OnPrint`. Müssen Sie möglicherweise Fenster Ursprungs oder der Block vor dem Aufruf anpassen [OnDraw](../mfc/reference/cview-class.md#ondraw) zu vermeiden, dass den Text der Seite Überlappung der Kopf- oder Fußzeile. Sie müssen ggf. auch ändern `OnDraw` , da die Menge des Dokuments, das passt, auf der Seite reduziert werden könnten.  
  
 Eine Möglichkeit, um dies zu kompensieren, für der Bereich, der von der Kopf- oder Fußzeile ist die Verwendung der **M_rectDraw** Mitglied [CPrintInfo](../mfc/reference/cprintinfo-structure.md). Jedes Mal, wenn eine Seite gedruckt wird, wird bei diesem Member mit dem verwendbaren Bereich der Seite initialisiert. Wenn Sie einer Kopf- oder Fußzeile vor dem Drucken der Hauptteil der Seite drucken, reduzieren Sie die Größe des Rechtecks in gespeicherten **M_rectDraw** um den Bereich, der von der Kopf- oder Fußzeile zu berücksichtigen. Klicken Sie dann `OnPrint` ersehen **M_rectDraw** um herauszufinden, wie viel Bereich bleibt für den Text der Seite zu drucken.  
  
 Sie können nicht drucken, einen Header oder Sonstiges, aus [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc), da sie, bevor aufgerufen wird die `StartPage` Memberfunktion von [CDC](../mfc/reference/cdc-class.md) aufgerufen wurde. An diesem Punkt gilt der Druckergerätekontext Seitengrenze sein. Ausführen beim Drucken nur über die `OnPrint` Memberfunktion.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Drucken von mehrseitige Dokumenten](../mfc/multipage-documents.md)  
  
-   [Zuordnen von GDI-Ressourcen für das Drucken](../mfc/allocating-gdi-resources.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken](../mfc/printing.md)

