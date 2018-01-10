---
title: Reservieren und Freigeben von Arbeitsspeicher (Fenster) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 294de3c4d4ecdfcb31f6e8c227bd8a3c6764268d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-and-deallocating-window-memory"></a>Reservieren und Freigeben von Fensterspeicher
Verwenden Sie nicht den C++ **löschen** Operator, um eine Rahmenfenster oder die Sicht zu zerstören. Rufen Sie stattdessen die `CWnd` Memberfunktion `DestroyWindow`. Rahmenfenster, daher sollten zugeordnet werden, auf dem Heap mit dem Operator **neue**. Seien Sie vorsichtig beim Rahmenfenster im Stapelrahmen oder Global zuweisen. Andere Fenster sollte auf den Stapelrahmen nach Möglichkeit zugewiesen werden.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

