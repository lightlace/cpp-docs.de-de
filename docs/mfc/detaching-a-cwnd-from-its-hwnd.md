---
title: Trennen eines CWnd von seinem HWND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa24e0e9a0d9ee50a0c5c69e280ea7a727ca38b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Trennen eines CWnd von seinem HWND
Wenn Sie den Objekt - umgehen müssen`HWND` Beziehung MFC bietet eine andere `CWnd` Memberfunktion [trennen](../mfc/reference/cwnd-class.md#detach), dem das Windows-Fenster die C++-Fensterobjekt trennt. Dadurch wird verhindert, dass den Destruktor zerstören das Windows-Fenster aus, wenn das Objekt zerstört wird.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Reservieren und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

