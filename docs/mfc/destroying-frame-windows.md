---
title: "Zerst&#246;ren von Rahmenfenstern"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "PostNcDestroy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Standardmethode"
  - "Zerstören von Rahmenfenstern"
  - "DestroyWindow-Methode"
  - "Dokumentrahmenfenster, Zerstören"
  - "Rahmenfenster [C++], Zerstören"
  - "MFC [C++], Rahmenfenster"
  - "OnClose-Methode"
  - "OnNcDestroy-Methode, und Rahmenfenster"
  - "PostNcDestroy-Methode"
  - "Fenster [C++], Zerstören"
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Zerst&#246;ren von Rahmenfenstern
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das MFC\-Framework verwaltet Fensterzerstörung sowie \-Erstellung für diese Fenster, die mit Frameworkdokumenten und Ansichten zugeordnet werden.  Wenn Sie zusätzliche Fenster erstellen, sind Sie das Zerstören sie verantwortlich.  
  
 Im Framework wenn der Benutzer das Rahmenfenster enthält, wird der Standard\- [OnClose](../Topic/CWnd::OnClose.md)\-Handler des Fensters [DestroyWindow](../Topic/CWnd::DestroyWindow.md) auf.  Die letzte aufgerufene Memberfunktion, wenn das Windows\-Fenster zerstört wird, ist [OnNcDestroy](../Topic/CWnd::OnNcDestroy.md), die eine Bereinigung durchführt, Aufrufe die Memberfunktion [Standard](../Topic/CWnd::Default.md), um Windows\-Bereinigung auszuführen und zuletzt wird die virtuelle Memberfunktion [PostNcDestroy](../Topic/CWnd::PostNcDestroy.md) auf.  Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung von `PostNcDestroy` löscht das C\+\+\-Fensterobjekt.  Sie sollten den Operator **löschen** C\+\+ auf einem Rahmenfenster nicht verwenden.  Verwenden Sie stattdessen `DestroyWindow`.  
  
 Wenn das Hauptfenster geschlossen wird, wird die Anwendung.  Wenn es geänderte nicht gespeicherten Dokumente, gibt das Framework wird ein Meldungsfeld angezeigt, um zu fragen, ob die Dokumente gespeichert werden und sichergestellt, dass die entsprechenden Dokumenten ggf. gespeichert werden.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erstellen von Dokumentrahmenfenstern](../mfc/creating-document-frame-windows.md)  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)