---
title: Zuordnen und Freigeben von Arbeitsspeicher (Fenster) | Microsoft-Dokumentation
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
ms.openlocfilehash: 149a8e860913515551fc85be9b49675856d7e129
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415191"
---
# <a name="allocating-and-deallocating-window-memory"></a>Reservieren und Freigeben von Fensterspeicher

Verwenden Sie nicht die C++ **löschen** Operator, um eine Rahmenfenster oder die Sicht zu zerstören. Rufen Sie stattdessen die `CWnd` Memberfunktion `DestroyWindow`. Rahmenfenster, daher zugewiesen werden soll auf dem Heap mit dem Operator **neue**. Seien Sie vorsichtig beim Zuweisen der Frame-Fensters auf den Stapelrahmen oder Global. Andere Fenster sollte auf den Stapelrahmen möglichst zugeordnet werden.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Erstellen von Fenstern](../mfc/creating-windows.md)

- [Fensterzerstörungssequenz](../mfc/window-destruction-sequence.md)

- [Trennen eines CWnd von seinem HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>Siehe auch

[Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)

