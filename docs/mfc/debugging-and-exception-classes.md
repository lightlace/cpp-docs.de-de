---
title: Debugging- und Ausnahmeklassen | Microsoft Docs
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
ms.openlocfilehash: 9adf6a585771336de9fb33abbebdd6bab97383ed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341760"
---
# <a name="debugging-and-exception-classes"></a>Klassen für Debugging und Ausnahmen
Diese Klassen bieten Unterstützung für das Debuggen der dynamischen speicherbelegung und für die Weitergabe von Informationen über die Ausnahme von der Funktion, in dem die Ausnahme ausgelöst, in dem abgefangen wird, an die Funktion.  
  
 Verwenden Sie Klassen [CDumpContext](../mfc/reference/cdumpcontext-class.md) und [CMemoryState](../mfc/reference/cmemorystate-structure.md) während der Entwicklung zu debuggen, zu unterstützen, wie in beschrieben [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques). Verwendung [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) die Klasse eines Objekts zur Laufzeit zu bestimmen, wie im Artikel beschrieben [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md). Das Framework verwendet `CRuntimeClass` Objekte einer bestimmten Klasse dynamisch zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

