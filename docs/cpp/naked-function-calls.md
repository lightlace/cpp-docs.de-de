---
title: Naked-Funktionsaufrufe
ms.date: 11/04/2016
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
ms.openlocfilehash: 242fe83807c6608a09492d0f1f817e3b6e50e530
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857397"
---
# <a name="naked-function-calls"></a>Naked-Funktionsaufrufe

**Microsoft-spezifisch**

Funktionen, die mit dem **Naked** -Attribut deklariert werden, werden ohne Prolog-oder Epilogcode ausgegeben, sodass Sie mit dem [Inline Assembler](../assembler/inline/inline-assembler.md)eigene benutzerdefinierte Prolog-/Epilog-Sequenzen schreiben können. Naked-Funktionen werden als erweiterte Funktion bereitgestellt. Sie ermöglichen es Ihnen, eine Funktion zu deklarieren, die von einem anderen Kontext als C/C++ aufgerufen wird, und somit andere Annahmen darüber trifft, wo die Parameter sind oder welche Register beibehalten werden. Zu den Beispielen zählen Routinen wie Interrupthandler. Diese Funktion ist für Writer von virtuellen Gerätetreibern (VxDs) besonders nützlich.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [naked](../cpp/naked-cpp.md)

- [Regeln und Einschränkungen für Naked-Funktionen](../cpp/rules-and-limitations-for-naked-functions.md)

- [Überlegungen zum Schreiben des Prolog-/Epilogcodes](../cpp/considerations-for-writing-prolog-epilog-code.md)

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Aufrufkonventionen](../cpp/calling-conventions.md)