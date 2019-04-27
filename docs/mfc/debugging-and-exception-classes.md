---
title: Klassen für Debugging und Ausnahmen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.debug
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
ms.openlocfilehash: 328d7a38c544b56f83ea3e8b1136b1122c4dfa14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241172"
---
# <a name="debugging-and-exception-classes"></a>Klassen für Debugging und Ausnahmen

Diese Klassen bieten Unterstützung für das Debuggen die dynamische speicherbelegung und für die Übergabe von Informationen zur Ausnahme von der Funktion an die Funktion wird, in dem die Ausnahme ausgelöst, wo sie abgefangen wird.

Verwenden Sie Klassen [CDumpContext](../mfc/reference/cdumpcontext-class.md) und [CMemoryState](../mfc/reference/cmemorystate-structure.md) während der Entwicklung, debugging, zur Unterstützung für Anwendungen unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques). Verwendung [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) die Klasse eines Objekts zur Laufzeit zu bestimmen, wie in diesem Artikel beschrieben [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md). Das Framework verwendet `CRuntimeClass` Objekte einer bestimmten Klasse dynamisch zu erstellen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
