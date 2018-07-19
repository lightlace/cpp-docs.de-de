---
title: Naked-Funktionsaufrufe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 161d47601423b84b0847186e1c5aed8aec8a631b
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942002"
---
# <a name="naked-function-calls"></a>Naked-Funktionsaufrufe
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Funktionen deklariert, mit der **naked** Attribut ausgegeben werden, ohne Prolog- oder Epilogcode Code, sodass Sie eigene benutzerdefinierte Prolog-/epilogsequenzen mit schreiben die [Inlineassembler](../assembler/inline/inline-assembler.md). Naked-Funktionen werden als erweiterte Funktion bereitgestellt. Sie ermöglichen es Ihnen, eine Funktion zu deklarieren, die von einem anderen Kontext als C/C++ aufgerufen wird, und somit andere Annahmen darüber trifft, wo die Parameter sind oder welche Register beibehalten werden. Zu den Beispielen zählen Routinen wie Interrupthandler. Diese Funktion ist für Writer von virtuellen Gerätetreibern (VxDs) besonders nützlich.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Regeln und Einschränkungen für Naked-Funktionen](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Überlegungen zum Schreiben des Prolog-/Epilogcodes](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonventionen](../cpp/calling-conventions.md)