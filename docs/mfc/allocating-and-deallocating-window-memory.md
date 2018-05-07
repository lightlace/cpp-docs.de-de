---
title: Reservieren und Freigeben von Arbeitsspeicher (Fenster) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1364b4d29e2ccd2c9563359716eba6880df5436
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="allocating-and-deallocating-window-memory"></a>Reservieren und Freigeben von Fensterspeicher
Verwenden Sie nicht den C++ **löschen** Operator, um eine Rahmenfenster oder die Sicht zu zerstören. Rufen Sie stattdessen die `CWnd` Memberfunktion `DestroyWindow`. Rahmenfenster, daher sollten zugeordnet werden, auf dem Heap mit dem Operator **neue**. Seien Sie vorsichtig beim Rahmenfenster im Stapelrahmen oder Global zuweisen. Andere Fenster sollte auf den Stapelrahmen nach Möglichkeit zugewiesen werden.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

