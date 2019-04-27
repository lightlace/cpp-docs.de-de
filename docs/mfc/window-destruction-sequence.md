---
title: Fensterzerstörungssequenz
ms.date: 11/04/2016
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
ms.openlocfilehash: d4592e6ac0077d6bc335b50f2d67b140402b4fe2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167646"
---
# <a name="window-destruction-sequence"></a>Fensterzerstörungssequenz

In der MFC-Framework, wenn der Benutzer das Rahmenfenster, des Fensters Standardmäßig schließt [OnClose](../mfc/reference/cwnd-class.md#onclose) handleraufrufen [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ist die letzte Memberfunktion aufgerufen, wenn das Windows-Fenster zerstört wird [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), geschieht das Cleanup, ruft der [Standard](../mfc/reference/cwnd-class.md#default) Member Funktion, um die Windows-Bereinigung durchführen, und schließlich Ruft die virtuelle Memberfunktion [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung `PostNcDestroy` löscht das C++-Fensterobjekt.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Zuordnen und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)

- [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Siehe auch

[Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)
