---
title: "Zuordnen von GDI-Ressourcen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GDI-Objekte, Zuordnen während des Druckens"
  - "Drucken [MFC], Zuordnen von GDI-Ressourcen"
  - "Ressourcen [MFC], Drucken"
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Zuordnen von GDI-Ressourcen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird beschrieben, wie Sie die für das Drucken benötigten Objekte der Windows\-GDI \(Graphics Device Interface\) zuweisen und ihre Zuweisung aufheben.  
  
> [!NOTE]
>  GDI\+ ist in Windows XP enthalten und ist als verteilbare Komponente für Windows NT 4.0 SP6, Windows 2000, Windows 98 und Windows Me verfügbar.  Informationen zum Herunterladen der neuesten verteilbaren Komponente erhalten Sie unter [http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm).  Weitere Informationen finden Sie in der Dokumentation zu GDI\+ SDK bei MSDN: [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp).  
  
 Angenommen, Sie müssen bestimmte Schriften, Stifte oder andere GDI\-Objekte für das Drucken, aber nicht für die Bildschirmanzeige verwenden.  Aufgrund des erforderlichen Arbeitsspeichers ist es ineffizient, diese Objekte beim Start der Anwendung zuzuordnen.  Wenn die Anwendung gerade kein Dokument druckt, wird dieser Speicher möglicherweise für andere Zwecke benötigt.  Es ist besser, sie bei Beginn des Druckens zuzuordnen und nach dem Druckvorgang zu löschen.  
  
 Um diese GDI\-Objekte zuzuweisen, überschreiben Sie die [OnBeginPrinting](../Topic/CView::OnBeginPrinting.md)\-Memberfunktion.  Diese Funktion ist aus zwei Gründen gut für diesen Zweck geeignet: Das Framework ruft diese Funktion einmal zu Beginn jedes Druckauftrags auf und im Gegensatz zu [OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) hat diese Funktion Zugriff auf das [CDC](../mfc/reference/cdc-class.md)\-Objekt, das den Druckertreiber darstellt.  Sie können diese Objekte für die Verwendung während des Druckauftrags speichern, indem Sie Membervariablen in Ihrer Ansichtsklasse definieren, die auf GDI\-Objekte verweisen \(z. B. **CFont \***\-Member usw.\).  
  
 Um die erstellten GDI\-Objekte zu verwenden, wählen Sie diese in den Drucker\-Gerätekontext in der [OnPrint](../Topic/CView::OnPrint.md)\-Memberfunktion.  Wenn Sie unterschiedliche GDI\-Objekte für verschiedene Seiten des Dokuments benötigen, können Sie das `m_nCurPage`\-Member der [CPrintInfo](../mfc/reference/cprintinfo-structure.md)\-Struktur überprüfen und das GDI\-Objekt entsprechend wählen.  Wenn Sie ein GDI\-Objekt für mehrere aufeinanderfolgende Seiten benötigen, müssen Sie es bei jedem Aufrufen von `OnPrint` in den Gerätekontext wählen.  
  
 Um die Zuweisung dieser GDI\-Objekte aufzuheben, überschreiben Sie die [OnEndPrinting](../Topic/CView::OnEndPrinting.md)\-Memberfunktion.  Das Framework ruft diese Funktion am Ende jedes Druckauftrags auf, wodurch Sie die Zuweisung druckspezifischer GDI\-Objekte aufheben können, bevor die Anwendung zu anderen Aufgaben zurückkehrt.  
  
## Siehe auch  
 [Drucken](../mfc/printing.md)   
 [Funktionsweise des Standarddrucks](../mfc/how-default-printing-is-done.md)