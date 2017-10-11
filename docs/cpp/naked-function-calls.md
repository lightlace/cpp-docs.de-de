---
title: Naked-Funktionsaufrufe | Microsoft Docs
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
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: dcf93756bf4d10feb63238a1ecf3b6d3f8b340f6
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="naked-function-calls"></a>Naked-Funktionsaufrufe
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Funktionen deklariert, mit der `naked` Attribut ausgegeben werden, ohne Prolog- oder Epilogcode-Code, sodass Sie eigene benutzerdefinierte Prolog-/epilogsequenzen mit Schreiben der [Inlineassembler](../assembler/inline/inline-assembler.md). Naked-Funktionen werden als erweiterte Funktion bereitgestellt. Sie ermöglichen es Ihnen, eine Funktion zu deklarieren, die von einem anderen Kontext als C/C++ aufgerufen wird, und somit andere Annahmen darüber trifft, wo die Parameter sind oder welche Register beibehalten werden. Zu den Beispielen zählen Routinen wie Interrupthandler. Diese Funktion ist für Writer von virtuellen Gerätetreibern (VxDs) besonders nützlich.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Regeln und Einschränkungen für Naked-Funktionen](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Überlegungen zum Schreiben des Prolog-/Epilogcodes](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)
