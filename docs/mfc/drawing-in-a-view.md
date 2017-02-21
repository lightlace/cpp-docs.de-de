---
title: "Zeichnen in einer Ansicht | Microsoft Docs"
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
  - "Gerätekontexte, Bildschirmzeichnungen"
  - "Zeichnung, In Ansichten"
  - "paint-Meldungen in view-Klasse"
  - "Drucken [MFC], Ansichten"
  - "Druckansichten"
  - "Ansichten, Drucken"
  - "Ansichten, Rendern"
  - "Ansichten, Aktualisieren"
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Zeichnen in einer Ansicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fast alle Zeichnungen in der Anwendung wird in der Memberfunktion `OnDraw` der Ansicht auf, die Sie in der Ansichtsklasse überschreiben müssen. \(Eine Ausnahme ist die Mauszeichnung, erläutert in [Interpretieren der Benutzereingaben über eine Ansicht](../mfc/interpreting-user-input-through-a-view.md).\) Ihre `OnDraw` Override:  
  
1.  Ruft Daten durch Aufrufen der Dokumentmemberfunktionen ab, die Sie bereitstellen.  
  
2.  Zeigt die Daten durch das Gerätekontextobjekts Memberfunktionen eines an, dass das Framework an `OnDraw` übergeben.  
  
 Wenn die Daten eines Dokuments auf eine bestimmte Weise ändern, muss die Ansicht neu gezeichnet werden, um die Änderungen wiederzugeben.  Normalerweise geschieht dies, wenn der Benutzer eine Änderung von einer Ansicht im Dokument vornehmen.  In diesem Fall ruft die Ansicht die Memberfunktion [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) des Dokuments aufgerufen, um alle Ansichten auf dasselbe Dokument zu benachrichtigen, um sich zu aktualisieren.  `UpdateAllViews` ruft [OnUpdate](../Topic/CView::OnUpdate.md)\-Memberfunktion jeder Ansicht auf.  Die Standardimplementierung von `OnUpdate` macht den gesamten Clientbereich der Ansicht ungültig.  Sie können sie überschreiben, um lediglich diese Bereiche des Clientbereichs NULL zu ermöglichen, die zu den geänderten Teile des Dokuments zuordnen.  
  
 Die Memberfunktion `UpdateAllViews` der **CDocument**\-Klasse und die `OnUpdate`\-Memberfunktion der Klasse `CView` können Sie die Informationen vermitteln, die beschreiben, welche Teile des Dokuments geändert wurden.  Dieser "Hinweis" Mechanismus können Sie den Bereich begrenzen, die in der Ansicht neu zeichnen muss.  `OnUpdate` benötigt zwei "Hinweis" Argumente.  Der erste, `lHint`, des Typs **LPARAM**, können Sie alle Daten übergeben, die Ihnen zusagt, während das zweite, `pHint`, des Typs `CObject`\*, können Sie einen Zeiger auf ein Objekt übergeben, das von `CObject` abgeleitet wird.  
  
 Wenn eine Ansicht ungültig wird, sendet Windows sie eine `WM_PAINT` \- Meldung.  Die [OnPaint](../Topic/CWnd::OnPaint.md)\-Handlerfunktion der Ansicht reagiert auf die Meldung, indem sie ein Gerätekontextobjekt der [CPaintDC](../mfc/reference/cpaintdc-class.md) erstellt und ruft `OnDraw`\-Memberfunktion der Ansicht auf.  Sie müssen nicht normalerweise eine überschreibende `OnPaint`\-Handlerfunktion schreiben.  
  
 [Gerätekontext](../mfc/device-contexts.md) ist eine Windows\-Datenstruktur, die Informationen über die Zeichnungsattribute eines Geräts wie eine Anzeige oder Drucker enthält.  Alle Zeichnungsaufrufe werden durch ein Gerätekontextobjekt gemacht.  Für das Zeichnen auf dem Bildschirm, wird `OnDraw` ein `CPaintDC`\-Objekt übergeben.  Für das Zeichnen auf einem Drucker, werden ein [CDC](../mfc/reference/cdc-class.md)\-Objekt übergeben, das für den aktuellen Drucker installiert ist.  
  
 Der Code zum Zeichnen in der Ansicht zuerst ruft einen Zeiger auf das Dokument ab, wird Zeichnungsaufrufe durch den Gerätekontext.  Das folgende einfache Beispiel veranschaulicht `OnDraw` den Prozess:  
  
 [!CODE [NVC_MFCDocView#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#1)]  
  
 In diesem Beispiel würden Sie die `GetData`\-Funktion als Member der abgeleiteten Dokumentklasse definieren.  
  
 Das Beispiel gibt, welche Zeichenfolge sie im Dokument abgerufen, zentriert in der Ansicht.  Wenn der Aufruf für `OnDraw` Bildschirmzeichnung ist, ist das `CDC`\-Objekt, das an `pDC` übergeben wird, `CPaintDC`, dessen Konstruktor bereits `BeginPaint` aufgerufen hat.  Aufrufe zum Zeichnen aus Funktionen werden durch den Gerätekontextzeiger gemacht.  Informationen zum Gerätekontexte und Zeichnungsaufrufe, Klasse finden Sie unter [CDC](../mfc/reference/cdc-class.md) in der *MFC\-Referenz* und [Arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md).  
  
 Weitere Beispiele dafür, wie `OnDraw`, finden Sie unter [MFC\-Beispiele](../top/visual-cpp-samples.md).  
  
## Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)