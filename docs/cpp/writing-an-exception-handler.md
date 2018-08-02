---
title: Schreiben eines Ausnahmehandlers | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb06c23e17f16bdf33fe469327351105d6a4571c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461048"
---
# <a name="writing-an-exception-handler"></a>Schreiben eines Ausnahmehandlers
Ausnahmehandler werden in der Regel verwendet, um auf bestimmte Fehler zu reagieren. Sie können die Syntax für die Ausnahmebehandlung nutzen, um alle Ausnahmen außer denen zu filtern, deren Behandlung bekannt ist. Andere Ausnahmen sollten an andere Handler übergeben werden (möglicherweise in der Laufzeitbibliothek oder im Betriebssystem), die geschrieben wurden, um nach diesen speziellen Ausnahmen zu suchen.  
  
 Ausnahmehandler verwenden die try-except-Anweisung.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Die Try-except-Anweisung](../cpp/try-except-statement.md)  
  
-   [Schreiben eines Ausnahmefilters](../cpp/writing-an-exception-filter.md)  
  
-   [Auslösen von Softwareausnahmen](../cpp/raising-software-exceptions.md)  
  
-   [Hardwareausnahmen](../cpp/hardware-exceptions.md)  
  
-   [Einschränkungen bei Ereignishandlern](../cpp/restrictions-on-exception-handlers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)