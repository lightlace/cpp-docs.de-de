---
title: Trennen eines CWnd von seinem HWND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a776b4ff4799750c89a322379a063030db748eec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342678"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Trennen eines CWnd von seinem HWND
Wenn Sie den Objekt - umgehen müssen`HWND` Beziehung MFC bietet eine andere `CWnd` Memberfunktion [trennen](../mfc/reference/cwnd-class.md#detach), dem das Windows-Fenster die C++-Fensterobjekt trennt. Dadurch wird verhindert, dass den Destruktor zerstören das Windows-Fenster aus, wenn das Objekt zerstört wird.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Erstellen von Fenstern](../mfc/creating-windows.md)  
  
-   [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)  
  
-   [Reservieren und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)

