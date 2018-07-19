---
title: Zerstören von Fensterobjekten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3aacb01d945429bc36543f78e3635c39ef58223d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343375"
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

