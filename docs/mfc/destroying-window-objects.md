---
title: "Zerstören von Fensterobjekten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e7b8b2cf605e0f53418755b65151fd9eb2cff5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-window-objects"></a>Zerstören von Fensterobjekten
Mit eigene untergeordnete Fenster muss geachtet werden, die C++-Fensterobjekt zerstört, wenn der Benutzer mit dem Fenster abgeschlossen ist. Wenn diese Objekte nicht zerstört werden, wird Ihre Anwendung nicht ihren Speicher wiederhergestellt wird. Glücklicherweise verwaltet das Framework fensterzerstörung sowie das Erstellen von Rahmenfenstern, Ansichten und Dialogfelder. Wenn Sie zusätzliche Fenster erstellen, können Sie sie zerstören.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Reservieren und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [Allgemeine Ablauffolge bei der Fenstererstellung](../mfc/general-window-creation-sequence.md)  
  
-   [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

