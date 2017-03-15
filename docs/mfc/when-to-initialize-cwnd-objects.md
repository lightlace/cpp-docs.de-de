---
title: "Wann m&#252;ssen CWnd-Objekte initialisiert werden? | Microsoft Docs"
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
  - "CWnd-Objekte, wenn HWND angefügt ist"
  - "CWnd-Objekte, wann wird initialisiert"
  - "HWND, wenn an CWnd-Objekt angefügt"
  - "Initialisieren von CWnd-Objekten"
  - "Initialisieren von Objekten, CWnd"
  - "Fensterobjekte, wann CWnd initialisiert wird"
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Wann m&#252;ssen CWnd-Objekte initialisiert werden?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eigene untergeordnete Fenster erstellen oder keine Windows\-API\-Funktionen im Konstruktor von `CWnd` abgeleitetes Objekt aufrufen.  Dies ist, da `HWND` für das `CWnd`\-Objekt noch nicht erstellt wurde.  Die häufigste Windows\-spezifische Initialisierung, das Hinzufügen von untergeordneten Fenstern, muss in einem [OnCreate](../Topic/CWnd::OnCreate.md) Meldungshandler erfolgen.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Erstellen von Dokumentrahmenfenstern](../mfc/creating-document-frame-windows.md)  
  
-   [Dokument\/Ansichts\-Erstellung](../mfc/document-view-creation.md)  
  
## Siehe auch  
 [Verwenden von Rahmenfenstern](../mfc/using-frame-windows.md)