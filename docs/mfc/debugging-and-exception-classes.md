---
title: Debugging- und Ausnahmeklassen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [MFC], exception classes
- debugging [MFC], classes for debugging
ms.assetid: 0d158efd-2e62-452e-9d2a-d3c30dfee7f9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 622e6d04a567668ebfd2c737c5cdde1c2ea09b35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="debugging-and-exception-classes"></a>Klassen für Debugging und Ausnahmen
Diese Klassen bieten Unterstützung für das Debuggen der dynamischen speicherbelegung und für die Weitergabe von Informationen über die Ausnahme von der Funktion, in dem die Ausnahme ausgelöst, in dem abgefangen wird, an die Funktion.  
  
 Verwenden Sie Klassen [CDumpContext](../mfc/reference/cdumpcontext-class.md) und [CMemoryState](../mfc/reference/cmemorystate-structure.md) während der Entwicklung zu debuggen, zu unterstützen, wie in beschrieben [MFC-Anwendungen Debuggen](/visualstudio/debugger/mfc-debugging-techniques). Verwendung [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) die Klasse eines Objekts zur Laufzeit zu bestimmen, wie im Artikel beschrieben [zugreifen auf Laufzeit-Klasseninformationen](../mfc/accessing-run-time-class-information.md). Das Framework verwendet `CRuntimeClass` Objekte einer bestimmten Klasse dynamisch zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

