---
title: Debugging- und Ausnahmeklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b7c88c5d12f56318bbb37a825e28c2bfcbc132d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418176"
---
# <a name="debugging-and-exception-classes"></a>Klassen für Debugging und Ausnahmen

Diese Klassen bieten Unterstützung für das Debuggen die dynamische speicherbelegung und für die Übergabe von Informationen zur Ausnahme von der Funktion an die Funktion wird, in dem die Ausnahme ausgelöst, wo sie abgefangen wird.

Verwenden Sie Klassen [CDumpContext](../mfc/reference/cdumpcontext-class.md) und [CMemoryState](../mfc/reference/cmemorystate-structure.md) während der Entwicklung, debugging, zur Unterstützung für Anwendungen unter [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques). Verwendung [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) die Klasse eines Objekts zur Laufzeit zu bestimmen, wie in diesem Artikel beschrieben [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md). Das Framework verwendet `CRuntimeClass` Objekte einer bestimmten Klasse dynamisch zu erstellen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

