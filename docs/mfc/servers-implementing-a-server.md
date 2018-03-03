---
title: 'Server: Implementieren eines Servers | Microsoft Docs'
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
- servers, implementing
- OLE server applications [MFC], implementing OLE servers
ms.assetid: 5bd57e8e-3b23-4f23-9597-496fac2d24b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 148a3da3c904f5c314c75fb71deede3c92163cc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="servers-implementing-a-server"></a>Server: Implementieren eines Servers
Dieser Artikel beschreibt den Code, den die MFC-Anwendungs-Assistent für eine visuelle Bearbeitung Server erstellt. Wenn Sie den Anwendungsassistenten nicht verwenden, führt in diesem Artikel die Bereiche, in dem Sie Code zum Implementieren einer Serveranwendung schreiben müssen.  
  
 Wenn Sie den Assistenten zum Erstellen eine neuen Serveranwendung verwenden, bietet es sehr viel serverspezifischen Code für Sie. Wenn Sie visuelle Bearbeitung Serverfunktionen zu einer vorhandenen Anwendung hinzufügen, müssen Sie den Code, den der Anwendungs-Assistent eingegeben haben, würde bevor Sie den Rest des Codes erforderlichen Server hinzufügen, duplizieren.  
  
 Der Code der vom Anwendungsassistenten bereitgestellten fällt in verschiedene Kategorien:  
  
-   Definieren von Serverressourcen:  
  
    -   Die Menüressource verwendet, wenn der Server ein eingebettetes Element in einem eigenen Fenster bearbeitet wird.  
  
    -   Die Menü- und Symbolleistenelemente Ressourcen verwendet, wenn der Server aktiv ist.  
  
     Weitere Informationen zu diesen Ressourcen finden Sie unter [Menüs und Ressourcen: Servererweiterungen](../mfc/menus-and-resources-server-additions.md).  
  
-   Definieren eine Elementklasse abgeleitet `COleServerItem`. Weitere Details für die Elemente des Servers finden Sie unter [Server: Serverelemente](../mfc/servers-server-items.md).  
  
-   Ändern die Basisklasse der Dokumentklasse in `COleServerDoc`. Weitere Informationen finden Sie unter [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md).  
  
-   Definieren einer Rahmenfenster Klasse abgeleitet `COleIPFrameWnd`. Weitere Informationen finden Sie unter [Server: Implementieren von In-Place-Frame-Fensters](../mfc/servers-implementing-in-place-frame-windows.md).  
  
-   Erstellen einen Eintrag für die Serveranwendung in der Datenbank der Windows-Registrierung, und registrieren die neue Instanz des Servers mit dem OLE-System. Informationen zu diesem Thema finden Sie unter [Registrierung](../mfc/registration.md).  
  
-   Initialisieren und starten die Server-Anwendung. Informationen zu diesem Thema finden Sie unter [Registrierung](../mfc/registration.md).  
  
 Weitere Informationen finden Sie unter [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerDoc](../mfc/reference/coleserverdoc-class.md), und [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md) in der *Klassenbibliotheksreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Server](../mfc/servers.md)   
 [Containers](../mfc/containers.md)   
 [Menüs und Ressourcen (OLE)](../mfc/menus-and-resources-ole.md)   
 [Registrierung](../mfc/registration.md)

