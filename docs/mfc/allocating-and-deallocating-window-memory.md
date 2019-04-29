---
title: Reservieren und Freigeben von Fensterspeicher
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: 60f99c01c7a311c31602269b49efaf434d16827a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394701"
---
# <a name="allocating-and-deallocating-window-memory"></a>Reservieren und Freigeben von Fensterspeicher

Verwenden Sie nicht die C++ **löschen** Operator, um eine Rahmenfenster oder die Sicht zu zerstören. Rufen Sie stattdessen die `CWnd` Memberfunktion `DestroyWindow`. Rahmenfenster, daher zugewiesen werden soll auf dem Heap mit dem Operator **neue**. Seien Sie vorsichtig beim Zuweisen der Frame-Fensters auf den Stapelrahmen oder Global. Andere Fenster sollte auf den Stapelrahmen möglichst zugeordnet werden.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen von Fenstern](../mfc/creating-windows.md)

- [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)

- [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Siehe auch

[Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)
