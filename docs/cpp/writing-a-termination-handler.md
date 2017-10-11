---
title: Schreiben eines Beendigungshandlers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 06fb01f2ee2782f8786308554923b3c5597a4574
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="writing-a-termination-handler"></a>Schreiben eines Beendigungshandlers
Im Gegensatz zu einem Ausnahmehandler wird ein Beendigungshandler immer ausgeführt, unabhängig davon, ob der geschützte Codeblock ordnungsgemäß beendet wurde. Der Beendigungshandler sollte nur sicherstellen, dass Ressourcen, wie Arbeitsspeicher, Handles und Dateien ordnungsgemäß geschlossen werden, unabhängig davon, wie die Ausführung eines Codeabschnitts beendet wird.  
  
 Beendigungshandler verwenden die try-finally-Anweisung.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Die Try-finally-Anweisung](../cpp/try-finally-statement.md)  
  
-   [Bereinigen von Ressourcen](../cpp/cleaning-up-resources.md)  
  
-   [Zeitliche Steuerung von Aktionen in der Ausnahmebehandlung](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [Einschränkungen bei beendigungshandlern](../cpp/restrictions-on-termination-handlers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
