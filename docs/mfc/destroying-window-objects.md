---
title: Zerstören von Fensterobjekten
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: f50d198f9868a70d25370f6c1399b66efaa5490b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289844"
---
# <a name="destroying-window-objects"></a>Zerstören von Fensterobjekten

Mit Ihren eigenen untergeordneten Fenster müssen geachtet werden, die C++-Fensterobjekt zerstört, wenn der Benutzer mit dem Fenster abgeschlossen ist. Wenn diese Objekte nicht zerstört werden, wird Ihre Anwendung nicht deren Speicher wiederhergestellt werden. Glücklicherweise verwaltet das Framework fensterzerstörung und die Erstellung für die Frame-Fensters, Ansichten und Dialogfelder. Wenn Sie zusätzliche Fenster erstellen, sind Sie verantwortlich für das sie löschen.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)

- [Zuordnen und Freigeben von Arbeitsspeicher (Fenster)](../mfc/allocating-and-deallocating-window-memory.md)

- [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [Allgemeine Ablauffolge bei der Fenstererstellung](../mfc/general-window-creation-sequence.md)

- [Zerstören von Rahmenfenstern](../mfc/destroying-frame-windows.md)

## <a name="see-also"></a>Siehe auch

[Fensterobjekte](../mfc/window-objects.md)
