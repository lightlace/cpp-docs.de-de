---
title: Trennen eines CWnd von seinem HWND
ms.date: 11/04/2016
f1_keywords:
- CWnd
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: 259af94958f88643e9c3ce725b25c4e92cc38226
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394571"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Trennen eines CWnd von seinem HWND

Wenn Sie die Objekt - umgehen müssen`HWND` Beziehung MFC bietet eine andere `CWnd` Member-Funktion [trennen](../mfc/reference/cwnd-class.md#detach), die das Windows-Fenster das C++-Fensterobjekt trennt. Dadurch wird verhindert, dass den Destruktor zerstören das Windows-Fenster aus, wenn das Objekt zerstört wird.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen von Fenstern](../mfc/creating-windows.md)

- [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)

- [Zuordnen und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)
