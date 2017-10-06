---
title: Schreiben eines Ausnahmehandlers | Microsoft Docs
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
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5f3f81ff6ea954cda7270ff32650d5744280d918
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="writing-an-exception-handler"></a>Schreiben eines Ausnahmehandlers
Ausnahmehandler werden in der Regel verwendet, um auf bestimmte Fehler zu reagieren. Sie können die Syntax für die Ausnahmebehandlung nutzen, um alle Ausnahmen außer denen zu filtern, deren Behandlung bekannt ist. Andere Ausnahmen sollten an andere Handler übergeben werden (möglicherweise in der Laufzeitbibliothek oder im Betriebssystem), die geschrieben wurden, um nach diesen speziellen Ausnahmen zu suchen.  
  
 Ausnahmehandler verwenden die try-except-Anweisung.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Try-except-Anweisung](../cpp/try-except-statement.md)  
  
-   [Schreiben eines Ausnahmefilters](../cpp/writing-an-exception-filter.md)  
  
-   [Durch das Auslösen von Softwareausnahmen](../cpp/raising-software-exceptions.md)  
  
-   [Hardwareausnahmen](../cpp/hardware-exceptions.md)  
  
-   [Einschränkungen bei Ereignishandlern](../cpp/restrictions-on-exception-handlers.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
