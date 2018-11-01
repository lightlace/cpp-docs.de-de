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
ms.openlocfilehash: 07312d6c7bba219cebcfa2c73a8d66c9c97ec08e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571352"
---
# <a name="window-destruction-sequence"></a>Fensterzerstörungssequenz

In der MFC-Framework, wenn der Benutzer das Rahmenfenster, des Fensters Standardmäßig schließt [OnClose](../mfc/reference/cwnd-class.md#onclose) handleraufrufen [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Ist die letzte Memberfunktion aufgerufen, wenn das Windows-Fenster zerstört wird [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), geschieht das Cleanup, ruft der [Standard](../mfc/reference/cwnd-class.md#default) Member Funktion, um die Windows-Bereinigung durchführen, und schließlich Ruft die virtuelle Memberfunktion [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). Die [CFrameWnd](../mfc/reference/cframewnd-class.md) Implementierung `PostNcDestroy` löscht das C++-Fensterobjekt.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Zuordnen und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)

- [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Siehe auch

[Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

