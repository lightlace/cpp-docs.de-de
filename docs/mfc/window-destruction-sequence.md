---
title: "Fensterzerstörungssequenz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b873d51f585336425537756064582eb709988f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="window-destruction-sequence"></a>Fensterzerstörungssequenz
In der MFC-Framework, wenn der Benutzer das Rahmenfenster, standardmäßig das Fenster schließt [OnClose](../mfc/reference/cwnd-class.md#onclose) Ereignishandler ruft [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ist die letzte Memberfunktion aufgerufen, wenn das Windows-Fenster zerstört wird [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), führt die Cleanup, ruft der [Standard](../mfc/reference/cwnd-class.md#default) Member Funktion, um die Windows-Bereinigung durchführen, und schließlich ruft der virtuelle Memberfunktion [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung von `PostNcDestroy` löscht die C++-Fensterobjekt.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Reservieren und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

