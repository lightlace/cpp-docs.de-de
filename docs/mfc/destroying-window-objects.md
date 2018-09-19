---
title: Zerstören von Fensterobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 704122f028cd744f0ce064f0153825830144d5b7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401640"
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

