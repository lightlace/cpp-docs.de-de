---
title: Was Rahmenfenstern | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f5143bab1ea84392efe1bd5783889c45375365ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="what-frame-windows-do"></a>Funktionsweise von Rahmenfenstern
Neben dem einfachen Einrahmen eine Sicht, sind Rahmenfenster für zahlreiche Aufgaben, die beim Koordinieren von des Frames mit seinen Ansichtszustand und die Anwendung verantwortlich. [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) und [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) Vererben [CFrameWnd](../mfc/reference/cframewnd-class.md), also sie müssen `CFrameWnd` Funktionen sowie neue Funktionen, die sie hinzufügen. Beispiele für untergeordnete Fenster sind Ansichten, Steuerelemente, z. B. Steuerleisten, einschließlich Symbolleisten, Statusleisten und Dialogleisten und Listenfelder und Schaltflächen.  
  
 Das Rahmenfenster ist verantwortlich für die Verwaltung des Layouts des zugehöriges untergeordnetes Fenster. In der MFC-Framework positioniert ein Rahmenfensters alle Steuerleisten, Ansichten und anderen untergeordneten Fenster innerhalb seines Clientbereichs.  
  
 Das Rahmenfenster leitet auch Befehle zum zugehörigen Ansichten und zum benachrichtigungsmeldungen aus steuern reagieren kann.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Steuerleisten (wie sie in das Rahmenfenster passen)](../mfc/control-bars.md)  
  
-   [Verwalten von Menüs, Steuerleisten und Zugriffstasten (wie sie in das Rahmenfenster passen)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [Befehlsrouting (vom Rahmenfenster an seine Ansicht und andere Befehlsziele)](../mfc/command-routing.md)  
  
-   [Document/View-Architektur](../mfc/document-view-architecture.md)  
  
-   [Steuerleisten](../mfc/control-bars.md)  
  
-   [Steuerelemente](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Rahmenfenster](../mfc/frame-windows.md)

