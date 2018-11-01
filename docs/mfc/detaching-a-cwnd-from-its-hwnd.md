---
title: Trennen eines CWnd von seinem HWND | Microsoft-Dokumentation
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
ms.openlocfilehash: c69703d8c528d82a696fc94be76ac4a569628b4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392645"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>Trennen eines CWnd von seinem HWND

Wenn Sie die Objekt - umgehen müssen`HWND` Beziehung MFC bietet eine andere `CWnd` Member-Funktion [trennen](../mfc/reference/cwnd-class.md#detach), die das Windows-Fenster das C++-Fensterobjekt trennt. Dadurch wird verhindert, dass den Destruktor zerstören das Windows-Fenster aus, wenn das Objekt zerstört wird.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen von Fenstern](../mfc/creating-windows.md)

- [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)

- [Zuordnen und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)

