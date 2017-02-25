---
title: "Kopf- und Fu&#223;zeilen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fußzeilen, Drucken"
  - "Kopfzeilen, Drucken"
  - "Seitenfußzeilen"
  - "Seitenfußzeilen, Drucken"
  - "Seitenkopfzeilen"
  - "Seitenkopfzeilen, Drucken"
  - "Drucken [MFC], Kopf- und Fußzeilen"
  - "Drucken [MFC], Mehrseitige Dokumente"
ms.assetid: b0be9c53-5773-4955-a777-3c15da745128
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Kopf- und Fu&#223;zeilen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt, wie Kopf\- und Fußzeilen einem gedruckten Dokument hinzugefügt werden.  
  
 Wenn Sie ein Dokument auf dem Bildschirm berücksichtigen, werden Name des Dokuments und die aktuelle Position im Dokument im Allgemeinen in einer Titelleiste und einer Statusleiste angezeigt.  Wenn Sie eine Kopie eines Dokuments gedruckte betrachtet, ist es hilfreich, den Namen und die Seitenzahl verfügen, die in einer Kopf\- oder eine Fußzeile dargestellt werden.  Dies ist eine häufige Methode, in der noch WYSIWYG\-Programme unterscheiden in, wie sie Drucken und Bildschirmanzeige ausführen.  
  
 Die Memberfunktion [OnPrint](../Topic/CView::OnPrint.md) ist der geeignete Ort, z Headern oder von Fußzeilen zu drucken, da sie für jede Seite aufgerufen wird und da sie nur zum Drucken aufgerufen wird, nicht für Bildschirmanzeige.  Sie können eine separate Funktion definieren, um eine Kopf\- oder eine Fußzeile zu drucken und sie der Druckergerätekontext von `OnPrint`.  Möglicherweise müssen Sie den Fensterursprung oder \-Wertebereich anpassen, bevor Sie [OnDraw](../Topic/CView::OnDraw.md) aufrufen, um zu vermeiden, den Text der Seitenüberschneidung verfügen die Header oder Footer.  Sie müssen auch `OnDraw` ändern, da der Umfang des Dokuments, das auf der Seite anpassen, reduziert werden kann.  
  
 Eine Möglichkeit, Bereich entgegenzuwirken, der durch die Header oder Footer verwendet wird, ist, den **m\_rectDraw**\-Member von [CPrintInfo](../mfc/reference/cprintinfo-structure.md).  Immer wenn eine Seite festzulegen, wird dieser Member mit dem verwendbaren Bereich der Seite initialisiert.  Wenn Sie einen Header oder Footer drucken, bevor Sie den Text der Seite drucken, können Sie die Größe des Rechtecks verringern, das in **m\_rectDraw** gespeichert ist, um den Bereich zu berücksichtigen, der von Header oder Footer stammt.  Anschließend kann `OnPrint`**m\_rectDraw** verweisen, um herauszufinden, wie viel Bereich zum Drucken des Texts der Seite bleibt.  
  
 Sie können einen Header oder etwas Anderes, [OnPrepareDC](../Topic/CView::OnPrepareDC.md) nicht gedruckt, da sie aufgerufen wird, bevor die `StartPage`\-Memberfunktion von [CDC](../mfc/reference/cdc-class.md) aufgerufen wurde.  An diesem Punkt wird der Druckergerätekontext berücksichtigt, an einer Seitengrenze zu sein.  Sie können das Drucken ausschließlich von der `OnPrint`\-Memberfunktion ausführen.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Drucken von mehrseitigen Dokumenten](../mfc/multipage-documents.md)  
  
-   [Zuordnen von GDI\-Ressourcen für Druck](../mfc/allocating-gdi-resources.md)  
  
## Siehe auch  
 [Drucken](../mfc/printing.md)